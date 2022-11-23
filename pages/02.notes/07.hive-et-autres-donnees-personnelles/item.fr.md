---
title: 'Mastodon, Hive, Twitter… données perso, quelle différence ?'
header_image:
    color: '#000000'
    vertical_centering: 50
    image: pranav-kumar-jain-PR_0IPlMXgk-unsplash.jpg
    author: 'Pranav Kumar Jain'
    link: 'https://unsplash.com/@peejayvisual'
license: by-sa
visible: false
abstract: 'Mastodon a été critiqué pour sa gestion des données personnelles, et Hive, un nouveau réseau social, a débarqué comme une fleur en promettant monts et merveilles. Qu''en est-il vraiment ?'
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

Oui, cette conclusion est provocatrice. Mais techniquement parlant, il n'y en a aucune.

Pour le contexte, [suite aux agissements d'un certain milliardaire après son rachat de Twitter](https://twitterisgoinggreat.com), beaucoup de monde sur Twitter ont cherché une alternative. Une des plus prisées fut Mastodon, qui a gagné plusieurs millions de personnes en quelques jours à peine.

Bien sûr, un tel mouvement a attiré les convoitises, et d'autres réseaux cherchent à profiter du pactole qu'est cette manne de nouvelles et nouveaux utilisateurs en recherche d'un nouveau lieu de sociabilisation. Aussi, les alternatives gagnant un énorme coup de projecteur, nombre de commentaires, retours, et critiques, sont adressées. Une bonne partie d'entre elles concernent la gestion des données personnelles.

Une alternative a brutalement émergé : Hive Social. Presque inconnu jusqu'alors, ce nouveau réseau promet monts et merveilles, malgré un certain nombre de problèmes de sécurité et de _red flags_[^hive-red] au moment où j'écris ces lignes.

[^hive-red]: Notamment : réseau centralisé, propriétaire, basé aux USA (donc soumis au Cloud Act), refusant de s'expliquer sur les agissements de certains collaborateurs, avec une sécurité faible, un mécène anonyme très généreux, une grande opacité sur le traitement des données personnelles, pas de DPO (donc pas conforme RGPD), des demandes d'autorisations extrêmement louches (accès à l'intégralité des médias exigé alors que ce n'est pas la façon normale de permettre d'envoyer des fichiers), géré par deux personnes…

La question a donc émergé : face aux critiques concernant [la gestion des données de Mastodon](https://social.imirhil.fr/@aeris/109316559706610326), vaut-il mieux aller sur Hive Social ? Ou Twitter ? Ou ailleurs ? En bref, comment être sûr de la sécurité de ses données ? C'est… pas si simple.

# Mastodon : toutes vos données lues des admins ?

Les premières critiques sont arrivées sur Mastodon : les administrateurs d'instance[^instance] pourraient lire tous vos messages privés ! Voler vos mots de passe ! Et… c'est vrai. Contrairement à ce que certain·es ont pu affirmer, ce n'est pas une fonctionnalité intégrée comme ça à Mastodon (ou les autres réseaux similaires du fédivers[^fédi]), mais c'est totalement vrai.

[^instance]: Mastodon est un réseau décentralisé. Contrairement aux réseaux sociaux classiques, comme Twitter ou Instagram, il n'y a pas qu'un seul _Mastodon point com_ contrôlé par _Mastodon, Inc._ où tout le monde a un compte. Au contraire, il y a plein de « petits Mastodons » sur lesquels on peut s'inscrire, mais comme ces petits Mastodons communiquent tous entre eux, on peut communiquer avec tout le monde. Un peu comme les mails : il y a plein de fournisseurs (GMail, Orange, Free, les universités, ProtonMail, FastMail…), mais pas besoin d'être sur le même pour partager des messages : ils communiquent tous entre eux. Ces _petits Mastodons_ s'appellent des _instances_, dans la langue de Mastodon.

[^fédi]: Le _fédivers_, contraction de _federated universe_ ou _univers fédéré_ en français, est l'ensemble des instances Mastodon connectées entre elles en réseau (on dit qu'elles sont _fédérées_).

https://soatok.blog/2022/11/22/towards-end-to-end-encryption-for-direct-messages-in-the-fediverse/