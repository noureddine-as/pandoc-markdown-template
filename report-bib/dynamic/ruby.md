---
title: "Example Title"
date: \today{}
author: "Maxwell Ogden, Karissa McKelvey, Mathias Buus Madsen, Code for Science"

papersize: a4paper

header-includes:
  - \hypersetup{colorlinks=true,
            allbordercolors={0 0 0},
            pdfborderstyle={/S/U/W 0}}

linkcolor: blue

bibliography: biblio.bib

csl: ieee.csl
---

\newpage

<!-- \chapter{Dynamic languages}
 -->
## Ruby
Ruby is a dynamic, reflective, object-oriented, general-purpose programming
language [@item1].

### Code examples
Some simple code examples [-@item1].

#### Hello World

```ruby
puts "Hello World!"
```

An example of a figure

![My caption here.](images/3dprinter.png){#fig:description width=50%}

And then you can reference it just here Figure @fig:description.

And this is an example of an equation:

$$ y = mx + b $$ {#eq:label-of-the-eq}

Here you can reference the equation @eq:label-of-the-eq.


You can refer to a venue using ^[@asplos] or ^[@ase].

