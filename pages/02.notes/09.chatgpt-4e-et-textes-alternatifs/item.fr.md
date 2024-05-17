---
title: 'Avec ChatGPT-4e, plus besoin d’écrire des textes alternatifs ? (non)'
license: by-sa
visible: false
taxonomy:
    category:
        - Accessibilité
    tag:
        - contraste
        - normes
        - WCAG
        - APCA
media_order: 'divazus-fabric-store-87wQJJu85Fs-unsplash - Grande.jpeg'
header_image:
    image: divazus-fabric-store-87wQJJu85Fs-unsplash.jpeg
    color: '#3e611a'
    author: 'Divazus Fabric Store'
    link: 'https://unsplash.com/fr/photos/textile-vert-sur-textile-blanc-87wQJJu85Fs?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash'
    vertical_centering: 50
---

C’est effectivement mieux que ce qui se faisait avant pour générer des descriptions d’images, mais ce n’est pas encore parfait pour autant. Yep, je viens encore faire le rabat-joie, mais partez pas, j’ai des arguments :p

# Contexte ?

Ces systèmes manquent toujours de quelque chose d’indispensable : une compréhension du contexte et une priorisation en fonction de ce dernier. Normalement, un texte alternatif *commence par ce qui est contextuellement important dans l’image* (ce qu’il n’est pas forcément facile de déterminer automatiquement), de façon brève et vue-d’ensemble, avant de partir sur une description plus précise.

L’objectif est de permettre de passer à la suite si on a eu assez d’informations au début et qu’on ne s’intéresse que peu au détail de la prise au fond de l’image — c’est la même différence qu’entre un cas où on balaye des yeux une image et où on la regarde attentivement. C’est un choix que l’on peut faire en tant que valide des yeux ; c’est un choix que l’on devrait pouvoir également faire si on utilise un lecteur d’écran ou une plage braille. La description telle que générée par ChatGPT-4o ne le permet pas.

Une description alternative tel que celle-ci est mieux que rien du tout, on est d’accord, mais elle va faire perdre beaucoup de temps à s'arrêter sur des détails quand un humain aurait commencé par écrire quelque chose comme « Un gros pouf vert vaguement humanoïde avec des yeux et une bouche joyeuse tirant la langue semble s’amuser avec un trépied, dans un bureau vide ».

Idéalement, si on n’avait pas que le champ “ALT”, on pourrait même faire ça de façon plus fine en séparant clairement les deux (par exemple en HTML avec les attributs alt pour la description courte, et un lien vers la description longue (ce qui remplace feu-l’attribut longdesc), ou aria-describedby, ou similaire. Mais c’est un peu annexe.

# C'est toujours la même chose

Le problème avec les systèmes tentant de corriger automatiquement l’accessibilité est toujours le même : ces systèmes manquent de la *compréhension de l’intention* de ce qui est montré et donc rendu accessible. C’est un problème similaire, bien qu’un peu différent, que rencontrent toutes les tentatives, jamais réussies, toujours mauvaises, d’overlays d’accessibilité tentant de magiquement rendre un site accessible avec un script, qui tentent de le faire automatiquement sans aucune vue d’ensemble. On pourra argumenter que des outils plus modernes tel que les LLM ont un peu plus de “vue d’ensemble”, quoique cela veuille dire pour un LLM. J’entends. Mais cela reste insuffisant pour générer quelque chose de correct et de totalement utile aujourd’hui.

# C'est fiable ?

Enfin, il reste toujours l’éternel problème de fiabilité de ces LLM.

~~On a un bel exemple ici : il n’y a… pas de caméra ? Juste un trépied. Et pourtant le LLM insiste : caméra *professionnelle*, *équipée de divers accessoires*…~~ [erreur](https://mamot.fr/@spacefox@mastodon.spacefox.fr/112455718632334447)

Il n’y a pas non plus deux poufs verts derrière la “caméra” (mais un seul).

La description est donc fausse. Certes, il y a de l’amélioration extrêmement rapide à ce niveau, j’en conviens, mais je ne crois pas qu’on ait moyen de corriger de façon sûre ces problèmes d’erreurs ou d’hallucinations — corrige-moi si je me trompe.

Dans un cas léger comme celui-ci, avoir une petite erreur pourrait être perçu comme peu grave : il n’y a pas d’enjeu. Mais, **ce serait considérer les personnes non-valides comme pouvant se satisfaire d'une moindre qualité que les autres** ; je ne pense pas qu'il s'agisse du modèle que nous souhaitons.

Aussi, ce serait encore plus gênant sur des images où les détails sont importants : présence ou absence de personnes à un événement clef, images contenant des données, graphs, photos d'expériences où les détails comptent, que sais-je.

---

Mais, comme je le disais tantôt, c'est mieux que rien.

Je pense qu'il faudrait malgré tout libeller les descriptions générées automatiquement comme tel, a minima, afin qu'une personne les lisant/entendant sache qu'il faut les prendre avec des pincettes.