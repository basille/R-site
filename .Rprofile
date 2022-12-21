### Interactive sessions
if (interactive()) {

    ## Options: CRAN mirror, papersize (letter), no tcltk, and max print
    options(
        ## Use closest CRAN mirror automatically:
        repos = c(CRAN = "https://cloud.r-project.org/"),
        ## Paper size is A4:
        papersize = "a4",
        ## No graphic menu with Tcl/Tk:
        menu.graphics = FALSE,
        ## Increase amount of information printed on screen (default is
        ## 99):
#        max.print = 999,
        ## Turn scientific notation on after ~10 digits
#        scipen = 5,
        ## Display 10 significant digits by default (instead of 7):
        digits = 10,
        ## Use multiple cores to speed up package installation:
        Ncpus = 3,
        ## Warnings for partial matching (arguments, extraction):
#        warnPartialMatchArgs = TRUE,
#        warnPartialMatchDollar = TRUE,
#        warnPartialMatchAttr = TRUE
        ## Cache for styler
        styler.cache_root = "styler"
    )

    ## Interactive sessions get a fortune cookie (needs cosway and
    ## fortunes packages)
    if (require("cowsay", quietly = TRUE))
        suppressWarnings(cowsay::say(what = "fortune",
            by = sample(names(animals)[!(names(animals) %in%
                c("shortcat", "longcat", "fish", "signbunny",
                    "stretchycat", "anxiouscat", "longtailcat",
                    "grumpycat", "mushroom"))], 1)))
    ## Work (as of Dec 8 2016)
    ##  [1] "cow"          "chicken"      "clippy"       "poop"
    ##  [5] "bigcat"       "ant"          "pumpkin"      "ghost"
    ##  [9] "spider"       "rabbit"       "pig"          "snowman"
    ## [13] "frog"         "hypnotoad"    "facecat"      "behindcat"
    ## [17] "cat"          "trilobite"    "shark"        "buffalo"
    ## [21] "smallcat"     "yoda"         "endlesshorse" "bat"
    ## [25] "bat2"
    ## Don't work:
    ## [1] "shortcat"    "longcat"     "fish"        "signbunny"   "stretchycat"
    ## [6] "anxiouscat"  "longtailcat" "grumpycat"   "mushroom"

    ## Load packages at the start of R if the package list exists
#    if (suppressPackageStartupMessages(require("basr", quietly = TRUE)))
#    {
#        basr:::.loadpkglist()
#    } else (message("The package basr is not installed. Install it with:
#
#    remotes::install_github(\"basille/basr\")"))

    ## Conflict resolution with conflicted:
#    require("conflicted", quietly = TRUE)

    ## ## Change some defaults
    ## ## Table with NAs
    ## default::default(table) <- list(useNA = "always")
    ## ## Dataframes without string as factors
    ## default::default(data.frame) <- list(stringsAsFactors = FALSE)
    ## default::default(as.data.frame.character) <- list(stringsAsFactors = FALSE)
    ## default::default(as.data.frame.list) <- list(stringsAsFactors = FALSE)
    ## default::default(as.data.frame.matrix) <- list(stringsAsFactors = FALSE)

    ## Function to install selected packages, by theme
    install.selected <- function(all = TRUE,
        spatial = all,
        moveco = all,
        tidyverse = all,
        tidymodels = FALSE,
        plotting = all,
        data = all,
        modeling = all,
        others = all,
        github = FALSE)
    {
        ## Packages on CRAN

        ## Spatial packages https://cran.r-project.org/web/views/Spatial.html
        if (spatial) {
            packages.list <- c(
                "autoimage",        # Multiple Heat Maps for Projected Coordinates
                "concaveman",       # A Very Fast 2D Concave Hull Algorithm
                "elevatr",          # Access Elevation Data from Various APIs
                "geodata",          # Download Geographic Data
                "ggspatial",        # Spatial Data Framework for ggplot2
                "gstat",            # Spatial and Spatio-Temporal Geostatistical Modelling, Prediction and Simulation
                "landscapemetrics", # Landscape Metrics for Categorical Map Patterns
                "leaflet",          # Create Interactive Web Maps with the JavaScript 'Leaflet' Library
                "lwgeom",           # Bindings to Selected 'liblwgeom' Functions for Simple Features
                "mapsf",            # Thematic Cartography
                "mapview",          # Interactive Viewing of Spatial Data in R
                "raster",           # Geographic Data Analysis and Modeling
                "rasterVis",        # Visualization Methods for Raster Data
                "RColorBrewer",     # ColorBrewer Palettes
                "rayshader",        # Create Maps and Visualize Data in 2D and 3D
                "rnaturalearth",    # World Map Data from Natural Earth
                "rnaturalearthdata", # World Vector Map Data from Natural Earth Used in 'rnaturalearth'
                "sf",               # Simple Features for R
                "sp",               # Classes and Methods for Spatial Data
                "spData",           # Datasets for spatial analysis
                "spacetime",        # Classes and Methods for Spatio-Temporal Data
                "spatstat",         # Spatial Point Pattern Analysis, Model-Fitting, Simulation, Tests
                "spdep",            # Spatial Dependence: Weighting Schemes, Statistics and Models
                "splancs",          # Spatial and Space-Time Point Pattern Analysis
                "stars",            # Spatiotemporal Arrays, Raster and Vector Data Cubes
                "terra",            # Spatial Data Analysis
                "tidyterra",        # 'tidyverse' Methods and 'ggplot2' Utils for 'terra' Objects
                "tmap"              # Thematic Maps
            )
            ## Installation of new packages (i.e. not previously installed):
            packages.new <- packages.list[!(packages.list %in% installed.packages()[,"Package"])]
            if (length(packages.new)) {
                message(paste0("Installing packages (with dependencies):\n  ", paste(packages.new, collapse = "\n  ")))
                install.packages(packages.new)
            }
            ## spDataLarge
            if (!("spDataLarge" %in% installed.packages()[,"Package"])) {
                message(paste0("Installing packages (with dependencies): spDataLarge"))
                install.packages("spDataLarge", repos = "https://nowosad.github.io/drat/", type = "source")
            }
        }

        ## adehabitat, rpostgis and friends
        if (moveco) {
            packages.list <- c(
                "adehabitatHS",      # Analysis of Habitat Selection by Animals
                "amt",               # Animal Movement Tools
                "biomod2",          # Ensemble Platform for Species Distribution Modeling
                "ctmm",              # Continuous-Time Movement Modeling
                "dismo",            # Species Distribution Modeling
                "ecospat",          # Spatial Ecology Miscellaneous Methods
                "move",              # Visualizing and Analyzing Animal Track Data
                "rpostgis",          # R Interface to a 'PostGIS' Database
                "sftrack"            # Modern Classes for Tracking and Movement Data
                ## "rpostgisLT"         # Managing Animal Movement Data with 'PostGIS' and R
            )
            ## Installation of new packages (i.e. not previously installed):
            packages.new <- packages.list[!(packages.list %in% installed.packages()[,"Package"])]
            if (length(packages.new)) {
                message(paste0("Installing packages (with dependencies):\n  ", paste(packages.new, collapse = "\n  ")))
                install.packages(packages.new)
            }
        }

        ## Tidyverse & Tidymodels
        ## As of v1.3.1 includes (2021-04-15), tidyverse installs:
        ## ** Core (automatically loaded with `library(tidyverse)`:
        ## - dplyr: A Grammar of Data Manipulation
        ## - forcats: Tools for Working with Categorical Variables (Factors)
        ## - ggplot2: Create Elegant Data Visualisations Using the Grammar of Graphics
        ## - purrr: Functional Programming Tools
        ## - readr: Read Tabular Data
        ## - stringr: Simple, Consistent Wrappers for Common String Operations
        ## - tibble: Simple Data Frames
        ## - tidyr: Easily Tidy Data with 'spread()' and 'gather()' Functions
        ## ** Import:
        ## - DBI: R Database Interface
        ## - googledrive: An Interface to Google Drive
        ## - googlesheets4: Access Google Sheets using the Sheets API V4
        ## - haven: Import and Export 'SPSS', 'Stata' and 'SAS' Files
        ## - httr: Tools for Working with URLs and HTTP
        ## - jsonlite: A Robust, High Performance JSON Parser and Generator for R
        ## - readxl: Read Excel Files
        ## - rvest: Easily Harvest (Scrape) Web Pages
        ## - xml2: Parse XML
        ## ** dplyr backends:
        ## - dbplyr: A 'dplyr' Back End for Databases
        ## - dtplyr: Data Table Back-End for 'dplyr'
        ## ** Wrangle:
        ## - blob: A Simple S3 Class for Representing Vectors of Binary Data ('BLOBS')
        ## - hms: Pretty Time of Day
        ## - lubridate: Make Dealing with Dates a Little Easier
        ## ** Program:
        ## - glue: Interpreted String Literals
        ## - magrittr: A Forward-Pipe Operator for R
        ## ** Model: use tidymodels https://www.tidymodels.org/packages/
        if (tidyverse) {
            packages.list <- c(
                "tidyverse"          # Easily Install and Load 'Tidyverse' Packages
            )
            ## Installation of new packages (i.e. not previously installed):
            packages.new <- packages.list[!(packages.list %in% installed.packages()[,"Package"])]
            if (length(packages.new)) {
                message(paste0("Installing packages (with dependencies):\n  ", paste(packages.new, collapse = "\n  ")))
                install.packages(packages.new)
            }
        }
        if (tidymodels) {
            packages.list <- c(
                "tidymodels"          # Easily Install and Load 'Tidymodels' Packages
            )
            ## Installation of new packages (i.e. not previously installed):
            packages.new <- packages.list[!(packages.list %in% installed.packages()[,"Package"])]
            if (length(packages.new)) {
                message(paste0("Installing packages (with dependencies):\n  ", paste(packages.new, collapse = "\n  ")))
                install.packages(packages.new)
            }
        }

        ## Plotting extra
        if (plotting) {
            packages.list <- c(
                "adegraphics",       # An S4 Lattice-Based Package for the Representation of Multivariate Data
                "Cairo",             # R graphics device using cairo graphics library for creating high-quality bitmap (PNG, JPEG, TIFF), vector (PDF, SVG, PostScript) and display (X11 and Win32) output
                "colorRamps",        # Builds color tables
                "cowplot",           # Streamlined Plot Theme and Plot Annotations for 'ggplot2'
                "explor",            # Interactive Interfaces for Results Exploration
                "extrafont",         # Tools for using fonts
                "geomtextpath",      # Curved Text in 'ggplot2'
                "ggalluvial",        # Alluvial Diagrams in 'ggplot2'
                "ggalt",             # Extra Coordinate Systems, Geoms, Statistical Transformations, Scales & Fonts for 'ggplot2' [requires proj4]
                "gganimate",         # A Grammar of Animated Graphics
                "ggbeeswarm",        # Categorical Scatter (Violin Point) Plots
                "ggdark",            # Dark Mode for 'ggplot2' Themes
                "ggExtra",           # Add Marginal Histograms to 'ggplot2', and More 'ggplot2' Enhancements
                "ggforce",           # Accelerating 'ggplot2'
                "ggfortify",         # Data Visualization Tools for Statistical Analysis Results
                "gghighlight",       # Highlight Lines and Points in 'ggplot2'
                "ggraph",            # An Implementation of Grammar of Graphics for Graphs and Networks
                "ggrepel",           # Repulsive Text and Label Geoms for 'ggplot2'
                "ggthemes",          # Extra Themes, Scales and Geoms for 'ggplot2'
                "ggwordcloud",       # A Word Cloud Geom for 'ggplot2'
                "gridExtra",         # Miscellaneous Functions for "Grid" Graphics
                "hexbin",            # Hexagonal Binning Routines
                "hrbrthemes",        # Additional Themes, Theme Components and Utilities for 'ggplot2'
                "factoextra",        # Extract and Visualize the Results of Multivariate Data Analyses
                "patchwork",         # The Composer of Plots
                "plotly",            # Create Interactive Web Graphics via 'plotly.js'
                "rphylopic",         # Get Silhouettes of Organisms from 'Phylopic'
                "scales",            # Scale Functions for Visualization
                "scatterpie",        # Scatter Pie Plot
                "tweenr",            # Interpolate Data for Smooth Animations
                "viridis",           # Default Color Maps from 'matplotlib'
                "wordcloud",         # Word Clouds
                "xkcd"               # Plotting ggplot2 Graphics in an XKCD Style
            )
            ## Installation of new packages (i.e. not previously installed):
            packages.new <- packages.list[!(packages.list %in% installed.packages()[,"Package"])]
            if (length(packages.new)) {
                message(paste0("Installing packages (with dependencies):\n  ", paste(packages.new, collapse = "\n  ")))
                install.packages(packages.new)
            }
        }

        ## Data management
        if (data) {
            packages.list <- c(
                "anytime",           # Anything to 'POSIXct' or 'Date' Converter
                "constants",         # Reference on Constants, Units and Uncertainty
                "errors",            # Error Propagation for R Vectors
                "fancycut",          # A Fancy Version of 'base::cut'
                "foreign",           # Read Data Stored by Minitab, S, SAS, SPSS, Stata, Systat, Weka, dBase, ...
                "janitor",           # Simple Tools for Examining and Cleaning Dirty Data
                "padr",              # Quickly Get Datetime Data Ready for Analysis
                "pointblank", # Data Validation and Organization of Metadata for Local and Remote Tables
                "summarytools",      # Tools to Quickly and Neatly Summarize Data
                "tibbletime",        # Time Aware Tibbles
                "units"              # Measurement Units for R Vectors
            )
            ## Installation of new packages (i.e. not previously installed):
            packages.new <- packages.list[!(packages.list %in% installed.packages()[,"Package"])]
            if (length(packages.new)) {
                message(paste0("Installing packages (with dependencies):\n  ", paste(packages.new, collapse = "\n  ")))
                install.packages(packages.new)
            }
        }

        ## Modeling
        if (modeling) {
            packages.list <- c(
                "ade4",              # Analysis of Ecological Data: Exploratory and Euclidean Methods in Environmental Sciences
                "broom",             # Convert Statistical Analysis Objects into Tidy Data Frames
                "CircStats",         # Circular Statistics, from "Topics in circular Statistics" (2001)
                "coxme",             # Mixed Effects Cox Models
                "lme4",              # Linear Mixed-Effects Models using 'Eigen' and S4
                "lsmeans",           # Least-Squares Means
                "MuMIn",             # Multi-Model Inference
                "popbio",            # Construction and Analysis of Matrix Population Models
                "randomForest",      # Breiman and Cutler's Random Forests for Classification and Regression
                "RMark",             # R Code for Mark Analysis
                "visreg"             # Visualization of Regression Models
            )
            ## Installation of new packages (i.e. not previously installed):
            packages.new <- packages.list[!(packages.list %in% installed.packages()[,"Package"])]
            if (length(packages.new)) {
                message(paste0("Installing packages (with dependencies):\n  ", paste(packages.new, collapse = "\n  ")))
                install.packages(packages.new)
            }
        }

        ## Other packages
        if (others) {
            packages.list <- c(
                "blogdown",          # Create Blogs and Websites with R Markdown
                "bookdown",          # Authoring Books and Technical Documents with R Markdown
                "calendR", # Ready to Print Monthly and Yearly Calendars Made with 'ggplot2'
                "charlatan",         # Make Fake Data
                "conflicted",        # An Alternative Conflict Resolution Strategy
                "cowsay",            # Messages, Warnings, Strings with Ascii Animals
                "default",           # Change the Default Arguments in R Functions
                "devtools",          # Tools to Make Developing R Packages Easier
                "diffr",             # Display Differences Between Two Files using Codediff Library
                "distill",           # 'R Markdown' Format for Scientific and Technical Writing
                "equatiomatic",      # Transform Models into 'LaTeX' Equations
                "formatR",           # Format R Code Automatically
                "formattable",       # Create 'Formattable' Data Structures
                "fortunes",          # R Fortunes
                "Hmisc",             # Harrell Miscellaneous
                "httpgd",            # A 'HTTP' Server Graphics Device
                "ids",               # Generate Random Identifiers
                "kableExtra",        # Construct Complex Table with 'kable' and Pipe Syntax
                "knitr",             # A General-Purpose Package for Dynamic Report Generation in R
                "latex2exp",         # Use LaTeX Expressions in Plots
                "liftr",             # Containerize R Markdown Documents for Continuous Reproducibility
                "lintr",             # Static R Code Analysis
                "magick",            # Advanced Graphics and Image-Processing in R
                "nomnoml",           # Sassy 'UML' Diagrams
                "packrat", # A Dependency Management System for Projects and their R Package Dependencies
                "pkgdown",           # Make Static HTML Documentation for a Package
                "printr", # Automatically Print R Objects to Appropriate Formats According to the 'knitr' Output Format
                "processx",          # Execute and Control System Processes
                "remotes",           # R Package Installation from Remote Repositories, Including 'GitHub'
                "rmarkdown",         # Dynamic Documents for R
                "rorcid",            # Interface to the 'Orcid.org' 'API'
                "roxygen2",          # In-Source Documentation for R
                "rticles",           # Article Formats for R Markdown
                "scholar",           # Analyse Citation Data from Google Scholar
                "sessioninfo",       # R Session Information
                "shiny",             # Web Application Framework for R
                "styler",            # Non-Invasive Pretty Printing of R Code
                "sudokuAlt",         # Tools for Making and Spoiling Sudoku Games
                "tigris", # Download TIGER/Line shapefiles from the United States Census Bureau and load into R as 'SpatialDataFrame' or 'sf' objects
                "tint",              # 'tint' is not 'Tufte'
                "tkrplot",           # TK Rplot
                "vitae",             # Curriculum Vitae for R Markdown
                "waldo"              # Find Differences Between R Objects
            )
            ## Installation of new packages (i.e. not previously installed):
            packages.new <- packages.list[!(packages.list %in% installed.packages()[,"Package"])]
            if (length(packages.new)) {
                message(paste0("Installing packages (with dependencies):\n  ", paste(packages.new, collapse = "\n  ")))
                install.packages(packages.new)
            }
        }

        ## Packages on GitHub
        if (github) {
            packages.list <- data.frame(source = c(
                "basille/basr",
                "basille/hab",
                ## "basille/seasonality",
                "gadenbuie/ggpomological",          # Pomological Colors
                "xvrdm/ggrough",                    # converts ggplot2 plots to sketchy charts using rough.js
                "didacs/ggsunburst",                # Sunburst diagrams in ggplot2
                "cttobin/ggthemr",                  # ggplot2 themes (for posters/presentations)
                "lina2497/Giftmap",                 # Create map posters
                "cloudyr/limer",                    # A LimeSurvey R client
                "sctyner/memer",                    # Creating memes with R and magick
                "picardis/nestR",                   # Estimation of Bird Nesting from Tracking Data
                "jsugarelli/packagefinder",         # Comfortable Search for R Packages on CRAN
                "cloudyr/rmote"                     # Running R on a remote server
            ))
            packages.list$name <- unlist(lapply(strsplit(as.character(packages.list$source), "/"), function(li) li[2]))

            ## Installation of new packages (i.e. not previously installed):
            packages.new <- packages.list$source[!(packages.list$name %in% installed.packages()[,"Package"])]
            if (length(packages.new)) {
                message(paste0("Installing packages from GitHub (with dependencies):\n  ", paste(packages.new, collapse = "\n  ")))
                remotes::install_github(packages.new, build_vignettes = TRUE)
            }

        }

    }

    ## Init a web graphic device from httpgd
    init_httpgd <- function(width = getOption("httpgd.width", 720),
        height = getOption("httpgd.height", 576), asp = NA) {
        if (!is.na(asp))
            height <- asp*width
        httpgd::hgd(width = width, height = height)
        httpgd::hgd_browse()
    }

}

## Identifications: ORCiD & GBIF
source("~/.R-site/.ORCiD")
source("~/.R-site/.GBIF")

## date in different locale (e.g. French)
## https://stackoverflow.com/questions/65412576/how-to-ouput-a-date-punctually-in-another-language-in-r
locale_date <- function(x =  Sys.Date(), format = "%A %d %B",
    locale = "fr_FR.utf8") {
    current_locale <- Sys.getlocale("LC_TIME")
    ## When function exits, restore original locale
    on.exit(Sys.setlocale("LC_TIME", current_locale))
    Sys.setlocale("LC_TIME", locale)
    format(x, format = format)
}

## session_info adapted for Markdown output
session_info_md <- function(language = c("EN", "FR"), header_level = 2,
    unnumbered = FALSE, sort_attached =  TRUE) {
    if (!(header_level %in% 2:6))
        stop("`header_level` must be an integer between 1 and 6")
    header_main <- paste(rep("#", header_level), collapse = "")
    header_second <- paste(rep("#", header_level + 1), collapse = "")
    header_numb <- ifelse(unnumbered, " {-}", "")
    language <- match.arg(language)
    switch(language,
        "EN" = {
            session_header <- "R session information"
            platform_header <- "Platform"
            packages_header <- "Packages"
            library_header <- "Library paths"
            setting_name <- "Setting"
            value_name <- "Value"
            package_name <- "Package"
            attached_name <- "Attached"
            version_name <- "Version"
            date_name <- "Date"
            lib_name <- "lib"
            source_name <- "Source"
        },
        "FR" = {
            session_header <- "Informations de session R"
            platform_header <- "Plateforme"
            packages_header <- "Packages"
            library_header <- "Chemin des librairies"
            setting_name <- "Paramètre"
            value_name <- "Valeur"
            package_name <- "Package"
            attached_name <- "Attaché"
            version_name <- "Version"
            date_name <- "Date"
            lib_name <- "lib"
            source_name <- "Source"
        })
    cat(paste0(header_main, " ", session_header, header_numb, "\n\n"))
    sess <-sessioninfo::session_info()
    cat(paste0(header_second, " ", platform_header, header_numb))
    platform <- data.frame(setting = names(sess$platform ),
        value = unlist(sess$platform))
    print(knitr::kable(platform, row.names = FALSE,
        col.names = c(setting_name, value_name)))
    cat(paste0("\n", header_second, " ", packages_header, header_numb))
    flib <- function(x) ifelse(is.na(x), "?", as.integer(x))
    packages <- data.frame(package = sess$packages$package,
        attached = ifelse(sess$packages$attached, "*", ""),
        version = ifelse(is.na(sess$packages$loadedversion),
            sess$packages$ondiskversion, sess$packages$loadedversion),
        `date (UTC)` = sess$packages$date,
        lib = paste0("[", flib(sess$packages$library), "]"),
        source = sessioninfo:::abbrev_long_sha(sess$packages$source),
        stringsAsFactors = FALSE, check.names = FALSE)
    if (sort_attached)
        packages <- packages[order(packages$attached, packages$package,
            decreasing = c(TRUE, FALSE), method = "radix"), ]
    print(knitr::kable(packages, row.names = FALSE, align = "lcrrrr",
        col.names = c(package_name, attached_name, version_name,
            date_name, lib_name, source_name)))
    cat(paste0("\n**", library_header, "**\n\n"))
    cat(paste(sapply(seq_along(levels(sess$packages$library)), function(i) {
        paste0("* [", i, "] `", levels(sess$packages$library)[i], "`")
    }), collapse = "\n"))
    cat("\n")
}
