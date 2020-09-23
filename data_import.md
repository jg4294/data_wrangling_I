Data Import
================

# we focus on readr package.

``` r
library(tidyverse) 
```

    ## -- Attaching packages --------------------------------------------------------- tidyverse 1.3.0 --

    ## v ggplot2 3.3.2     v purrr   0.3.4
    ## v tibble  3.0.3     v dplyr   1.0.2
    ## v tidyr   1.1.2     v stringr 1.4.0
    ## v readr   1.3.1     v forcats 0.5.0

    ## -- Conflicts ------------------------------------------------------------ tidyverse_conflicts() --
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

## Read in some data

Read in the litters dataset.

``` r
litters_df = read_csv("./data/FAS_litters.csv") 
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
# read_csv is a fucntion in reader package
# give a relative path "./data/FAS_litters.csv"
# starting here "data_wrangling_i" go into the data folder and go into fas litters.csv
# absolute path would be starting from the really begin of your computer, says the desktop

litters_df # take a look
```

    ## # A tibble: 49 x 8
    ##    Group `Litter Number` `GD0 weight` `GD18 weight` `GD of Birth`
    ##    <chr> <chr>                  <dbl>         <dbl>         <dbl>
    ##  1 Con7  #85                     19.7          34.7            20
    ##  2 Con7  #1/2/95/2               27            42              19
    ##  3 Con7  #5/5/3/83/3-3           26            41.4            19
    ##  4 Con7  #5/4/2/95/2             28.5          44.1            19
    ##  5 Con7  #4/2/95/3-3             NA            NA              20
    ##  6 Con7  #2/2/95/3-2             NA            NA              20
    ##  7 Con7  #1/5/3/83/3-3/2         NA            NA              20
    ##  8 Con8  #3/83/3-3               NA            NA              20
    ##  9 Con8  #2/95/3                 NA            NA              20
    ## 10 Con8  #3/5/2/2/95             28.5          NA              20
    ## # ... with 39 more rows, and 3 more variables: `Pups born alive` <dbl>, `Pups
    ## #   dead @ birth` <dbl>, `Pups survive` <dbl>

``` r
# overwrite the original dataset: clean_names() with a transformed version
# janitor::clean_names() means in the janitor package, use function clean_names(); or we can load the package by library(janitor), but we're not, b/c clean_names() is the only function we use.
litters_df = janitor::clean_names(litters_df)
```

## Take a look at the data
