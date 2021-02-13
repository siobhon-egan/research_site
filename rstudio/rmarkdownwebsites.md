# RMarkdown and websites

source: `{{ page.path }}`

:link: Documentation on authoring webpages using RMarkdown and Github (to host the site)

* [Chapter 10 Websites](https://bookdown.org/yihui/rmarkdown/websites.html) from [R Markdown: The Definitive Guide](https://bookdown.org/yihui/rmarkdown/)
* [Happy Git and GitHub for the useR](https://happygitwithr.com/)
* Great tutorial to follow on getting started with [GitHub and RStudio](https://resources.github.com/whitepapers/github-and-rstudio/)
* Offical [R Markdown Websites](https://rmarkdown.rstudio.com/lesson-13.html) lesson from RStudio
* An [R Markdown Website Template](https://github.com/yutannihilation/rmarkdown-website-template) available here

:link: Other helpful resources

* [workflowr package](https://jdblischak.github.io/workflowr/), [tutorial here](https://cran.r-project.org/web/packages/workflowr/vignettes/wflow-01-getting-started.html), [example here](https://stephenslab.github.io/wflow-divvy/index.html)
* [Useful workflow](https://robertmitchellv.com/blog-building-site-with-rmarkdown.html)
* [Distill](https://rstudio.github.io/distill/)
* [tutorial](https://robchavez.github.io/datascience_gallery/html_only/websites.html)
* [Awesome blogdown](https://awesome-blogdown.com/)


# YAML

Example `_site.yml` doc


```
name: "Bioinformatics & Phylogenetics"
output_dir: "docs"
navbar:
  title: "Code"
  left:
  - text: "Home"
    href: index.html
  - text: "RStudio"
    icon: fa-file-alt
    menu:
      - text: Introduction
        href: rstudio-intro.html
      - text: "---------"
      - text: "Plots & data"
      - text: Aesthetics
        href: rstudio-aesthetics.html
      - text: Plots
        href: rstudio-plots.html
      - text: Statistics
        href: rstudio-statistics.html
      - text: "---------"
      - text: "RMarkdown"
      - text: Introduction
        href: rmd-intro.html
      - text: Bookdown
        href: rmd-bookdown.html
      - text: Websites
        href: rmd-webpages.html
  - text: "Sequence files"
    icon: fa-dna
    menu:
      - text: Command line
        href: sequence-files.html
      - text: Visualising and editing
        href: visualise.html
      - text: "Muscle"
        href: muscle.html
  - text: "Phylogenetics"
    icon: fa-code-branch
    menu:
      - text: "Introduction"
        href: phylo-intro.html
      - text: "Evolutionary models"
        href: evolutionary-models.html
      - text: "IQ-TREE"
        href: iqtree.html
      - text: "MrBayes"
        href: mrbayes.html
output:
  html_document:
    theme: yeti
    highlight: monochrome
    include:
      after_body: footer.html
```


**Icons for webpages**

[A blog here](https://www.r-bloggers.com/icon-web-icons-for-rmarkdown/)

[Font Awesome icons](https://fontawesome.com/)

## Themes

If using the `Simple R Markdown website` option to create a website then the default available themes options include:
“cerulean”, “cosmo”, “cyborg”, “darkly”, “flatly”, “journal”, “lumen”, “paper”, “readable”, “sandstone”, “simplex”, “slate”, “spacelab”, “superhero”, “united”, “yeti”...check them out [here](https://bootswatch.com/).
Highlight options include:
“default”, “tango”, “pygments”, “kate”, “monochrome”, “espresso”, “zenburn”, “haddock”, “breezedark”, “textmate”.

[Overiew here](https://www.datadreaming.org/post/r-markdown-theme-gallery/)

They can be changed by including the following in the 'YAML'
```
output:
  html_document:
    theme: united
    highlight: monochrome
```

### Bootswatch

[Library here](https://bootswatch.com/)

[Bootstraplibs](https://rstudio.github.io/bootstraplib/)

```
remotes::install_github("rstudio/bootstraplib")
library(bootstraplib)
```
To start using bootstraplib in your rmarkdown::html_documents, install the following:
```
remotes::install_github("rstudio/rmarkdown#1706")
```

Use `bootstrap_version` and `theme` to choose the Bootstrap version and a Bootswatch theme. These arguments are currently supported only in `html_document` and `html_document_base`.
```
---
output:
  html_document:
    bootstrap_version: 4+3
    theme: minty
---
```

You can also add theme customizations inside any R code chunk (these customizations end up influencing the Bootstrap CSS included in the output document).

```
library(bootstraplib)
bs_theme_accent_colors(primary = 'green')
```

Some extra info [here](https://community.rstudio.com/t/in-rstudio-rmarkdown-how-to-add-new-html-themes-from-bootswatch/15791)

### Extra

Get extra bits of html from the bootswatch theme webpages. E.g. [minty](https://bootswatch.com/minty/)

## Footers

You can add footers to your webpages.
Add a `footer.html` file to your directory and insert the following.

```
&nbsp;
<hr />
<p style="text-align: center;">Work by <a href="https://github.com/siobhon-egan">Siobhon Egan</a></p>
<p style="text-align: center;"><span style="color: #808080;"><em>siobhon.egan@murdoch.edu.au</em></span></p>

<!-- Add icon library -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">

<!-- Add font awesome icons -->
<p style="text-align: center;">
    <a href="https://siobhon-egan.github.io/" class="fas fa-home"></a>
    <a href="https://www.researchgate.net/profile/Siobhon_Egan" class="fab fa-researchgate"></a>
    <a href="https://github.com/siobhon-egan" class="fa fa-github"></a>
</p>

&nbsp;
```

Edit your YAML to include the following
```
output:
 html_document:
    theme: united
    include:
      after_body: footer.html
```

For a more simple footer, use the following
```
<p> <font size="2"><font color="purple">Copyright &copy; 2020 Siobhon Egan. </font></font> </p>
```

## Bootstrap customisation

Further HTML customisation with the bootstrap theme available [here](https://getbootstrap.com/docs/4.5/components/alerts/)

***

## Blogdown

Another option of creating a website in RStudio is using Blogdown.

Useful resources and examples

* [Chi Zhang](https://andreaczhang.rbind.io/post/my-1st-blogpost/)
* [John R Little](https://www.johnlittle.info/)
* [Rob Hyndman](https://robjhyndman.com)
