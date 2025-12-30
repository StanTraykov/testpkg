# test

``` r
library(testpkg)
```

``` r
hello()
#> [1] "Hello"
Sys.setLanguage("bg")
hello()
#> [1] "Hello"
Sys.setenv(LANGUAGE = "bg")
hello()
#> [1] "Hello"
```
