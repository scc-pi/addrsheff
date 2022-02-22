
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

## Example

This is a basic example which shows you how to solve a common problem:

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

The `add_postcode_vars()` functions depends on the
[PostcodesioR](https://docs.ropensci.org/PostcodesioR/) R package and
the [postcodes.io](https://postcodes.io/) free postcode and geolocation
API for the UK.
