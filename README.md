# LD50R

Lethal Dose 50% calicuration R script for bio assay with insecticide in Rstudio. 

## Files

* **LD50Probit.Rmd**    main R mark down script for Rstudio
* **data.tsv**          a example file of input data
* **LD50Probit.html**   Output Example html file containing a graph by knit in Rstudio

I checked my script under the environment as below.

* [R version 4.1.0 (2021-05-18) -- "Camp Pontanezen"](https://cran.r-project.org/)
  * [MASS Library](https://cran.r-project.org/web/packages/MASS/index.html) Installation is needed.
* [RStudio Version 1.4.1106](https://www.rstudio.com/)



## Test data from Finney 1947

[Original Article: Probit Analysis (Book)](https://www.cambridge.org/gb/academic/subjects/statistics-probability/statistics-econometrics-finance-and-insurance/probit-analysis?format=PB&isbn=9780521135900)

AUTHOR: David Finney

ORIGINAL PUBLISHED: 1947 (Re-issue PUBLISHED: 2009) 

ISBN: 9780521135900

<img src="https://github.com/oskomagata/LD50R/blob/images/Finny2.png" width="640px">

<img src="https://github.com/oskomagata/LD50R/blob/images/Finny8.png" width="640px">

In Finney 1947, the LD50 was estimated as 4.86, estimated as 4.845492 by my script. 


**My Script Graph Out Put Example** 

X-axis is concentration in logarithmic scale and Y-Asix is Mortarity rate (%) in probit scale. 

<img src="https://github.com/oskomagata/LD50R/blob/images/outputGraph1.png" width="640px">


