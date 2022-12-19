---
title: 'Proposition pour le site de PogScience'
homepage:
    invite: 'Une maison pour Pog !'
tntsearch:
    index: false
---

L'objectif est de créer un site pour la communauté PogScience, qui n'en a pas réellement un actuellement (sinon [un substitut généreusement hébergé par Collectif Conscience](https://collectifconscience.org/pogscience/)).

# Objectif

Le site doit permettre :

- de savoir ce qu'est PogScience ;
- de savoir qui en fait partie ;
- d'afficher les streamer·euses actuellement en direct (sur la page d'accueil).

Et plus si affinités, mais dans un premier temps ce sera déjà pas mal, afin de ne pas délayer éternellement le site. Par exemple, on pourrait imaginer à terme :

- afficher les éventuels gros événements communs (ou individuels ?) à venir ;
- afficher le planning commun de tout Pog (il existe déjà du code pour récupérer et consolider ça, ce serait facile à réutiliser a priori) ;
- créer des pages dédiés aux temps forts de Pog (comme _Générations Sorciers_) ;
- créer une page presse partiellement automatique (statistiques, etc.).

# PogScience _on the Edge_ ?

Afin de limiter les frais et la complexité de maintenance, j'ai eu l'idée de gérer le site totalement _on the edge_, c'est à dire sur une [Jamstack](https://fr.wikipedia.org/wiki/Jamstack) (j'avais pensé à l'infrastructure de Cloudflare, notamment car je la connais bien). Ça a plusieurs avantages : 

- site extrêmement rapide (car sur CDN) ;
- sécurisé (virtuellement pas de _backend_, donc rien à mettre à jour ou à hacker, que du statique ou presque) ;
- coûts faibles sinon nuls (probablement nuls, en pratique, vues les très généreuses limites du plan gratuit de Cloudflare).

Il y a deux parties : celles qui sont statiques et celles dynamiques.

## Partie statique

Les parties statiques sont simples à gérer : un site statique (peu importe le générateur) et basta. Très léger inconvénient : la modification se fait en modifiant des fichiers Markdown sur GitHub ou autres, mais c'est quand même très accessible (GitHub ayant une interface de modification totalement en ligne). Le site est mis à jour automatiquement à chaque _push_ (ou modification sur GitHub directement), comme il est d'usage pour ce genre de _stack_.

## Partie dynamique

La partie dynamique est l'affichage, en temps réel ou approchant, des membres de Pog actuellement en live, basé sur une liste de comptes Twitch. Le suivi se ferait idéalement _on the edge_ également, sur des _workers_ Cloudflare ou similaire. J'ai deux options en tête.

Dans les deux cas, le site statique contacterait via une sorte d'API, en _pooling_ régulier, un site pour savoir qui est en live parmi les gens de Pog, et éventuellement leur planning. Pour rester 100% _on the edge_, on pourrait héberger les deux sur Cloudflare Pages, l'API n'étant qu'un site statique avec du JSON dedans, regénéré automatiquement quand l'état de personnes connectées de Twitch change. Disons que le site principal serait `pogscience.pages.dev` (accessible via `pogscience.org`), et le site de données, `pogscience-data.pages.dev`.

Ainsi, utiliser du _pooling_ ne poserait pas de souci, étant donné que l'API serait statique aussi, sur un CDN, donc répondant quasi instantanément sans utiliser de ressources.

[[i]]
| PogScience comporte actuellement 24 membres. L'API de Twitch est limitée à 800 appels par minute ([en gros](https://dev.twitch.tv/docs/api/guide#twitch-rate-limits)).

### Première option : _pooling_ depuis l'API de Twitch

Un _worker_ Cloudflare récupèrerait toutes les minutes l'état de stream de chacun des membres de Pog et mettrait à jour `pogscience-data.pages.dev/online.json` en cas de changement. Ça consomme plus d'exécutions de _workers_, et ça nécessite de planifier leur exécution, mais ça a l'avantage d'être simple au delà de ça.

### Seconde option : implémenter EventSub _on the edge_

[EventSub est une API secondaire de Twitch](https://dev.twitch.tv/docs/eventsub/handling-webhook-events) permettant d'être informé en temps réel de changements auxquels on est abonné. C'est un peu plus complexe, mais plus économe en requêtes : une fois en place, ça n'implique qu'une exécution de _worker_ (via une requête reçue) par changement d'état, au lieu d'une vingtaine.

[[i]]
| Twitch a deux versions d'EventSub : une par _webhook_ et une par websocket. La première impliquerait de garder un _worker_ fonctionner très longtemps, ou d'établir une connexion depuis chaque visiteur, mangeant extrêmement vite la limite de trois connexions simultanées ; elle est donc exclue d'office. On part donc sur l'utilisation de _webhooks_ (sauf autre suggestion).

Ce pourrait être implémenté par un _worker_ Cloudflare : appelé avec les bons paramètres (et la bonne clef), il souscrirait à un abonnement auprès de Twitch pour être informé des changements. Il utiliserait des _Workers KV_ (un système de stockage clef-valeurs de Cloudflare _on the edge_) pour stocker les secrets et la liste des gens enregistrés, et génèrerait à chaque fois que Twitch le contacte un JSON avec les données à jour sur un site statique hébergé sur Cloudflare Pages (sur `https://pogscience-data.pages.dev/online.json`, dans l'idée).

La souscription d'abonnements via EventSub se fait en quelques étapes :
- envoi d'une requête de souscription en donnant l'URL que Twitch doit appeler en cas d'événement ;
- Twitch répond un peu plus tard sur l'URL donnée avec un _challenge_ pour vérifier qu'on contrôle bien l'URL (un peu plus tard = quelques (milli)secondes généralement) ;
- Twitch envoie une requête sur l'URL quand il se passe un truc ;
- Twitch envoie une requête sur l'URL si la souscription est annulée (alors il faut la relancer).

Dans tous les cas il y a une signature à vérifier (à partir d'une clef secrète qu'on doit stocker) dans les _headers_. Il faut pouvoir accéder au corps de la requête et à ses en-têtes pour pouvoir traiter correctement les requêtes. Pas besoin d'URL différente, tout pourrait être par exemple sur `https://pogscience-eventsub.workers.dev/ingest` (ou autre, peu importe).

On pourrait en simplifier l'usage en créant un petit formulaire qui appellerait le _worker_ pour ajouter/supprimer des comptes (une requête, choisie, vers `https://pogscience-eventsub.workers.dev`, ferait l'affaire, donc il suffit de faire un petit formulaire par dessus et ça roule).