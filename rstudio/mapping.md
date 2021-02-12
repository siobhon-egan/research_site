# Mapping

source: `{{ page.path }}`

:link: Links to get to started for mapping in RStudio

- [R-spatial](https://www.r-spatial.org/)
    - This tutorial [here](https://www.r-spatial.org/r/2018/10/25/ggplot2-sf.html) is a good place to start
- [ggplot, maps](https://ggplot2-book.org/maps.html)
- [Making maps with R, by Eric C. Anderson](https://eriqande.github.io/rep-res-web/lectures/making-maps-with-R.html)
- [Tutorial 5.4 - Mapping and spatial analyses in R](http://www.flutterbys.com.au/stats/tut/tut5.4.html)
- [Making maps of your study sites, Environmental Computing](http://environmentalcomputing.net/making-maps-of-your-study-sites/)
- [Displaying Geo-Spatial Data with R by Martin Schweinberger](https://slcladal.github.io/maps.html)
- [Leaflet for R](https://rstudio.github.io/leaflet) - Leaflet is one of the most popular open-source JavaScript libraries for interactive maps. It’s used by websites ranging from The New York Times and The Washington Post to GitHub and Flickr, as well as GIS specialists like OpenStreetMap, Mapbox, and CartoDB.
- [Map Plots Created With R And Ggmap, by Litte Miss Data](https://www.littlemissdata.com/blog/maps)
- [Using spatial data wth R by Claudia A Engel](https://cengel.github.io/R-spatial/)
- [Spatial Data Science, analysing species distribution data](https://rspatial.org/raster/cases/3-speciesdistribution.html)
- [Mapping Australia in R by Charles Coverdale](https://medium.com/analytics-vidhya/mapping-australia-in-r-6ce092c48b49)
- [Ozmaps Github](https://github.com/mdsumner/ozmaps)
- [Raster and vector geospatial data with R by Hayley Puckeridge](https://rpubs.com/haydenp/649457)
- [Geocomputation with R by Spatial Vision](https://spatialvision.com.au/blog-geocomputation-with-r/)
- [Data wrangling for spatial analysis: R Workshop by Dr. Chris J Brown, Prof. David Schoeman, Prof. Anthony J Richardson, Dr. Bill Venables](https://www.seascapemodels.org/data/data-wrangling-spatial-course.html#introduction)
- [Visualizing Climate Data: A Tidy Tuesday Project From January 2020 Using Data From The Australia Wildfires](https://samia.rbind.io/post/australia-wildfires-a-tidy-tuesday-project-from-january-2020/)
- [Lesson 8. Creating Interactive Spatial Maps in R Using Leaflet by Carson Farmer, Leah Wasser](https://www.earthdatascience.org/courses/earth-analytics/get-data-using-apis/leaflet-r/)
- [tmap package](https://cran.r-project.org/web/packages/tmap/vignettes/tmap-getstarted.html)
- [Geocomputation with R by Robin Lovelace, Jakub Nowosad, Jannes Muenchow](https://geocompr.robinlovelace.net/index.html)
- [An Introduction to Spatial Analysis in R by Seascape models](https://www.seascapemodels.org/rstats/rspatial/2015/06/22/R_Spatial_course.html)
- [Oz viridis by Nicholas Tierney](https://github.com/njtierney/ozviridis) - mapping bom temperature and rainfall data for Australia
- [AWAPer - an R-package for catchment-weighted climate data anywhere in Australia](https://github.com/peterson-tim-j/AWAPer)
- [ClimClass package](https://rdrr.io/cran/ClimClass/)
- [Climate Distance Mapper R script, USGS](https://www.sciencebase.gov/catalog/item/5b6354bce4b006a11f718279)
- [Making maps with R, by Eric C Anderson](https://eriqande.github.io/rep-res-web/lectures/making-maps-with-R.html)
- [Spatial data in R: Using R as a GIS by Francisco Rodriguez-Sanchez](http://pakillo.github.io/R-GIS-tutorial/)
- [Calculating species climate envelopes in R, by Remko Duursma](http://rstudio-pubs-static.s3.amazonaws.com/226109_0a5ded4fc21347278f02e8f22b4473bd.html)
- [Niche - An R Shint app](https://medium.com/swlh/niche-an-interface-for-exploring-your-moving-options-858a0baa29b2)

:link: Useful data sets for mapping

- [Australian government, climatology/meteorology/atmosphere](https://data.gov.au/data/dataset?tags=climatologyMeteorologyAtmosphere)
- [Interim Biogeographic Regionalisation for Australia (IBRA), Version 7 (Regions)](https://data.gov.au/data/dataset/interim-biogeographic-regionalisation-for-australia-ibra-version-7-regions), datset download [here](http://www.environment.gov.au/fed/catalog/search/resource/details.page?uuid=%7B8B9E3F42-9856-4487-AE9E-C76A322809A1%7D)
- [Biodiversity and Climate change virtual lab](https://app.bccvl.org.au/datasets#c12=modified&reversed=on&b_start=0)

***

# Example workflow 1

Following tutorial at this [link](http://environmentalcomputing.net/making-maps-of-your-study-sites/)

```
library(sp)
library(dplyr)
library(rgdal)
library(raster)
library(ggplot2)
library(readr)
```

Import csv file containing lon and lat coords
```
Sites <- read_csv("../../data/sites.csv")
```

Create buffer around your data points
```
buffer <- 0.11
geo_bounds <- c(left = min(Sites$Lon)-buffer,
                bottom = min(Sites$Lat)-buffer,
                right = max(Sites$Lon)+buffer,
                top = max(Sites$Lat)+buffer)
Sites.grid <- expand.grid(lon_bound = c(geo_bounds[1], geo_bounds[3]),
                          lat_bound = c(geo_bounds[2], geo_bounds[4]))
```

```
coordinates(Sites.grid) <- ~ lon_bound + lat_bound
```

Load mapping files
Downloaded from GEODATA COAST 100K 2004 shapefiles available [here](https://data.gov.au/dataset/geodata-coast-100k-2004/resource/455ee5c6-2862-445e-8fbe-604476926b4c)
```
Aus <- readOGR(dsn = "~/Documents/Programs/R/Maps/Rpackage_Geodata-coast/australia",layer = "cstauscd_r")
```

Remove coastline clutter from map
```
Aus_coast <- subset(Aus, FEAT_CODE != "sea")
plot(Aus_coast)
```


Plot map and points using `ggplot2`
```
g1 = ggplot(data = Aus_coast) +
  geom_polygon(aes(x = long, y = lat, group = group), fill = NA, color = "black") +
  coord_fixed(1.3) + theme_classic()
g2 = g1 + geom_point(data = Sites, aes (x=Lon, y=Lat, colour=Locality, stroke=1.5)) +
  scale_colour_viridis_d(option = "plasma")
```

Customise colour of points
```
g3 = g1 + geom_point(data = Sites, aes (x=Lon, y=Lat, colour=Locality, stroke=1.5), colour="#CC0000")
```

Make interactive plot with plotly
```
library(plotly)
gp <- ggplotly(g3)
gp
```

To save a html version of the interactive plot execute the following

```
htmlwidgets::saveWidget(gp, "index.html")
gp
```

# Example workflow 2

Tutorial from [Displaying Geo-Spatial Data with R by Martin Schweinberger](https://slcladal.github.io/maps.html)

Install packages
```
# clean current workspace
rm(list=ls(all=T))
# set options
options(stringsAsFactors = F)         # no automatic data transformation
options("scipen" = 100, "digits" = 4) # suppress math annotation
op <- options(gvis.plot.tag='chart')  # set gViz options
# install libraries
install.packages(c("RgoogleMaps", "ggmap", "mapproj", "sf",
                   "dplyr", "OpenStreetMap", "devtools", "DT"))
# install package from github
devtools::install_github("dkahle/ggmap", ref = "tidyup")
```

Load library and produce simple map of Australia
```
# load library
library(OpenStreetMap)
# extract map
AustraliaMap <- openmap(c(-8,110),
    c(-45,160),
   type = "osm",
#   type = "esri",
#    type = "nps",
    minNumTiles=7)
# plot map
plot(AustraliaMap)
```
