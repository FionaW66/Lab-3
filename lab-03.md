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

Next, we create a new variable: country_us.

``` r
nobel_living <- nobel_living %>% 
  mutate(
    country_us = if_else(country == "USA", "USA", "Other")
  )
```

We will limit our analysis to only Physics, Medicine, Chemistry, and
Economics.

``` r
nobel_living_science <- nobel_living %>% 
  filter(category %in% c("Physics", "Medicine", "Chemistry", "Economics"))
```

It’s interesting that we still have 228 observations.

### Exercise 3

``` r
nobel_living_science %>% 
  ggplot(mapping = aes(y = country_us, color=category, fill = category)) + 
  geom_bar() + facet_wrap(~category, nrow = 2) + 
  labs(title = "Born in the U.S vs. Others", subtitle = "by category")
```

![](lab-03_files/figure-gfm/bar_plot-1.png)<!-- -->

According to the visualization, I do observe that more Nobel laureate
were based in the U.S. when they won the Nobel prize for all four
categories. This is more true for Economics than other categories. I
would conclude that the visualization supports Buzzfeed headline, but I
can’t be sure whether the difference between the bars is significant.

### Exercise 4

…

### Exercise 5

…

### Exercise 6

…
