
<!-- README.md is generated from README.Rmd. Please edit that file -->
ukpolice
========

[![AppVeyor Build Status](https://ci.appveyor.com/api/projects/status/github/njtierney/ukpolice?branch=master&svg=true)](https://ci.appveyor.com/project/njtierney/ukpolice)[![Travis-CI Build Status](https://travis-ci.org/njtierney/ukpolice.svg?branch=master)](https://travis-ci.org/njtierney/ukpolice)[![Coverage Status](https://img.shields.io/codecov/c/github/njtierney/ukpolice/master.svg)](https://codecov.io/github/njtierney/ukpolice?branch=master)

ukpolice is an R package that facilitates retrieving data from the [UK police database.](https://data.police.uk/)

This package is in a very beta stage, and I'm still learning a lot about APIs!

Installation
============

Install from GitHub

``` r

#install.packages("devtools")
devtools::install_github("njtierney/ukpolice")
```

Usage
=====

`ukp_neighbourhood`, retrieves a list of neighbourhoods for a force, <https://data.police.uk/docs/method/neighbourhoods/>

This returns a tibble with columns `id` and `name`.

``` r

library(ukpolice)
ukp_neighbourhood("leicestershire")
#> No encoding supplied: defaulting to UTF-8.
#> # A tibble: 67 × 2
#>       id                           name
#>    <chr>                          <chr>
#> 1   NC04                    City Centre
#> 2   NC66               Cultural Quarter
#> 3   NC67                      Riverside
#> 4   NC68                 Clarendon Park
#> 5   NE09                 Belgrave South
#> 6   NE10                 Belgrave North
#> 7   NE11                    Rushey Mead
#> 8   NE12                    Humberstone
#> 9   NE13 Northfields, Tailby and Morton
#> 10  NE14                     Thurncourt
#> # ... with 57 more rows
```

-   `id` is a Police force specific team identifier, (note that this identifier is not unique and may also be used by a different force).
-   `name` is the name for the neighbourhood.

`ukp_crime_street_point` draws crimes from within a one mile radius.

``` r

ukp_crime_street_point(lat = 52.629729, lng = -1.131592)
#> No encoding supplied: defaulting to UTF-8.
#> Warning in bind_rows_(x, .id): Unequal factor levels: coercing to character

#> Warning in bind_rows_(x, .id): Unequal factor levels: coercing to character

#> Warning in bind_rows_(x, .id): Unequal factor levels: coercing to character

#> Warning in bind_rows_(x, .id): Unequal factor levels: coercing to character

#> Warning in bind_rows_(x, .id): Unequal factor levels: coercing to character

#> Warning in bind_rows_(x, .id): Unequal factor levels: coercing to character

#> Warning in bind_rows_(x, .id): Unequal factor levels: coercing to character

#> Warning in bind_rows_(x, .id): Unequal factor levels: coercing to character

#> Warning in bind_rows_(x, .id): Unequal factor levels: coercing to character

#> Warning in bind_rows_(x, .id): Unequal factor levels: coercing to character

#> Warning in bind_rows_(x, .id): Unequal factor levels: coercing to character

#> Warning in bind_rows_(x, .id): Unequal factor levels: coercing to character

#> Warning in bind_rows_(x, .id): Unequal factor levels: coercing to character
#> # A tibble: 1,386 × 13
#>                 category context       id location_subtype location_type
#>                    <chr>   <chr>    <chr>            <chr>         <chr>
#> 1  anti-social-behaviour         50559804                          Force
#> 2  anti-social-behaviour         50565912                          Force
#> 3  anti-social-behaviour         50562730                          Force
#> 4  anti-social-behaviour         50562692                          Force
#> 5  anti-social-behaviour         50562689                          Force
#> 6  anti-social-behaviour         50562680                          Force
#> 7  anti-social-behaviour         50565899                          Force
#> 8  anti-social-behaviour         50559811                          Force
#> 9  anti-social-behaviour         50559816                          Force
#> 10 anti-social-behaviour         50562670                          Force
#> # ... with 1,376 more rows, and 8 more variables: latitude <chr>,
#> #   longitude <chr>, street_id <chr>, street_name <chr>, date <chr>,
#> #   persistent_id <chr>, outcome_category <chr>, outcome_date <chr>
```

This is still a little buggy at the moment as it returns blank columns, but this is a work in progress!

Contributor Code of Conduct
===========================

As contributors and maintainers of this project, we pledge to respect all people who contribute through reporting issues, posting feature requests, updating documentation,submitting pull requests or patches, and other activities.

We are committed to making participation in this project a harassment-free experience for everyone, regardless of level of experience, gender, gender identity and expression, sexual orientation, disability, personal appearance, body size, race, ethnicity, age, or religion.

Examples of unacceptable behavior by participants include the use of sexual language or imagery, derogatory comments or personal attacks, trolling, public or private harassment, insults, or other unprofessional conduct.

Project maintainers have the right and responsibility to remove, edit, or reject comments, commits, code, wiki edits, issues, and other contributions that are not aligned to this Code of Conduct. Project maintainers who do not follow the Code of Conduct may be removed from the project team.

Instances of abusive, harassing, or otherwise unacceptable behavior may be reported by opening an issue or contacting one or more of the project maintainers.

This Code of Conduct is adapted from the Contributor Covenant (<http:contributor-covenant.org>), version 1.0.0, available at <http://contributor-covenant.org/version/1/0/0/>
