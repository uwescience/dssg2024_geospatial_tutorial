# DSSG 2024 Geospatial Analysis Tutorial

A brief tour of geospatial analysis, mostly focused on open source software. 

## Organization
[DSSG 2024](https://escience.washington.edu/using-data-science/data-science-for-social-good/dssg-projects/) has groups working in Python and R with a variety of geospatial data! Fortunately, there are a lot of great public tutorials, textbooks, and resources out there to introduce data scientists to geospatial data analysis.

This repository is intended as a snapshot to point groups toward a selection of resources that might be useful for projects over the summer. We're going to assume no prior experience working with geospatial data, but some experience with Python or R, and GitHub.

The intent is to provide a guided 3-hour tour with a few coding examples and experiments along the way.

### Interactive Computing
You can use [Pangeo Docker Images](https://github.com/pangeo-data/pangeo-docker-images) + [GitHub Codespaces](https://github.com/features/codespaces) to run Python code examples during this tutorial!

https://codespaces.new/uwescience/dssg2024_geospatial_tutorial?quickstart=1  

Be sure to stop the Codespace when you're not using it from this page (https://github.com/codespaces). A "codespace" is a server running in Microsoft Azure, and you have a quota of free minutes per month.


## Start Here
"Geospatial" data is simply data that can be located in space (usually the surface of the Earth) and time. You'll often hear people analyzing geospatial data talk about "Geographic Information System" (GIS), which is essentially software to manage and process a number of independent geospatial datasets.

If you are new to geospatial analysis and like to start with history and theory I recommend this online course material from Penn State University (e.g. [maps](https://www.e-education.psu.edu/maps/l2_p2.html), [GIS](https://www.e-education.psu.edu/natureofgeoinfo/node/1672))

[The Carpentries](https://carpentries.org/index.html) provide instructor-lead workshops with well-designed public lessons in different programming languages

| | |
| - | - |
|R| https://datacarpentry.org/geospatial-workshop/ |
|Python | https://carpentries-incubator.github.io/geospatial-python/ |

**Exercise** 
> Take 5 minutes to explore the above resources or others. Can you find information on "vector" and "raster" geospatial data?

## Concept 1: *Understand the landscape of of open source software tools (GDAL, QGIS, PostGIS, Python libraries, R libraries)*

The [Geospatial Data Abstraction Library("GDAL")](https://gdal.org/index.html) is a foundational software library released in 2000 written in `C` that is a dependency of most major GIS software today! Read more and gain experience with GDAL in this excellent series of blog posts by Robert Simmon: https://medium.com/planet-stories/a-gentle-introduction-to-gdal-part-1-a3253eb96082 

[QGIS](https://www.qgis.org) is an excellent free and open-source Desktop GIS application to work with (see also https://uwgda-jupyterbook.readthedocs.io/en/latest/resources/qgis.html)

[PostGIS](https://postgis.net) is a spatial extension for the open source PostgreSQL database. As you amass a large amount of data it is convenient to use a database to have efficient searches, enforce format schemas, and optionally permissions and handling of simultaneous users.

Python is a popular programming language due to it's versatility and [huge ecosystem of libraries](https://github.com/sacridini/Awesome-Geospatial?tab=readme-ov-file#python). It can be overwhelming trying to find the right one! [Here](https://github.com/opengeos/python-geospatial) is a slightly more curated list. In general there are a few foundational libraries, and many more that depend on these. You'll often here references to a software 'stack' and indeed, it is layer upon layer of source code all the way down!
| | |
| - | - | 
| Vector | [Geopandas](https://geopandas.org/en/stable/) |
| 2D Raster | [Rasterio](https://rasterio.readthedocs.io) | 
| nD Arrays | [Xarray](https://github.com/pydata/xarray) |

R is a programming language that is very popular among statisticians. Similar to Python, there is a [large ecosystem of packages](https://github.com/sacridini/Awesome-Geospatial?tab=readme-ov-file#r) with various specializations. Core libraries can be found here https://github.com/r-spatial.

> Are there other software libraries you recommend?

## Open Data

Unfortunately, there is no single 'Google Search' for geospatial data (...yet). So each data provider often has idiosyncratic search utilities. [SpatialTemporal Asset Catalog (STAC)](https://stacspec.org/en) is a recent effort to standardize metadata across data providers. 

**Civilian Satellite Remote Sensing**
| | | 
| - | - | 
| NASA EarthData | https://www.earthdata.nasa.gov |
| ESA Copernicus Open Data | https://dataspace.copernicus.eu/explore-data |

**Climate Models**
| | | 
| - | - |
| ECMWF | https://www.ecmwf.int/en/forecasts/datasets |
| NCAR | https://www.cesm.ucar.edu/models | 

**Census Data**
| | | 
| - | - | 
| United States | https://data.census.gov |

> What other data providers do you regularly use?

### Cloud computing and big data

> Geospatial data is experiencing exponential growth in both size and complexity. As a result, traditional data access methods, such as file downloads, have become increasingly impractical for achieving scientific objectives (https://guide.cloudnativegeo.org)

| | | 
| - | - |
| Microsoft Planetary Computer | https://planetarycomputer.microsoft.com/catalog
| Google Cloud / Earth Engine | https://cloud.google.com/datasets?hl=en |
| AWS Open Data | https://aws.amazon.com/earth/  |

Major Cloud Providers host mirrored archives of public data from NASA, ESA, and other agencies, which have been converted to "cloud-optimized" formats. Google Earth Engine is a unique Cloud-computing platform focused on geospatial imagery analysis that is free for non-commercial use.

## Skill 1 / Exercise: **Find and analyze imagery and GIS datasets with open-source software**

> Take 20 minutes to find public geospatial data from one of the above and use QGIS or another tool to view it on a map!

## Concept 2. **Combining raster and vector data (reprojection, sampling, subsetting, interpolation)**

* Review Understanding Map Projections lesson https://uwgda-jupyterbook.readthedocs.io/en/latest/modules/04_Vector1_Geopandas_CRS_Proj/04_Vector1_Tissot_MapDistortion_demo.html 

* Microsoft Planetary Computer Examples (both R and Python): https://planetarycomputer.microsoft.com/docs/overview/about 
    * https://github.com/microsoft/PlanetaryComputerExamples 
    * Not sure what data is available in your area of interest? Start here! https://planetarycomputer.microsoft.com/explore

* Additional readingGeoscience-focused Python tutorials https://foundations.projectpythia.org/landing-page.html 

## Skill 2 / Exercise: **Reproject data to have a common coordinate reference system for joint analysis**

> 60 minutes. Go over intro-geopandas.ipynb in this repository focused on vector data and the Microsoft Planetary Computer *quickstart* https://planetarycomputer.microsoft.com/docs/quickstarts/reading-stac/


## Concept 3. **Geostatistics**

"Geostats" is the collection of methods for analyzing and predicting values and uncertainties associated with spatiotemporal phenomena. In other words, given measurements at *known* locations, how well can we predict unknown values at *different* locations? There are many methods! But a key thing to remember is that geospatial observations close in time and space tend to be more closely related (correlated) compared to measurements that are far apart. Geostatistical methods come up with sophisticated ways to deal with this. Below are two online comprehensive textbooks that have practical code examples.

### Python

Spatial Data Science for Social Geography https://github.com/martinfleis/sds

### R
Geocomputation with R, a book on geographic data analysis, visualization and modeling https://r.geocompx.org 


## Skill 3 / Exercise **Be able to visualize and share results of your analysis efficiently among your team**

The easiest way to share a small amount of data is to put it on GitHub. [GitHub will render maps for you!](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/creating-diagrams)

> Use https://geojson.io to create a GeoJSON file, put it in a GitHub repository, and share a link with your colleague!

## Additional Resources

### Explore the Cutting Edge

* DuckDB is relatively new database system that works well for analysis of very large datasets in GeoParquet format https://medium.com/radiant-earth-insights/duckdb-the-indispensable-geospatial-tool-you-didnt-know-you-were-missing-5fe11c5633e5 

* Lots of current developments for connecting various open-source libraries for ML-focused work https://xarray.dev/blog/pangeo-ml-ecosystem-2023 

* This discussion forum is a great resource for groups working with large geospatial data. is a focus on cloud computing and open science. https://discourse.pangeo.io 

### Formal coursework

* **UW Geospatial Data Analysis with Python** https://uwgda-jupyterbook.readthedocs.io/ 

* **UW Machine Learning in the Geosciences** https://geo-smart.github.io/mlgeo-book/about_this_book/about_this_book.html 

* **The Nature of Geographic Information: An Open Geospatial Textbook.** David DiBiase with contributions by James L. Sloan II, Ryan Baxter, Wesley Stroh, Beth Fletcher King, and many students. The Pennsylvania State University. https://www.e-education.psu.edu/natureofgeoinfo/node/1672 
    * NOTE: The John A. Dutton e-Education Institute has a lot of other excellent resources!

* Geographic Data Science with Python https://geographicdata.science

* Spatial data science for sustainable development https://sustainability-gis.readthedocs.io

### Programming
* @giswqs has lots of excellent open source python tools
    https://github.com/opengeos/python-geospatial
    https://leafmap.org 

* 2023 workshop on Geopandas https://github.com/martinfleis/efficient-geopandas-workshop 

* The social science data lab at UC Berkeley https://github.com/dlab-berkeley 

* Geostatistical interpolation and simulation https://github.com/GatorGlaciology/GStatSim