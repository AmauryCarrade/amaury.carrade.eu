---
title: 'On a retrouvé π au beau milieu du hasard'
abstract: 'π, ce nombre si emblématique des mathématiques, a cette fâcheuse tendance à apparaître partout, et surtout là où on ne l''attend pas. Et même… dans le hasard le plus complet ?'
media_order: 'blobpeek.png,logo-zds-dé-pi-bannière.png,logo-zds-dé-pi.png'
header_image:
    image: logo-zds-dé-pi-bannière.png
    color: '#084561'
    vertical_centering: 50
taxonomy:
    category:
        - Sciences
    tag:
        - mathématiques
        - pi
        - piday
        - probabilités
page-toc:
    active: true
published: true
date: '16:00 14-03-2020'
license: by-sa
zestedesavoir: 'https://zestedesavoir.com/articles/3452/on-a-retrouve-p-au-beau-milieu-du-hasard/'
routable: true
visible: true
override_default_title: 'On a retrouvé π au beau milieu du hasard'
override_default_desc: 'π, ce nombre si emblématique des mathématiques, a cette fâcheuse tendance à apparaître partout, et surtout là où on ne l''attend pas. Et même… dans le hasard le plus complet ?'
override_default_img: logo-zds-dé-pi.png
process:
    zmarkdown: true
    markdown: false
    twig: false
---

π, ce nombre si emblématique des mathématiques, a cette fâcheuse tendance à apparaître partout, et surtout là où on ne l'attend pas. Facétieux, il se cache dans tous les recoins des mathématiques… même les plus inattendus !

À l'origine, π est le rapport entre la circonférence d'un cercle et son diamètre : c'est comme ça qu'on l'a découvert dans l'antiquité et que sa folle histoire a commencé. Déjà en 2000 avant notre ère, on en retrouvait la trace, certes très approximative.

$$\pi \approx 3,14\,15\,92\,65\,35\,89\,79\,32$$
Equation: Les seize premières décimales de π

On retrouve π dans beaucoup de formules de géométrie bien sûr, π étant issu de cette branche des mathématiques, mais aussi dans des séries, autour des nombres complexes, en statistiques, dans bien des branches de la physique ou de la chimie au détour d'équations…

Aujourd'hui, histoire de parler d’inattendu dans tous les sens du terme, retrouvons-le dans *le hasard*. Car il s'y cache aussi !


# π tiré au sort ?

Alors bien sûr on ne va pas tirer des nombres au hasard jusqu'à tomber par (énorme) chance sur π ! On va être un peu plus intelligent que ça… en tirant *deux* nombres. Attendez, vous allez comprendre…

## Une histoire de nombres premiers entre eux

Tout nombre entier peut s'écrire comme le produit d'autres nombres : jusque-là, rien de bien compliqué. Si on prend quelques nombres et qu'on les écrit de la sorte, on obtient quelque chose comme ça :

$$\begin{array}{rcl}12 &=& 3 \times 4\\11 &=& 11 \ \ \text{(il n'y a rien de mieux)}\\100 &=& 4 \times 5 \times 5\\40 &=& 2 \times 2 \times 2 \times 5\end{array}$$

Si on regarde les nombres deux par deux, on aura dans certains cas des facteurs en commun (par exemple, 100 et 40 partagent 2 et 5). Dans d'autres cas, il n'y en a pas (11 et 12 ne partagent rien) : on dit alors que ces nombres sont **premiers entre eux**.

Quand on tire deux nombres au hasard, il y a donc deux possibilités : ils peuvent être *premiers entre eux*, ou ne pas l'être.

Par exemple, j'ai tiré avec deux dés à cent faces les nombres **77** et **87** : 87 s'écrit 3 × 29 et 77 = 7 × 11 — ils sont premiers entre eux, ne partageant aucun facteur commun. J'ai relancé mes dés pour trouver **2** et **14** : 2 est premier et 14 s'écrit 2 × 7 — ils ne sont donc, eux, pas premiers entre eux.

## Expérimentons : tirons plein de nombres !

Mais *so what*, me diriez-vous, où trouve-t-on π là-dedans ? Dans les probabilités ! Car en tirant deux nombres au hasard, on n'a pas autant de chance d'avoir deux nombres premiers entre eux que de nombres qui ne le sont pas. Lancez plein de dés, vous verrez : **vous obtiendrez plus souvent des nombres premiers entre eux que le contraire**. Cette probabilité se calcule, et devinez quoi ? Elle est liée à π !

En effet (et je le justifierai plus loin),

[[neutre|Théorème de Cesàro en théorie des nombres]]
| -> **La probabilité que deux nombres tirés au hasard soient premiers entre eux vaut** <-
| 
| $$\frac{6}{\pi^2}$$

Comment vérifier ça ? Un moyen simple est de… tirer plein de nombres. En réalisant l'expérience tout plein de fois et en comptant quel pourcentage de couples premiers entre eux on a obtenu, on approche la probabilité expérimentalement :) .

Oh, on pourrait tirer des milliers de couples de dés et vérifier que les nombres obtenus sont premiers entre eux… mais ce serait un peu longuet.[^dés-matt-parker] Comme j'ai un peu la flemme, j'ai décidé d'écrire un petit programme qui fait tout le boulot pour moi, ce qui me permet de faire des millions (ou milliards si l'envie m'en prend) de tirages sans effort. Ha !

### Commencer doucement…

Comme il faut savoir commencer petit, j'ai démarré avec un millier de tirages. J'ai obtenu **643** couples de nombres premiers entre eux, ce qui fait une probabilité expérimentale, basée sur ce tirage, de :

$$P = \frac{643}{1000} = 0,643$$

On aurait donc $6 / \pi^2 = 0,643$ ? Si oui, ça donnerait :

$$\pi^2 = 6 \times \frac{1}{0,643} \approx 9,331$$

et donc :

$$\pi \approx \sqrt{6 \times \frac{1}{0,643}} \approx 3,054$$

Je vous l'accorde, la précision n'est pas extraordinaire… mais tout de même, pour à peine un millier de paires de nombres tirés au hasard, retrouver π avec une précision de 2 %, c'est pas si mal ! Cela dit, *on peut faire mieux*.

Comme ce n'est pas moi qui lance les dés, autant se faire plaisir : partons sur **un million de tirages**. En moins d'une seconde, c'est bon, et on a trouvé **607 780 couples de nombres premiers entre eux**. En appliquant le même calcul que plus haut, avec une probabilité expérimentale de $\frac{607\,780}{1\,000\,000} = 0,607\,780$, on trouve :

$$\pi \approx 3,141\,972$$

Voilà qui n'est pas si mal ! Certes, dès la quatrième décimale on perd la précision (elle devrait être un 5, la vraie valeur commençant par 3,14159) — mais encore une fois, on tire cette valeur du hasard complet, donc une précision de 0,01 % c'est relativement acceptable. Surtout qu'en pratique, prendre 3,14 comme approximation de π, ça suffit à la majorité des usages…

### …mais finir gourmand

Dans un brin de folie (et surtout car ça travaille tout seul pendant que je fais autre chose), j'ai demandé dix milliards de tirages (oui, 10 000 000 000 de tirages). Après seulement trois heures et quart de calcul (ahrem)[^non-parallélisé], 6 079 281 509 couples de nombres premiers entre eux avaient été tirés, ce qui nous permet d'estimer que π a pour valeur…

$$\pi \approx 3,141\,589\,943$$

C'est déjà mieux : on a quatre décimales justes (la vraie valeur étant π = 3,1415**92**…) !

[[s|Le code source, pour les curieuses et les curieux]]
| Il n'y a en soit rien de très complexe dans le programme de tirage, pour qui connaît un peu la programmation : il s'agit juste de calculer le PGCD de plein de nombres tirés au hasard, et de compter ceux pour lesquels le PGCD vaut 1 (correspondant au cas où les nombres sont premiers entre eux). Ensuite, en divisant ce nombre par le nombre total de tirages, on obtient la probabilité d'avoir deux nombres premiers entre eux, soit une approximation de $6 / \pi^2$. Un peu de maths en plus et on extrait une approximation de π :) .
| 
| J'ai juste ajouté par dessus un petit calcul de la précision en se basant sur la valeur de π “réelle” (à 15 décimales).
| 
| Le programme a été fait en Rust, parce que c'est rapide (j'avais pour volonté de tirer _beaucoup_ de couples de nombres pour avoir une précision correcte) et que j'aime bien le langage (totalement subjectif, oui).
| 
| ```rust
| extern crate gcd;
| extern crate rand;
| 
| use std::env;
| 
| use gcd::Gcd;
| use rand::Rng;
| 
| use std::f64::consts::PI;
| 
| const DEFAULT_DRAWS: u64 = 1_000_000;
| const MAX_NUMBER: u128 = std::u128::MAX;
| 
| #[inline(always)]
| fn are_randoms_coprime<R: Rng>(rng: &mut R) -> bool {
|     rng.gen_range(1, MAX_NUMBER).gcd(rng.gen_range(1, MAX_NUMBER)) == 1
| }
| 
| fn main() {
|     let args: Vec<String> = env::args().collect();
|     let draws: u64 = args.get(1).unwrap_or(&String::new()).parse().unwrap_or(DEFAULT_DRAWS);
| 
|     let mut rng = rand::thread_rng();
| 
|     let coprimes = (1..draws)
|         .filter(|_| are_randoms_coprime(&mut rng))
|         .count() as f64;
| 
|     let pi = (6_f64 / (coprimes / draws as f64)).sqrt();
|     let precision = (pi - PI).abs() / PI * 100_f64;
| 
|     println!("{} coprimes in {} draws", coprimes, draws);
|     println!("π ≈ {} (precision {} %)", pi, precision);
| }
| ```
| 
| En le lançant pour un million de tirages, on peut trouver la valeur obtenue plus haut — bien sûr, comme c'est aléatoire, la valeur exacte change un peu à chaque fois mais la précision reste sensiblement la même, entre 0,1 et 0,01 %.
| 
| ```console
| $ cargo run --release --quiet               
| 607780 coprimes in 1000000 draws
| π ≈ 3.141972812647824 (precision 0.01210083864935896 %)
| ```
| 
| Avec dix milliards de tirages, c'est… un peu plus long, mais le résultat est bien meilleur !
| 
| ```console
| $ cargo run --release --quiet -- 10000000000
| 6079281509 coprimes in 10000000000 draws
| π ≈ 3.14158994300916 (precision 0.0000862804128715215 %)
| ```

[^dés-matt-parker]: Cela dit, si vraiment vous y tenez, [Matt Parker l'a fait](https://www.youtube.com/watch?v=ESU4KdRLzu0) (en anglais, avec 500 couples de nombres tirés).
[^non-parallélisé]: Comme vous pouvez le voir dans le bloc secret un peu après, le code qui a fait ce calcul n'est pas parallélisé, ce qui explique la durée énorme de calcul alors qu'on aurait pu faire beaucoup mieux en tirant plein de nombres en même temps. Cela dit et comme nous le verrons plus loin, même avec un système massivement parallélisé pour faire le plus de tirages possibles, cette méthode n'est franchement pas la meilleure, et certainement pas celle qu'est utilisée pour calculer des dizaines de milliards de décimales de π !


# Pourquoi ça marche ?

Bon allez, il est temps de rentrer un peu dans les mathématiques afin de comprendre d'où vient cette probabilité !

[[a|Une formule peut en cacher une autre]]
| Cette section rentre dans des détails mathématiques. J'ai tenté d'être le plus clair possible même si vous n'avez pas de grosses connaissances (les maths du collège français, étudiées vers 14/15 ans, devraient suffire), mais si vous n'êtes pas à l'aise ou que l'explication ne vous intéresse pas, vous pouvez me faire confiance et sauter à la partie suivante.

Partons de ce qu'on cherche. Avec $a$ et $b$ deux entiers naturels quelconques (ceux qu'on tire au dé), on cherche la probabilité qu'ils soient premiers entre eux, autrement dit que leur plus grand diviseur commun (PGCD) soit égal à 1.

[[i]]
| En effet, si le PGCD vaut 1, les deux nombres ne peuvent partager aucun autre facteur commun (car alors il serait plus grand que 1, et donc le PGCD ne vaudrait pas 1) ; ils sont donc premiers entre eux.

Pour la suite, on va noter $p_1$ cette probabilité (vous comprendrez assez vite pourquoi ce 1 en indice), et on la note ainsi : 

$$p_1 = P\left(\text{pgcd}(a, b) = 1\right)$$

Une première observation que l'on peut faire, c'est qu'on peut avoir des nombres arbitrairement grands ici (et même potentiellement *très* grands, la seule limite étant l'infini). Le plus grand diviseur commun de deux nombres peut donc être, lui aussi, *aussi grand que l'on veut*. $\text{pgcd}(a, b)$ peut valoir 1, ou 2, ou 3, ou… ou $k$, ou $k + 1$, ou… jusqu'à l'infini.

Mais alors, il est _certain_ que le PGCD a l'une de ces valeurs. Donc si on somme la probabilité que le PGCD soit 1, et soit 2, et 3, et…, et $k$, et…, jusqu'à l'infini, on doit trouver 1 (la probabilité certaine).

Autrement dit, si on note $p_k$ la probabilité que le PGCD de $a$ et $b$ soit $k$ :

$$p_k = P\left(\text{pgcd}(a, b) = k\right)$$

…alors on sait que :

$$p_1 + p_2 + \cdots + p_k + \cdots = 1$$

Ce qu'on peut écrire d'une façon un peu plus compacte :

$$\sum\limits_{k = 1}^\infty p_k = 1$$

On va donc tenter de déterminer la probabilité que le PGCD de $a$ et $b$ soit $k$, c'est peut-être plus simple…

## Alors, dans quels cas est-ce que $\, \text{pgcd}(a, b) = k\,$ ?

Réfléchissons. Pour que le PGCD de $a$ et $b$ soit $k$, il faut respecter deux critères en même temps :

- $k$ doit diviser $a$ et $b$ (c'est mieux… sinon il aura du mal à être le plus grand *diviseur*) ; et
- il ne doit pas y avoir de diviseur _plus grand que $k$_.

Pour trouver la probabilité $p_k$, il nous faut donc trouver la probabilité de ces deux événements et les multiplier (car on veut les deux _en même temps_, et que ces événements sont indépendants les uns des autres).

### Probabilité que $k$ divise $a$ et $b$

Quand on y pense,

- 2 divise la moitié des nombres (tous les nombres pairs) ;
- 3 en divise un tiers (3, 6, 9, 12, …) ;
- 4 en divise un quart…

En généralisant, un nombre quelconque $k$ divise un $k$-ième des nombres… la probabilité qu'il en divise un en particulier est donc $1/k$ — par exemple, 2 divise la moitié des nombres, donc en prenant un nombre au hasard, il y a une chance sur deux qu'il soit divisible par deux (autrement dit, pair).

[[i]]
| Une autre façon de s'en convaincre est que dans la division d'un nombre quelconque par $k$, il peut y avoir $k$ restes différents : 0, 1, 2, …, et $k-1$. Le seul bon cas est celui où le reste est nul ; comme on a autant de chance de tomber sur l'un ou l'autre des restes, la probabilité de tomber sur zéro est bien $1/k$.

Ici on veut que $k$ divise $a$ **et** $b$. La probabilité qu'on cherche est donc celle que $k$ divise $a$ multipliée par celle que $k$ divise $b$. Les deux nombres n'ayant pas particulièrement de différence de traitement, cette probabilité est bien sûr la même, et **la probabilité que $k$ divise $a$ et $b$ vaut donc $1/k^2$.**

### Probabilité qu'il n'y ait pas de diviseur plus grand que $k$

On veut qu'il n'y ait pas de diviseur commun plus grand que $k$ : c'est équivalent au fait qu'il n'y ait pas de diviseur plus grand que 1 si on divise par $k$ (autrement dit que le $\text{pgcd}\left(\frac{a}{k}, \frac{b}{k}\right)$ soit 1)[^a-sur-k-entier].

[[i]]
| Pour s'en convaincre, il suffit de regarder un cas particulier : disons 42 et 70. $42 = 2 \times 3 \times 7$, et $70 = 2 \times 5 \times 7$, donc leur plus grand commun diviseur est $2 \times 7 = 14$. Si on divise par quatorze, il ne nous reste que 3 d'un côté, et 5 de l'autre.
| 
| Si 14 n'avait pas été le plus grand diviseur commun, en divisant par lui, il serait resté de tels diviseurs, et alors le PGCD des versions divisées n'aurait pas été 1. Par exemple, si on s'était trompé et qu'on avait considéré 7 comme le PGCD, il serait resté $2 \times 3$ d'un côté et $2 \times 5$ de l'autre : le PGCD de ces deux nombres vaut 2 (ça se voit), et non 1.

Mais attendez, la probabilité que deux nombres aient un PGCD de 1… on l'a déjà nommée plus haut, c'est $p_1$ !

[^a-sur-k-entier]: $a/k$ est bien un entier, car on se place dans le cas où $k$ divise $a$ (sinon ça n'a pas d'intérêt, vu qu'on veut que les deux soient vrais en même temps).


## Revenons donc à ce qu'on cherchait…

Si on rassemble ces deux points, on peut donc affirmer que $p_k$, la probabilité que le PGCD de $a$ et $b$ vaille $k$, vaut le produit de ces deux valeurs trouvées, donc :

$$p_k = \frac{1}{k^2} \times p_1 = \frac{p_1}{k^2}$$

Or, on avait plus haut une relation avec $p_k$ ! Et si on essayait d'injecter cette nouvelle valeur ? On obtient : 

$$\sum\limits_{k = 1}^\infty p_k = p_1 + \frac{p_1}{2^2} + \frac{p_1}{3^2}+ \frac{p_1}{4^2} + \cdots = 1$$

Or $p_1$ est une constante, on peut donc factoriser pour la sortir de la somme :

$$p_1 \times \left(1 + \frac{1}{2^2} + \frac{1}{3^2}+ \frac{1}{4^2} + \cdots\right) = 1$$

Et donc en réorganisant :

$$p_1 = \frac{1}{1 + \frac{1}{2^2} + \frac{1}{3^2}+ \frac{1}{4^2} + \cdots} = \frac{1}{\sum\limits_{k = 1}^\infty \frac{1}{k^2}}$$

On avance ! Il ne nous reste plus qu'à déterminer ce mystérieux terme : la somme des inverses des carrés de tous les nombres entiers positifs non nuls… mais il se trouve que c'est un problème connu, le **[problème de Bâle](https://fr.wikipedia.org/wiki/Probl%C3%A8me_de_B%C3%A2le)**, résolu par Euler en 1741. Et il se trouve que justement… on y retrouve… π !

$$\sum\limits_{k = 1}^\infty \frac{1}{k^2} = \frac{\pi^2}{6}$$

De là, il est trivial de conclure que :

$$p_1 = \frac{1}{\pi^2 / 6} = \frac{6}{\pi^2}$$

Et *voilà*.

[[information|Point rigueur : les limites de cette démonstration]]
| Il y a une faiblesse dans cette démonstration : il n'existe pas de probabilité uniforme sur l'ensemble des entiers strictement positifs $\mathbb N^\star$. La démonstration ci-dessus est juste (avec quelques menus ajustements) si on considère qu'on calcule la probabilité $P_N$ d'avoir deux nombres premiers entre eux dans un ensemble fini $[1 ; N]$ ($N \in \mathbb N^\star$), et qu'on prend pour probabilité finale la limite de cette valeur quand $N$ tend vers l'infini :
|
| $$\lim\limits_{N \to \infty} P_N = \frac{6}{\pi^2}$$
|
| On peut justifier que prendre ainsi la limite a un sens en terme de probabilités, mais je ne l'ai absolument pas fait ici — faites-moi confiance, ou consultez d'autres preuves certes plus rigoureuses, mais bien moins accessibles.


# Une méthode efficace pour obtenir π ?

Alors oui, on _peut_ calculer π avec cette méthode, en tirant plein de nombres au dé… mais est-elle efficace ? En pratique, pas vraiment. Ou plutôt, **vraiment pas**.

Le problème, c'est que pour que ça fonctionne correctement, il faudrait pouvoir tirer des nombres sur _l'ensemble des nombres entiers positifs qui existent_, donc jusqu'à l'infini. Et l'infini, c'est grand.

Si on ne tire pas des nombres sur tout ça, la précision s'en ressent beaucoup (vraiment beaucoup). Avec un gros dé on tire entre quoi, un et deux-cent ? C'est ridiculement petit… et on obtient au mieux zéro ou une décimale. Et même avec le logiciel que j'ai écrit pour faire les tirages à ma place, en prenant le plus grand nombre possible facilement, un nombre à trente-huit chiffres tout de même[^u128-max], tellement grand qu'il est difficile de se l'imaginer — on est très, très loin de l'infini, et on peine à dépasser quatre ou cinq décimales.

Lorsqu'on calcule π avec une très grande précision, espérant des milliards de chiffres après la virgule, on utilise des méthodes très différentes et bien plus efficaces, donc on pourrait éventuellement parler s'il y a de l'intérêt parmi mes lecteurs. Mais ces méthodes n'ont pas la poésie de tirer π du hasard le plus total…

[^u128-max]: Pour ceux à qui ça parle, j'ai pris la valeur maximale d'un entier non-signé de 128 bits. Ce nombre vaut environ $3 \times 10^{38}$, ou exactement $340\ 282\ 366\ 920\ 938\ 463\ 463\ 374\ 607\ 431\ 768\ 211\ 455$.



[[information|Un peu plus de détails mathématiques pour les intéressé⋅e⋅s]]
| La valeur de la probabilité est juste, certes, c'est bien $6/\pi^2$. Mais le fait est que cette probabilité vaut $6/\pi^2$ *uniquement si on tire un nombre dans l'ensemble des entiers positifs non nuls* (cf. la formulation sous forme de limite plus haut, si vous connaissez cette notion).
| 
| Problème : **la convergence est extrêmement lente**. Il faut énormément augmenter la taille de l'échantillon pour avoir une précision de $6/\pi^2$ qui augmente _un peu_. Et quand ce n'est pas le cas, on peut toujours faire des centaine de milliards de tirages : la probabilité ne permet pas d'atteindre π, mais une valeur qui s'en approche.

------


J'aime beaucoup cette tendance de π à pointer le bout de son nez un peu partout en mathématiques sans vraiment qu'on s'y attende. Tel un discret ange gardien qui n'est jamais très loin, caché derrière un mur prêt à bondir dans tous les domaines des sciences…

![Un personnage un peu pipou et mignon, jaune et tout arrondi avec un sourire un peu espiègle, qui se cache derrière un mur et n'apparaît que partiellement.](blobpeek.png)
Figure: π, allégorie.

Le tirer du hasard est d'autant plus surprenant, c'est pourquoi j'avais envie d'en parler à l'occasion du _π–day_ de cette année. Cela dit, la démonstration ci-dessus pourrait vous laisser un peu… frustré⋅e. π semble arriver tel un cheveu sur la soupe qu'il faut accepter sans broncher, ce qui n'est, je l'admets, pas très satisfaisant.

Il existe une démonstration que je trouve très élégante et compréhensible du problème de Bâle, qui permet de très bien comprendre *d'où sort* ce π. On peut relier ce problème à un problème géométrique impliquant des cercles, et qui dit cercle… dit π ;) . La preuve est assez longue et ne sera pas traitée dans cet article — cela dit, une suite est prévue pour justement la présenter, et ainsi comprendre complètement comment on obtient π à partir du hasard :) .

[[i]]
| Les curieux anglophones et à l'aise avec les mathématiques pourront également consulter la sixième source dans le bloc masqué ci-dessous.

Cette méthode n'est pas la seule qui existe pour extraire π du hasard, sois dit en passant. Il existe notamment la [méthode de Monte-Carlo](https://fr.wikipedia.org/wiki/M%C3%A9thode_de_Monte-Carlo#D%C3%A9termination_de_la_valeur_de_%CF%80) qui permet d'estimer une valeur de $\pi/4$ (et donc par extension de π) assez simplement. J'ai préféré traiter le théorème de Cesàro car je le trouve plus amusant, mais c'est complètement subjectif.

*Je tiens à remercier Pifra pour ses conseils sur le traitement d'une partie de l'article, ainsi que @Aabu pour la relecture et validation de cet article dans des délais assez courts !*


[[secret|Sources, références, et crédits]]
| ## Sources et références pour aller plus loin
| 
| 1. Hardy, G. H., & Wright, E. M. (2007). *Introduction à la théorie des nombres*. Vuibert ; Springer.
| 1. [*Pi et les nombres premiers : $6/\pi^2$*](http://serge.mehl.free.fr/anx/prem_alea.html). (s. d.). Consulté 11 mars 2020.
| 1. [*Probability of Two Integers Being Coprime*](http://www.cut-the-knot.org/m/Probability/TwoCoprime.shtml). (s. d.). Consulté 11 mars 2020.
| 1. [*Probability that two random numbers are coprime is $\frac{6}{\pi^2}$*](https://math.stackexchange.com/questions/64498/probability-that-two-random-numbers-are-coprime-is-frac6-pi2). (s. d.). Mathematics Stack Exchange. Consulté 11 mars 2020.
| 1. [Problème de Bâle](https://fr.wikipedia.org/w/index.php?title=Probl%C3%A8me_de_B%C3%A2le&oldid=167674143). (2020). In *Wikipédia*.
| 1. Wastlund, J. (s. d.). [*Summing inverse squares by euclidean geometry*](http://www.math.chalmers.se/~wastlund/Cosmic.pdf). 10.
| 
| ## Crédits
|
| - L'allégorie de π, *blob peek*, est diffusée sous licence Apache 2 par Google / [blobs.gg](https://blobs.gg).
| - La bannière est un travail dérivé de *Dice* par [Flaticon / *Those Icons*](https://www.flaticon.com/free-icon/dices_2088804).