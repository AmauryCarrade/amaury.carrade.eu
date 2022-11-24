---
title: 'Nos chères données personnelles : Mastodon, Hive, Twitter… quelle différence ?'
header_image:
    color: '#000000'
    vertical_centering: 50
    image: pranav-kumar-jain-PR_0IPlMXgk-unsplash.jpg
    author: 'Pranav Kumar Jain'
    link: 'https://unsplash.com/@peejayvisual'
license: by-sa
visible: false
abstract: 'Mastodon a été critiqué pour sa gestion des données personnelles, et Hive, un nouveau réseau social, a débarqué comme une fleur en promettant monts et merveilles. Qu''en est-il vraiment ? Je suis convaincu que le problème est bien plus profond que cela.'
published: true
media_order: pranav-kumar-jain-PR_0IPlMXgk-unsplash.jpg
taxonomy:
    category:
        - Opinion
    tag:
        - mastodon
        - fédivers
        - twitter
        - social
        - 'données personnelles'
        - sécurité
page-toc:
    active: false
---

Techniquement, aucune.

Oui, cette conclusion introductive est provocatrice. Mais techniquement parlant, il n'y en a aucune.

Pour le contexte, [suite aux agissements d'un certain milliardaire après son rachat de Twitter](https://twitterisgoinggreat.com), bien du monde sur Twitter a cherché une alternative. [Mastodon](https://joinmastodon.org/fr) a gagné plusieurs millions de personnes en quelques jours à peine.

Bien sûr, un tel mouvement a attiré les convoitises, et d'autres réseaux cherchent à profiter du pactole qu'est cette manne de nouvelles et nouveaux utilisateurs en recherche d'un nouveau lieu de sociabilisation. Aussi, les alternatives gagnant un énorme coup de projecteur, nombre de commentaires, retours, et critiques, sont adressées. Une bonne partie d'entre elles concernent la gestion des données personnelles.

Une alternative a brutalement émergé : [Hive Social](https://www.hivesocial.app). Presque inconnu jusqu'alors, ce nouveau réseau promet monts et merveilles, malgré un certain nombre de problèmes de sécurité et de _red flags_[^hive-red] au moment où j'écris ces lignes.

[^hive-red]: Notamment : réseau centralisé, propriétaire, basé aux USA (donc soumis au [_Cloud Act_](https://fr.wikipedia.org/wiki/CLOUD_Act)), [refusant de s'expliquer sur les agissements de certains collaborateurs](https://twitter.com/althsee/status/1594733986122792965), avec une sécurité faible (notifications privées reçues après déconnexion, absence de double-authentification…), une grande opacité sur le traitement des données personnelles [tout en précisant qu'elles seront partagées avec des tiers non-précisés](https://web.archive.org/web/20221123012923/https://www.hivesocial.app/privacy), pas de DPO (donc pas conforme RGPD), des demandes d'autorisations extrêmement louches (accès à l'intégralité des médias exigé alors que ce n'est pas la façon normale de permettre d'envoyer des fichiers), géré par deux personnes financées par un mécène anonyme et très généreux…

La question a donc émergé : face aux critiques concernant [la gestion des données de Mastodon](https://social.imirhil.fr/@aeris/109316559706610326), vaut-il mieux aller sur Hive Social ? Ou Twitter ? Ou ailleurs ? En bref, comment être sûr de la sécurité de ses données ? C'est… pas si simple.

# Mastodon : toutes vos données lues des admins ?

Les premières critiques sont arrivées sur Mastodon : les administrateurs d'instance[^instance] pourraient lire tous vos messages privés ! Voler vos mots de passe ! Et… c'est vrai. Contrairement à ce que certain·es ont pu affirmer, ce n'est pas une fonctionnalité intégrée à Mastodon (ou les autres réseaux similaires du _fédivers_[^fédi]), mais c'est totalement vrai.

[^instance]: Mastodon est un réseau décentralisé. Contrairement aux réseaux sociaux classiques, comme Twitter ou Instagram, il n'y a pas qu'un seul _Mastodon point com_ contrôlé par _Mastodon, Inc._ où tout le monde a un compte. Au contraire, il y a plein de « petits Mastodons » sur lesquels on peut s'inscrire, mais comme ces petits Mastodons communiquent tous entre eux, on peut communiquer avec tout le monde. Un peu comme les mails : il y a plein de fournisseurs (GMail, Orange, Free, les universités, ProtonMail, FastMail…), mais pas besoin d'être sur le même pour partager des messages : ils communiquent tous entre eux. Ces _petits Mastodons_ s'appellent des _instances_, dans la langue de Mastodon.

[^fédi]: Le _fédivers_, contraction de _federated universe_ ou _univers fédéré_ en français, est l'ensemble des instances Mastodon connectées entre elles en réseau (on dit qu'elles sont _fédérées_).

Il n'y a pas d'interface d'administration listant les messages privés de tout le monde. Cependant, les messages privés sont bien stockés quelque part — sinon, comment pourriez-vous les lire ? Une personne avec un accès à une machine hébergeant une instance Mastodon peut donc aller les consulter, directement dans la base de données. Il faudra filtrer un peu, car ils sont tous stockés ensemble, mais ce n'est pas très complexe pour quelqu'un avec des compétences techniques. C'est vrai pour toute personne avec un accès direct à la base de données, à savoir certain·es administrateurices d'instances, mais aussi les entreprises offrant des services d'hébergement d'instances Mastodon[^masto-host].

[^masto-host]: Par exemple, [Masto.host](https://masto.host).

Concernant les mots de passe, c'est un peu plus subtil. Quand vous vous inscrivez, vous envoyez votre mot de passe qui est ensuite stocké de façon sécurisée : une personne ayant accès à la base de données _ne pourra pas retrouver le mot de passe_[^password-hash]. Mais… le mot de passe arrive quand même au serveur en clair, avant d'être sécurisé. Rien n'empêche quelqu'un de malicieux de modifier le code pour lire les mots de passe en douce…

[^password-hash]: L'idée, c'est qu'on transforme le mot de passe avec un algorithme spécial qui fait qu'on peut calculer la version transformée avec le mot de passe d'origine, mais qu'il est impossible de revenir au mot de passe d'origine depuis la version transformée, sauf à avoir une puissance de calcul démesurée (on parle de [_hachage_](https://fr.wikipedia.org/wiki/Fonction_de_hachage)). Pour vérifier que le mot de passe est bon, on re-transforme le mot de passe entré lors de la connexion et on vérifie que la transformation correspond à ce qu'on a stocké.

C'est pas très joyeux tout ça… Mastodon serait donc dangereux pour nos identifiants et données personnelles ? Il peut l'être, mais attendez, car le pire est à venir.

# En réalité, tout ça, c'est vrai partout.

Partout. Ce fonctionnement que je viens de décrire, avec ses défauts, c'est le fonctionnement de _quasiment tous les services que vous utilisez au quotidien_. Mastodon, certes, mais aussi Twitter, Instagram, Google, Facebook[^fb-quotidien], BeReal, votre forum favori, vos jeux en ligne… Ce fonctionnement (que ce soit pour les mots de passe ou le stockage des données), vous le retrouvez partout.

[^fb-quotidien]: Ah non pardon, j'ai dit _au quotidien_.

Donc oui, Mastodon a ces failles… tout comme l'intégralité, ou presque, d'internet !

C'est là le message important : **ce problème est réel, et il est bien d'en avoir conscience, mais il existe presque partout**. La question se transforme de _est-ce que tel site web peut lire mes données personnelles ?_ (la réponse est généralement oui) en _est-ce que je peux faire confiance à ce site pour ne pas faire n'importe quoi avec mes données personnelles ?_.

Et la réponse est loin, très loin, d'être toujours simple.

https://soatok.blog/2022/11/22/towards-end-to-end-encryption-for-direct-messages-in-the-fediverse/