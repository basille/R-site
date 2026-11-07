## Options: CRAN mirror, papersize (letter), no tcltk, styler
options(
    ## Use closest CRAN mirror automatically:
    repos = c(CRAN = "https://cloud.r-project.org/"),
    ## Paper size is A4:
    papersize = "a4",
    ## No graphic menu with Tcl/Tk:
    menu.graphics = FALSE,
    ## Display 10 significant digits by default (instead of 7):
    digits = 10,
    ## Cache for styler
    styler.cache_root = "styler"
)

## Conflict resolution with conflicted:
require("conflicted", quietly = TRUE)

## Load basr:
require("basr", quietly = TRUE)

## Print a fortune:
if (require("cowsay", quietly = TRUE) & require("fortunes", quietly = TRUE))
    cowsay::say(what = "fortune",
        by = sample(cowsay::animals[!(cowsay::animals %in%
                 c("shortcat", "longcat", "fish", "signbunny", "stretchycat",
                     "anxiouscat", "longtailcat", "grumpycat", "mushroom"))], 1))

## Identifications: ORCiD & GBIF
source("~/.R-site/.ORCiD")
source("~/.R-site/.GBIF")
