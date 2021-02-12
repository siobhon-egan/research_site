# RMarkdown docs

source: `{{ page.path }}`


:link: Lets start with some of my favourite essential resources

* [R Markdown: The Definitive Guide](https://bookdown.org/yihui/rmarkdown/) by Yihui Xie, J. J. Allaire, Garrett Grolemund.
* [R Markdown Cookbook](https://bookdown.org/yihui/rmarkdown-cookbook/) by Yihui Xie and Christophe Dervieux
* [Pimp by RMD: a few tips for R Markdown](https://holtzy.github.io/Pimp-my-rmd/) by Yan Holtz.
* [Reference Guide](https://rstudio.com/wp-content/uploads/2015/03/rmarkdown-reference.pdf?_ga=2.203245073.1802232962.1587452707-209816525.1575608236)
* [R Markdown Cheat Sheet](https://github.com/rstudio/cheatsheets/raw/master/rmarkdown-2.0.pdf)
* [R Markdown formats - R for data science](https://r4ds.had.co.nz/r-markdown-formats.html)
* [RMarkdown overview/references](https://rmarkdown.rstudio.com/docs/)
* [pagedown](https://rstudio.github.io/pagedown/#pagedjs)
* [Creating Dynamic Documents with RMarkdown and Knitr](https://rpubs.com/ivim/Rmd-v1)
* [Creating Dynamic Documents with RMarkdown and Knitr](https://rstudio-pubs-static.s3.amazonaws.com/180546_e2d5bf84795745ebb5cd3be3dab71fca.html#71_code_folding)
* [Pandoc markdown](https://rmarkdown.rstudio.com/authoring_pandoc_markdown.html%23raw-tex#Pandoc_Markdown)
* [BIMS8382 Reproducible reporting with Rmarkdown](https://bioconnector.github.io/workshops/r-rmarkdown.html)
* Ulrik Lyngs
      - [RMarkdown workshop 2019 day 1 slide](https://ulyngs.github.io/rmarkdown-workshop-2019/slides/Day1.html#1)
     - [Github repo for workshop](https://github.com/ulyngs/rmarkdown-workshop-2019)
* [From raw data to paper and presentation, by Eva Mae Rey](https://github.com/EvaMaeRey/from_raw_data_to_paper_and_presentation)
* Steven V. Miller
    - [article example](https://github.com/svmiller/svm-r-markdown-templates/tree/master/article-example)
    - [course website](https://github.com/svmiller/course-website)
    - [RMarkdown CV](http://svmiller.com/blog/2016/03/svm-r-markdown-cv/),
    - [RMarkdown syllabus](http://svmiller.com/blog/2016/07/r-markdown-syllabus/)
* Lucy McGown
    - [website](https://www.lucymcgowan.com/)
    - [disseration toolkit](https://github.com/LucyMcGowan/dissertation-toolkit/tree/master/thesis)
* [RMarkdown Template that Manages Academic Affiliations, by Lab-R-torian](https://labrtorian.com/2019/08/26/rmarkdown-template-that-manages-academic-affiliations/)
* Robert Mitchell, [GitHub repo](https://github.com/robertmitchellv/robertmitchellv.github.io), [website](http://robertmitchellv.com/#)

If are a R Markdown newbie I suggest starting at the official lessons on [R Markdown by R Studio](https://rmarkdown.rstudio.com/).

[Here is a presentation](https://docs.google.com/presentation/d/e/2PACX-1vRpQkv2wRcJILZ69i9H9z38XukVGi94XjdkTzwlVXhbHaG4aqVn2QZ3mo01xeixsw_SgtxnOkZ299Rm/pub?start=false&loop=false&delayms=3000) I have presented in the past to give you a give overview of using RMarkdown


**INSTALL**
Just like the rest of R packages, get started with R Markdown by executing the following from the console
```
install.packages("rmarkdown")
```

Create a new RMarkdown document by selecting `File > New File > R Markdown... > Document > HTML > Open`
This will open the default `RMarkdown` document that will knit to html, however you can change to PDF, word etc.

## Templates

To get the most out of RMarkdown there are a number of various templates to suit whatever document and style you need. Below are some links to get you started.

:link: General links on RMarkdown templates

* [Document templates](https://bookdown.org/yihui/rmarkdown/document-templates.html)
* [Pandoc](https://pandoc.org/MANUAL.html)
* [RMarkdown overview/references](https://rmarkdown.rstudio.com/docs/)

check this one https://robertmitchellv.com/index.html
https://ulriklyngs.com/
https://github.com/svmiller?tab=repositories
https://github.com/ulyngs

### Bookdown

* [Document Templates](https://bookdown.org/yihui/rmarkdown/document-templates.html)
* [Bookdown](https://bookdown.org/yihui/rmarkdown/books.html)
* [Oxforddown](https://ulyngs.github.io/oxforddown/)
* [R Markdown for Scientists](https://rmd4sci.njtierney.com/figures-tables-captions-.html)
* [Latex line breaks and blank space overleaf](https://www.overleaf.com/learn/latex/line_breaks_and_blank_spaces)
* [knitr::kable and kableExtra](http://haozhu233.github.io/kableExtra/awesome_table_in_pdf.pdf)
* [kableExtra](http://haozhu233.github.io/kableExtra/)
* [RMarkdown cookbook](https://bookdown.org/yihui/rmarkdown-cookbook/)
* [bookdown: Authoring Books and Technical Documents with R Markdown](https://bookdown.org/yihui/bookdown/why-read-this-book.html)
* [R Bookdownplus textbook](https://bookdown.org/baydap/bookdownplus/bookdownplus.pdf)
* [pagedown](https://rstudio.github.io/pagedown/#pagedjs)
* [Bookdownplus gallery](https://bookdownplus.netlify.app/portfolio/)

### CV

[`vitae`](https://ropensci.org/blog/2019/01/10/vitae/), [pkg](https://pkg.mitchelloharawild.com/vitae/)
[Nick Strayer](https://github.com/nstrayer/cv) based on pagedown
[pagedown CVs](https://ulyngs.github.io/pagedown-cv/)
[another example from pagedown](https://github.com/jienagu/Jiena_McLellan_CV/blob/master/Jiena_McLellan_CV.pdf)
[another example from pagedown](https://landongetz.github.io/documents/CV.pdf)

### Articles

[`rticles`](https://github.com/rstudio/rticles)

## Thesis

Write your thesis with ease [Thesisdown](https://github.com/ismayc/thesisdown)
[Oxforddown[(https://ulyngs.github.io/oxforddown/)
https://livefreeordichotomize.com/2018/09/14/one-year-to-dissertate/
https://github.com/LucyMcGowan

## Websites

* [blogdown](https://bookdown.org/yihui/blogdown/)
* [hugo academic](https://github.com/gcushen/hugo-academic)
* [hugo academic](https://georgecushen.com/create-your-website-with-hugo/)
* [hugo themes](https://themes.gohugo.io/)

## Other themes

[EpuRate](https://github.com/holtzy/epuRate)

* [Blog post by Dr. Jianghao Wang](http://jianghao.wang/post/2017-12-08-rmarkdown-templates/)
* [Rob Hyndman](https://github.com/robjhyndman/MonashEBSTemplates)


## Posters

A new R package to make posters by Brent Thorne called [posterdown](https://github.com/brentthorne/posterdown)

```
install.packages("posterdown")
```

## Gnatt chart

Libraries
```
library(ggplot2)
library(readr)
```
Make gnatt chart

```
# Load data
gnatt <- read_csv("data/gnatt.csv", col_types = cols(end = col_date(format = "%d/%m/%Y"),
    start = col_date(format = "%d/%m/%Y")))
```

## Set factor level to order the activities on the plot

```
gnatt$chapter <- factor(gnatt$chapter)

plot_gnatt <- qplot(ymin = start,
                    ymax = end,
                    x = chapter,
                    colour = activity,
                    geom = "linerange",
                    data = gnatt,
                    size = I(5)) +
    scale_colour_manual(values = c("red", "grey", "purple", "orange", "blue")) +
    coord_flip() +
    theme_bw() +
    theme(panel.grid = element_blank()) +
    xlab("") +
    ylab("") +
    ggtitle("Project planning")
plot_gnatt
```
