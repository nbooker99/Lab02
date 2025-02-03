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

Unlike the box plots, the violin plots show the shape of the
distribution. This allows one to visualize, for example, whether the
distribution is multimodal (more than one peak). Unlike a violin plot,
box plots explicitly mark the first and third quartiles, the median, and
outliers of each distribution.

``` r
ggplot(
  data = plastic_waste,
  mapping = aes(
    x = continent,
    y = plastic_waste_per_cap
  )
) +
  geom_violin()
```

    ## Warning: Removed 51 rows containing non-finite outside the scale range
    ## (`stat_ydensity()`).

![](lab-02_files/figure-gfm/plastic-waste-violin-1.png)<!-- -->

### Exercise 4

The scatterplot below visualizes the relationship between plastic waste
per capita and mismanaged plastic waste per capita. There seems to be an
overall positive correlation. Also, there seems to be more variance in
mismanaged plastic waste than in overall plastic waste (though they are
visualized in different scales, so this may be misleading).

``` r
ggplot(data = plastic_waste, mapping = aes(x = plastic_waste_per_cap, y = mismanaged_plastic_waste_per_cap)) + geom_point()
```

    ## Warning: Removed 51 rows containing missing values or values outside the scale range
    ## (`geom_point()`).

![](lab-02_files/figure-gfm/plastic-waste-mismanaged-1.png)<!-- -->

There seems to be an overall postive correlation between plastic waste
per capita and mismanage plastic waste per capita. However, some
continents seem to have a larger correlation. For instance, when
comparing Africa to North America, it seems that as plastic waste per
capita increases, mismanaged plastic saste per capita increases more
quickly in Africa than it does in North America.

``` r
ggplot(data = plastic_waste, mapping = aes(x = plastic_waste_per_cap, y = mismanaged_plastic_waste_per_cap, color = continent)) + geom_point()
```

    ## Warning: Removed 51 rows containing missing values or values outside the scale range
    ## (`geom_point()`).

![](lab-02_files/figure-gfm/plastic-waste-mismanaged-continent-1.png)<!-- -->

There seems to be more variance in countries’ coastal populations than
there is countries’ total population, but there doesn’t seem to be any
notable differences in the relationship between the two of these
variables and plastic waste per capita.

``` r
ggplot(data = plastic_waste, mapping = aes(x = plastic_waste_per_cap, y = total_pop, color = continent)) + geom_point()
```

    ## Warning: Removed 61 rows containing missing values or values outside the scale range
    ## (`geom_point()`).

![](lab-02_files/figure-gfm/plastic-waste-population-total-1.png)<!-- -->

``` r
ggplot(data = plastic_waste, mapping = aes(x = plastic_waste_per_cap, y = coastal_pop, color = continent)) + geom_point()
```

    ## Warning: Removed 51 rows containing missing values or values outside the scale range
    ## (`geom_point()`).

![](lab-02_files/figure-gfm/plastic-waste-population-coastal-1.png)<!-- -->

### Exercise 5

Remove this text, and add your answer for Exercise 5 here.

``` r
# insert code here
```
