1. Pick package name:
	- available::available("darksky") -- no
	- available::available("usweather") -- ok

2. usethis::create_package("~/Desktop/usweather")

3. usethis::use_data_raw("weather")

4. Create a folder called weather, put weather.R and weather.csv in there

5. Load, clean, save data

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
| usethis::use_data(weather, overwrite = TRUE)

6. devtools::load_all(), check that weather exists. then try ?weather -- nothing.

7. use_r("weather"), then go to https://r-pkgs.org/data.html#documenting-data and copy-paste

8. write documentation

| #' Hourly weather for 50 US cities
| #'
| #' A dataset containing hourly weather data for 50 US cities.
| #'
| #' @format A data frame with 6000 rows and 21 variables:
| ...
| #' @source Dark Sky, \url{https://darksky.net/dev}
| "weather"

9. data dictionary

names(weather) %>% cat(sep = "\n")

city					- Name of city.
state					- Name of state.
time					- Time.
summary					- A human-readable text summary.
icon					- A machine-readable text summary, suitable for selecting an icon for display.
precip_intensity		- The intensity (in inches of liquid water per hour) of precipitation occurring at the given time. This value is conditional on probability (that is, assuming any precipitation occurs at all).		
precip_probability		- The probability of precipitation occurring, between 0 and 1, inclusive.
temperature				- The air temperature in degrees Fahrenheit.
apparent_temperature	- The apparent (or “feels like”) temperature in degrees Fahrenheit.
dew_point				- The dew point in degrees Fahrenheit.
humidity				- The relative humidity, between 0 and 1, inclusive.
pressure				- The sea-level air pressure in millibars.
wind_speed				- The wind speed in miles per hour.
wind_gust				- The time at which the maximum wind gust speed occurs during the day.
wind_bearing			- The direction that the wind is coming from in degrees, with true north at 0° and progressing clockwise. (If windSpeed is zero, then this value will not be defined.)
cloud_cover				- The percentage of sky occluded by clouds, between 0 and 1, inclusive.
uv_index				- The UV index.
visibility				- The average visibility in miles, capped at 10 miles.
ozone					- The columnar density of total atmospheric ozone at the given time in Dobson units.
precip_type				- The type of precipitation occurring at the given time. If defined, this property will have one of the following values: "rain", "snow", or "sleet" (which refers to each of freezing rain, ice pellets, and “wintery mix”).
forecast				- Indicator for whether measurement is historical (FALSE) or forecast (`TRUE`). 


10. document(), load_all(), ?weather

11. use_git(), use_github("pkgname")

12. use_readme_rmd()

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

13. DESCRIPTION

- Title: Provides hourly temperature for 50 US cities
- Authors@R: 
    person("Mine", "Çetinkaya-Rundel", , "cetinkaya.mine@gmail.com, role = c("aut", "cre"),
           comment = c(ORCID = "0000-0001-6452-2420"))
- use_gpl3_license()

14. use_pkgdown(), build_site()

15. use_github_pages(), use_github_action(name = "pkgdown"), check action on repo, find page


your turn: add cities.csv


16. use_tutorial("explore-usweather", title = "Exploring weather in US cities")

add library(usweather)
plop weather into a code chunk

install pkg from github show it works in tutorials pane