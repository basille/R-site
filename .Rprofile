## Only in interactive sessions
if (interactive()) {

    ## Global options:
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

    ## Conflict resolution with `conflicted`:
    ## require("conflicted", quietly = TRUE)

    ## Load `basr`:
    require("basr", quietly = TRUE)
    ## Load packages at the start of R if the package list exists:
    basr:::.loadpkglist()

    ## Print a fortune with `cowsay` & `fortunes` (in interactive sessions):
    if (require("cowsay", quietly = TRUE) & require("fortunes", quietly = TRUE))
        cowsay::say(what = "fortune",
            by = sample(cowsay::animals[!(cowsay::animals %in%
                 c("shortcat", "longcat", "fish", "signbunny", "stretchycat",
                     "anxiouscat", "longtailcat", "grumpycat", "mushroom"))], 1))

    ## Credentials for ORCiD:
    ## The file .ORCiD contains a single line with the ORCiD token:
    ## options(orcid_token = "xxxx-xxxx")
    source("~/.R-site/.ORCiD")

    ## Credentials for GBIF
    ## The file .ORCiD contains three lines with the GBIF user account:
    ## Sys.setenv(GBIF_USER = "<user>",
    ##            GBIF_PWD = "<password>",
    ##            GBIF_EMAIL = "<email>")
    source("~/.R-site/.GBIF")
}
