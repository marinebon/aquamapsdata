[![Build Status](https://travis-ci.org/raquamaps/aquamapsdata.svg?branch=master)](https://travis-ci.org/raquamaps/aquamapsdata)

<!-- README.md is generated from README.Rmd. Please edit that file -->
``` console
Welcome to ...
  _.  _.      _. ._ _   _. ._   _  _|  _. _|_  _.
 (_| (_| |_| (_| | | | (_| |_) _> (_| (_|  |_ (_|
       |                   |
```

Introduction
------------

`aquamapsdata` is an R package that can download and create a local SQLite database with datasets from AquaMaps.org (2017)

These datasets are available to web browsers through <https://aquamaps.org>, but the `aquamapsdata` package offers an a couple of convenient functions for accessing this data programmatically in an IDE like `RStudio`.

Installing from github
----------------------

If you want to install the latest version of the `aquamapsdata` package from github, you can do it like so:

``` r
# First make sure you have the devtools package
# which simplifies installations from github
# Note: Windows users have to first install Rtools to use devtools

install.packages("devtools") 

library("devtools")
install_git("https://github.com/raquamaps/aquamapsdata.git", build_vignettes=FALSE)
```

Quick start
-----------

Load the package in your R environment:

``` r

library(aquamapsdata)

download_db()

my_db <- aquamapsdata:::src_sqlite_aquamapsdata()

my_db %>% tbl("nativemaps")
my_db %>% tbl("hcaf")
my_db %>% tbl("hspen")
my_db %>% tbl("occ")
my_db %>% tbl("taxa")
```

To see some quick usage examples to get you started, open the Vignette.

The package uses SQLite3 - a portable and fast database which is included in the RSQLite package.

You can also install SQLite3 using your platform's package manager, for example using these commands:

``` console
# on linux
sudo apt install sqlite3

# on mac
brew install sqlite3
```

Credits
-------

`aquamapsdata` would have not been possible without many amazing R libraries, such as

-   "tidyverse" ie dplyr, tidyr, stringr etc from Hadley Wickham
-   rgbif etc from ROpenSci

Meta
----

-   Please [report any issues or bugs](https://github.com/raquamaps/aquamapsdata/issues).
-   License: AGPL
