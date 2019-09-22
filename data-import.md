data import
================
Keyi Wang
9/22/2019

``` r
litters_data1 = read_csv(file = "./data/FAS_litters.csv")
```

    ## Parsed with column specification:
    ## cols(
    ##   Group = col_character(),
    ##   `Litter Number` = col_character(),
    ##   `GD0 weight` = col_double(),
    ##   `GD18 weight` = col_double(),
    ##   `GD of Birth` = col_double(),
    ##   `Pups born alive` = col_double(),
    ##   `Pups dead @ birth` = col_double(),
    ##   `Pups survive` = col_double()
    ## )

``` r
litters_data2 = read_csv(
  file = "./data/FAS_litters.csv", skip = 10, col_names = FALSE)
```

    ## Parsed with column specification:
    ## cols(
    ##   X1 = col_character(),
    ##   X2 = col_character(),
    ##   X3 = col_double(),
    ##   X4 = col_double(),
    ##   X5 = col_double(),
    ##   X6 = col_double(),
    ##   X7 = col_double(),
    ##   X8 = col_double()
    ## )

``` r
### converting name from capital letters into lower case 
litters_data = janitor::clean_names(litters_data1)
pups_data = read_csv(file = "./data/FAS_pups.csv")
```

    ## Parsed with column specification:
    ## cols(
    ##   `Litter Number` = col_character(),
    ##   Sex = col_double(),
    ##   `PD ears` = col_double(),
    ##   `PD eyes` = col_double(),
    ##   `PD pivot` = col_double(),
    ##   `PD walk` = col_double()
    ## )

``` r
pups_data = janitor::clean_names(pups_data)
```

``` r
##play with column names
litters_data3 = read_csv(file = "./data/FAS_litters.csv",
                         col_types = cols(
                            Group = col_character(),
                            `Litter Number` = col_character(),
                            `GD0 weight` = col_double(),
                            `GD18 weight` = col_double(),
                            `GD of Birth` = col_integer(),
                            `Pups born alive` = col_integer(),
                            `Pups dead @ birth` = col_integer(),
                            `Pups survive` = col_integer()
                           
                         )
                         )
##short hand version to change column types
litters_data4 = read_csv(file = "./data/FAS_litters.csv",
  col_types = "ccddiiii"
)
```
