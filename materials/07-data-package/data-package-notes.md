1. Pick package name:
	- available::available("darksky") -- no
	- available::available("usweather") -- ok, fine

2. usethis::create_package("~/Desktop/usweather")

3. usethis::use_data_raw("weather")

4. Create a folder called weather, put weather.R and weather.csv in there.

5. Load, clean, save data.

| ## code to prepare `weather` dataset goes here
| 
| # load packages ----------------------------------------------------
| 
| library(tidyverse)
| library(janitor)
| 
| # load data --------------------------------------------------------
| 
| weather_raw <- read_csv("data-raw/weather/weather.csv")
| 
| weather <- weather_raw |>
|   clean_names()
| 
| # use data ---------------------------------------------------------
|
| usethis::use_data(weather, overwrite = TRUE)

6. devtools::load_all(), check that weather exists. then try ?weather -- nothing.

7. usethis::use_r("weather"), then go to https://r-pkgs.org/data.html#documenting-data and copy-paste.

8. write documentation

| #' Hourly weather for 50 US cities
| #'
| #' A dataset containing hourly weather data for 50 US cities.
| #'
| #' @format A data frame with 6000 rows and 21 variables:
| ...
| #' @source Dark Sky, \url{https://darksky.net/dev}
| "weather"

9. Data dictionary

names(weather) %>% cat(sep = "\n")

#' \describe{
#'   \item{city}{Name of city.}
#'   \item{state}{Name of state.}
#'   \item{time}{Time.}
#'   \item{summary}{A human-readable text summary.}
#'   \item{icon}{A machine-readable text summary, suitable for selecting an icon for display.}
#'   \item{precip_intensity}{The intensity (in inches of liquid water per hour) of precipitation occurring at the given time.}
#'   \item{precip_probability}{The probability of precipitation occurring, between 0 and 1, inclusive.}
#'   \item{temperature}{The air temperature in degrees Fahrenheit.}
#'   \item{apparent_temperature}{The apparent (or “feels like”) temperature in degrees Fahrenheit.}
#'   \item{dew_point}{The dew point in degrees Fahrenheit.}
#'   \item{humidity}{The relative humidity, between 0 and 1, inclusive.}
#'   \item{pressure}{The sea-level air pressure in millibars.}
#'   \item{wind_speed}{The wind speed in miles per hour.}
#'   \item{wind_gust}{The time at which the maximum wind gust speed occurs during the day.}
#'   \item{wind_bearing}{The direction that the wind is coming from in degrees, with true north at 0° and progressing clockwise. (If windSpeed is zero, then this value will not be defined.)}
#'   \item{cloud_cover}{The percentage of sky occluded by clouds, between 0 and 1, inclusive.}
#'   \item{uv_index}{The UV index.}
#'   \item{visibility}{The average visibility in miles, capped at 10 miles.}
#'   \item{ozone}{The columnar density of total atmospheric ozone at the given time in Dobson units.}
#'   \item{precip_type}{The type of precipitation occurring at the given time. If defined, this property will have one of the following values: "rain", "snow", or "sleet".}
#'   \item{forecast}{Indicator for whether measurement is historical (FALSE) or forecast (`TRUE`).}
#' }

10. devtools::document(), devtools::load_all(), ?weather -- yay!

11. Edit DESCRIPTION

- Title: Provides hourly temperature for 50 US cities
- Authors@R: 
    person("Mine", "Çetinkaya-Rundel", , "cetinkaya.mine@gmail.com, role = c("aut", "cre"),
           comment = c(ORCID = "0000-0001-6452-2420"))
- use_gpl3_license()

12. devtools::check()

13. usethis::use_git(), uusethis::use_github()

14. usethis::use_readme_rmd(), update (use example below), knit, commit, push.

| ```{r}
| #| label: example
| #| message: false
| 
| library(usweather)
| library(dplyr)
| 
| weather |>
|   filter(!forecast) |>
|   group_by(city) |>
|   summarise(mean_temp = mean(temperature)) %>%
|   arrange(desc(mean_temp))
| ```

15. usethis::use_pkgdown(), devtools::build_site()

16. usethis::use_github_pages(), usethis::use_github_action(name = "pkgdown"), check action on repo, find page

> your turn: add cities.csv

17. usethis::use_tutorial("explore-usweather", title = "Exploring weather in US cities")

add library(usweather)
plop weather into a code chunk

18. install pkg from github show it works in tutorials pane