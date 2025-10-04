# ~/.Rprofile

# The site-wide Rprofile file is located at:
# /etc/R/Rprofile.site
# That is the file which sets `pwd` and `cd` commands

if(interactive()){
  rsthemes::set_theme_light("GitHub {rsthemes}")
  rsthemes::set_theme_dark("Material Ocean {rsthemes}")
  rsthemes::set_theme_favorite(
    c("GitHub {rsthemes}",
      "One Light {rsthemes}",
      "Material Ocean {rsthemes}")
  )
  library(devtools)

  dict <- c()
  .First <- function(){
    source("~/rprofile-nice-dict.R")
    hr <- lubridate::hour(lubridate::now())
    cat("\n")
    csasdown:::check_notify(
      csasdown:::completed_message_color(
        paste0("Good ", ifelse(hr < 12,
                                "morning ",
                                ifelse(hr < 6,
                                       "afternoon ",
                                       "evening ")),
               "you ",
               sample(dict, 1, replace = FALSE),
               "!\n")))
    csasdown:::notify("Print the working directory with pwd.")
    csasdown:::notify("Change directories using cd() with a quoted or unquoted directory name.\n")
    csasdown:::check_notify("Current directory is: ", getwd(), "\n")
  }

  # warn on partial matches
  options(warnPartialMatchAttr = TRUE,
          warnPartialMatchDollar = TRUE,
          warnPartialMatchArgs = TRUE)

  # enable autocompletions for package names in
  # `require()`, `library()`
  utils::rc.settings(ipck = TRUE)

  options(max.print = 100)

  # today <- lubridate::today()
  # month <- lubridate::month(today)
  # day <-  lubridate::day(today)

  # Solid "play button"
  options(prompt = "▶ ")
  #options(prompt = " ")
  #options(prompt = "⇸ ")
  #options(prompt = "≻ ")
  #options(prompt = "⊁ ")
  #options(prompt = "⊱ ")
}

