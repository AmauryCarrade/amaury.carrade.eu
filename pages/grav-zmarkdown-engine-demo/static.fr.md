---
title: 'zmarkdown-engine demo'
homepage:
    invite: 'The zmarkdown engine inside Grav?'
---

[[i]]
| This is a demo of the `zmarkdown` engine being used in a Grav website, *via* the [zmarkdown engine plugin](https://github.com/AmauryCarrade/grav-plugin-zmarkdown-engine). Everything in this page is written in pure-Markdown, without any shortcode.
|
| You can see other demos (and capabilities—did you know `zmarkdown` can also export in LaTeX and epub?) in the [project's demo page](https://zestedesavoir.github.io/zmarkdown/) and [in its repository](https://github.com/zestedesavoir/zmarkdown).


This is my first paragraph.

This is my second ~~paraf~~ paragraph.
I'm on a new line, but this is still on the same paragraph—you need to add _two spaces_ to **force** a line break.  
Here I do.

# Level 1 title

## Level 2 title

### Level 3 title

#### Level 4 title

-> This is centered. <-

-> This is left-aligned. ->

2^10^ is 1024.

Water molecule is H~2~O.

- What about a ;
- list ;
- with small little dots or hyphens?

Hum what does I need…

- [ ] Pâtes
- [ ] Œufs
- [ ] Riz
- [x] Thé

1. First.
2. Second.
3. Third.

- Oh, a list ;
- with ;
    - sub-lists ;
- inside... (see that? [typography](https://practicaltypography.com "Practical Typography")!)

Name     |   Age
------|-----
Fred |   39
Sam |   38
Alice  |   35
Mathilde  | 35
Table: Ages table


+-------+----------+------+
| Table Headings   | Here |
+-------+----------+------+
| Sub   | Headings | Too  |
+=======+==========+======+
| cell  | column spanning |
+ spans +----------+------+
| rows  | normal   | cell |
+-------+----------+------+
| multi | cells can be    |
| line  | *formatted*     |
|       | **paragraphs**  |
| cells |                 |
| too   |                 |
+-------+-----------------+
Table: You can do complex tables in pure Markdown! Bonus tips if you love ASCII art.


------


$$a \cdot x^2 + b \cdot x + c = 0 \quad \Longrightarrow \quad x = \frac {-b \pm \sqrt{b^2 - 4ac}}{2a}$$

You can also inline formulas: $a \cdot x^2 + b \cdot x + c = 0$ with a single `$` sign before and after. This is using [KaTeX](https://katex.org) under the hood: fully server-side rendered, blazing fast to display!

## Tech and source codes

```
#!/usr/bin/env python3

print("Hello, World!")
```

With highlighting :

```python
#!/usr/bin/env python3

print("Hello, World!")
```

Oh and you can highlight specific lines, useful to point out at something!

```perl hl_lines="1 4-6"
use strict;
use warnings;

print "Comment vous appelez-vous ? ";
my $nom = <>; # Récupération du nom de l'utilisateur
chomp $nom;   # Retrait du saut de ligne
print "Bonjour, $nom !\n";
```

![Logo Creative Commons](http://mirrors.creativecommons.org/presskit/logos/cc.logo.png)

!(http://www.youtube.com/watch?v=oavMtUWDBTM)

Use ||Ctrl|| + ||C|| to copy.


[[information]]
| This is an info box.
|
| Cool, uh?

[[i|Quid?]]
| With title!

[[q|Quid??]]
| Questions too!

[[a|Quid???]]
| Warnings too!

[[e|Quid???]]
| Errors too!

[[n|This is why]]
| Neutral blocks too (for theorems, highlights, …).

[[s|What's in it?]]
| Secret blocks too! Boo

> Ceci est une citation… 
> sur plusieurs lignes
Source: Citez vos sources !


[[neutre | Théorème de Pythagore]]
| Un triangle ABC est rectangle en a si et seulement si $AB^2 + AC^2 = BC^2$

Welcome on ZdS !

*[ZdS]: Zeste de Savoir

Markdown[^mdown] is a light syntax to edit documents. Pandoc[^pandoc] is a documents converter.

[^mdown]: More on [Markdown](http://daringfireball.net/projects/markdown/).

[^pandoc]: More on [Pandoc](http://johnmacfarlane.net/pandoc/).
