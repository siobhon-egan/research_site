# Statistics

source: `{{ page.path }}`

:link: As always links first

* [Statistics & analysis RCompanion](https://rcompanion.org/handbook/C_03.html)
* [PropCIs](https://github.com/shearer/PropCIs)
* [binom](https://cran.rstudio.com/web/packages/binom/binom.pdf)
* [BIMS8382 essential statistics with R](https://bioconnector.github.io/workshops/r-stats.html)


Some commonly used statistics calculations for use in RStudio.

**Load data**

We'll load some data on Tasmanian devils and presence of DFTD (cancer) and *Trypanosoma* presence.
The data is coded so that 0 is negative and 1 is positive.

```
library(readr)
# Load data
tasdevil <- read_csv("data/tasdevil-parasite.csv")
```

## Basics

Sructure of data set
```
str(tasdevil)
```

How many had DFTD
```
sum(tasdevil$DFTDStatus)
```


##  Proportion and CIs


**Load libraries**

```
# Install first if you need
#
# install.packages("DescTools")
# install.packages("PropCIs")
# install.packages("binom")
# install.package("rcompanion")
# install.package("tidyverse")
```

```
library(DescTools)
library(PropCIs)
library(binom)
library(rcompanion)
library(tidyverse)
```


Calculate different in *Trypanosoma* prevalence between males and females with 95% CIs
```
groupwiseMean(TrypStatus ~ Sex,
              data = tasdevil,
              conf = 0.95,
              digits = 3)
```

We could plot the values above using this...
```
#save values to a data.frame
CI <- groupwiseMean(TrypStatus ~ Sex,
              data = tasdevil,
              conf = 0.95,
              digits = 3)
#plot
qplot(x= Sex,
      y = Mean,
      data = CI,
      shape= Sex) +

  geom_point(size=2.5) +

  geom_errorbar(aes(
    ymin = Trad.lower,
    ymax = Trad.upper,
    width = 0.15)) + theme_bw() + ylim(0,1)
```

Calculate different in *Trypanosoma* prevalence between males and females and 4 different sites with 95% CIs

```
groupwiseMean(TrypStatus ~ Sex + Site_code,
              data   = tasdevil,
              conf   = 0.95,
              digits = 3)
```

#### Simple stuff

If you need here are some simple bits of code where you have basic numbers such as...7 positive out of sample size of 21.
```
binom.test(7, 21,
           0.5,
           alternative="two.sided",
           conf.level=0.95)
```

Now we'll calculate the 95% CIs using the Jeffreys method.
```
BinomCI(7, 21,
        conf.level=0.95,
        method="jeffreys")
```


### Odds ratio & Relative risk

Using epitools - [manual here](https://cran.r-project.org/web/packages/epitools/epitools.pdf)

*Reminder:* If you need more information on the tests use the help command in the console (e.g. `?riskratio`, `?oddsratio`).

**Library**
```
library(epitools)
# if you don't have this package, first install using `install.packages("epitools")`
```

Create a simple dataframe. In this case we'll test effect of gender on parasite presence with a simple positive/negative summary. Of course if you have a your raw data in a spreadsheet you could make your own by summarising the releavnt information into a dataframe. (Need help tidying and summarising your data...check out [this tutorial](https://datacarpentry.org/R-ecology-lesson/03-dplyr.html) to check you hooked on the `dplyr` and `tidyr` packages
```
factor1 <- c("Female", "Male")
factor2 <- c("Positive", "Negative")
```

```
dat <- matrix(c(16, 30, 15, 34), nrow = 2, ncol = 2, byrow = TRUE)
dimnames(dat) <- list("Sex" = factor1, "Parasite present" = factor2)
```

Your dataframe should look like this
```
dat
```

Now lets calculate our **odds ratio**
```
oddsratio(dat)
```

and **relative risk**
```
riskratio(dat)
```

## Modelling

[Manual here](http://users.stat.ufl.edu/~aa/cda/R_web.pdf) and [webpage](http://users.stat.ufl.edu/~aa/cda2/cda.html)
