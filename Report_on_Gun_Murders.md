Report on Gun Murders (US)
================
Vasu Vikram
July 10, 2018

In this report we will analyse Gun Murders in United States as reported by the latest data of FBI. We will download data from the URL mentioned below: "<https://raw.githubusercontent.com/rafalab/dslabs/master/inst/extdata/murders.csv>" We will then wrangle data ang would make certain changes that would help us plot state=wise murder rates in the United States.

``` r
url<-"https://raw.githubusercontent.com/rafalab/dslabs/master/inst/extdata/murders.csv"
dest_file<-"data/murders.csv"
download.file(url, destfile = dest_file)
```

Wrangling Data
--------------

You can also embed plots, for example:

    ## Warning: package 'tidyverse' was built under R version 3.5.1

    ## -- Attaching packages --------------------------------------- tidyverse 1.2.1 --

    ## v ggplot2 3.0.0     v purrr   0.2.5
    ## v tibble  1.4.2     v dplyr   0.7.6
    ## v tidyr   0.8.1     v stringr 1.3.1
    ## v readr   1.1.1     v forcats 0.3.0

    ## Warning: package 'ggplot2' was built under R version 3.5.1

    ## Warning: package 'tidyr' was built under R version 3.5.1

    ## Warning: package 'purrr' was built under R version 3.5.1

    ## Warning: package 'dplyr' was built under R version 3.5.1

    ## Warning: package 'stringr' was built under R version 3.5.1

    ## -- Conflicts ------------------------------------------ tidyverse_conflicts() --
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

    ## Parsed with column specification:
    ## cols(
    ##   state = col_character(),
    ##   abb = col_character(),
    ##   region = col_character(),
    ##   population = col_integer(),
    ##   total = col_integer()
    ## )

    ## Warning: package 'bindrcpp' was built under R version 3.5.1

Note that the `echo = FALSE` parameter was added to the code chunk to prevent printing of the R code that generated the plot.

![](Report_on_Gun_Murders_files/figure-markdown_github/unnamed-chunk-3-1.png) We can see that Washington DC has an exceptionally high rate of Gun Murders, about 6 times the mean.
