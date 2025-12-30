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

``` r
cat("NLS capability:", capabilities("NLS"), "\n\n")
#> NLS capability: TRUE

cat("ENV:\n")
#> ENV:
print(Sys.getenv(c("LANGUAGE", "LC_ALL", "LC_MESSAGES", "LANG")))
#>    LANGUAGE      LC_ALL LC_MESSAGES        LANG 
#>        "bg"          ""          ""   "C.UTF-8"
cat("\nLOCALE:\n")
#> 
#> LOCALE:
print(Sys.getlocale())
#> [1] "LC_CTYPE=C.UTF-8;LC_NUMERIC=C;LC_TIME=C.UTF-8;LC_COLLATE=C.UTF-8;LC_MONETARY=C.UTF-8;LC_MESSAGES=C.UTF-8;LC_PAPER=C.UTF-8;LC_NAME=C;LC_ADDRESS=C;LC_TELEPHONE=C;LC_MEASUREMENT=C.UTF-8;LC_IDENTIFICATION=C"

cat("\nl10n_info():\n")
#> 
#> l10n_info():
print(l10n_info())
#> $MBCS
#> [1] TRUE
#> 
#> $`UTF-8`
#> [1] TRUE
#> 
#> $`Latin-1`
#> [1] FALSE
#> 
#> $codeset
#> [1] "UTF-8"
```

``` r
ok <- Sys.setlocale("LC_MESSAGES", "bg_BG.UTF-8")
ok
#> [1] "bg_BG.UTF-8"
hello()
#> [1] "Здравей!"

Sys.setlocale("LC_ALL", "bg_BG.UTF-8")
#> [1] "LC_CTYPE=bg_BG.UTF-8;LC_NUMERIC=C;LC_TIME=bg_BG.UTF-8;LC_COLLATE=bg_BG.UTF-8;LC_MONETARY=bg_BG.UTF-8;LC_MESSAGES=bg_BG.UTF-8;LC_PAPER=C.UTF-8;LC_NAME=C;LC_ADDRESS=C;LC_TELEPHONE=C;LC_MEASUREMENT=C.UTF-8;LC_IDENTIFICATION=C"
hello()
#> [1] "Здравей!"

Sys.setenv(
  LANG = "bg_BG.UTF-8",
  LC_MESSAGES = "bg_BG.UTF-8",
  LANGUAGE = "bg"
)
hello()
#> [1] "Здравей!"
```
