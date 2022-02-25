
<!-- README.md is generated from README.Rmd. Please edit that file -->

# addrsheff

<!-- badges: start -->
<!-- badges: end -->

addrsheff is an R package. The goal is to help with address data
e.g. postcodes.

## Installation

You can install the development version of addrsheff from
[GitHub](https://github.com/) with:

``` r
# install.packages("devtools")
devtools::install_github("scc-pi/addrsheff")
```

If you work for Sheffield City Council you can install the binary
package for Windows from:

> S:\\BI Team\\ShareToAll\\RPackages

Using RStudio you can does this via the *Tools \> Install packages…*
menu.

## add_postcode_vars()

This package currently has just one function `add_postcode_vars()`. Pass
it a data frame with a postcode column and it will return the data frame
with new columns e.g. Ward:

``` r
library(addrsheff)

# Create a data frame with some example records
df <- tibble::tribble(
  ~name,    ~postcode,
  "SCC",    "S1 2HH",
  "Blades", "S2 4SU",
  "Owls",   "S6 1SW"
)

add_postcode_vars(
  df,
  pcd_name = "postcode",
  .admin_district = FALSE,
  .lat_long = TRUE,
  other_vars = c("admin_ward", "msoa_code")
)
```

## Credit

The `add_postcode_vars()` function depends on the
[PostcodesioR](https://docs.ropensci.org/PostcodesioR/) R package and
the [postcodes.io](https://postcodes.io/) free postcode and geolocation
API for the UK.

This package was built using
[fusen](https://thinkr-open.github.io/fusen/index.html).
