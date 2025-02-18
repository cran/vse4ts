vse4ts
================

<!-- badges: start -->
<!-- badges: end -->

## Introduction

Methods for calculating the variance scale exponent to identify memory
patterns in time series data. Includes tests for white noise, short
memory, and long memory. See Fu, H. et
al. (2018)\<<doi:10.1016/j.physa.2018.06.092>\>.

## Installation

You can install the development version of vse4ts from
[GitHub](https://github.com/z-my-cn/vse4ts) with:

``` r
# install.packages("devtools")
devtools::install_github("z-my-cn/vse4ts")
```

## Example

Here is a basic example of how to use the `vse` function in the vse4ts
package:

``` r
library(vse4ts)
set.seed(123)
x <- rnorm(1024)
x.vse <- vse(x)
print(x.vse)
#> [1] 0.4987233
```

This package also provides two hypothesis test functions `Wnoise.test`
and `SLmemory.test` to test the white noise and short/long memory of a
time series, respectively. Here is an example of how to use the
`Wnoise.test` function and `SLmemory.test` function in the vse4ts
package:

``` r
library(vse4ts)
# install.packages("pracma")
library(pracma)

data("brown72")
x <- brown72

# Test white noise
Wnoise.test(x)
#> Wnoise Test
#>
#> Wnoise statistic: 135.1091
#> degrees of freedom: 31
#> p-value: 5.884182e-15
#>
#> alternative hypothesis: non-independent stochastic process

# Test long memory
SLmemory.test(x)
#> SLmemory Test
#>
#> SLmemory statistic: 21.20841
#> degrees of freedom: 31
#> p-value: 0.09369624
#>
#> alternative hypothesis: long memory
```

## License

MIT © 2024 vse4ts authors
