# Tidy data and research links

source: `{{ page.path }}`

<i class="fab fa-r-project"></i> is a programming language that is especially powerful for data exploration, visualization, and statistical analysis. ["`R`"](http://www.r-project.org/) is also a software that interprets the scipts written using it. The most popular way to interact with R is by using [RStudio](http://www.rstudio.com/). To get started you need to install R and RStudio on your computer.


## An extra note

<style>
div.blue { background-color:#db9671; border-radius: 5px; padding: 20px;}
</style>
<div class = "blue">

As a general rule these pages on RStudio are not meant as a stand alone tutorial/workflow to learn coding.
Generally they includes lots of links to people who have done the hard work, and I just have a small subset of code that is relevant to my workflow or some common code chunks I use.
So please read on with caution - mostly this is just a place for me to collate *some* websites/tutorials/information that I have found useful during my research in one central location.
</div>

## Learning R links

* [Data Visualization class by Andrew Heiss](https://datavizm20.classes.andrewheiss.com/), [github link](https://github.com/andrewheiss/datavizm20.classes.andrewheiss.com)
* [Tidymodels](https://www.tidymodels.org/), [github](https://github.com/tidymodels/tidymodels.org)
* [Stat 431 by Kelly Bodwin and Hunter Glanz](https://cal-poly-advanced-r.github.io/STAT-431/)
* [Ready  for R by Ted Laderas](https://ready4r.netlify.app/)
* [Data science heros](https://livebook.datascienceheroes.com/)
* [R weekly](https://rweekly.org/)
    - [An R View into Epidemiology](https://rviews.rstudio.com/2020/05/20/some-r-resources-for-epidemiology/)
    - [R Open data](https://ropensci.org/blog/2020/05/19/covid-19-open-data/)
    - [Reproducible research in R](https://annakrystalli.me/rrresearchACCE20/)



## Tidy data

Keeping data tuidy and record keeping is essential for science.

I recommend some useful links to get you started.

- [R for data science, by Wickham and Grolemund](https://r4ds.had.co.nz/)
- [R for Reproducible Scientific Analysis, by software carpentry](http://swcarpentry.github.io/r-novice-gapminder/)
- [Tidyverse](https://www.tidyverse.org/)
- [Data carpentry](https://datacarpentry.org/)

## Must haves

:link: When making your plots there are two **must haves** you need to bookmark:

* [ggplot2 book](https://ggplot2-book.org/index.html)
* [ggplot2 as part of the tidyverse packages](https://ggplot2.tidyverse.org/)
* [R graph gallery](https://www.r-graph-gallery.com/)
* [R for data science](https://r4ds.had.co.nz/)
* [Interactive data viz in R - plotly and shiny](https://plotly-r.com/index.html)
* [Plotly in ggplot2](https://plotly.com/ggplot2/getting-started/)
* [Interactive web-based data visualization with R, plotly, and shiny Carson Sievert](https://plotly-r.com/index.html)
* [ggplot2 extension](https://exts.ggplot2.tidyverse.org/gallery/)
* [esquisse](https://dreamrs.github.io/esquisse/index.html)

Useful resources for data analysis/visualization in RStudio

* [STAT545](https://stat545.com/)
* [Data carpentry for biologists](https://datacarpentry.org/semester-biology/)
* [DATA 598](https://canvas.uw.edu/courses/1354201)
* [ESM 206](https://allisonhorst.github.io/)
* [RStudio essentials](https://rstudio.com/collections/rstudio-essentials/)
* [RStudio education](https://github.com/rstudio/education.rstudio.com)
* [Open scapes](https://www.openscapes.org/resources/)
* [RStudio education learn tidyverse](https://tourmaline.netlify.app/learn/)
* [Data challenge lab](https://dcl-2017-04.github.io/curriculum/)
* [STA199](http://www2.stat.duke.edu/courses/Spring18/Sta199/)
* [learn - r for data science](https://github.com/rstudio/hugo-tourmaline/blob/master/exampleSite/content/learn/index.md)

## Specific packages and tutorials

[sangeranalyseR](https://sangeranalyser-documentation.readthedocs.io/en/latest/)

## Figures

Figures are an important part of any publication. They are often the first thing readers look at and will help usually are the deciders as to whether non-specialists are going to read on...a good figure goes a long way! If you can spend the time it is well worth it (*within reason of course*).
A good read on some do and don'ts for figures by [Rougier et al. 2014 PLOS comp biol](https://doi.org/10.1371/journal.pcbi.1003833), while your at it check out this one by [Mensh and Kording 2017](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1005619).


:link: I don't see the need to reinvent the wheel so see some useful pages:

* [`ggplot2` reference](https://ggplot2.tidyverse.org/reference/index.html)
* [STHDA](http://www.sthda.com/english/wiki/ggplot2-colors-how-to-change-colors-automatically-and-manually)
* [Selva Prabhakaran](http://r-statistics.co/Top50-Ggplot2-Visualizations-MasterList-R-Code.html)


## Colour

:link: Handy links for colour

* [GeoDataViz Toolkit](https://github.com/OrdnanceSurvey/GeoDataViz-Toolkit/tree/master/Colours)
* [Your Friendly Guide to Colors in Data Visualisation](https://blog.datawrapper.de/colorguide/) by Lisa Charlotte Rost
* [Colorbrewer2](https://colorbrewer2.org/#type=sequential&scheme=BuGn&n=3)
* [Color-hex](https://www.color-hex.com/)
* [Coloring for colorblindness](https://davidmathlogic.com/colorblind/#%23D81B60-%231E88E5-%23FFC107-%23004D40)
* [Viz palette](https://projects.susielu.com/viz-palette) - love this resource!
* [CSS Colours](https://www.w3schools.com/cssref/css_colors.asp)
* [HTML colour names](https://www.w3schools.com/colors/colors_names.asp)
* [HTML colour codes](https://htmlcolorcodes.com/)

One of my favourite colour palettes at the moment is [Viridis](https://cran.r-project.org/web/packages/viridis/vignettes/intro-to-viridis.html)

```
install.packages("viridis")
library(viridis)
```

Usage of this palette with various ggplots [here](https://ggplot2.tidyverse.org/reference/scale_viridis.html)
