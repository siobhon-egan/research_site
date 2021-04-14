---
sort: 2
---

# RStudio

source: `{{ page.path }}`

{% include list.liquid all=true %}


<i class="fab fa-r-project"></i> is a programming language that is especially powerful for data exploration, visualization, and statistical analysis. ["`R`"](http://www.r-project.org/) is also a software that interprets the scipts written using it. The most popular way to interact with R is by using [RStudio](http://www.rstudio.com/). To get started you need to install R and RStudio on your computer.

In addition to being able to do all your statistics and graphing R/RStudio is a holds a work of opportunities, it is a never-ending tool that is constantly being updated. Before we know it R will be able to cook your dinner and go to the shops too! But for now check out its great range of features for project management. It can talk all types of coding languages, and is useful to keep track of exactly what you are doing (RMarkdown). You can even make your own webpage to help keep track of all that code and information, just like I am doing here!

:link: Some links to get you started:

- [R markdown](https://rmarkdown.rstudio.com/lesson-1.html)
- [R shiny](https://shiny.rstudio.com/)
- [R project for statistical computing](https://www.r-project.org/)
- [Project management with RStudio](https://swcarpentry.github.io/r-novice-gapminder/02-project-intro/)
- [R bookdown](https://bookdown.org/)

## An extra note

<style>
div.blue { background-color:#db9671; border-radius: 5px; padding: 20px;}
</style>
<div class = "blue">

As a general rule these pages on RStudio are not meant as a stand alone tutorial/workflow to learn coding.
Generally they includes lots of links to people who have done the hard work, and I just have a small subset of code that is relevant to my workflow or some common code chunks I use.
So please read on with caution - mostly this is just a place for me to collate <i><b>highly</b></i> websites/tutorials/information that I have found useful during my research in one central location.
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


![*RStudio interface*](../images/rstudio.png)


1. Source pane - for your scripts and document
2. Environment/history - lists all your variables loaded
3. Files/Plots/Helper etc - here you can navigate to find (and upload) files, this is where your plots will appear when you view them, and its also here any `?help` info will appear
4. Console - this is running document of what code you have executed.

Need further convincing to user R...[read on](https://datacarpentry.org/R-ecology-lesson/00-before-we-start.html)

***

## Install (& updates) {#install}


### Windows {#windows}

If you already have R and RStudio installed:

* Open RStudio, and click on “Help” > “Check for updates”. If a new version is available, quit RStudio, and download the latest version for RStudio.
* To check which version of R you are using, start RStudio and the first thing that appears in the console indicates the version of R you are running. Alternatively, you can type `sessionInfo()`, which will also display which version of R you are running. Go on the [CRAN website](https://cran.r-project.org/bin/windows/base/) and check whether a more recent version is available. If so, please download and install it. You can [check here](https://cran.r-project.org/bin/windows/base/rw-FAQ.html#How-do-I-UNinstall-R_003f) for more information on how to remove old versions from your system if you wish to do so.

If you don’t have R and RStudio installed:

* Download R from the [CRAN website](http://cran.r-project.org/bin/windows/base/release.htm.
* Run the `.exe` file that was just downloaded
* Go to the [RStudio download page](https://www.rstudio.com/products/rstudio/download/#download)
* Under *Installers* select **RStudio x.yy.zzz - Windows Vista/7/8/10** (where x, y, and z represent version numbers)
* Double click the file to install it
* Once it’s installed, open RStudio to make sure it works and you don’t get any error messages.

[Video Tutorial](https://www.youtube.com/watch?v=q0PjTAylwoU)

### MacOS {#macos}

If you already have R and RStudio installed:

* Open RStudio, and click on “Help” > “Check for updates”. If a new version is available, quit RStudio, and download the latest version for RStudio.
* To check the version of R you are using, start RStudio and the first thing that appears on the terminal indicates the version of R you are running. Alternatively, you can type `sessionInfo()`, which will also display which version of R you are running. Go on the [CRAN website](https://cran.r-project.org/bin/macosx/) and check whether a more recent version is available. If so, please download and install it.

If you don’t have R and RStudio installed:

* Download R from the [CRAN website](http://cran.r-project.org/bin/macosx/).
* Select the `.pkg` file for the latest R version
* Double click on the downloaded file to install R
* It is also a good idea to install [XQuartz](https://www.xquartz.org/) (needed by some packages)
* Go to the [RStudio download page](https://www.rstudio.com/products/rstudio/download/#download)
* Under Installers select **RStudio x.yy.zzz - Mac OS X 10.6+ (64-bit)** (where x, y, and z represent version numbers)
* Double click the file to install RStudio
* Once it’s installed, open RStudio to make sure it works and you don’t get any error messages.

[Video Tutorial](https://www.youtube.com/watch?v=5-ly3kyxwEg)

## Packages {#packages}

No matter what you use RStudio for you'll need to install some packages. Think of these as like add ins, there are loads out there. If they are available on [CRAN](https://cran.r-project.org/web/packages/available_packages_by_name.html) you can install using `install.packages("package")`, if not on CRAN most will be downloading using `devtools::install_github("package/repo")`, just make sure you `install.packages("devtools")` first. You only need to install once so usually do this by typing straight into the `Console` and then you will need to load your packages using `library(package)`, you can save the R environment so when you reopen it should be there but its a good idea to ensure you always load libraries you will need at the start of the session.

:link: Here's some good places to start find packages:

* [CRAN](https://cran.r-project.org/web/packages/available_packages_by_name.html)
* [ROpenSci](https://ropensci.org/packages/)
* [RStudio packages homepage](https://rstudio.com/products/rpackages/)
* [Rstudio quick list of useful packages](https://support.rstudio.com/hc/en-us/articles/201057987-Quick-list-of-useful-R-packages)

## Project Management and R for Research


* [R for reproducible research](https://annakrystalli.me/rrresearch/)
* [workflowr](https://jdblischak.github.io/workflowr/)
* [Reproducible research data and project management in R](https://annakrystalli.me/rrresearchACCE20/)
* [Reproducible research with rrtools](https://annakrystalli.me/rrtools-repro-research/index.html)

## R for Research

* [R for Research by Abhay Singh](https://singh1985.github.io/RforResearch/)
* [R for Data Science by Hadley Wickham and Garrett Grolemund](https://r4ds.had.co.nz/) and [here](http://www.rforresearch.com/r-for-research-the-course)
