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
media_order: 'pranav-kumar-jain-PR_0IPlMXgk-unsplash.jpg,Capture d’écran 2022-11-24 à 14.37.46 - Grande.jpeg'
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

Les premières critiques sont arrivées sur Mastodon : les gestionnaires d'instance[^instance] pourraient lire tous vos messages privés ! Voler vos mots de passe ! Et… c'est vrai. Contrairement à ce que certain·es ont pu affirmer, ce n'est pas une fonctionnalité intégrée à Mastodon (ou les autres réseaux similaires du _fédivers_[^fédi]), mais c'est totalement vrai.

[^instance]: Mastodon est un réseau décentralisé. Contrairement aux réseaux sociaux classiques, comme Twitter ou Instagram, il n'y a pas qu'un seul _Mastodon point com_ contrôlé par _Mastodon, Inc._ où tout le monde a un compte. Au contraire, il y a plein de « petits Mastodons » sur lesquels on peut s'inscrire, mais comme ces petits Mastodons communiquent tous entre eux, on peut communiquer avec tout le monde. Un peu comme les mails : il y a plein de fournisseurs (GMail, Orange, Free, les universités, ProtonMail, FastMail…), mais pas besoin d'être sur le même pour partager des messages : ils communiquent tous entre eux. Ces _petits Mastodons_ s'appellent des _instances_, dans la langue de Mastodon.

[^fédi]: Imaginez qu'avec votre compte Twitter, vous pouviez suivre, aimer, commenter, des gens sur Instagram, Facebook, Tumblr, ou autres ? Directement depuis Twitter, nativement intégré ? Et pareil depuis n'importe quelle autre plateforme ? Eh bien c'est ça, l'idée derrière le _fédivers_. Contraction de _federated universe_ (_univers fédéré_ en français), c'est l'ensemble des instances Mastodon, et d'autres réseaux sociaux conçus pour pouvoir communiquer tous ensemble ([PixelFed](https://pixelfed.org/), [PeerTube](https://joinpeertube.org/), [GNUSocial](https://fr.wikipedia.org/wiki/GNU_social), …) : on dit que tous ces réseaux sont _fédérés_ entre eux. Ça forme un immense réseau social unifié et totalement décentralisé.

Il n'y a pas d'interface d'administration listant les messages privés de tout le monde. Cependant, les messages privés sont bien stockés quelque part — sinon, comment pourriez-vous les lire ? Une personne avec un accès à une machine hébergeant une instance Mastodon peut donc aller les consulter, directement dans la base de données. Il faudra filtrer un peu, car ils sont tous stockés ensemble, mais ce n'est pas très complexe pour quelqu'un avec des compétences techniques. C'est vrai pour toute personne avec un accès direct à la base de données, à savoir certain·es administrateurices d'instances, mais aussi les entreprises offrant des services d'hébergement d'instances Mastodon[^masto-host].

[^masto-host]: Par exemple, [Masto.host](https://masto.host).

Concernant les mots de passe, c'est un peu plus subtil. Quand vous vous inscrivez, vous envoyez votre mot de passe qui est ensuite stocké de façon sécurisée : une personne ayant accès à la base de données _ne pourra pas retrouver le mot de passe_[^password-hash]. Mais… le mot de passe arrive quand même au serveur en clair, avant d'être sécurisé. Rien n'empêche quelqu'un de malicieux de modifier le code pour lire les mots de passe en douce…

[^password-hash]: L'idée, c'est qu'on transforme le mot de passe avec un algorithme spécial qui fait qu'on peut calculer la version transformée avec le mot de passe d'origine, mais qu'il est impossible de revenir au mot de passe d'origine depuis la version transformée, sauf à avoir une puissance de calcul démesurée (on parle de [_hachage_](https://fr.wikipedia.org/wiki/Fonction_de_hachage)). Pour vérifier que le mot de passe est bon, on re-transforme le mot de passe entré lors de la connexion et on vérifie que la transformation correspond à ce qu'on a stocké.

C'est pas très joyeux tout ça… Mastodon serait donc dangereux pour nos identifiants et données personnelles ? Il peut l'être, mais attendez, car le pire est à venir.

# En réalité, tout ça, c'est vrai partout.

Partout. Ce fonctionnement que je viens de décrire, avec ses défauts, c'est le fonctionnement de _quasiment tous les services que vous utilisez au quotidien_. Mastodon, certes, mais aussi Twitter, Instagram, Google, Facebook[^fb-quotidien], BeReal, votre forum favori, vos jeux en ligne… Ce fonctionnement (que ce soit pour les mots de passe ou le stockage des données), vous le retrouvez partout.

[^fb-quotidien]: Ah non pardon, j'ai dit _au quotidien_.

Donc oui, Mastodon a ces failles… tout comme l'intégralité, ou presque, d'internet !

C'est là le message important : **ce problème est réel, et il est bien d'en avoir conscience, mais il existe presque partout**. La question n'est plus _est-ce que tel site web peut lire mes données personnelles ?_ (la réponse est généralement oui).

> Est-ce que je peux faire confiance à ce site pour ne pas faire n'importe quoi avec mes données personnelles ?
> Source: La question que vous vous posez désormais.

Et la réponse est loin, très loin, d'être toujours simple. Il faudra peser les intérêts de l'éditeur du site :
- est-ce une entité commerciale qui pourrait vouloir faire de l'argent avec, ou est-ce géré par une entité sans but lucratif ?
- est-ce géré par un·e individu·e qui pourrait avoir de la curiosité mal placée, ou être mal intentionnée ?
- est-ce que l'hébergeur a un passif ? une charte d'engagement qui a été prouvée suivie par le passé ? des actions qui souligneraient sa crédibilité, ou feraient naître des doutes ?

C'est peut-être une des grandes difficultés du réseau Mastodon (et plus généralement du Fédivers) : nous étions habitués, depuis l'explosion des réseaux sociaux commerciaux, à n'avoir qu'un seul actuel que nous n'avions pas vraiment le choix de rejoindre (par pression sociale, tout le monde étant là). On se contentait de ressentir (ou non) un pincement de culpabilité en cochant la case _j'ai lu les conditions d'utilisation et la charte sur les données personnelles_ sans rien lire, et on oubliait tout ça bien vite. Désormais, il y a du choix — quelle instance ? —, et le problème des données personnelles se ressent plus fort car il est plus _concret_ : ce n'est plus une société un peu anonyme, c'est quelques personnes, des vraies personnes avec des intentions et des biais, qui gèreraient nos précieuses données personnelles.

C'est toute la difficulté du monde associatif, dont l'esprit des réseaux  sociaux décentralisés n'est pas si loin, et la source de bien des _dramas_ en son sein : on retrouve les biais humains et on s'en méfie d'autant plus que c'est concret, alors qu'une grosse entreprise… c'est très abstrait finalement.

Mais pourtant, la question à se poser est bien la même. Pour revenir à Hive Social, c'est une entreprise derrière, et c'est tout joli tout mignon, mais c'est… géré par deux personnes et un investisseur _anonyme et très généreux_. Quelles sont leurs intentions ? Ce n'est pas précisé, sinon conquérir un marché juteux qu'est celui des très nombreuses personnes fuyant Twitter[^comm-lgbt-hive]. Peut-on leur faire confiance, en l'état ? C'est à chacun d'en juger. Mais il serait dommage de ne le faire que sur le fait que c'est un réseau avec une jolie interface, en oubliant de regarder tout le reste. De la même façon qu'il serait dommage de faire confiance aveugle en une instance Mastodon juste car l'admin a l'air gentil.

[^comm-lgbt-hive]: Ce qui rend très logique la communication inclusive et pro-LGBT de HiveSocial : qui fuit Twitter ? Certainement pas les gens de droite et extrême droite qui se retrouvent très bien dans la nouvelle politique de sois-disant _free speech_. On pourrait argumenter que Hive existe déjà depuis deux ou trois ans, mais la problématique de la modération de Twitter fermant les yeux sur les attaques LGBTPhobes et autres était déjà la même, bien que pas aussi marquée qu'aujourd'hui.

Nous sommes donc condamné·es à être à la merci du doute. Nos données personnelles sont condamnées à être traitées sans que l'on ne puisse jamais avoir une pleine confiance…

![Michaël Stevens (VSauce), sur fond noir, fait une moue typique en disant “Or, are they?”](or-are-they-vsauce.jpeg?resize=512)
Figure: Or, are they?

# Le chiffrement de bout en bout, notre sauveur

Tout n'est en réalité pas perdu : on _peut_ avoir confiance.

Une solution, un peu radicale et fort peu réaliste au demeurant, est de contrôler _tout_ : sa propre instance Mastodon, par exemple, mais les instances avec lesquelles des messages sont échangés, le navigateur de toute personne la visitant… ce n'est pas une sinécure, quand c'est même _possible_.



https://soatok.blog/2022/11/22/towards-end-to-end-encryption-for-direct-messages-in-the-fediverse/