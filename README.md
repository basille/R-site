R stuff
=======

What this repository contains:

* Config files `.Renviron` & `.Rprofile` with custom options and functions
* CSS files for Rmd or R code within pages (within `CSS` folder)
* Templates (within `Templates` folder)

Functions in `.Rprofile`:

* `install.selected()`: Selection of packages to install (categories `spatial`,
  `moveco`, `tidyverse`, `plotting`, `data`, `modeling`, `others`, `github`).
* `init_httpgd()`: Initialize a HTTP server graphics device and opens it in the
  browser.
* `locale_date()`: Pretty printing of dates (today by default) with respect to
  locale.
* `session_info_md()`: Pretty printing of session information for Markdown output.
