---
title: Colophon
homepage:
    invite: 'Sommes-nous jamais achevé d''imprimer ?'
process:
    twig: true
    zmarkdown: true
    markdown: false
---

Ce site web est développé [avec le CMS Grav](https://getgrav.org/), qui a pour particularité d'être basé sur des fichiers plats, le rendant très simple à modifier et à sauvegarder, tout en proposant une interface d'administration pratique et personnalisable pour les modifications de tous les jours. L'installation de base de Grav est étendue grâce à [un thème personnel](https://github.com/AmauryCarrade/grav-theme-amaury-carrade), développé pour l'occasion, ainsi que [quelques plugins](https://github.com/AmauryCarrade/thestias-infra/blob/main/roles/amaury.carrade.eu/vars/main.yml).

En développant ce site web, j'ai pris soin à ce qu'il reste léger et accessible (ce serait un comble), tout en étant respectueux de la vie privée de ses visiteurs·euses. Ainsi, vous ne trouverez ici :
- pas de services de suivi appelant des services tiers : Grav me donne quelques légères statistiques similaires à ce qu'on pourrait extraire d'un fichier de log d'un serveur web, et cela me suffit amplement ;
- pas de publicité, car tout le monde déteste cela et moi avec (faites-vous une fleur, utilisez [uBlock Origin](https://ublockorigin.com/fr)) ;
- pas de polices ou scripts hébergées sur des services pistant les utilisateurs, tel Google Fonts.

Le contenu est rédigé avec Markdown, mais en divergeant du moteur de Grav : celui initialement développé pour Zeste de Savoir, [`zmarkdown`](https://github.com/zestedesavoir/zmarkdown), est [utilisé à la place](https://github.com/AmauryCarrade/grav-plugin-zmarkdown-engine). Il me permet, notamment :
- d'importer plus facilement des contenus depuis ou vers Zeste de Savoir, étant donné que le même moteur Markdown est utilisé ;
- de profiter d'un moteur plus complet et riche que celui de Grav ;
- de gérer automatiquement la typographie française (accents typographiques, guillemets, etc.).

