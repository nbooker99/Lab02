Lab 02 - Plastic waste
================
Noah Booker
01/29/25

## Load packages and data

``` r
library(tidyverse)
```

``` r
plastic_waste <- read.csv("data/plastic-waste.csv")
```

## Exercises

### Exercise 1

Below are histograms plotting the distribution of plastic waste per
capita faceted by continent. The majority of all continents’
distributions of plastic waste per capita fall between 0 and .5 kg/day.
For those continents which have countries with a plastic waste per
capita above .5 kg/day, it seems that North America has the most
followed by South America and Asia tied for second place.

``` r
ggplot(data = plastic_waste, aes(x = plastic_waste_per_cap)) +
    geom_histogram(binwidth = 0.2) + facet_wrap(~continent)
```

    ## Warning: Removed 51 rows containing non-finite outside the scale range
    ## (`stat_bin()`).

![](lab-02_files/figure-gfm/plastic-waste-continent-1.png)<!-- -->

### Exercise 2

Below, we define the color and fill of the curves by mapping aesthetics
of the plot but define the alpha level as a characteristic of the
plotting geom because we want color and fill to vary according to the
data (by continent) but want the alpha level (transparency) to be
applied the same way all the density curves.

``` r
ggplot(
  data = plastic_waste,
  mapping = aes(
    x = plastic_waste_per_cap,
    color = continent,
    fill = continent
  )
) +
  geom_density(alpha = 0.2)
```

    ## Warning: Removed 51 rows containing non-finite outside the scale range
    ## (`stat_density()`).

![](lab-02_files/figure-gfm/plastic-waste-density-1.png)<!-- -->

### Exercise 3

Remove this text, and add your answer for Exercise 3 here.

``` r
# insert code here
```

### Exercise 4

Remove this text, and add your answer for Exercise 4 here.

``` r
# insert code here
```

``` r
# insert code here
```

``` r
# insert code here
```

``` r
# insert code here
```

### Exercise 5

Remove this text, and add your answer for Exercise 5 here.

``` r
# insert code here
```
