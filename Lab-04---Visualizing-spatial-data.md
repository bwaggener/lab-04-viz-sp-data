Lab 04 - La Quinta is Spanish for next to Denny’s, Pt. 1
================
Ben Waggener
2/07/2025

### Load packages and data

``` r
library(tidyverse) 
library(dsbox) 
```

``` r
states <- read_csv("data/states.csv")
```

### Exercise 1

“What are the dimensions of the Denny’s dataset? (Hint: Use inline R
code and functions like nrow and ncol to compose your answer.) What does
each row in the dataset represent? What are the variables?”

``` r
glimpse(dennys)
```

    ## Rows: 1,643
    ## Columns: 6
    ## $ address   <chr> "2900 Denali", "3850 Debarr Road", "1929 Airport Way", "230 …
    ## $ city      <chr> "Anchorage", "Anchorage", "Fairbanks", "Auburn", "Birmingham…
    ## $ state     <chr> "AK", "AK", "AK", "AL", "AL", "AL", "AL", "AL", "AL", "AL", …
    ## $ zip       <chr> "99503", "99508", "99701", "36849", "35207", "35294", "35056…
    ## $ longitude <dbl> -149.8767, -149.8090, -147.7600, -85.4681, -86.8317, -86.803…
    ## $ latitude  <dbl> 61.1953, 61.2097, 64.8366, 32.6033, 33.5615, 33.5007, 34.206…

``` r
nrow(dennys)
```

    ## [1] 1643

``` r
ncol(dennys)
```

    ## [1] 6

There are 1,643 rows in the Dennys dataset which represents individual
Dennys locations. There are 6 columns which represents the variables
that describe the location.

### Exercise 2

“What are the dimensions of the La Quinta’s dataset? What does each row
in the dataset represent? What are the variables?”

``` r
glimpse(laquinta)
```

    ## Rows: 909
    ## Columns: 6
    ## $ address   <chr> "793 W. Bel Air Avenue", "3018 CatClaw Dr", "3501 West Lake …
    ## $ city      <chr> "\nAberdeen", "\nAbilene", "\nAbilene", "\nAcworth", "\nAda"…
    ## $ state     <chr> "MD", "TX", "TX", "GA", "OK", "TX", "AG", "TX", "NM", "NM", …
    ## $ zip       <chr> "21001", "79606", "79601", "30102", "74820", "75254", "20345…
    ## $ longitude <dbl> -76.18846, -99.77877, -99.72269, -84.65609, -96.63652, -96.8…
    ## $ latitude  <dbl> 39.52322, 32.41349, 32.49136, 34.08204, 34.78180, 32.95164, …

``` r
nrow(laquinta)
```

    ## [1] 909

``` r
ncol(laquinta)
```

    ## [1] 6

There are 909 rows in the La Quinta dataset which represent individual
La Quintas. There are 6 columns that represent the variables that
describe the location of each hotel.

### Exercise 3

Looking at the webpages, I saw that there are no Dennys outside of the
United States while there are La Quintas outside of the United States.

This includes locations Canada, Mexico, China, New Zealand, Turkey, UAE,
Chile, Colombia, and Ecuador. …

### Exercise 4

Filtering using the state variable might be the best way to tell if
there are locations outside of the US because as far as I can tell these
are unique to America. For a rough method maybe you could set a boundary
with the lines of longitude and latitude but I don’t know if that would
be precise enough to capture the entire United states and not
accidentally include hotels in Mexico or Canada.

…

### Exercise 5

“Find the Denny’s locations that are outside the US, if any. To do so,
filter the Denny’s locations for observations where state is not in
states$abbreviation. The code for this is given below. Note that the %in% operator matches the states listed in the state variable to those listed in states$abbreviation.
The ! operator means not. Are there any Denny’s locations outside the
US?”

``` r
dennys %>%
  filter(!(state %in% states$abbreviation))
```

    ## # A tibble: 0 × 6
    ## # ℹ 6 variables: address <chr>, city <chr>, state <chr>, zip <chr>,
    ## #   longitude <dbl>, latitude <dbl>

…

### Exercise 6

…

Add exercise headings as needed.
