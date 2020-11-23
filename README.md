<!-- README.md is generated from README.Rmd. Please edit that file -->

    ## Loading required package: ggplot2

    ## Warning: package 'ggplot2' was built under R version 4.0.2

# nmfspalette

an R color palette for `ggplot2` using NOAA Fisheries official colors

-----

This implements these
[steps](https://drsimonj.svbtle.com/creating-corporate-colour-palettes-for-ggplot2)
to create a `ggplot2` compatible palette according to NOAA Fisheries
branding.

## Installation

To install from Github use the following:

``` r
remotes::install_github("nmfs-general-modeling-tools/nmfspalette")
#> Using github PAT from envvar GITHUB_PAT
#> Skipping install of 'nmfspalette' from a github remote, the SHA1 (f3b1f467) has not changed since last install.
#>   Use `force = TRUE` to force installation
library(nmfspalette)
```

Examples using the built-in color palettes. These are named oceans
(default), waves, seagrass, urchin, coral, regional web, and secondary.

## Usage

Extract an interpolated color palette from the default “oceans” palette

``` r
nmfspalette::nmfs_palette("oceans")(10)
#>  [1] "#0093D0" "#007EC1" "#0069B2" "#0055A4" "#005097" "#004B8B" "#00467F"
#>  [8] "#5483A9" "#A9C1D4" "#FFFFFF"
```

If no argument is given to scale\_color\_nmfs(), default “oceans” is
used

`{r, default_plot) p <- ggplot(iris, aes(Sepal.Width, Sepal.Length,
color = Species)) + geom_point(size = 4) + scale_color_nmfs() p`

`scale_fill_nmfs` requires a named argument for now, this is an example
using the crustacean palette

``` r
ggplot(mpg, aes(manufacturer, fill = manufacturer)) +
    geom_bar() +
    theme(axis.text.x = element_text(angle = 45, hjust = 1)) +
    scale_fill_nmfs(palette = "crustacean")
```

![](figure/scale_fill_example-1.png)<!-- -->

-----

## Disclaimer

“The United States Department of Commerce (DOC) GitHub project code is
provided on an ‘as is’ basis and the user assumes responsibility for its
use. DOC has relinquished control of the information and no longer has
responsibility to protect the integrity, confidentiality, or
availability of the information. Any claims against the Department of
Commerce stemming from the use of its GitHub project will be governed by
all applicable Federal law. Any reference to specific commercial
products, processes, or services by service mark, trademark,
manufacturer, or otherwise, does not constitute or imply their
endorsement, recommendation or favoring by the Department of Commerce.
The Department of Commerce seal and logo, or the seal and logo of a DOC
bureau, shall not be used in any manner to imply endorsement of any
commercial product or activity by DOC or the United States Government.”

  - This project code is made available through GitHub but is managed by
    NOAA at
    <https://vlab.ncep.noaa.gov/redmine/projects/integrated-fisheries-toolbox/files>

-----
