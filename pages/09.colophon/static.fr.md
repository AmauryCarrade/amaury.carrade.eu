---
title: Colophon
homepage:
    invite: 'Sommes-nous jamais achevé d''imprimer ?'
process:
    twig: true
    zmarkdown: true
    markdown: false
---

Ce site web est développé [avec le CMS Grav](https://getgrav.org/). Il a pour particularité de stocker l'ensemble des données du site dans un système de fichiers, le rendant très simple à modifier et à sauvegarder, tout en proposant une interface d'administration pratique et facilement personnalisable. Le contenu est [synchronisé dans les deux sens avec un dépôt git](https://github.com/AmauryCarrade/amaury.carrade.eu).

L'installation de base de Grav est étendue grâce à [un thème personnel](https://github.com/AmauryCarrade/grav-theme-amaury-carrade), développé pour l'occasion en [Sass](https://sass-lang.com) et [Twig](https://twig.symfony.com/), ainsi que [quelques plugins](https://github.com/AmauryCarrade/thestias-infra/blob/main/roles/amaury.carrade.eu/vars/main.yml). Le tout est [déployé par un _playbook_ Ansible](https://github.com/AmauryCarrade/thestias-infra), derrière _nginx_.

En développant ce site web, j'ai pris soin à ce qu'il reste léger et accessible (ce serait un comble), tout en étant respectueux de la vie privée de ses visiteurs·euses. Côté serveur, une mise en cache agressive assure un temps de traitement des pages des plus rapides, proche d'un site statique — même si quelques améliorations sont encore possibles. De plus, vous ne trouverez ici :
- pas de services de suivi appelant des services tiers : Grav me donne quelques légères statistiques similaires à ce qu'on pourrait extraire d'un fichier de log d'un serveur web, et cela me suffit amplement ;
- pas de publicité, car tout le monde déteste cela, et moi avec (faites-vous une fleur, utilisez [uBlock Origin](https://ublockorigin.com/fr), même sur mobile[^ublock]) ;
- pas de polices ou scripts hébergées sur des services pistant les utilisateurs, tel Google Fonts.

[^ublock]: uBlock Origin n'est disponible sur mobile que pour Firefox pour Android, à l'heure actuelle. Ne pas confondre avec uBlock (tout court), qui est une reprise malicieuse d'une ancienne version d'uBlock Origin, et que je vous conseille de fuir.

Le contenu est rédigé avec Markdown, mais en divergeant du moteur natif de Grav : celui initialement développé pour Zeste de Savoir, [`zmarkdown`](https://github.com/zestedesavoir/zmarkdown), est [utilisé à la place](https://github.com/AmauryCarrade/grav-plugin-zmarkdown-engine). Il me permet, notamment :
- d'importer plus facilement des contenus depuis ou vers Zeste de Savoir, étant donné que le même moteur Markdown est utilisé partout ;
- de profiter d'un moteur plus complet et riche que celui de Grav ;
- de gérer automatiquement la typographie française (apostrophes typographiques, guillemets, espaces insécables normales ou fines, etc.).

Trois polices de caractères sont utilisées sur ce site, choisies avec soin.
- **[Fira Sans](https://mozilla.github.io/Fira)**, pour les textes des interfaces. Créée par Mozilla, c'est une police _sans serif_ très complète et dont j'aime beaucoup les traits, qui sait rester sobre tout en ayant, malgré tout, une certaine personnalité.
- **[Lora](https://github.com/cyrealtype/Lora-Cyrillic)**, pour le contenu des pages et articles, ainsi que pour les titres de la page d'accueil. Je l'ai découverte par hasard en voguant sur le web. J'utilisais initialement une police proche, [EB Garamond](http://www.georgduffner.at/ebgaramond/fr/index.html), mais je trouve Lora plus moderne et lisible, tout en gardant le cachet d'une belle police _serif_. Seul défaut : elle ne supporte pas les caractères grecs[^lora-grec]. Étrangement, depuis que je l'ai découverte, [son site web semble cassé](https://www.cyreal.org/fonts/lora/) ; l'aurais-je tuée ? 😰
- **[JetBrains Mono](https://www.jetbrains.com/lp/mono)**, pour les `codes source`. Créée, comme son nom l'indique, par [JetBrains](https://www.jetbrains.com), éditeur de logiciels dédiés à la programmation, elle est optimisée pour l'affichage et la lisibilité des codes sources. [Fira Code](https://github.com/tonsky/FiraCode) est une excellente alternative, mais j'ai finalement préféré cette dernière — il y a une part de subjectivité, soyons honnête. C'est une police qui supporte les [ligatures de programmation](https://www.jetbrains.com/lp/mono/#ligatures), mais si j'aime ces ligatures dans mon environnement de développement personnel, je ne les active pas ici par souci de clarté.

[^lora-grec]: Heureusement, les polices système utilisées en repli font leur office pour afficher des caractères grecs avec empattement, s'intégrant proprement à Lora — α, γ, δ, ζ, ξ, π, φ, ω. Si le rendu n'est pas correct chez vous et que vous avez quelques minutes à perdre pour moi, n'hésitez pas à [me le signaler](/contact) en indiquant votre système, que je trouve une meilleure police de repli.

Les textes ne sont pas justifiés, par souci d'accessibilité. Ils sont cependant sourcés, le plus possible, avec beaucoup trop de notes de bas de page.

Tout ce qui est utilisé pour ce site est disponible sous une licence libre. Le thème est publié [sous licence CeCILL-B](https://cecill.info/licences/Licence_CeCILL-B_V1-fr.html), une licence permissive en droit français proche de la licence BSD. Le plugin Grav que j'ai développé pour intégrer `zmarkdown` est [sous licence MIT](https://opensource.org/licenses/MIT). Quant à Grav lui-même et l'essentiel de ses plugins, ils sont [sous licence MIT également](https://opensource.org/licenses/MIT). Enfin, les trois polices sont diffusées sous licence [SIL Open Font License](https://scripts.sil.org/cms/scripts/page.php?item_id=OFL).

Le thème est [une reprise d'un thème que j'avais précédemment développé](https://github.com/AmauryCarrade/grav-theme-amaury-carrade/tree/79ed47781e60366dbafaf3804a9e9df64ea48594) pour un de mes ancien sites web, _Nébulius_, avec l'aide de [Kiliann Becquet](https://kiliannbecquet.fr/) (merci !). Ce dernier a plus ou moins été converti en le présent site et redirige intégralement vers ici.