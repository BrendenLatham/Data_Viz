Iris
================
Brenden Latham
1/13/2022

# The Iris Dataset

## Brenden Latham

``` r
df <- read.csv('https://raw.githubusercontent.com/nurfnick/Data_Viz/main/iris.csv')
head(df)
```

    ##   SepalLength SepalWidth PedalLength PedalWidth       Class
    ## 1         5.1        3.5         1.4        0.2 Iris-setosa
    ## 2         4.9        3.0         1.4        0.2 Iris-setosa
    ## 3         4.7        3.2         1.3        0.2 Iris-setosa
    ## 4         4.6        3.1         1.5        0.2 Iris-setosa
    ## 5         5.0        3.6         1.4        0.2 Iris-setosa
    ## 6         5.4        3.9         1.7        0.4 Iris-setosa

``` r
df_class <- df %>% select('Class')
ggplot2::ggplot(data=plyr::count(df), aes(x=Class)) + geom_bar()
```

![](Iris_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->

``` r
table(df$Class)
```

    ## 
    ##     Iris-setosa Iris-versicolor  Iris-virginica 
    ##              50              50              50

``` r
ggplot2::ggplot(data=df,aes(x=PedalWidth)) + geom_histogram(bins=25)
```

![](Iris_files/figure-gfm/unnamed-chunk-5-1.png)<!-- -->

``` r
ggplot2::ggplot(data=df,aes(y=PedalWidth, color=Class)) + geom_boxplot()
```

![](Iris_files/figure-gfm/unnamed-chunk-6-1.png)<!-- -->

``` r
ggplot2::ggplot(data=df,aes(x=Class, y=PedalWidth, color=Class)) + geom_violin()
```

![](Iris_files/figure-gfm/unnamed-chunk-7-1.png)<!-- -->

``` r
min(df$PedalWidth)
```

    ## [1] 0.1

``` r
mean(df$PedalWidth)
```

    ## [1] 1.198667

``` r
max(df$PedalWidth)
```

    ## [1] 2.5
