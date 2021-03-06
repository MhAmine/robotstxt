
## A ‘robots.txt’ Parser and ‘Webbot’/‘Spider’/‘Crawler’ Permissions Checker

[![ropensci\_footer](https://raw.githubusercontent.com/ropensci/robotstxt/master/logo/github_footer.png)](https://ropensci.org)

**Status**

*lines of R code:* 493, *lines of test code:* 1133

[![Project Status: Active – The project has reached a stable, usable
state and is being actively
developed.](http://www.repostatus.org/badges/latest/active.svg)](http://www.repostatus.org/#active)
[![](https://badges.ropensci.org/25_status.svg)](https://github.com/ropensci/onboarding/issues/25)

<a href="https://travis-ci.org/ropensci/robotstxt">
<img src="https://api.travis-ci.org/ropensci/robotstxt.svg?branch=master">
<a/> <a href="https://cran.r-project.org/package=robotstxt">
<img src="http://www.r-pkg.org/badges/version/robotstxt"> </a>

<a href="https://codecov.io/gh/ropensci/robotstxt">
<img src="https://codecov.io/gh/ropensci/robotstxt/branch/master/graph/badge.svg" alt="Codecov" />
</a> <img src="http://cranlogs.r-pkg.org/badges/grand-total/robotstxt">
<img src="http://cranlogs.r-pkg.org/badges/robotstxt">

**Development version**

0.6.1 - 2018-02-10 / 23:06:12

**Description**

Provides functions to download and parse ‘robots.txt’ files. Ultimately
the package makes it easy to check if bots (spiders, crawler, scrapers,
…) are allowed to access specific resources on a domain.

**License**

MIT + file LICENSE <br>Peter Meissner \[aut, cre\], Oliver Keys \[ctb\],
Rich Fitz John \[ctb\]

**Citation**

``` r
citation("robotstxt")
```

**BibTex for citing**

``` r
toBibtex(citation("robotstxt"))
```

**Contribution - AKA The-Think-Twice-Be-Nice-Rule**

Please note that this project is released with a Contributor Code of
Conduct. By participating in this project you agree to abide by its
terms:

> As contributors and maintainers of this project, we pledge to respect
> all people who contribute through reporting issues, posting feature
> requests, updating documentation, submitting pull requests or patches,
> and other activities.
> 
> We are committed to making participation in this project a
> harassment-free experience for everyone, regardless of level of
> experience, gender, gender identity and expression, sexual
> orientation, disability, personal appearance, body size, race,
> ethnicity, age, or religion.
> 
> Examples of unacceptable behavior by participants include the use of
> sexual language or imagery, derogatory comments or personal attacks,
> trolling, public or private harassment, insults, or other
> unprofessional conduct.
> 
> Project maintainers have the right and responsibility to remove, edit,
> or reject comments, commits, code, wiki edits, issues, and other
> contributions that are not aligned to this Code of Conduct. Project
> maintainers who do not follow the Code of Conduct may be removed from
> the project team.
> 
> Instances of abusive, harassing, or otherwise unacceptable behavior
> may be reported by opening an issue or contacting one or more of the
> project maintainers.
> 
> This Code of Conduct is adapted from the Contributor Covenant
> (<http://contributor-covenant.org>), version 1.0.0, available at
> <http://contributor-covenant.org/version/1/0/0/>

## Installation

**Installation and start - stable version**

``` r
install.packages("robotstxt")
library(robotstxt)
```

**Installation and start - development version**

``` r
devtools::install_github("ropensci/robotstxt")
library(robotstxt)
```

## Usage

**Robotstxt class documentation**

``` r
?robotstxt
```

Simple path access right checking …

``` r
library(robotstxt)

paths_allowed(
  paths  = c("/api/rest_v1/?doc", "/w/"), 
  domain = "wikipedia.org", 
  bot    = "*"
)
## Warning: The implementation of future_lapply() in the 'future' package has been deprecated. Please use the one
## in the 'future.apply' package instead.
## 
 wikipedia.org
## [1]  TRUE FALSE

paths_allowed(
  paths = c(
    "https://wikipedia.org/api/rest_v1/?doc", 
    "https://wikipedia.org/w/"
  )
)
## Warning: The implementation of future_lapply() in the 'future' package has been deprecated. Please use the one
## in the 'future.apply' package instead.
## 
 wikipedia.org                      
 wikipedia.org
## [1]  TRUE FALSE
```

… or use it that way …

``` r
library(robotstxt)

rtxt <- robotstxt(domain = "wikipedia.org")
rtxt$check(paths = c("/api/rest_v1/?doc", "/w/"), bot= "*")
## [1]  TRUE FALSE
```

## More information

[Have a look at the vignette at
https://cran.r-project.org/package=robotstxt/vignettes/using\_robotstxt.html](https://cran.r-project.org/package=robotstxt/vignettes/using_robotstxt.html)
