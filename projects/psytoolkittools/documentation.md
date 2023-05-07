---
layout: single
permalink: /projects/psytoolkittools/documentation
title: "psytoolkittools Documentation"
toc: true
toc_label: "Table of Contents"
toc_sticky: true
---
# Getting Started

## Installing 

Because the package is currently not avaible on CRAN, you have to download it from GitHub and compile it yourself.
Both can be be easily done by using the following R code.
```r
#if devtools are not installed
install.packages("devtools")

library(devtools)
devtools::install_github("JonasEnCode/psytoolkittools")
```

**Dependecies**
- reticulate
- cpp11
- cli
- glue
- devtools

Also, RTools are required for compiling the source code.

## Loading Data

At first, download your survey and experiment results from the
PsyToolkit website. You will receive a .ZIP file. Move this file to your
current R working directory.

In R, load the `psytoolkittools` package and run the `load(filename)` function.
For example:
```r
library(psytoolkittools)
data <- load("data.zip")
```
The function returns a data frame with the survey awnsers.
A folder called "psy_data" is created. Do not delete this folder as it is nessecary for loading experiment data.

### Load Experiment Data
To easily load the experiment data, the package provides the `load.experiment.data()` function.
This functions requires two arguments:
- Column with the experiment data filenames
- Vector of strings which correspond to the structure of the saved experiment data

The function returns a data frame which can be combined with the survey data frame by passing it to the function.
```r
load.experiment.data(experiment.file.names, label.structure, merge.dataframe = surveydata)
```
