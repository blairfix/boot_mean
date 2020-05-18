# boot_mean

`boot_mean` is an R function that calculates confidence intervals for the mean using the [bootstrap method](https://en.wikipedia.org/wiki/Bootstrapping_%28statistics%29).


### Inputs

* `x` = the input vector of data
* `conf` =  the desired confidence interval for the mean (expressed as a decimal)
* `n_boot` = the number of bootstrap iterations


### Output
`boot_mean` returns a vector containing 3 elements:

* [1] lower confidence interval
* [2] the mean
* [3] upper confidence interval


### Example:

```R
library(RcppArmadillo)
library(Rcpp)

sourceCpp("boot_mean.cpp")

# make a lognormal distribution
x = rlnorm(10^3, 1, 2)

# confidence interval
conf = 0.95

# number of bootstrap iterations
n_boot = 1000

# get bootstrap confidence interval of mean
boot_mean(x, conf, n_boot)

         [,1]
[1,] 18.36625
[2,] 29.19358
[3,] 45.19535

```


### Installation
To use `boot_mean`, install the following R packages:
 * [Rcpp](https://cran.r-project.org/web/packages/Rcpp/index.html) 
 * [RcppArmadillo](https://cran.r-project.org/web/packages/RcppArmadillo/index.html) 

Put the source code (`boot_mean.cpp`) in the directory of your R script. Then source it with the command `sourceCpp('boot_mean.cpp')`.



