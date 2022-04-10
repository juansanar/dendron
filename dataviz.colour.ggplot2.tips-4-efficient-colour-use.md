---
id: u0tklg6dmyqb3yfl5frl538
title: Tips 4 Efficient Colour Use
desc: ''
updated: 1649552774016
created: 1649523804124
tags:
  - colour
  - dataviz
  - ggplot2
---

## Useful packages

- [`thematic`](https://rstudio.github.io/thematic/)
    - Simplified theming of ggplot2, lattice, and {base} R graphics. In addition to providing a centralized approach to styling R graphics, thematic also enables automatic styling of R plots in Shiny, R Markdown, and RStudio.
    - Works well with [[showtext | dataviz.text.ggplot2.showtext]] and `ragg`.

## Some useful principles

#### Show shades, not hues

When dealing with multiple factors, group the factors within higher level factors (use as hues by mapping it to `fill`) and visualize the lower level factors as shades (by mapping it to `alpha`).

##### Example 1

```r
# Group classes into three groups (to reduce colors to 3)
dat <- mpg %>% 
  mutate(
    year = factor(year),
    class_group = case_when(
      class %in% c('2seater', 'compact', 'midsize') ~ "grp1",
      class == 'minivan' ~ "grp2",
      T ~ "grp3"
    )
  )

# Plot
shades_plt <- dat %>% 
  ggplot(aes(x = year, fill = class_group, alpha = class)) +
  geom_bar() +
  labs(
    x = 'Year',
    y = 'Counts',
    alpha = 'Class',
    title = 'Show shades, not hues'
  )
shades_plt 
```
![](https://albert-rapp.de/post/2022-02-19-ggplot2-color-tips-from-datawrapper/index_files/figure-html/unnamed-chunk-5-1.png)

#### Additional control of fill and alpha and a sprinkle of colour

```r
# Color-blind safe colors
colors <-  thematic::okabe_ito(3)
# Possible levels of transparency (one for each class)
alpha_max <- 1
alpha_min <- 0.7
alpha_vals <- c(
  seq(alpha_max, alpha_min, length.out = 4), 
  seq(alpha_min, alpha_max, length.out = 4)[-1]
)
alpha_vals
## [1] 1.0 0.9 0.8 0.7 0.8 0.9 1.0

# Tweak previous plot
shades_plt <- shades_plt +
  scale_fill_manual(values = colors) +
  scale_alpha_manual(values = alpha_vals)
shades_plt
```
![](https://albert-rapp.de/post/2022-02-19-ggplot2-color-tips-from-datawrapper/index_files/figure-html/unnamed-chunk-6-1.png)

To enahnce differentiation of the different groups, adjusting the value of `colour` in `geom_bar` will add a border (of a given colour/HEX value) to the bars.

```r
dat %>% 
  ggplot(aes(x = year, fill = class_group, alpha = class)) +
  geom_bar(col = 'white') + # Add lines for distinction
  scale_fill_manual(values = colors) +
  scale_alpha_manual(values = alpha_vals) +
  guides(
    fill = guide_none(),
    alpha = guide_legend(override.aes = list(fill = colors[c(1, 1, 1, 2, 3, 3, 3)]))
  ) +
  labs(
    x = 'Year',
    y = 'Counts',
    alpha = 'Class',
    title = 'Group categories together by color, \nbut keep showing them'
  )

```
![](https://albert-rapp.de/post/2022-02-19-ggplot2-color-tips-from-datawrapper/index_files/figure-html/unnamed-chunk-8-1.png)

#### Consolidating legends

With the function `guie`, legends can be consolidated.

Below, `guide_none()` removes the legend for the higher group (used for `fill`). A new legednt that incorporates the custom `fill` and `alpha` into one using `override.aes` and `guide.legend`.

```r
shades_plt <- shades_plt +
  guides(
    fill = guide_none(),
    alpha = guide_legend(
      override.aes = list(fill = colors[c(1, 1, 1, 2, 3, 3, 3)]
      )
    )
  ) 
shades_plt
```

### Highlighting traces within timeseries data

Made super easy with the [`gghighlight` package](https://yutannihilation.github.io/gghighlight/).

#### Example 2

```r
# p  is a timeseries plot
# Line plot
p <- time_data %>% 
  ggplot(aes(x = age, y = minutes, col = person)) +
  geom_line(size = 1.5) +
  scale_color_manual(values = colors) +
  coord_cartesian(xlim = c(15, 81), expand = F) +
  scale_y_continuous(minor_breaks = NULL) +
  labs(x = 'Age (in years)', y = 'Minutes', col = 'Time spent')
p
library(gghighlight)
alone_plt <- p + 
  gghighlight(person == 'alone', use_direct_label = F) +
  labs(title = 'Emphasize just one or a few categories')
alone_plt
```

| ![](https://albert-rapp.de/post/2022-02-19-ggplot2-color-tips-from-datawrapper/index_files/figure-html/unnamed-chunk-9-1.png) | ![](https://albert-rapp.de/post/2022-02-19-ggplot2-color-tips-from-datawrapper/index_files/figure-html/unnamed-chunk-10-1.png) |
-----| ----|

`gghighlight` is compatible with `facet_wrap`


```r
library(gghighlight)

p <- ggplot(d) +
  geom_line(aes(idx, value, colour = type)) +
  gghighlight(max(value) > 19)

p + theme_minimal() + facet_wrap(~ type)
```
![](https://yutannihilation.github.io/gghighlight/reference/figures/README-gghighlight-theme-facets-2.png)

and can be used to highlight only certain values 

```r
library(gghighlight)

p <- ggplot(d) +
  geom_line(aes(idx, value, colour = type)) +
  gghighlight(max(value) > 19)

p
```
![](https://yutannihilation.github.io/gghighlight/reference/figures/README-gghighlight-simple-1.png)

### Annotate plots with correspoedning coloured labels/text

This will require the functions `annotate` and `geom_text` and some HTML to define the coloured-text (`<span style = 'color:HEX-colour-code;'>...</span>`).



## References

- [[ Albert Rapp. 4 Ways to use colors in ggplot more efficiently| reading-list.dataviz]]. [URL](https://albert-rapp.de/post/2022-02-19-ggplot2-color-tips-from-datawrapper/)
