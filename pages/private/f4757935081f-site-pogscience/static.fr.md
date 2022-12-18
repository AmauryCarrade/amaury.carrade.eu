---
title: 'Proposition pour le site de PogScience'
homepage:
    invite: 'Une maison pour Pog !'
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

Afin de limiter les frais et la complexité de maintenance, j'ai eu l'idée de gérer le site totalement _on the Edge_, c'est à dire sur une [Jamstack](https://fr.wikipedia.org/wiki/Jamstack) (j'avais pensé à l'infrastructure de Cloudflare, notamment car je la connais bien). Ça a plusieurs avantages : 

- site extrêmement rapide (car sur CDN) ;
- sécurisé (virtuellement pas de _backend_, donc rien à mettre à jour ou à hacker, que du statique ou presque) ;
- coûts faibles sinon nuls (probablement nuls, en pratique, vues les très généreuses limites du plan gratuit de Cloudflare).

Il y a deux parties : celles qui sont statiques et celles dynamiques. Les parties statiques sont simples à gérer : un site statique (peu importe le générateur) et basta. Très léger inconvénient : la modification se fait en modifiant des fichiers Markdown sur GitHub ou autres, mais c'est quand même très accessible (GitHub ayant une interface de modification totalement en ligne). Le site est mis à jour automatiquement à chaque _push_ (ou modification sur GitHub directement), comme il est d'usage pour ce genre de _stack_.

Concernant la partie dynamique, je suis en