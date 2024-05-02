# Comptext24: Intro to Web Scraping (in R)


This is the course material for the *Intro to Web Scraping (in R)* workshop at the 2024 COMPTEXT meeting at the Vrije Universiteit (VU), Amsterdam, May 2nd 2024.

# Get the material

You can either clone this repository (if you know how to do that) or download all material as a zip file.
To download as a zip:

- click [here](https://github.com/JBGruber/comptext_webscraping_workshop/archive/refs/heads/main.zip) to download the repository as a zip file
- unzip the file to a location of your choosing
- if you have RStudio installed, open the file “comptext_webscraping_workshop.Rproj” or open the directory with VSCodium

The source code of the entire workshop is located in “comptext_webscraping_workshop.qmd”. This contains all slides, exercises, code etc. “comptext_webscraping_workshop.html” is the rendered version. During the workshop, I will jump back and forth between the rendered slides and source code, to demonstrate things live.

# Required software

You should have several software applications installed o follow along in the workshop:

- [R](https://cran.r-project.org/)
- [RStudio Desktop](https://posit.co/download/rstudio-desktop/) or [VSCodium](https://vscodium.com/) or [VSCodium](https://code.visualstudio.com/download) or another IDE if you insist.
- [Quarto](https://quarto.org/docs/get-started/)

The course uses the base pipe character (`|>`) which **is only available in `R` version 4.1.0+**.
If you still use an older version of `R`, we recommend that you update it.
Since the newer version is not compatible with old installations of `R`, you will have to install all your old packages again.
You can use a small function for this, which guides you through retrieving your old packages, from this [Github gist](https://gist.github.com/JBGruber/28c79af6d5f9015370feef31da2cb1da):

``` r
source("https://gist.githubusercontent.com/JBGruber/28c79af6d5f9015370feef31da2cb1da/raw/8165f560fc53647e3456ba661fc65d0244ac437c/get_old_packages.R")
get_old_packages()
```

To install all packages used in the workshop, simply use the code below:

``` r
if (!requireNamespace("rlang", quietly = TRUE)) install.packages("rlang", dependencies = TRUE)
rlang::check_installed("attachment")
used_pkgs <- attachment::att_from_qmd("comptext_webscraping_workshop.qmd")
rlang::check_installed("remotes")
if (!rlang::is_installed("paperboy")) remotes::install_github("JBGruber/paperboy")
if (!rlang::is_installed("traktok")) remotes::install_github("JBGruber/traktok")
rlang::check_installed(used_pkgs)
```
