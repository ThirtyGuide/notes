# Group Assignment 1

**New York City rat-sighting data project**

[← All chapters](README.md) · [Original PDF](PDF%20Slides.pdf#page=796)

## Overview

- Preparing and inspecting 311 rat-sighting data.
- Exploratory plots, mapping and regression with diagnostics.
- Source assignment, R Markdown, rubric and data previews.

## Source documents

1. [Group_Assignment_1.html](#source-1) — HTML, reader page 797
2. [Group_Assignment_1.Rmd](#source-2) — RMD, reader page 806
3. [rubric_final_project.xlsx](#source-3) — XLSX, reader page 812
4. [nyc_weather.csv](#source-4) — CSV, reader page 815
5. [Rat_Sightings_20251004.zip](#source-5) — ZIP, reader page 818

---

<a name="source-1"></a>

## Group_Assignment_1.html

<small>File type: HTML · Reader pages 797–805 · [View source PDF](PDF%20Slides.pdf#page=797)</small>

> This source was converted from HTML to PDF before upload; some inline code is fragmented. Use an adjacent `.Rmd` source when provided.

Show All Code

Hide All Code

### CA09: Group Project 1

----- Group XX

New York City is full of urban wildlife, and rats are one of the city’s most infamous animals. Rats in NYC are plentiful and in September 2015 a viral video of a brown rat carrying a slice of pizza down the steps of a NYC subway station in Manhattan created the legend of Pizza Rat .

The source for the data of rat sightings in the city is from NYC’s 311 Service Requests from 2010 to Present . This is a dataset that is pretty much constantly updated and I downloaded this dataset on 4-Oct-2025. For this group project, you will use R , dplyr , and ggplot2 to explore and explain the data, and tell an interesting story. The data fields are shown below and a full data dictionary can be found here

### 1 Loading the data

I have provided some starter code below. A couple comments about it:

By default, vroom() treats cells that are empty or “NA” as missing values. This rat dataset uses “N/A” to mark missing values, so we need to add that as a possible marker of missingness (hence na = c("", "NA", "N/A") )

To make life easier, I always use janitor::clean_names() to remove spaces, upper case letters, etc. from variable names.

I’ve also created a few date-related variables ( sighting_year , sighting_month , sighting_day , and sighting_weekday ). You don’t have to use them, but they’re there if you need them. The functions that create these, like year() and wday() are part of the lubridate library.

There are a few rows with an unspecified borough, so I filtered them out.

I use str_to_title() to turn the upper case borough into a more legible format, from MANHATTAN to Manhattan and from STATEN ISLAND to Staten Island

```text
# If you get an error "All formats failed to parse. No formats found",
# it's because the mdy_hms function couldn't parse the date. The date
# variable *should* be in this format: "09/14/2018 05:46:05 PM", but in some
# rare instances, it might load without the seconds as "09/14/2018 05:00 PM".
# If there are no seconds, use mdy_hm() instead of mdy_hms().
rats
<-
vroom
::
vroom
(
"Rat_Sightings_20251004.zip"
```
```text
,
na =
c
(
""
,
"NA"
,
"N/A"
))
%>%
janitor
::
clean_names
()
%>%
mutate
(
# convert the string to a date format
created_date =
mdy_hms
(created_date),
# just the date without hour info
sighting_date =
as.Date
(created_date),
# get the year, month, etc
sighting_year =
year
(created_date),
sighting_month =
month
(created_date),
sighting_month_name =
month
(created_date,
label =
TRUE
,
abbr =
FALSE
),
sighting_day =
day
(created_date),
sighting_weekday =
wday
(created_date,
label =
TRUE
,
abbr =
FALSE
)
)
%>%
filter
(borough
!=
"Unspecified"
)
%>%
```
```text
mutate
(
borough =
str_to_title
(borough))
```

### 2 Exploratory Data Analysis (EDA)

### 2.1 Task Description

In the R4DS Exploratory Data Analysis chapter , the authors state:

“EDA is not a formal process with a strict set of rules. More than anything, EDA is a state of mind. During the initial phases of EDA you should feel free to investigate every idea that occurs to you. Some of these ideas will pan out, and some will be dead ends. As your exploration continues, you will home in on a few particularly productive insights that you’ll eventually write up and communicate to others.”

In this section, our goal is to conduct a thorough EDA. The raw data has more than 270,000 rows, which means you’ll need to aggregate the data ( filter() , group_by() , and summarise() are your friends).

Recall that an EDA involves three things:

Looking at the raw values. dplyr::glimpse()

dplyr::glimpse()

Computing summary statistics of the variables of interest. skimr::skim() Functions from dplyr , such as count() , arrange() , select() , filter() , group_by() , summarise() , and mutate() . corrr::correlate() mosaic::favstats()

skimr::skim()

Functions from dplyr , such as count() , arrange() , select() , filter() , group_by() , summarise() , and mutate() .

corrr::correlate()

mosaic::favstats()

Creating informative visualizations. ggplot2::ggplot() geom_histogram() or geom_density() for numeric continuous variables geom_bar() or geom_col() for categorical variables GGally::ggpairs() for scatter plot / correlation matrix Note that you can add transparency to points/density plots in the aes call, for example: aes(colour = borough, alpha = 0.4)

ggplot2::ggplot() geom_histogram() or geom_density() for numeric continuous variables geom_bar() or geom_col() for categorical variables

geom_histogram() or geom_density() for numeric continuous variables

geom_bar() or geom_col() for categorical variables

GGally::ggpairs() for scatter plot / correlation matrix Note that you can add transparency to points/density plots in the aes call, for example: aes(colour = borough, alpha = 0.4)

Note that you can add transparency to points/density plots in the aes call, for example: aes(colour = borough, alpha = 0.4)
You may wish to have a level 1 header ( # ) for your EDA, then use level 2 sub-headers ( ## ) to make sure you cover all three EDA elements. At a minimum , make sure to include some answer to these questions in your report:

How many variables/columns? How many rows/observations?

Which variables are numbers?

Which are categorical or factor variables?

Is there any pattern in the number of sightings per borough, per year, per dwelling type, etc., or a combination of these, like the change in the number sightings across the 5 boroughs between, say, 2015 and 2024.

Is there any change in rat sighting patterns after systematic shocks, such as covid-19?

What are the correlations between variables? Does each scatter plot support a linear relationship between variables? Do any of the correlations appear to be conditional on the value of a categorical variable?

However, don’t constrain your EDA to the questions above - I’m sure you are able to draw more interesting insights using the R codes we have seen in class sessions.

A thousand data scientists may explore the data in a thousand different ways. There is not specific cookbook to follow in EDA. Let your curiosity lead you!

In all cases, please think about the message your plot is conveying. Don’t just say “This is my X-axis, this is my Y-axis”, but rather what’s the so what of the plot. Tell some sort of story and speculate about the differences in the patterns in a paragraph.

### 2.1.1 Plotting figures

For each table, make sure to include a relevant figure. One tip for starting is to draw out on paper what you want your x- and y-axis to be first and what your geom is; that is, start by drawing the plot you want ggplot to give you.

Your figure does not have to depict every last number from the data aggregation result. Use your judgement. It just needs to complement the table, add context, and allow for some sanity checking both ways.

Think twice about which figures are easy/hard to make, which data formats make better inputs for plotting functions vs. for human-friendly tables.

### 2.1.2 Mapping

Visualisations of feature distributions and their relations are key to understanding a data set, and they can open up new lines of exploration.

While we do not have time to go into all the wonderful geospatial visualisations one can do with R, you can use the following code to start with a map of your city, and overlay all rat sighting coordinates to get an overview of the spatial distribution of reported rat activity.

For this visualisation we use the leaflet package, which includes a variety of tools for interactive maps, so you can easily zoom in-out, click on a point to get the actual location type and date/ time of sighting.
If you wanted to, you can learn more about leafelt the package that draws the interactive map, by following the relevant Datacamp course on mapping with leaflet

```text
# let's get the top 7 location types, which account for > 90% of all cases
# this code generates a vector with the top 7 location types
top_location_types
<-
rats
%>%
count
(location_type,
sort=
TRUE
)
%>%
mutate
(
perc =
100
*
n
/
sum
(n))
%>%
slice
(
1
:
7
)
%>%
dplyr
::
select
(location_type)
%>%
pull
()
# lets us choose how to colour each point. What palette and colours to use?
# A great site to get the relevant color hex codes for maps is
# https://colorbrewer2.org/#type=qualitative&scheme=Set1&n=7
my_colours
<-
c
(
'#e41a1c'
,
'#377eb8'
,
'#4daf4a'
,
'#984ea3'
,
'#ff7f00'
,
'#ffff33'
,
'#a65628'
)
# create a function point_fill, that assigns `my_colours` to different location types
```
```text
# you can read more here https://rstudio.github.io/leaflet/colors.html
point_fill
<-
colorFactor
(
palette =
my_colours,
rats
$
location_type)
rats
%>%
filter
(sighting_year
==
2024
)
%>%
# just show 2024 data
filter
(location_type
%in%
top_location_types)
%>%
leaflet
()
%>%
addProviderTiles
(
"OpenStreetMap.Mapnik"
)
%>%
addCircleMarkers
(
lng =
~
longitude,
lat =
~
latitude,
radius =
1
,
color =
~
point_fill
(location_type),
fillOpacity =
0.6
,
popup =
~
created_date,
label =
~
location_type)
%>%
addLegend
(
"bottomright"
,
pal =
```
```text
point_fill,
values =
~
location_type,
title =
"2024 Location Type"
,
opacity =
0.5
)
```

### 3 Regression

Besides the variables included in the rats tibble, I have also downloaded weather data for NYC which can be found at the nyc_weather tibble. It may be the case that rats are more active when it’s warmer? or when it rains?

Our target is to build a regression model that helps you explain the number of sightings per day. The variables of the dataset nyc_weather are shown below:

```text
Rows: 4,097
Columns: 32
$ name  <chr> "New York", "New York", "New York", "New York", "New …
$ datetime  <date> NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, …
$ tempmax  <dbl> 4.3, 1.1, -5.5, -1.0, -0.8, 1.3, 3.2, 0.9, -0.8, -1.8…
$ tempmin  <dbl> 0.9, -8.0, -8.0, -6.8, -6.1, -3.0, -1.1, -4.8, -6.8, …
$ temp  <dbl> 2.4, -3.5, -6.9, -4.7, -3.7, -1.6, 0.7, -1.3, -4.6, -…
$ feelslikemax  <dbl> 4.1, -3.8, -13.2, -6.6, -6.1, -3.3, -0.7, 0.7, -5.1, …
$ feelslikemin  <dbl> -1.8, -17.3, -17.3, -14.8, -12.8, -9.0, -6.6, -11.4, …
$ feelslike  <dbl> 1.0, -10.5, -15.2, -11.3, -9.7, -7.1, -3.8, -5.5, -10…
$ dew  <dbl> -0.4, -10.2, -14.4, -12.4, -11.3, -9.5, -6.2, -6.5, -…
$ humidity  <dbl> 82, 60, 55, 55, 56, 55, 60, 68, 47, 42, 48, 52, 51, 5…
$ precip  <dbl> 2.40, 0.18, 0.00, 0.00, 0.00, 0.00, 0.00, 0.68, 0.00,…
$ precipprob  <dbl> 100, 100, 0, 0, 0, 0, 0, 100, 0, 0, 0, 0, 0, 0, 0, 0,…
$ precipcover  <dbl> 16.7, 4.2, 0.0, 0.0, 0.0, 0.0, 0.0, 25.0, 0.0, 0.0, 0…
$ preciptype  <chr> "rain,snow", "rain,snow", NA, NA, NA, NA, NA, "rain,s…
$ snow  <dbl> NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, N…
$ snowdepth  <dbl> 3, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA…
$ windgust  <dbl> 37, 58, 61, 42, 41, 45, 48, 49, 41, 37, 31, 47, 43, N…
$ windspeed  <dbl> 16, 35, 36, 27, 26, 27, 26, 32, 24, 20, 16, 29, 25, 1…
$ winddir  <dbl> 309.2, 295.4, 290.4, 294.4, 295.1, 299.2, 292.5, 281.…
$ sealevelpressure <dbl> 1012, 1005, 1001, 1006, 1006, 1006, 1011, 1008, 1017,…
$ cloudcover  <dbl> 99.6, 79.3, 73.3, 28.1, 50.1, 55.5, 50.2, 78.4, 1.5, …
$ visibility  <dbl> 10.6, 14.3, 15.3, 16.0, 16.0, 16.0, 16.0, 12.7, 16.0,…
$ solarradiation  <dbl> 80, 50, 36, 69, 113, 100, 114, 68, 120, 122, 106, 100…
$ solarenergy  <dbl> 6.8, 4.1, 3.1, 5.9, 9.7, 8.7, 9.8, 5.9, 10.4, 10.6, 9…
$ uvindex  <dbl> 4, 2, 1, 3, 5, 5, 5, 4, 5, 5, 5, 4, 5, 5, 4, 5, 1, 5,…
$ severerisk  <dbl> NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, N…
$ sunrise  <dttm> 2010-01-01 07:20:12, 2010-01-02 07:20:17, 2010-01-03…
$ sunset  <dttm> 2010-01-01 16:39:17, 2010-01-02 16:40:08, 2010-01-03…
$ moonphase  <dbl> 0.51, 0.53, 0.55, 0.60, 0.65, 0.70, 0.76, 0.81, 0.86,…
$ conditions  <chr> "Snow, Rain, Overcast", "Snow, Rain, Partially cloudy…
$ description  <chr> "Cloudy skies throughout the day with rain or snow cl…
$ icon  <chr> "rain", "rain", "partly-cloudy-day", "partly-cloudy-d…
```

Please join the two tibble before you run your regression model.
### 3.1 Your regression tasks

Use histograms or density plots to examine the distributions of n , the number of rat sightings, and log(n) . Which variable should you use for the regression model? Why?

Use histograms or density plots to examine the distributions of n , the number of rat sightings, and log(n) . Which variable should you use for the regression model? Why?

Fit a regression model called model1 with the following explanatory variables: temp . Is the effect of temp significant? Why? What proportion of the overall variability in rat sightings does temp explain?

Fit a regression model called model1 with the following explanatory variables: temp .

Is the effect of temp significant? Why?

What proportion of the overall variability in rat sightings does temp explain?

Fit a regression model called model2 with the following explanatory variables: temp and borough Is the effect of temp significant? Why? What proportion of the overall variability in rat sightings does this model explain? Why is Bronx missing from the boroughs in our model? How do we interpret the coefficients for each of the boroughs? What’s the difference between fitting the model of n versus log(n) If you use a log transformation, the interpretation of the betas/coefficients is slightly different. You can read more about that here FAQ HOW DO I INTERPRET A REGRESSION MODEL WHEN SOME VARIABLES ARE LOG TRANSFORMED?

Fit a regression model called model2 with the following explanatory variables: temp and borough

Is the effect of temp significant? Why?

What proportion of the overall variability in rat sightings does this model explain?

Why is Bronx missing from the boroughs in our model?

How do we interpret the coefficients for each of the boroughs?

What’s the difference between fitting the model of n versus log(n)

If you use a log transformation, the interpretation of the betas/coefficients is slightly different. You can read more about that here FAQ HOW DO I INTERPRET A REGRESSION MODEL WHEN SOME VARIABLES ARE LOG TRANSFORMED?

Further variables/questions to explore on your own

Further variables/questions to explore on your own

The dataset has many more variables, so here are some ideas on how you can extend your ana‐

lysis:

Are other weather variables useful in explaining n ?

We also have data on days of the week, month of the year, etc. Could those be helpful?

What’s the best model you can come up with?

Is this a regression model to predict or explain? If we use it to predict, what’s the Residual Standard Error?
### 3.2 Diagnostics, collinearity, summary tables

As you keep building your models, it makes sense to:

Check the residuals, using autoplot() . You will always have some deviation from normality, especially for very high values of n .

As you start building models with more explanatory variables, make sure you use car::vif(model_x) to calculate the Variance Inflation Factor (VIF) for your predictors and determine whether you have colinear variables. A general guideline is that a VIF larger than 10 is large, and your model may suffer from collinearity. Remove the variable in question and run your model again without it.

Create a summary table, using huxtable::huxreg() that display your model estimations side by side, see which predictors are significant, compare the adjusted \(R^2\) , and the Residual Standard Error.

### 4 Submission Notes

Please remember that it’s not enough for your code to run– it must be well documented and commented, so another person can read your work, reproduce your code, and easily understand what you are trying to achieve.

Submit your work and analysis on Canvas. Please submit the Rmd file, and the knitted HTML document that contains all of your code, analyses, and explanations.

Everyone in the group will receive the same grade. To ensure a fair division of labor, please include a paragraph at the end of your Rmd file detailing the contribution of each group member.

You are allowed to collaborate with GenAI when working on this assignment, and the usage of GenAI will not impact your grade. To ensure a responsible use of GenAI, please include a paragraph at the end of your Rmd file clarifying whether you have used GenAI. If yes, please share how you have used GenAI for this assignment and whether you have found it helpful.

### 5 ----------

There is a detailed ---------- rubric in the folder. Please delete all of the paragraphs of text which I have written. Please hide output from the code that I have written in the knitted file. The visible knitted output should be from your code and the explanations / comments which you have written. This will allow for easier grading.


[↑ Back to the source list](#source-documents)

---

<a name="source-2"></a>

## Group_Assignment_1.Rmd

<small>File type: RMD · Reader pages 806–811 · [View source PDF](PDF%20Slides.pdf#page=806)</small>

```r
# leave this chunk alone
options(knitr.table.format = "html")
knitr::opts_chunk$set(warning = FALSE, message = FALSE,
comment = NA, dpi = 300)
options(digits = 2)
options(scipen = 999)
library(tidyverse) # the usual stuff: dplyr, readr, and other goodies
library(lubridate) # to handle dates
library(GGally) # for correlation-scatter plot matrix
library(janitor) # clean_names()
library(broom) # use broom:augment() to get tidy table with regression output, residuals, etc
library(huxtable) # to get summary table of all models produced
library(kableExtra) # for formatting tables
library(skimr) # for skim
library(mosaic)
library(leaflet) # for interactive HTML maps
library(ggtext)
library(viridis)
library(kableExtra)
library(vroom)
library(here)
library(performance)  # to produce residual diagnostic plots
library(ggtext)
library(patchwork)
```

New York City is full of urban wildlife, and rats are one of the city’s most infamous animals. Rats in NYC are plentiful and in September 2015 [a viral video of a brown rat carrying a slice of pizza down the steps of a NYC subway station](https://www.youtube.com/watch?v=3i0_uyGyvis) in Manhattan created the legend of [Pizza Rat](https://en.wikipedia.org/wiki/Pizza_Rat).

The source for the data of rat sightings in the city is from NYC's [311 Service Requests from 2010 to Present](https://data.cityofnewyork.us/Social-Services/Rat-Sightings/3q43-55fe). This is a dataset that is pretty much constantly updated and I downloaded this dataset on 4-Oct-2025. For this group project, you will use `R`, `dplyr`, and `ggplot2` to explore and explain the data, and tell an interesting story. The data fields are shown below and a [full data dictionary can be found here] (https://data.cityofnewyork.us/Social-Services/Rat-Sightings/3q43-55fe)

### Loading the data

I have provided some starter code below. A couple comments about it:

- By default, `vroom()` treats cells that are empty or "NA" as missing values.

This rat dataset uses "N/A" to mark missing values, so we need to add that as a possible marker of missingness (hence `na = c("", "NA", "N/A")`)

- To make life easier, I **always** use `janitor::clean_names()` to remove spaces, upper

case letters, etc. from variable names.
- I've also created a few date-related variables (`sighting_year`, `sighting_month`, `sight‐

ing_day`, and `sighting_weekday`). You don't have to use them, but they're there if you need them.

The functions that create these, like `year()` and `wday()` are part of the **lubridate** library.

- There are a few rows with an unspecified borough, so I filtered them out.

- I use `str_to_title()` to turn the upper case borough into a more legible format, from

`MANHATTAN` to `Manhattan` and from `STATEN ISLAND` to `Staten Island`

```r
# If you get an error "All formats failed to parse. No formats found",
# it's because the mdy_hms function couldn't parse the date. The date
# variable *should* be in this format: "09/14/2018 05:46:05 PM", but in some
# rare instances, it might load without the seconds as "09/14/2018 05:00 PM".
# If there are no seconds, use mdy_hm() instead of mdy_hms().
rats <- vroom::vroom("Rat_Sightings_20251004.zip", na = c("", "NA", "N/A")) %>%
janitor::clean_names() %>%
mutate(
# convert the string to a date format
created_date = mdy_hms(created_date),
# just the date without hour info
sighting_date = as.Date(created_date),
# get the year, month, etc
sighting_year = year(created_date),
sighting_month = month(created_date),
sighting_month_name = month(created_date, label = TRUE, abbr = FALSE),
sighting_day = day(created_date),
sighting_weekday = wday(created_date, label = TRUE, abbr = FALSE)
) %>%
filter(borough != "Unspecified") %>%
mutate(borough = str_to_title(borough))
```

### Exploratory Data Analysis (EDA)

### Task Description

In the [R4DS Exploratory Data Analysis chapter](https://r4ds.hadley.nz/EDA.html), the authors

state:

> "EDA is not a formal process with a strict set of rules. More than anything, EDA is a state of mind. During the initial phases of EDA you should feel free to investigate every idea that occurs to you. Some of these ideas will pan out, and some will be dead ends. As your exploration continues, you will home in on a few particularly productive insights that you’ll eventually write up and communicate to others."

In this section, our goal is to conduct a thorough EDA. The raw data has more than 270,000 rows, which means you’ll need to aggregate the data (`filter()`, `group_by()`, and `summarise()` are your friends).

Recall that an EDA involves three things:

- Looking at the raw values.

- `dplyr::glimpse()`
- Computing summary statistics of the variables of interest.

- `skimr::skim()`

- Functions from **dplyr**, such as `count()`, `arrange()`, `select()`, `filter()`,

`group_by()`, `summarise()`, and `mutate()`.

- `corrr::correlate()`

- `mosaic::favstats()`

- Creating informative visualizations.

- `ggplot2::ggplot()`

- `geom_histogram()` or `geom_density()` for numeric continuous variables

- `geom_bar()` or `geom_col()` for categorical variables

- `GGally::ggpairs()` for scatter plot / correlation matrix

- Note that you can add transparency to points/density plots in the `aes` call, for example:

`aes(colour = borough, alpha = 0.4)`

You may wish to have a level 1 header (`#`) for your EDA, then use level 2 sub-headers (`##`) to make sure you cover all three EDA elements. **At a minimum**, make sure to include some answer to these questions in your report:

- How many variables/columns? How many rows/observations?

- Which variables are numbers?

- Which are categorical or *factor* variables?

- Is there any pattern in the number of sightings per borough, per year, per dwelling type,

etc., or a combination of these, like the change in the number sightings across the 5 boroughs between, say, 2015 and 2024.

- Is there any change in rat sighting patterns after systematic shocks, such as covid-19?

- What are the correlations between variables? Does each scatter plot support a linear rela‐

tionship between variables? Do any of the correlations appear to be conditional on the value of a categorical variable?

However, don't constrain your EDA to the questions above - I'm sure you are able to draw more interesting insights using the R codes we have seen in class sessions.

A thousand data scientists may explore the data in a thousand different ways. There is not specific cookbook to follow in EDA. Let your curiosity lead you!

> In all cases, please think about the message your plot is conveying. Don’t just say "This is my X-axis, this is my Y-axis", but rather what’s the **so what** of the plot. Tell some sort of story and speculate about the differences in the patterns in a paragraph.

Plotting figures

For each table, make sure to include a relevant figure. One tip for starting is to draw out on paper what you want your x- and y-axis to be first and what your `geom` is; that is, start by drawing the plot you want `ggplot` to give you.
Your figure does not have to depict every last number from the data aggregation result. Use your judgement. It just needs to complement the table, add context, and allow for some sanity checking both ways.

Think twice about which figures are easy/hard to make, which data formats make better inputs for plotting functions vs. for human-friendly tables.

Mapping

Visualisations of feature distributions and their relations are key to understanding a data set, and they can open up new lines of exploration. While we do not have time to go into all the wonderful geospatial visualisations one can do with R, you can use the following code to start with a map of your city, and overlay all rat sighting coordinates to get an overview of the spatial distribution of reported rat activity. For this visualisation we use the `leaflet` package, which includes a variety of tools for interactive maps, so you can easily zoom in-out, click on a point to get the actual location type and date/time of sighting. If you wanted to, you can learn more about `leafelt` the package that draws the interactive map, by following [the relevant Datacamp course on mapping with leaflet](https://www.datacamp.com/courses/interactive-maps-with-leaflet-in-r)

```r
# let's get the top 7 location types, which account for > 90% of all cases
# this code generates a vector with the top 7 location types
top_location_types <- rats %>%
count(location_type, sort=TRUE) %>%
mutate(perc = 100*n/sum(n)) %>%
slice(1:7) %>%
dplyr::select(location_type) %>%
pull()
# lets us choose how to colour each point. What palette and colours to use?
# A great site to get the relevant color hex codes for maps is
# https://colorbrewer2.org/#type=qualitative&scheme=Set1&n=7
my_colours <- c('#e41a1c','#377eb8','#4daf4a','#984ea3','#ff7f00','#ffff33','#a65628')
# create a function point_fill, that assigns `my_colours` to different location types
# you can read more here https://rstudio.github.io/leaflet/colors.html
point_fill <- colorFactor(palette = my_colours,
rats$location_type)
rats %>%
filter(sighting_year == 2024) %>% # just show 2024 data
filter(location_type %in% top_location_types) %>%
leaflet() %>%
addProviderTiles("OpenStreetMap.Mapnik") %>%
addCircleMarkers(lng = ~longitude,
lat = ~latitude,
radius = 1,
color = ~point_fill(location_type),
fillOpacity = 0.6,
popup = ~created_date,
label = ~location_type) %>%
addLegend("bottomright", pal = point_fill,
values = ~location_type,
title = "2024 Location Type",
opacity = 0.5)
```
### Regression

Besides the variables included in the `rats` tibble, I have also downloaded weather data for NYC which can be found at the `nyc_weather` tibble. It may be the case that rats are more active when it's warmer? or when it rains?

Our target is to build a regression model that helps you explain the number of sightings per day. The variables of the dataset `nyc_weather` are shown below:

```r
nyc_weather <-  read_csv("nyc_weather.csv") %>%
janitor::clean_names()  %>%
mutate(datetime = dmy(datetime))
glimpse(nyc_weather)
```

Please join the two tibble before you run your regression model.

```r
rats_weather <- rats %>%
mutate(date = as.Date(created_date)) %>%
count(borough,date) %>%
left_join(nyc_weather, by = c("date" = "datetime")) %>%
mutate(month = month(date),
month_name = month(date, label=TRUE),
day = wday(date),
day_of_week = wday(date, label=TRUE))
```

### Your regression tasks

- Use histograms or density plots to examine the distributions of `n`, the number of rat

sightings, and `log(n)`. Which variable should you use for the regression model? Why?

- Fit a regression model called `model1` with the following explanatory variables: `temp`.

- Is the effect of `temp` significant? Why?

- What proportion of the overall variability in rat sightings does `temp` explain?

- Fit a regression model called `model2` with the following explanatory variables: `temp`

and `borough`

- Is the effect of `temp` significant? Why?

- What proportion of the overall variability in rat sightings does this model explain?

- Why is `Bronx` missing from the boroughs in our model?

- How do we interpret the coefficients for each of the boroughs?

- What's the difference between fitting the model of `n` versus `log(n)`

- If you use a `log` transformation, the interpretation of the betas/coefficients is slightly dif‐

ferent. You can read more about that here [FAQ HOW DO I INTERPRET A REGRESSION MODEL WHEN SOME VARIABLES ARE LOG TRANSFORMED?](https://stats.oarc.ucla.edu/other/ mult-pkg/faq/general/faqhow-do-i-interpret-a-regression-model-when-some-variables-arelog-transformed/)

- **Further variables/questions to explore on your own**
The dataset has many more variables, so here are some ideas on how you can extend your ana‐

lysis:

- Are other weather variables useful in explaining `n`?

- We also have data on days of the week, month of the year, etc. Could those be helpful?

- What's the best model you can come up with?

- Is this a regression model to predict or explain? If we use it to predict, what's the Residual

Standard Error?

### Diagnostics, collinearity, summary tables

As you keep building your models, it makes sense to:

- Check the residuals, using `autoplot()`. You will always have some deviation from nor‐

mality, especially for very high values of `n`. 2. As you start building models with more explanatory variables, make sure you use `car::vif(model_x)` to calculate the **Variance Inflation Factor (VIF)** for your predictors and determine whether you have colinear variables. A general guideline is that a VIF larger than 10 is large, and your model may suffer from collinearity. Remove the variable in question and run your model again without it. 3. Create a summary table, using `huxtable::huxreg()` that display your model estimations side by side, see which predictors are significant, compare the adjusted $R^2$, and the Residual Standard Error.

### Submission Notes

Please remember that it's not enough for your code to run-- it must be well documented and commented, so another person can read your work, reproduce your code, and easily understand what you are trying to achieve.

Submit your work and analysis on Canvas. Please submit the Rmd file, and the knitted HTML document that contains all of your code, analyses, and explanations.

Everyone in the group will receive the same grade. To ensure a fair division of labor, please include **a paragraph** at the end of your Rmd file detailing the contribution of each group member.

You are allowed to collaborate with **GenAI** when working on this assignment, and the usage of GenAI will not impact your grade. To ensure a responsible use of GenAI, please include **a paragraph** at the end of your Rmd file clarifying whether you have used GenAI. If yes, please share how you have used GenAI for this assignment and whether you have found it helpful.

### ----------

There is a detailed ---------- rubric in the folder. Please delete all of the paragraphs of text which I have written. Please hide output from the code that I have written in the knitted file. The visible knitted output should be from your code and the explanations / comments which you have written. This will allow for easier grading.


[↑ Back to the source list](#source-documents)

---

<a name="source-3"></a>

## rubric_final_project.xlsx

<small>File type: XLSX · Reader pages 812–814 · [View source PDF](PDF%20Slides.pdf#page=812)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

### Worksheet: Sheet1

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (17 rows, 6 columns).

Group Assignment 1 Rubric

Row 2

Column 5 Points

Code - Reproducibility

Column 2 Excellent

Column 3 Good

Column 4 Needs work

Row 4

Column 2 6/5

Column 3 4/3

Column 4 2/1

Column 6

- Infinity

Row 5

Column 2 Code is well-documented (both self-documented and with additional comments as necessary). Your coding style conforms to https://style.tidyverse.org/

Column 3 Easy to follow (both the code, its documentation, and the output).

Column 4 Code is poorly written and not documented. You used base R extensively, rather than tidyverse. Few, if any, comments

Column 6 if your ggplot and dplyr sequences are all on one line

Data Viualisation

Column 2 Excellent

Column 3 Good

Column 4 Needs work
Row 7

Column 2 6/5

Column 3 4/3

Column 4 2/1

Row 8

Column 2 Visualizations are informative, insightful, and visually appealing.

Column 3 Visualizations are straightforward and provide some insight into the data.

Column 4 Limited attempts to visualize the data. Elements of the visualisation are confusing to your intended audience.

Analysis- Model comparison

Column 2 Excellent

Column 3 Good

Column 4 Needs work

Row 10

Column 2 6/5

Column 3 4/3

Column 4 2/1

Row 11

Column 2 Solid comparison of several models and thorough analysis of the performance (R2, SE) of the final model.

Column 3 Some comparison of different models and some analysis of the performance of the model

Column 4 Missing either a comparison of different models or an analysis of the performance of the model

Correctness of results

Column 2 Excellent

Column 3 Good

Column 4 Needs work
Row 13

Column 2 6/5

Column 3 4/3

Column 4 2/1

Row 14

Column 2 Results are correct, with no flaws; some of the analyses were also technically challenging

Column 3 Results are generally correct, with one major flaw or many minor flaws

Column 4 Many flaws in the analysis; results are unreliable

Submission Organisation

Column 2 Excellent

Column 3 Good

Column 4 Needs work

Row 16

Column 2 6/5

Column 3 4/3

Column 4 2/1

Row 17

Column 2 You included all your code and output in an R Markdown document that was knitted to HTML or PDF. The output in the final document does not include warnings or messages. Rmd file ru

Column 3 You included your code and output in an R Markdown document, but the output includes warnings and package loading messages. Rmd file doesn't run due to simple error that we fixed f

Column 4 You did not include your code in an R Markdown document. You submitted an unknitted Rmd document. Rmd file doesn't run and the error takes too long to understand / debug.

</details>


[↑ Back to the source list](#source-documents)

---

<a name="source-4"></a>

## nyc_weather.csv

<small>File type: CSV · Reader pages 815–817 · [View source PDF](PDF%20Slides.pdf#page=815)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

> Data preview (up to six records and twelve columns); the full CSV remains in the original files.

Table displayed as labelled records for readability (6 rows, 12 columns).

New York

datetime 2010-01-01

tempmax 4.3

tempmin 0.9

temp 2.4

feelslikemax 4.1

feelslikemin -1.8

feelslike 1

dew -0.4

humidity 82.5

precip 2.4

precipprob 100

New York

datetime 2010-01-02

tempmax 1.1

tempmin -8

temp -3.5

feelslikemax -3.8

feelslikemin -17.3

feelslike -10.5

dew -10.2

humidity 60.2

precip 0.18

precipprob 100
New York

datetime 2010-01-03

tempmax -5.5

tempmin -8

temp -6.9

feelslikemax -13.2

feelslikemin -17.3

feelslike -15.2

dew -14.4

humidity 55.1

precip 0

precipprob 0

New York

datetime 2010-01-04

tempmax -1

tempmin -6.8

temp -4.7

feelslikemax -6.6

feelslikemin -14.8

feelslike -11.3

dew -12.4

humidity 55.3

precip 0

precipprob 0

New York

datetime 2010-01-05

tempmax -0.8

tempmin -6.1

temp -3.7

feelslikemax -6.1

feelslikemin -12.8

feelslike -9.7

dew -11.3

humidity 55.6

precip 0

precipprob 0
New York

datetime 2010-01-06

tempmax 1.3

tempmin -3

temp -1.6

feelslikemax -3.3

feelslikemin -9

feelslike -7.1

dew -9.5

humidity 55

precip 0

precipprob 0

</details>


[↑ Back to the source list](#source-documents)

---

<a name="source-5"></a>

## Rat_Sightings_20251004.zip

<small>File type: ZIP · Reader pages 818–818 · [View source PDF](PDF%20Slides.pdf#page=818)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

> Archive contents: 1 entries. This is an inventory, not the full contents of the nested archive.

Rat_Sightings_20251004.csv

- 

</details>


[↑ Back to the source list](#source-documents)

---

