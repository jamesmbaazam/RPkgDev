James Azam

<!-- badges: start -->

[![R-CMD-check](https://github.com/jamesmbaazam/rpkg_wf/actions/workflows/R-CMD-check.yaml/badge.svg)](https://github.com/jamesmbaazam/rpkg_wf/actions/workflows/R-CMD-check.yaml)
<!-- badges: end -->

# _RPkgDev_: a compendium of resources for developing R packages.

RPkgDev provides a “list” of some of the most commonly used R commands
(mostly from [devtools](https://devtools.r-lib.org/) and
[usethis](https://usethis.r-lib.org/) for developing R packages. This
package is basically a summary of the commands from Hadley Wickham’s [R
Packages 2e](https://r-pkgs.org/) book.

For more comprehensive explanations of the commands, please check their
help files or the book

## DESCRIPTION file

Add a package to “Imports” or “Suggests” with
`usethis::use_package(<name of package>)`. For example:

``` r
usethis::use_package('rmarkdown', type = 'Suggests')
```

In general, to order and format DESCRIPTION fields according to a fixed
standard, run

``` r
usethis::use_tidy_description()
```

## Package README and vignettes

Use rmd instead of md for README

``` r
usethis::use_readme_rmd()
```

### Create a new rmd file for a vignette

``` r
usethis::use_vignette("my_vignette")
```

### Build README.Rmd manually

``` r
devtools::build_readme()
```

### Build README.Rmd with Github Actions

``` r
use_github_action("render-readme.yaml")
```

## Package build

Build and check package using all known best practices

``` r
devtools::check()
```

### Check package using all known best practices

``` r
goodpractice::gp()
```

## Package releases

Use the command below to increment the package version

``` r
usethis::use_version()
```

### Lifecycle

You can get much more detail in

``` r
vignette("stages", package = "lifecycle").
```

The lifecycle stage is often communicated through a badge. If you’d like
to use lifecycle badges, run the following to do some one-time setup:

``` r
usethis::use_lifecycle()
```

If you want to use a badge in README to indicate the lifecycle of an
entire package, call

``` r
usethis::use_lifecycle_badge()
```

If the lifecycle of a package is stable, it’s not really necessary to
use a badge, since that is the assumed default stage. Similarly, we
typically only use a badge for a function if its stage differs from that
of the associated package and likewise for an argument and the
associated function.

## Website

To do the initial website setup, run

``` r
usethis::use_pkgdown
```

To re-render your site locally, run

``` r
pkgdown::build_site()
```

## CRAN

The following command adds an issue to your repo with a checklist of
tasks to complete before submitting to CRAN:

``` r
usethis::use_release_issue(version = NULL)
```
