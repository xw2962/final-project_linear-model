linear model
================
Xiaoyu Wu
2023-11-28

``` r
library(readxl)
library(dplyr)
```

    ## 
    ## Attaching package: 'dplyr'

    ## The following objects are masked from 'package:stats':
    ## 
    ##     filter, lag

    ## The following objects are masked from 'package:base':
    ## 
    ##     intersect, setdiff, setequal, union

## Import the Data

``` r
file_path = "./PL_1819_data.xlsx"


player_df = read_excel(file_path, sheet = 4)
```

    ## New names:
    ## • `Gls` -> `Gls...12`
    ## • `Ast` -> `Ast...13`
    ## • `G+A` -> `G+A...14`
    ## • `G-PK` -> `G-PK...15`
    ## • `xG` -> `xG...20`
    ## • `npxG` -> `npxG...21`
    ## • `xAG` -> `xAG...22`
    ## • `npxG+xAG` -> `npxG+xAG...23`
    ## • `Gls` -> `Gls...27`
    ## • `Ast` -> `Ast...28`
    ## • `G+A` -> `G+A...29`
    ## • `G-PK` -> `G-PK...30`
    ## • `xG` -> `xG...32`
    ## • `xAG` -> `xAG...33`
    ## • `npxG` -> `npxG...35`
    ## • `npxG+xAG` -> `npxG+xAG...36`

## Data Wrangling

``` r
cleaned_player_df = player_df  |> 
 mutate(Age = as.numeric(as.character(Age)),
 Min = as.numeric(as.character(Min)))  |> 
 na.omit()
```

    ## Warning: There were 2 warnings in `mutate()`.
    ## The first warning was:
    ## ℹ In argument: `Age = as.numeric(as.character(Age))`.
    ## Caused by warning:
    ## ! NAs introduced by coercion
    ## ℹ Run `dplyr::last_dplyr_warnings()` to see the 1 remaining warning.
