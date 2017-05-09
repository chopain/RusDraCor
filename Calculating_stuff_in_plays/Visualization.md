Dramas Analysis
================
Ira Pavlova
08.05.2017

### This project is devoted to studying the evolution of Russian drama. The study is based on the Russian Drama Corpus which now contains 49 Russian plays encoded in TEI. The creation time of plays ranges from 1747 to 1925.

``` r
library(tidyverse)
library(plotly)
library(plotrix) 
setwd('/Users/IrinaPavlova/Desktop/Uni/Бакалавриат/2015-2016/Programming/github desktop/RusDraCor/Calculating_stuff_in_plays')
data = read.csv('calculations.csv')
data = data.frame(data)
data
```

### This graph shows how the number of characters in plays was changing from 1750 to 1950. The observations are the mean number of characters in plays of a particular year.

``` r
aggregate(data[, 4], list(Year_of_creation=data$Year_of_creation), mean) %>%
ggplot(aes(Year_of_creation, x)) +
  geom_point() + geom_line() + scale_x_continuous(breaks=seq(1700, 1950, 50)) +
  labs(title='Number of characters in Russian drama',
       x='Number of characters', y='Year of creation')
```

![](Visualization_files/figure-markdown_github/unnamed-chunk-2-1.png)