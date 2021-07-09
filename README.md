# LD50R

Lethal Dose calculation R script for bio assay with insecticide in Rstudio. 

## Files

* **LD50Probit.Rmd**    main R mark down script for Rstudio
* **data.tsv**          a example file of input data
* **LD50Probit.html**   Output Example html file containing a graph by knit in Rstudio
* **Finny1947Table2p26.xlsx** a example Excel file of input data
 
I checked my script under the environment as below.

* [R version 4.1.0 (2021-05-18) -- "Camp Pontanezen"](https://cran.r-project.org/)
  * [MASS Library](https://cran.r-project.org/web/packages/MASS/index.html) Installation is needed.
* [RStudio Version 1.4.1106](https://www.rstudio.com/)

## Calculation outline

Three columns are need for calculation. Chemical test doses, number of organisms tested for each dose, and number of affected. "Affected" means dead, knockdown, paralysis and more. 

Typical data is as follows. This data was quoted from Fenney1947.

```
dose  total affected
10.2  50  44
7.7 49  42
5.1 46  24
3.8 48  16
2.6 50  6
0 49  0
```

This script uses 
[glm](https://www.rdocumentation.org/packages/stats/versions/3.6.2/topics/glm)
 function in R. The function is used to fit generalized linear models.

The formula is "cbind(affected, total-affected) ~ dose", the error distribution is "binomial" and the link function is "probit".

If you have tested the dose as 0 and Affected not 0, the mortality rates will be adjusted by Abott's formula for adjust background by the control mortality.


## Test data from Finney 1947

[Original Article: Probit Analysis (Book)](https://www.cambridge.org/gb/academic/subjects/statistics-probability/statistics-econometrics-finance-and-insurance/probit-analysis?format=PB&isbn=9780521135900)

AUTHOR: David Finney

ORIGINAL PUBLISHED: 1947 (Re-issue PUBLISHED: 2009) 

ISBN: 9780521135900

<img src="https://github.com/oskomagata/LD50R/blob/images/Finny2.png" width="640px">

<img src="https://github.com/oskomagata/LD50R/blob/images/Finny8.png" width="640px">

In Finney 1947, the LD50 was estimated as 4.86, estimated as 4.845492 by my script.
The logarithmic standard errors for LD50 concetration wrere estimated 0.0229 in Finney 1947 and 0.02206838 by my script.

**My Script Graph Out Put Example** 

X-axis is concentration in logarithmic scale and Y-Asix is Mortarity rate (%) in probit scale. 

<img src="https://github.com/oskomagata/LD50R/blob/images/outputGraph1.png" width="640px">


