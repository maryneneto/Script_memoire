Untitled
================

``` r
library(tidyverse)
```

    ## Warning: le package 'dplyr' a été compilé avec la version R 4.5.3

    ## Warning: le package 'stringr' a été compilé avec la version R 4.5.3

    ## ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
    ## ✔ dplyr     1.2.1     ✔ readr     2.1.5
    ## ✔ forcats   1.0.1     ✔ stringr   1.6.0
    ## ✔ ggplot2   4.0.0     ✔ tibble    3.3.0
    ## ✔ lubridate 1.9.4     ✔ tidyr     1.3.1
    ## ✔ purrr     1.1.0     
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()
    ## ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors

``` r
setwd("C:/Users/maryn/Desktop/memoireM2")
data <- read_csv ("C:/Users/maryn/Desktop/memoireM2/base_16_08.csv")
```

    ## Rows: 380 Columns: 335
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## chr   (95): startlanguage, GEN, SIT[other], PROF, DIP, PRATSF[other], PRINSF...
    ## dbl  (223): id, lastpage, seed, AGE, SIT[SQ001], SIT[SQ002], SIT[SQ003], SIT...
    ## lgl   (14): INTRO, PRE, PR2, PRAL, PRCO, PRSD, groupTime391, groupTime390, g...
    ## dttm   (3): submitdate, startdate, datestamp
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
data <- data %>%
  filter(lastpage >= 8) %>%
  select(-c(2, 4:7, 245:335))

summary(data$lastpage)
```

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##       8      29      83      62      83      83
