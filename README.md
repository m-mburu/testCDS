TEST CDS
================

## CDS test for Sorting methods

- In python

``` python
def selection_sort(arr):
    for i in range(len(arr)):
        min_index = i
        for j in range(i+1, len(arr)):
            if arr[j] < arr[min_index]:
                min_index = j
        arr[i], arr[min_index] = arr[min_index], arr[i]
    return arr
  
mylist = [3, 6, 8, 10, 1, 2, 1]

print(selection_sort(mylist))
```

    ## [1, 1, 2, 3, 6, 8, 10]

## Bubble Sort

``` python

def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(0, n-i-1):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]
    return arr
```

## Plot

- Iris data set in R

``` r
library(ggplot2)
data(iris)
ggplot(iris, aes(x = Sepal.Length, y = Sepal.Width, color = Species)) + 
  geom_point()
```

![](README_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->

``` r
write.csv(iris, "iris.csv")
```

- use matplotlib in python

``` python
import matplotlib.pyplot as plt
import pandas as pd
iris = pd.read_csv("iris.csv")
#Define colors for each species
color_map = {
    "setosa": "red",
    "versicolor": "green",
    "virginica": "blue"
}

# Map species to colors
colors = iris["Species"].map(color_map)

# Plot
plt.figure(figsize=(8, 6))
plt.scatter(iris["Sepal.Length"], iris["Sepal.Width"], c=colors)
plt.xlabel("Sepal Length")
plt.ylabel("Sepal Width")
plt.title("Sepal Length vs Sepal Width by Species")
plt.legend(handles=[
    plt.Line2D([0], [0], marker='o', color='w', label='setosa', markerfacecolor='red', markersize=10),
    plt.Line2D([0], [0], marker='o', color='w', label='versicolor', markerfacecolor='green', markersize=10),
    plt.Line2D([0], [0], marker='o', color='w', label='virginica', markerfacecolor='blue', markersize=10)
])
plt.show()
```

## Linear Models

- Use mtcars dataset

``` r
data(mtcars)

model <- lm(mpg ~ hp, data = mtcars)

summary(model)
```

    ## 
    ## Call:
    ## lm(formula = mpg ~ hp, data = mtcars)
    ## 
    ## Residuals:
    ##     Min      1Q  Median      3Q     Max 
    ## -5.7121 -2.1122 -0.8854  1.5819  8.2360 
    ## 
    ## Coefficients:
    ##             Estimate Std. Error t value Pr(>|t|)    
    ## (Intercept) 30.09886    1.63392  18.421  < 2e-16 ***
    ## hp          -0.06823    0.01012  -6.742 1.79e-07 ***
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 3.863 on 30 degrees of freedom
    ## Multiple R-squared:  0.6024, Adjusted R-squared:  0.5892 
    ## F-statistic: 45.46 on 1 and 30 DF,  p-value: 1.788e-07

## T-test

``` r
t_test_result <- t.test(mpg ~ am, data = mtcars)

print(t_test_result)
```

    ## 
    ##  Welch Two Sample t-test
    ## 
    ## data:  mpg by am
    ## t = -3.7671, df = 18.332, p-value = 0.001374
    ## alternative hypothesis: true difference in means between group 0 and group 1 is not equal to 0
    ## 95 percent confidence interval:
    ##  -11.280194  -3.209684
    ## sample estimates:
    ## mean in group 0 mean in group 1 
    ##        17.14737        24.39231
