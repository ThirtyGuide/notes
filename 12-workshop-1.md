# Workshop 1

**Data visualisation exercises**

[← All chapters](README.md) · [Original PDF](PDF%20Slides.pdf#page=713)

## Overview

- R and tidyverse tasks involving drinks, temperature anomalies and aviation data.
- Histograms, density plots and transformations before charting.
- Practice code and worked-answer material.

## Source documents

1. [workshop_1.Rmd](#source-1) — RMD, reader page 714
2. [workshop_1_ANSWERS.Rmd](#source-2) — RMD, reader page 719
3. [Airplane_Crashes_and_Fatalities_Since_1908.csv](#source-3) — CSV, reader page 727
4. [londonBikes.csv](#source-4) — CSV, reader page 729
5. [Image1.png](#source-5) — PNG, reader page 732

---

<a name="source-1"></a>

## workshop_1.Rmd

<small>File type: RMD · Reader pages 714–718 · [View source PDF](PDF%20Slides.pdf#page=714)</small>

```r
# Install any missing packages through Packages pane (bottom right) using Packages -> Install.
library(tidyverse)  # Load ggplot2, dplyr, and all the other tidyverse packages
library(mosaic)
library(plotly)
library(lubridate)
library(fivethirtyeight)
library(janitor)  # examine and clean dirty data. Will use function: clean_names()
library(here)  # constructs paths to your project's files
library(scales)  # to use scale_x_date(labels = date_format("%Y-%b"))
library(tidytext)
library(gapminder)
library(tidyquant)
library(viridis)
```

### Task 1: Beer, Wine And Spirits

Back in 2014, [fivethiryeight.com](https://fivethirtyeight.com/features/dear-mona-followup-wheredo-people-drink-the-most-beer-wine-and-spirits/) published an article on alcohol consumption in different countries. The data `drinks` is available as part of the `fivethirtyeight` package. Make sure you have installed the `fivethirtyeight` package before proceeding.

```r
library(fivethirtyeight)
data(drinks)
glimpse(drinks)
# or download directly
# alcohol_direct <- read_csv("https://raw.githubusercontent.com/fivethirtyeight/data/master/
alcohol-consumption/drinks.csv")
```

### HISTOGRAM PLOT QUESTION:

Produce a facet wrapped histogram for servings based on drink type (i.e. single plot consisting of 3 sub-plots).

Data preparation:

- Before plotting ensure to extract only the columns of interest

- Remember that your data needs to be in a tidy format for the required plotting job. There‐

fore examine whether you need to pivot the data BEFORE attempting to plot.

- Print out the resulting tibble before plotting it to ensure the intended format.

Please reproduce Image1 exactly (released with the assignment) in your code below. The following page link may be useful [Cookbook](http://www.cookbook-r.com/Graphs/Facets_(ggplot2)/).

### DENSITY PLOT QUESTION:

Following on from the above, now make a single plot with 3 overlaid densities for the beer servings, wine servings and spirit servings.
Image formatting requirements:

- x-axis and y-axis are labelled (i.e. not just default)

- title is provided

- legend is labelled as Servings

- adjust axes settings create 'tight axes' for x and y axes i.e. remove space between the

plotted data and the axes (preferred plots for research papers). You may use approximate axes scale limits or find them from the data. You can read about how to create tight axes here: [stackoverflow](https://stackoverflow.com/questions/22945651/remove-spacebetween-plotted-data-and-the-axes).

Stackoverflow will be your friend for resolving questions, you can search questions and read how others dealt with similar issues you may be experiencing. Alternatively you can also use ChatGPT as your assistant / co-pilot to help you debug and get around small issues. I would not recommend it for writing full answers, as they may incorrect or use syntax which as not been taught in class.

### BEER CONSUMING COUNTRIES

Plot the top 25 beer consuming countries.

- First select the top 25 countries

- Next use ggplot to plot a bar chart. Ensure that within ggplot you use the reorder() func‐

tion

### Task 2: Climate change and temperature anomalies

If we wanted to ----- climate change, we can find data on the *Combined Land-Surface Air and Sea-Surface Water Temperature Anomalies* in the Northern Hemisphere at [NASA's Goddard Institute for Space -------](https://data.giss.nasa.gov/gistemp). The [tabular data of temperature anomalies can be found here](https://data.giss.nasa.gov/gistemp/tabledata_v3/NH.Ts+dSST.txt)

To define temperature anomalies you need to have a reference, or base, a period which NASA states to be between 1951-1980.

Run the code below to load the file:

```r
weather <-
read_csv("https://data.giss.nasa.gov/gistemp/tabledata_v3/NH.Ts+dSST.csv",
skip = 1,  # number of lines to skip before reading data
na = "***") # NAs in csv are coded with ***
```

Notice that, when using this function, we added two options: `skip` and `na`.

- `skip=1` option is there as the real data table only starts in Row 2, so we need to skip

one row. 2. `na = "***"` option informs R how missing observations in the spreadsheet are coded. When looking at the spreadsheet, you can see that missing data is coded as "***". It is best to specify this here, as otherwise some of the data is not recognized as numeric data.
Once the data is loaded, notice that there is a object titled `weather` in the `Environment` panel. If you cannot see the panel (usually on the top-right), go to `Tools` > `Global Options` > `Pane Layout` and tick the checkbox next to `Environment`. Click on the `weather` object to inspect the tibble.

For each month and year, the tibble shows the deviation of temperature from the normal (expected). Further to that, the tibble is in a wide format.

You have two objectives in this section:

- Select the year and the twelve month variables from the `weather` dataset. We do not

need the others (J-D, D-N, DJF, etc.) for this assignment.

- Convert the tibble from 'wide' to 'long' format. Name the new tibble as `tidyweather`,

name the variable containing the name of the month as `Month`, and the temperature deviation values as `delta`.

```r
# YOUR CODE GOES HERE
```

Inspect your tibble. It should have three variables, one each for:

- year, 2. month, and 3. delta, or temperature deviation.

### Plotting Information

Plot the data using a time-series scatter plot, and add a trendline using a linear method smoothing facility. To do that, we first need to create a new variable called `date` in order to ensure that the `delta` values are plotted chronologically [code provided].

```r
tidyweather <- tidyweather %>%
mutate(date = ymd(paste(as.character(Year), Month, "1")),
month = month(date, label = TRUE), # label = TRUE ensures we create factors rather than
character data type
year = year(date))
# ggplot:
```

Is the effect of increasing temperature more pronounced in some months? Use `facet_wrap()` to produce a separate scatter plot for each month, and add a polynomial smoother (instead of the linear model) to each faceted sub-plot. Make your sub-plot arrangement have 2 rows and 6 columns.

```r
# YOUR CODE GOES HERE
```

It is sometimes useful to group data into different time periods to ----- historical data. For example, we often refer to decades such as 1970s, 1980s, 1990s etc. to refer to a period of time. (Reminder: NASA calculates a temperature anomaly, as THE difference form the base period of 1951-1980). The code below creates a new data frame called `comparison` that groups data in five time periods: 1881-1920, 1921-1950, 1951-1980, 1981-2010 and 2011-present.

We remove data before 1800 and before using `filter`. Then, we use the `mutate` function to create a new variable `interval` which contains information on which period each observation belongs to. We can assign the different periods using `case_when()`.
```r
comparison <- tidyweather %>%
filter(Year>= 1881) %>% # remove years prior to 1881
# create new variable 'interval', and assign values based on criteria below
mutate(interval = case_when(
Year %in% c(1881:1920) ~ "1881-1920",
Year %in% c(1921:1950) ~ "1921-1950",
Year %in% c(1951:1980) ~ "1951-1980",
Year %in% c(1981:2010) ~ "1981-2010",
TRUE ~ "2011-present"))
```

Inspect the `comparison` tibble by clicking on it in the `Environment` pane.

Now that we have the `interval` variable, we can create a density plot to ----- the distribution of monthly deviations (`delta`), grouped by the different time periods we are interested in. Set `fill` to `interval` column to group and colour the data by different time periods.

### Task 3: Plane Crashes

Let us look at some data about airplane crashes (from [Kaggle](https://www.kaggle.com/saurograndi/airplane-crashes-since-1908/)). This dataset lists all plane crashes between 1908 and 2009. Because this is real world data, it's messy, so we'll create a few extra variables and get rid of incomplete rows. I am providing the code to clean the data in the cell below, so you don't have to worry about it.

```r
library(lubridate)  # Loads functions like mdy(), year(), and month() that make handling of
dates easy
crashes_raw <- read_csv(here::here("Data", "Airplane_Crashes_and_Fatalities_Since_1908.csv"))
crashes <- crashes_raw %>%
# Create new variables related to dates
mutate(Date = mdy(Date),
Year = year(Date),
Month = month(Date, label = TRUE)) %>%
# Get rid of rows with missing data or where there were no fatalities
filter(!is.na(Fatalities),
!is.na(Aboard),
!is.na(Operator),
Fatalities > 0,) %>%
# Make a new variable that indicates if the flight was operated by the military
mutate(Military = ifelse(str_detect(Operator, "Military"), "Military", "Not military")) %>%
# Make a new variable that shows what percentage of people on the flight died
mutate(percent_passengers_died = Fatalities / Aboard)
```

### CRASHES PER YEAR:

Summarise the data to obtain the total number of crashes for every year. Fit a polynomial smoothing method to the data.

```r
crashes_per_year <- crashes %>%
count(Year)
```
```r
# ggplot:
```

### TOTAL DEATHS BY AIRLINE

- Create a tibble containing total number of fatalities for non-military flights, ordered by

the airline with the largest total number of fatalities first. Print out the resulting tibble.

- Present this information (only for airlines those total fatalities are greater or equal to

500) using the chart of your choice which you believe would best represent the data. Ensure your axes & graph are labelled clearly.

### PERCENTAGE OF DEATHS IN CRASHES

Obtain a plot that shows the percentage of passengers that died in crashes over time, coloured by whether or not it was a military flight.

- Standard Plot: use scatter plot smoothed with a polynomial fit

- Advanced Plot: first calculate the average crashes per year for each group: whether it was

a military or non-military plane. Next plot the smoothed scatter plot coloured by (non)military information.

```r
# --- Option 1: plot standard
# --- Option 2: plot on average
```

### Task 4: Climate change and temperature anomalies

In the last workshop, you have worked with monthly weather anomalies. However, we might be interested in average annual anomalies. We can do this by using `group_by()` and `summarise()`, followed by a scatter plot to display the result. Find the average annual anomalies (grouping by year) and plot these using a smoothing method.

```r
weather <- read_csv("https://data.giss.nasa.gov/gistemp/tabledata_v3/NH.Ts+dSST.csv",
skip = 1,  # number of lines to skip before reading data
na = "***") # NAs in csv are coded with ***
tidyweather <- weather %>%
select(Year:Dec) %>%
pivot_longer(Jan:Dec, names_to = "Month", values_to = "delta")
#creating yearly averages
#plotting the data:
```


[↑ Back to the source list](#source-documents)

---

<a name="source-2"></a>

## workshop_1_ANSWERS.Rmd

<small>File type: RMD · Reader pages 719–726 · [View source PDF](PDF%20Slides.pdf#page=719)</small>

```r
# Install any missing packages through Packages pane (bottom right) using Packages -> Install.
library(tidyverse)  # Load ggplot2, dplyr, and all the other tidyverse packages
library(mosaic)
library(plotly)
library(lubridate)
library(fivethirtyeight)
library(janitor)  # examine and clean dirty data. Will use function: clean_names()
library(here)  # constructs paths to your project's files
library(scales)  # to use scale_x_date(labels = date_format("%Y-%b"))
library(tidytext)
library(gapminder)
library(tidyquant)
library(viridis)
```

### Task 1: Beer, Wine And Spirits

Back in 2014, [fivethiryeight.com](https://fivethirtyeight.com/features/dear-mona-followup-wheredo-people-drink-the-most-beer-wine-and-spirits/) published an article on alcohol consumption in different countries. The data `drinks` is available as part of the `fivethirtyeight` package. Make sure you have installed the `fivethirtyeight` package before proceeding.

```r
library(fivethirtyeight)
data(drinks)
# or download directly
# alcohol_direct <- read_csv("https://raw.githubusercontent.com/fivethirtyeight/data/master/
alcohol-consumption/drinks.csv")
glimpse(drinks)
```

### HISTOGRAM PLOT QUESTION:

Produce a facet wrapped histogram for servings based on drink type (i.e. single plot consisting of 3 sub-plots).

Data preparation:

- Before plotting ensure to extract only the columns of interest

- Data needs to be in a tidy format, therefore examine whether you need to pivot the data

before proceeding to plot.

- Print out the resulting tibble before plotting it to ensure the intended format.

Please reproduce Image1 exactly (released with the assignment) in your code below. Note that this is a dark themed plot. The following page link may be useful [Cookbook](http:// www.cookbook-r.com/Graphs/Facets_(ggplot2)/).

```r
tb1 <- drinks %>%
select(beer_servings, spirit_servings, wine_servings) %>%
pivot_longer(cols = everything(), names_to="servings", values_to="amount") # convert from
wide to long format in order to facet with ggplot
```
```r
print(tb1)
ggplot(data = tb1, aes(x = amount)) +
geom_histogram(color = "red") +
facet_wrap(~ servings) +
theme_dark() +
labs(
x = "Amount",
y = "Count"
) +
theme(strip.background = element_rect(colour="red"), # ONLY THIS LINE IS REQUIRED FROM THE
LINK!!!
axis.title = element_text(face = "bold", colour = "blue")
) +
NULL
```

### DENSITY PLOT QUESTION:

Following on from the above, now make a single plot with 3 overlaid densities for the beer servings, wine servings and spirit servings.

Image formatting requirements:

- x-axis and y-axis are labelled (i.e. not just default)

- title is provided

- legend is labelled as Servings

- adjust axes settings create 'tight axes' for x and y axes i.e. remove space between the

plotted data and the axes (preferred plots for research papers). You may use approximate axes scale limits or find them from the data. You can read about how to create tight axes here: [stackoverflow](https://stackoverflow.com/questions/22945651/remove-spacebetween-plotted-data-and-the-axes).

Stackoverflow will be your friend for resolving questions, you can search questions and read how others dealt with similar issues you may be experiencing. Alternatively you can also use ChatGPT as your assistant / co-pilot to help you debug and get around small issues. I would not recommend it for writing full answers, as they may incorrect or use syntax which as not been taught in class.

```r
tb1 <- drinks %>%
select(beer_servings, spirit_servings, wine_servings) %>%
pivot_longer(cols = everything(), names_to="servings", values_to="amount")
print(tb1)
# Find limits for x-axis to create tight axes (can also do approximate value by hand)
tb1 %>%
summarise(max_amount = max(amount))
# 438 but will use approximate of 450.
ggplot(data = tb1, aes(x = amount)) +
geom_density(aes(fill = servings, alpha = 0.3)) +
scale_x_continuous(limits = c(0,450), expand = c(0, 0)) +  # 438 is correct value but 450
approx ok
scale_y_continuous(limits = c(0,0.018), expand = c(0, 0)) + # approx value ok
labs(
```
```r
title = "Density plots for servings",
x = "Amount",
y = "Density",
fill = "Servings"
) +
NULL
```

### BEER CONSUMING COUNTRIES

Plot the top 25 beer consuming countries.

- First select the top 25 countries

- Next use ggplot to plot a bar chart. Ensure that within ggplot you use the reorder() func‐

tion

```r
df <- drinks %>%
select(country, beer_servings) %>%
arrange(desc(beer_servings)) %>%
top_n(n = 25)
ggplot(data = df, aes(x = reorder(country, beer_servings), y = beer_servings, fill = country))
+
geom_bar(stat = "identity") +
theme(legend.position = "none") +
coord_flip() + # we are flipping the x and y axis around to make the plot prettier.
theme(axis.text.x = element_text(angle = 90, hjust = 1, vjust = 0.5)) + # Note that the x-
axis ticks have been flipped 90 degrees
labs(
title = "Top 25 Beer consuming countries",
x = "Country",
y = "Beer servings"
)
```

### Task 2: Climate change and temperature anomalies

If we wanted to ----- climate change, we can find data on the *Combined Land-Surface Air and Sea-Surface Water Temperature Anomalies* in the Northern Hemisphere at [NASA's Goddard Institute for Space -------](https://data.giss.nasa.gov/gistemp). The [tabular data of temperature anomalies can be found here](https://data.giss.nasa.gov/gistemp/tabledata_v3/NH.Ts+dSST.txt)

To define temperature anomalies you need to have a reference, or base, a period which NASA states to be between 1951-1980.

Run the code below to load the file:

```r
weather <-
read_csv("https://data.giss.nasa.gov/gistemp/tabledata_v3/NH.Ts+dSST.csv",
skip = 1,  # number of lines to skip before reading data
na = "***") # NAs in csv are coded with ***
```

Notice that, when using this function, we added two options: `skip` and `na`.
- `skip=1` option is there as the real data table only starts in Row 2, so we need to skip

one row. 2. `na = "***"` option informs R how missing observations in the spreadsheet are coded. When looking at the spreadsheet, you can see that missing data is coded as "***". It is best to specify this here, as otherwise some of the data is not recognized as numeric data.

Once the data is loaded, notice that there is a object titled `weather` in the `Environment` panel. If you cannot see the panel (usually on the top-right), go to `Tools` > `Global Options` > `Pane Layout` and tick the checkbox next to `Environment`. Click on the `weather` object to inspect the tibble.

For each month and year, the tibble shows the deviation of temperature from the normal (expected). Further to that, the tibble is in a wide format.

You have two objectives in this section:

- Select the year and the twelve month variables from the `weather` dataset. We do not

need the others (J-D, D-N, DJF, etc.) for this assignment.

- Convert the tibble from 'wide' to 'long' format. Name the new tibble as `tidyweather`,

name the variable containing the name of the month as `Month`, and the temperature deviation values as `delta`.

```r
tidyweather <- weather %>%
select(Year:Dec) %>%
pivot_longer(Jan:Dec, names_to = "Month", values_to = "delta")
tidyweather # 1680 x 3
```

Inspect your tibble. It should have three variables, one each for:

- year, 2. month, and 3. delta, or temperature deviation.

### PLOTTING INFORMATION

Plot the data using a time-series scatter plot, and add a trendline using a linear method smoothing facility. To do that, we first need to create a new variable called `date` in order to ensure that the `delta` values are plotted chronologically [code provided].

```r
tidyweather <- tidyweather %>%
mutate(date = ymd(paste(as.character(Year), Month, "1")),
month = month(date, label = TRUE), # label = TRUE ensures we create factors rather than
character data type
year = year(date))
ggplot(tidyweather, aes(x = date, y = delta))+
geom_point() +
geom_smooth(method = "lm", color = "red") +
theme_bw() +
labs(title = "Weather Anomalies")
```

Is the effect of increasing temperature more pronounced in some months? Use `facet_wrap()` to produce a separate scatter plot for each month, and add a polynomial smoother (instead of the linear model) to each faceted sub-plot. Make your sub-plot arrangement have 2 rows and 6 columns.
```r
ggplot(tidyweather, aes(x = date, y = delta))+
geom_point() +
geom_smooth(method = "loess", color = "red") + # can also drop explicit command for method =
"loess" as it is the default setting
geom_hline(yintercept = 0, color = "blue") + # 0 degrees in blue
facet_wrap(~ month, nrow = 2) +
theme_bw() +
labs (title = "Weather Anomalies Per Month Of The Year")
```

There is more evident increase in temperature in the winter months.

It is sometimes useful to group data into different time periods to ----- historical data. For example, we often refer to decades such as 1970s, 1980s, 1990s etc. to refer to a period of time. (Reminder: NASA calculates a temperature anomaly, as THE difference form the base period of 1951-1980). The code below creates a new data frame called `comparison` that groups data in five time periods: 1881-1920, 1921-1950, 1951-1980, 1981-2010 and 2011-present.

We remove data before 1800 and prior, using `filter`. Then, we use the `mutate` function to create a new variable `interval` which contains information on which period each observation belongs to. We can assign the different periods using `case_when()`.

```r
comparison <- tidyweather %>%
filter(Year >= 1881) %>% # remove years prior to 1881
# create new variable 'interval', and assign values based on criteria below
mutate(interval =
case_when(
Year %in% c(1881:1920) ~ "1881-1920",
Year %in% c(1921:1950) ~ "1921-1950",
Year %in% c(1951:1980) ~ "1951-1980",
Year %in% c(1981:2010) ~ "1981-2010",
TRUE ~ "2011-present"))
```

Inspect the `comparison` tibble by clicking on it in the `Environment` pane.

Now that we have the `interval` variable, we can create a density plot to ----- the distribution of monthly deviations (`delta`), grouped by the different time periods we are interested in. Set `fill` to `interval` column to group and colour the data by different time periods.

```r
ggplot(comparison, aes(x = delta, fill = interval))+
geom_density(alpha = 0.3) + # density plot with transparency set to 30%
theme_bw() +  # theme
labs (title = "Density Plot for Monthly Temperature Anomalies",
y = "Density", x = "Delta")
```

### Task 3: Plane Crashes

Let us look at some data about airplane crashes (from [Kaggle](https://www.kaggle.com/saurograndi/airplane-crashes-since-1908/)). This dataset lists all plane crashes between 1908 and 2009. Because this is real world data, it's messy, so we'll create a few extra variables and get rid of incomplete rows. I am providing the code to clean the data in the cell below, so you don't have to worry about it.

```r
library(lubridate)  # Loads functions like mdy(), year(), and month() that make handling of
dates easy
```
```r
crashes_raw <- read_csv("Airplane_Crashes_and_Fatalities_Since_1908.csv")
crashes <- crashes_raw %>%
# Create new variables related to dates
mutate(Date = mdy(Date),
Year = year(Date),
Month = month(Date, label = TRUE)) %>%
# Get rid of rows with missing data or where there were no fatalities
filter(!is.na(Fatalities),
!is.na(Aboard),
!is.na(Operator),
Fatalities > 0,) %>%
# Make a new variable that indicates if the flight was operated by the military
mutate(Military = ifelse(str_detect(Operator, "Military"), "Military", "Not military")) %>%
# Make a new variable that shows what percentage of people on the flight died
mutate(percent_passengers_died = Fatalities / Aboard)
```

### CRASHES PER YEAR:

Summarise the data to obtain the total number of crashes for every year. Fit a curve of best fit to the data using polynomial smoothing method.

```r
crashes_per_year <- crashes %>%
group_by(Year) %>%
summarise(count = n())
ggplot(data = crashes_per_year, aes(x = Year, y = count)) +
geom_point() +
geom_line() +
stat_smooth(method = "loess", color = "red", size = 1.5) +
labs(x = "Year", y = "Number of crashes", title = "Polynomial fit for crashes per year")
```

### TOTAL DEATHS BY AIRLINE:

- Create a tibble containing total number of fatalities for non-military flights, ordered by

the airline with the largest total number of fatalities first. Print out the resulting tibble.

```r
gp_airline <- crashes %>%
filter(Military == 'Not military') %>% # note that -------- have to deal with the space in
the row names
select(Operator, Fatalities) %>%
group_by(Operator) %>%
summarise(tot_fatalities = sum(Fatalities)) %>%
arrange(desc(tot_fatalities))
print(gp_airline)
```

- Present this information (only for airlines those total fatalities are greater or equal to

500) using the chart of your choice which you believe would best represent the data. Ensure your axes & graph are labelled.

```r
gp_airline_filtered <- gp_airline %>%
filter(tot_fatalities >= 500)
```
```r
ggplot(data = gp_airline_filtered, aes(x = reorder(Operator, tot_fatalities), y =
tot_fatalities, fill = Operator)) +
geom_bar(stat = "identity") +
theme(legend.position = "none") +
coord_flip() + # we are flipping the x and y axis around to make the plot prettier.
theme(axis.text.x = element_text(angle = 90, hjust = 1, vjust = 0.5)) + # Note that the x-
axis ticks have been flipped 90 degrees
labs(
title = "Dangerous airlines",
x = "Operator",
y = "Total fatalities"
)
```

### PERCENTAGE OF DEATHS IN CRASHES

Obtain a plot that shows the percentage of passengers that died in crashes over time, coloured by whether or not it was a military flight.

- Standard Plot: use scatter plot smoothed with a polynomial fit

- Advanced Plot: first calculate the average crashes per year for each group: whether it was

a military or non-military plane. Next plot the smoothed scatter plot coloured by (non)military information.

```r
# --- Option 1: plot standard
crashes %>%
ggplot(aes(x = Date, y = percent_passengers_died, color = Military)) +
geom_point() +
geom_smooth(method = 'loess') +
theme(legend.title = element_blank()) + # remove legend title
labs(title = "Mortality rate of plane crashes over time",
subtitle = "Military vs. non-military plane crashes",
x = "Year",
y = "Mortality rate")
# --- Option 2: plot on average
crashes_average <- crashes %>%
select(Year, percent_passengers_died, Military)%>%
group_by(Year, Military)%>%
summarise(M = mean(percent_passengers_died))
ggplot(crashes_average, aes(x = Year, y = M, color = Military))+
geom_point() +
geom_smooth() +
labs(title = "Average % number of dead passengers over the last 100 years",
x = "Year",
y = "Average Percentage of dead passengers")
```

Plane crashes were rare before 1920 and increasing thereafter (especially so throughout the 1940s). Plane crashes before 1920 are almost exclusively military. This is most likely due to the fact that commercial air planes were not common at the time. A very large number of plane crashes ends deadly for 100% of passengers. There are also quite a few with less than 15% dead, however never reaching 0 (entries without fatalities were filtered earlier). In between it seems fairly evenly scattered. However, the trendlines are both very high (80% and more) throughout, once again highlighting that a great amount of crashes end deadly for everyone. Military plane crashes had a fatality rate below 90% in the early 1900s, but rose to close to 100% around 1940.
After that there were only minor fluctuations with the rate always being above 90%. The trendline for non-military crashes starts at almost 100% mortality rate but then decreases to about 80% in 1950, also having only minor fluctuations until now.

### Task 4: Climate change and temperature anomalies

In the last workshop, you have worked with monthly weather anomalies. However, we might be interested in average annual anomalies. We can do this by using `group_by()` and `summarise()`, followed by a scatter plot to display the result. Find the average annual anomalies (grouping by year) and plot these using a smoothing method.

```r
weather <- read_csv("https://data.giss.nasa.gov/gistemp/tabledata_v3/NH.Ts+dSST.csv",
skip = 1,  # number of lines to skip before reading data
na = "***") # NAs in csv are coded with ***
tidyweather <- weather %>%
select(Year:Dec) %>%
pivot_longer(Jan:Dec, names_to = "Month", values_to = "delta")
#creating yearly averages
average_annual_anomaly <- tidyweather %>%
group_by(Year) %>%  #grouping data by Year
# creating summaries for mean delta
# use `na.rm=TRUE` to eliminate NA (not available) values
summarise(annual_average_delta = mean(delta, na.rm=TRUE))
#plotting the data:
ggplot(average_annual_anomaly, aes(x = Year, y = annual_average_delta)) +
geom_point() +
# Fit the best fit line, using LOESS method
geom_smooth() + # note the default polynomial fit with confidence intervals around the fit.
theme_bw() +
labs(title = "Average Yearly Anomaly",
y = "Average Annual Delta")
```


[↑ Back to the source list](#source-documents)

---

<a name="source-3"></a>

## Airplane_Crashes_and_Fatalities_Since_1908.csv

<small>File type: CSV · Reader pages 727–728 · [View source PDF](PDF%20Slides.pdf#page=727)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

> Data preview (up to six records and twelve columns); the full CSV remains in the original files.

Table displayed as labelled records for readability (6 rows, 12 columns).

09/17/1908

Time 17:18

Location Fort Myer, Virginia

Operator Military - U.S. Army

Route Demonstration

Type Wright Flyer III

cn/In 1

Aboard 2

Fatalities 1

Ground 0

07/12/1912

Time 06:30

Location AtlantiCity, New Jersey

Operator Military - U.S. Navy

Route ---- flight

Type Dirigible

Aboard 5

Fatalities 5

Ground 0

08/06/1913

Location Victoria, British Columbia, Canada

Operator Private

Flight # -

Type Curtiss seaplane

Aboard 1

Fatalities 1

Ground 0
09/09/1913

Time 18:30

Location Over the North Sea

Operator Military - German Navy

Type Zeppelin L-1 (airship)

Aboard 20

Fatalities 14

Ground 0

10/17/1913

Time 10:30

Location Near Johannisthal, Germany

Operator Military - German Navy

Type Zeppelin L-2 (airship)

Aboard 30

Fatalities 30

Ground 0

03/05/1915

Time 01:00

Location Tienen, Belgium

Operator Military - German Navy

Type Zeppelin L-8 (airship)

Aboard 41

Fatalities 21

Ground 0

</details>


[↑ Back to the source list](#source-documents)

---

<a name="source-4"></a>

## londonBikes.csv

<small>File type: CSV · Reader pages 729–731 · [View source PDF](PDF%20Slides.pdf#page=729)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

> Data preview (up to six records and twelve columns); the full CSV remains in the original files.

Table displayed as labelled records for readability (6 rows, 12 columns).

01-01-11

bikes_hired 4555

season 1

avg_temp 6

avg_humidity 84

avg_pressure 1025

avg_windspeed 10

rainfall_mm 0

rain TRUE

fog FALSE

thunderstorm FALSE

snow FALSE

02-01-11

bikes_hired 6250

season 1

avg_temp 3

avg_humidity 79

avg_pressure 1028

avg_windspeed 8

rainfall_mm 0

rain FALSE

fog FALSE

thunderstorm FALSE

snow FALSE
03-01-11

bikes_hired 7262

season 1

avg_temp 0

avg_humidity 80

avg_pressure 1024

avg_windspeed 6

rainfall_mm 0

rain FALSE

fog FALSE

thunderstorm FALSE

snow TRUE

04-01-11

bikes_hired 13430

season 1

avg_temp 3

avg_humidity 87

avg_pressure 1013

avg_windspeed 6

rainfall_mm 0

rain TRUE

fog FALSE

thunderstorm FALSE

snow FALSE

05-01-11

bikes_hired 13757

season 1

avg_temp 6

avg_humidity 84

avg_pressure 1000

avg_windspeed 19

rainfall_mm 0

rain TRUE

fog FALSE

thunderstorm FALSE

snow FALSE
06-01-11

bikes_hired 9595

season 1

avg_temp 4

avg_humidity 92

avg_pressure 996

avg_windspeed 5

rainfall_mm 0

rain TRUE

fog TRUE

thunderstorm FALSE

snow TRUE

</details>


[↑ Back to the source list](#source-documents)

---

<a name="source-5"></a>

## Image1.png

<small>File type: PNG · Reader pages 732–732 · [View source PDF](PDF%20Slides.pdf#page=732)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

See the original media file for its visual content.

</details>


[↑ Back to the source list](#source-documents)

---

