# RMarkdown basics

source: `{{ page.path }}`

* [RStudio Markdown Basics](https://rmarkdown.rstudio.com/authoring_basics.html)
* [tutorial here](https://ourcodingclub.github.io/tutorials/rmarkdown/), [homepage here](https://ourcodingclub.github.io/tutorials.html)
* [RMarkdown overview/references](https://rmarkdown.rstudio.com/docs/)
* [Bookdown - rmarkdown syntax](https://bookdown.org/yihui/rmarkdown/markdown-syntax.html)

**Italics**

Can be producted by either `_text1_` or `*text1*` which will look this *text1* or *text2*.

**Bold**

Produced using a pair of double asterisks `**text3**` or `__text4__` which will look like this **text3** or **text4**.

**Headers**

```
# Header 1
## Header 2
### Header 3
etc...
```

**Numbered list**

```
1. Item 1
2. Item 2
3. Item 3
    + part a
    + part b
```

1. Item 1
2. Item 2
3. Item 3
    + part a
    + part b

**Unnumbered list**

```
* Item 1
* Item 2
* Item 3
    + part a
    + part b
```

* Item 1
* Item 2
* Item 3
    + part a
    + part b



**Script**

A pair of tildes (`~`) turn text to a subscript (e.g., `H~3~PO~4~` renders H~3~PO~4~).
A pair of carets (`^`) produce a superscript (e.g., `Cu^2+^` renders Cu^2+^).
To get strike through `~~strike~~` renders to this ~~strike~~

**Images**

```
![](http://example.com/logo.png)
![optional caption text](figures/img.png)
```

**Hyperlinks**

```
http://example.com
[linked phrase](http://example.com)
```

**Horizontal rule**

Three or more asterisks or dashes `***` or `---`

**Tables**

```
First Header  | Second Header
------------- | -------------
Content Cell  | Content Cell
Content Cell  | Content Cell
```


### Math and symbols

[Math in RMarkdown](https://www.calvin.edu/~rpruim/courses/s341/S17/from-class/MathinRmd.html)

`$x = y $` $x = y $
`$x < y $` $x < y $
`$x \le y $` $x \le y $
`$x^{n}$` $x^{n}$
`$\hat{x}$` $\hat{x}$
`$\tilde{x}$` $\tilde{x}$
`$\frac{a}{b}$` $\frac{a}{b}$
`$\mu M$` $\mu M$
`$\alpha A$` $\alpha A$
`$\beta B$` $\beta B$
`$\pi \Pi$` $\pi \Pi$
`$^\circ C$` $^\circ C$

## Code chunks & output

[here](https://bookdown.org/yihui/rmarkdown-cookbook/hide-one.html)

## Text colour

Below are some useful bits of code that you can use to change font. For basic Rmd syntax see offical [Reference Guide](https://rstudio.com/wp-content/uploads/2015/03/rmarkdown-reference.pdf?_ga=2.203245073.1802232962.1587452707-209816525.1575608236).

It is also handy to have colour guides/convertors at the ready, checkout the my section on colour in [Plot Aesthetics & Colour](https://siobhon-egan.github.io/bioinfo-phylo/rstudio-aesthetics.html#colour).

### For `Rmd` -> `PDF` docs

**Font colour**

The quickest option is this `\textcolor{olive}{This text is olive}`. It will look like this "<span style="color: olive;">This text is olive</span>" in your PDF document.


If you want a more customisable option you can use the following to first choose your font colour, and then apply it.
Define text colour (this won't appear in your Knitted PDF)
```
\definecolor{fancyTextColor}{HTML}{FF0000}
```

Then use the following syntax to change font colour `\colorbox{hightlightColor}{This text is red}` It will look like this "<span style="color: red;">This text is red</span>" in your PDF document.

### For `Rmd` -> `html` docs

**Font colour and text**

the following html code
```
Roses are <span style="color:red; font-family:Georgia; font-size:2em;">red.</span>
```
Will give you this output

> Roses are <span style="color:red; font-family:Georgia; font-size:2em;">red.</span>

**For coloured text blocks.**
```
<style>
div.blue { background-color:#e6f0ff; border-radius: 5px; padding: 20px;}
</style>
<div class = "blue">

- This is my first conclusion
- This is my second conclusion

</div>
```
<style>
div.blue { background-color:#e6f0ff; border-radius: 5px; padding: 20px;}
</style>
<div class = "blue">

- This is my first conclusion
- This is my second conclusion

</div>

[Custom Fonts in R Markdown PDF](https://community.rstudio.com/t/custom-fonts-in-rmarkdown-pdf/2098)
[Font Formatting - coloring and emphasis](https://edpflager.com/?p=4002)

## Hyperlinks

**Underlink links in `PDF` documents**
When you knit a document to PDF the hyperlinks are not underlined or colour, although they still work just fine.
If you prefer to have your hyperlinks underlined as the following to the header section
```
header-includes:
  - \hypersetup{colorlinks=false,
            allbordercolors={0 0 0},
            pdfborderstyle={/S/U/W 1}}
```

Another way is to use the following latex command, however this does not knit well to html.
`[\underline{R Markdown: The Definitive Guide}](https://bookdown.org/yihui/rmarkdown/)` will give the following: [R Markdown: The Definitive Guide](https://bookdown.org/yihui/rmarkdown/)

## Images, Figures and videos

[Tips and tricks for working with images and figures in R Markdown documents](http://zevross.com/blog/2017/06/19/tips-and-tricks-for-working-with-images-and-figures-in-r-markdown-documents/).

Simple add for image
```
![image caption](path/to/image.png)
```

### Videos

**Embed video**

`vebmedr` is a package that makes embedding video into Rmarkdown simple.

Install the package from CRAN
```
install.packages("vembedr")
```
*Example*
```{r}
library("htmltools")
library("vembedr")
```

```{r}
embed_url("https://www.youtube.com/watch?v=uV4UpCq2azs")
```


## Fun stuff

### emojis

You can add emojis into Rmarkdown html docs with the following code: `:bowtie:` which will give you this :bowtie:
A full list of emoji short cuts available [here](https://www.webfx.com/tools/emoji-cheat-sheet/).

You could also use unicode formatting - see [here](https://apps.timwhitlock.info/emoji/tables/unicode) for more info.

You can also use emojis in plotting, see [here](https://cran.r-project.org/web/packages/emojifont/vignettes/emojifont.html).

### Icons

Depending on the type of RMarkdown document you are working with (i.e. what are you "knitting" to), will depend on which code works for you. As always there is more than one way to this.

To start with the most commonly used icons are from `font awesome` suite - so [head here](https://fontawesome.com/icons?d=gallery&m=free) to pick your (*free*) icons.

**HTML docs**

<script src="https://unpkg.com/ionicons@5.0.0/dist/ionicons.js"></script>

For HTML docs (including webpages), I have found the following works best `<i class="fab fa-r-project"></i>` this will give you a beautiful RStudio icon <i class="fab fa-r-project"></i>.

If you want to use [`Ionicons`](https://ionicons.com/) then include you will first need to make sure the following line appears within your Rmarkdown doc (don't worry it wont appear in the knitted product) `<script src="https://unpkg.com/ionicons@5.0.0/dist/ionicons.js"></script>`. Then use the following code to insert your icons, for example this `<ion-icon name="bug-outline"></ion-icon>` produces a lovely bug for you <ion-icon name="bug"></ion-icon>. You can customise the icons, [see here](https://ionicons.com/usage).

This code `<span class="badge badge-info">Info</span>` will produce this badge <span class="badge badge-info">Info</span> in html document, more details found [here](https://getbootstrap.com/docs/4.0/components/badge/)


**Webpages (HTML) - nav bar**

You can add icons to the nav bar on your webpage, just like on this one.
In the YAML doc add the following bit of code under the relevent section `icon: fa-icon` e.g. for the rstudio icon use `fa-r-project` for this icon <i class="fab fa-r-project"></i>

*Example* - partial YAML doc, for more info on RMarkdown webpages/YAML head to [RMarkdown Webpages](https://siobhon-egan.github.io/bioinfo-phylo/rmd-webpages.html) section
```
navbar:
  title: "Code"
  left:
  - text: "Home"
    href: index.html
  - text: "RStudio"
    icon: fa-file-alt
```

**PDF docs**

When knitting to PDF I have found the easiest way using the [`icon` package](https://github.com/ropenscilabs/icon).

Install developer version from github
```
# install.packages("devtools")
devtools::install_github("ropenscilabs/icon")
```
Then add the following bit of code in your RMarkdown document.
```{r}
library(icon)
icon::fa("rocket") # equivalent to icon::fa_rocket()
```

and you'll get this <i class="fas fa-rocket"></i>. Got some extra tips and trick [see here](https://slides.mitchelloharawild.com/icon/#1).

Some more info on `icon` available [here](https://ropensci.org/technotes/2018/05/15/icon/) and [here](https://slides.mitchelloharawild.com/icon/#1).

### Buttons

The [`downloadthis`](https://github.com/fmmattioni/downloadthis) package is to implement download buttons in HTML outputs from RMarkdown without need for `runtime::shiny`

Install
```
install.packages("downloadthis")
```

Then add the following to your Rmarkdown document - this example will give you a red download button with a link to the `downloadthis` pdf manual (remember to hide the code so only the output appears using `{r echo=FALSE}` at the start of your code chunk).

```{r}
library(downloadthis)
download_link(
  link = "https://github.com/fmmattioni/downloadthis/raw/master/inst/example/file_1.pdf",
  button_label = "Download pdf file",
  button_type = "danger",
  has_icon = TRUE,
  icon = "fa fa-save",
  self_contained = FALSE
)
```

This code words when knitting to HTML, that opens a link when you click on it
```
<article>
<h3><a href="https://www.researchgate.net/publication/327174678_What's_in_a_tick_Meta-analysis_of_microbial_diversity_in_Australian_ticks">What’s in a tick? Meta-analysis of microbial diversity in Australian ticks</a></h3>
<div class="summary">
<span><i class="fa fa-calendar"></i> _2018-08_</span>
<p>Global Microbiome II 2018 (West Coast Microbiome Network) | Perth, Western Australia</p>
<a class="btn btn-outline-primary btn-sm" href="https://www.researchgate.net/publication/327174678_What's_in_a_tick_Meta-analysis_of_microbial_diversity_in_Australian_ticks" role="button">Poster</a>
</div>
```


### Diagram

[diagrams](https://mikeyharper.uk/flowcharts-in-r-using-diagrammer/)


## Table

In additional to using basic RMarkdown syntax for tables

```
First Header  | Second Header
------------- | -------------
Content Cell  | Content Cell
Content Cell  | Content Cell
```
Which look like this

First Header  | Second Header
------------- | -------------
Content Cell  | Content Cell
Content Cell  | Content Cell


You can use [KableExtra](http://haozhu233.github.io/kableExtra/awesome_table_in_html.html)

## Themes

[RMarkdown theme gallery](https://www.datadreaming.org/post/r-markdown-theme-gallery/)

## Headings and navigation

[bookdown](https://bookdown.org/yihui/rmarkdown/html-document.html) includes tabbed sections

This code here will created heading with tabbed sections:
```
### Quarterly Results {.tabset}

#### By Product

Content on tabbed section 1 here

#### By Region

Maybe insert a short list here:

* item 1
* item 2
* item 3
```
It will look like this:

### Quarterly Results {.tabset}

#### By Product

Content on tabbed section 1 here

#### By Region

Maybe insert a short list here:

* item 1
* item 2
* item 3

## Headings

In addition to info in the Rmarkdown page some extra bits.

Add sections to the book using the following at the start of a RMarkdown page

```
# (PART) Section A {-}

# Page 1
```

This will section will appear until it recognises another section.
