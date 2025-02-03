Lab 03 - Nobel laureates
================
Fiona Wang
2025-02-03

### Load packages and data

``` r
library(tidyverse) 
```

``` r
nobel <- read_csv("data/nobel.csv")
```

## Exercises

### Exercise 1

There are 935 rows in the dataset, meaning there are 935 observations in
total. There are 26 variables in the dataset. Each row gives the
information of one Nobel laureates, specifically, their names and
country of birth, death, and prize-winning.

### Exercise 2

``` r
nobel_living = nobel %>% 
  filter(!is.na(country) & gender != "org" & is.na(died_date))
```

This new data frame has 228 rows.

### Exercise 3

Remove this text, and add your answer for Exercise 1 here. Add code
chunks as needed. Don’t forget to label your code chunk. Do not use
spaces in code chunk labels.

### Exercise 4

…

### Exercise 5

…

### Exercise 6

…
