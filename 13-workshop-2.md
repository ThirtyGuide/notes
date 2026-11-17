# Workshop 2

**Confidence-interval exercises**

[← All chapters](README.md) · [Original PDF](PDF%20Slides.pdf#page=733)

## Overview

- Intervals for weather anomalies and stock returns.
- Comparison and interpretation of intervals.
- R Markdown tasks, answers and ticker-data previews.

## Source documents

1. [practice_questions_CI.pdf](#source-1) — PDF, reader page 734
2. [practice_questions_CI_ANSWERS.pdf](#source-2) — PDF, reader page 736
3. [workshop_2.Rmd](#source-3) — RMD, reader page 739
4. [workshop_2_ANSWERS.Rmd](#source-4) — RMD, reader page 743
5. [yahoo_finance_tickers.csv](#source-5) — CSV, reader page 749

---

<a name="source-1"></a>

## practice_questions_CI.pdf

<small>File type: PDF · Reader pages 734–735 · [View source PDF](PDF%20Slides.pdf#page=734)</small>

<small>Source Page 1 of 2</small>

Q2. The general manager for the Dairy Gold Creamery is interested in estimating the mean number of gallons of milk that are purchased by families in the Toledo, Ohio, area. He would like his estimate to be within plus or minus 0.50 gallons per month, and he would like the estimate to be at the 99% confidence level. Past ------- have shown that the population standard deviation for

purchase amount is 4.0 gallons. How large should the sample size be? Hint: think of it as z*σ/ SQRT(n) ≤ 0.5 Q3. Medlin & Associates is a regional certified public accounting (CPA) firm located near Minneapolis. Recently, a team conducted an audit for a discount chain. One part of the audit involved developing an estimate for the mean dollar error in total charges that occurs during the

checkout process. The firm wishes to develop a 90% confidence interval estimate for the population mean. To do so, a random sample of n=20 is selected, with the following data. (Note: Positive values indicate that the customer was overcharged.)

The sample mean is $0.77, and the sample standard deviation is $1.19.

a) Compute the above confidence interval for the mean of the errors made in all customers’ bills (“the population”) at the discount chain store.

b) Now build a 95% confidence interval.

c) Food for thought: if as a manager of the company you believed the true population mean was 0, given the intervals you built, do you think your sample data supports your belief? We will discuss this in Session 3. Q4. XtraNet, an Internet service provider (ISP), has experienced rapid growth in the past five years. As a part of its marketing strategy, XtraNet promises fast connections

and dependable service. To achieve its objectives, XtraNet constantly evaluates the capacity of its servers. One component of its evaluation is an analysis of the average amount of time a customer is connected and using the Internet daily. A random sample of 12 customer records shows the following daily usage times, in minutes,

and the following sample statistics were obtained: x̅ = 318, s= 37.214.

<small>Source Page 2 of 2</small>

a) Using the sample data, state the best point estimate of the population mean for daily usage times for XtraNet’s customers.
c) Construct and interpret a 99% confidence interval for the mean daily usage time for XtraNet’s customers.

b) The managers of Xtranet’s marketing department would like to develop a 99% confidence interval estimate for the population mean daily customer usage time. Because the population standard deviation of daily customer usage time is unknown and the sample size is small, what assumption must the marketing managers make concerning the population of daily customer usage times?


[↑ Back to the source list](#source-documents)

---

<a name="source-2"></a>

## practice_questions_CI_ANSWERS.pdf

<small>File type: PDF · Reader pages 736–738 · [View source PDF](PDF%20Slides.pdf#page=736)</small>

<small>Source Page 1 of 3</small>

### Solution:

a) small sample size (<30), normal distribution but estimated standard deviation -> use the t-distribution.

CL = 98% = t-critical = qt(0.99, 10-1) = 2.82. xbar = 134/10=13.4.

CI = 13.4 ± 2.82*3.1/sqrt(10) = [10.63, 16.17]

b) large size (>30), can use z value = qnorm(0.99) = 2.326.

xbar = 3744/120 = 31.2 CI = 31.2 ± 2.362 * 8.2/sqrt(120) = [29.43, 39.97]

c) small sample, but the standard deviation is known, the population is normal, can use the z value = qnorm(0.99) = 2.326. xbar = 40.5/9 = 4.5 CI = 4.5 ± 2.362 * 2.9/sqrt(9) = [2.22, 6.78] You can also look up the z-value from the tables. Q2. The general manager for the Dairy Gold Creamery is interested in estimating the mean number of gallons of milk that are purchased by families in

the Toledo, Ohio, area. He would like his estimate to be within plus or minus 0.50 gallons per month, and he would like the estimate to be at the 99% confidence level. Past ------- have shown that the population standard deviation for purchase amount is 4.0 gallons. How large should the sample size be? Hint: think of it as z*σ/SQRT(n) ≤ 0.5 Solution:

The hint tells us we need to find the z-score. In r the z-score for 99% CI is qnorm(0.995) = 2.5758. Now we can solve the above equation for n: 2.5758*4/sqrt(n) ≤ 0.5 = sqrt(n) ³ 2.5758

- 4/0.5 = 20.606 20.606 ^ 2 = 424.61 = 425 samples Q3. Medlin & Associates is a regional

certified public accounting (CPA) firm located near Minneapolis. Recently, a team conducted an audit for a discount

chain. One part of the audit involved developing an estimate for the mean dollar error in total charges that occurs during the checkout process. The firm wishes to develop a 90% confidence interval estimate for the population mean. To do so, a random sample of n=20 is selected, with the following data. (Note: Positive values indicate that the customer was overcharged.)

<small>Source Page 2 of 3</small>

The sample mean is $0.77, and the sample standard deviation is $1.19.

a) Compute the above confidence interval for the mean of the errors made in all
mean was 0, given the intervals you built, do you think your sample data supports your belief? We will discuss this in Session 3. Solution:

customers’ bills (“the population”) at the discount chain store.

b) Now build a 95% confidence interval.

c) Food for thought: if as a manager of the company you believed the true population

a) The sample size is small n<30, and we don’t know if the population is normally distributed therefore, we cannot simply apply the t-distribution straight away (it assumes that the underlying population is normally distributed). We can try to visualise the distribution in R to check if it resembles the normal first: sample <- c(0.00, 1.2, 0.43, 1, 1.47, 0.83, 0.50, 3.34, 1.58, 1.46 -0.36, -1.10, 2.60, 0.00, 0.00, -1.70, 0.83, 1.99, 0.00, 1.34) hist(sample, main="Histogram of Sample Data", xlab="Values", ylab="Frequency", col="lightblue", border="black")

Histogram of Sample Data

Frequency

−2 −1

Values

A histogram of n<30 observations, even if drawn from a normal distribution, would not generally have a normal shape. The graph above does resemble normal, so with caution, if we still pressed to come up with a range, we shall use the t-Dist: qt(0.95, 20-1) = 1.73 90% CI = 0.77 ± 1.73 * 1.19/sqrt(20) = [$0.31, $1.23]

b) 95% CI qt(0.975, 20-1) = 2.09 CI = 0.77 ± 2.09* 1.19/sqrt(20) = [$0.21, $1.33]

c) The calculated CI do not include the belief of 0, therefore most likely that belief

should not be upheld. We will see how to formatlly ---- this in session 3.

Q4. XtraNet, an Internet service provider (ISP), has experienced rapid growth in the past five years. As a part of its marketing strategy, XtraNet promises fast connections and dependable service. To achieve its objectives, XtraNet constantly evaluates the capacity of its servers. One component of its evaluation is an analysis of the average amount of time a customer is connected and using the Internet daily. A random sample of 12 customer records shows the following daily usage times, in minutes,

<small>Source Page 3 of 3</small>

and the following sample statistics were obtained: x̅ = 318, s= 37.214.

a) Using the sample data, state the best point estimate of the population mean for daily usage times for XtraNet’s customers.
b) The managers of Xtranet’s marketing department would like to develop a 99% confidence interval estimate for the population mean daily customer usage time. Because the population standard deviation of daily customer usage time is unknown and the sample size is small, what assumption must the marketing managers make concerning the population of daily customer usage times?

c) Construct and interpret a 99% confidence interval for the mean daily usage time for XtraNet’s customers.

Solution:

a) The sample mean of 318 is the best point estimate of the population mean.

b) If the managers want to apply the CI formulas covered in class, then they must verify that the population distribution is normal.

c) Assuming that the population distribution is normal, we can use the T-distribution to compute the confidence interval, we use the qt() function in R:

qt(0.995, 12-1) = 3.105807 CI = 318 ± 3.105807 * 37.214/sqrt(12) = [284.64, 351.36] Assuming that the population distribution is normal, if we built 100 such CI for different samples, 99 of them could contain the true population mean inside the intervals.


[↑ Back to the source list](#source-documents)

---

<a name="source-3"></a>

## workshop_2.Rmd

<small>File type: RMD · Reader pages 739–742 · [View source PDF](PDF%20Slides.pdf#page=739)</small>

```r
library(mosaic)
library(tidyverse)
library(tidyquant)
options(digits = 3)
# Some customization. You can alter or delete as desired (if you know what you are doing).
knitr::opts_chunk$set(
tidy = FALSE,  # display code as typed
size = "small")  # slightly smaller font for code
```

### Task 1: Confidence Intervals - Weather Anomalies

In the last workshop, you have worked with monthly weather anomalies.

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

[NASA points out on their website](https://earthobservatory.nasa.gov/world-of-change/ decadaltemp.php) that

A one-degree global change is significant because it takes a vast amount of heat to warm all the oceans, atmosphere, and land by that much. In the past, a one- to two-degree drop was all it took to plunge the Earth into the Little Ice Age.

We are going to work with the average temperature deviation (delta) since 2011. Construct a **90% confidence** interval for the average annual delta since 2011. Recall that the tibble `comparison` has already grouped temperature anomalies according to time intervals; we are only interested in what is happening between 2011-present.
Hints:

- this tibble contains missing values, however summarise() verb expects a tibble without

missing values. You could use na.omit() function before using summarise() in order to omit values that are not available.

- obtain the number of observations before deciding if you are allowed to use the z-value or

not (i.e. does CLT hold?)

- if CLT holds, then proceed to calculate the confidence interval

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
# extract data just for 2011 to present
data_2011_to_present <- comparison %>%
# obtain number of delta observations
n <- length(data_2011_to_present$delta)
print(n)
formula_ci <- comparison %>%
# YOUR CODE GOES HERE
# display the found CI
formula_ci
```

> Explain the meaning of a confidence interval. Explain the effect of using a 90% Confidence vs a 95% confidence on the width of the constructed CI.

### Task 2: Confidence Intervals - Stock Returns

Calculate and plot risk/return profile of stocks

We will use the `tidyquant` package to download historical data of stock prices, calculate returns, and examine the distribution of returns.

The `tidyquant` package allows us to download historical prices for many financial assets, most of them coming through Yahoo Finance. We must first identify which stocks we want to download data for, and for this we must know their **ticker** symbol; Apple is known as AAPL, Microsoft as MSFT, McDonald's as MCD, etc.

In September 2017, Samir Khan from the [investexcel.net website](http://investexcel.net/all-yahoo-finance-stock-tickers/) got a list of all Yahoo finance tickers, and we will use a modified version of that list of tickers.
```r
tickers  <- read_csv(here::here("Data","yahoo_finance_tickers.csv"))
```

The `tickers` dataframe contains 207,533 tickers of various instruments, the `name` of the instrument, the `exchange` it is traded at, which market sector it belongs to (`category_name`), and the `type` of the instrument, namely stocks, market indices, or ETFs.

Based on this dataset, I want you to create two bar plots:

- A bar plot that shows the top 25 countries with respect to tickers. The bars should be

arranged with the first one being the largest, etc.

- Similary, a bar plot with the top 25 market sectors (`category_name`), again arranged in

descending order.

Hint: be mindful of missing observations.

```r
# YOUR CODE GOES HERE
# YOUR CODE GOES HERE
```

Comment on your findings.

> TYPE YOUR ANSWER AFTER (AND OUTSIDE!) THIS BLOCKQUOTE.

Next, choose around a dozen stocks, preferably from your country, or a sector (`category_name`) that interests you. Create a new variable my_tickers with your chosen tickers, here are mine: `my_tickers <- c("AAPL", "MSFT", "IBM", "AMZN", "NVDA", "JLL", "INTC", "ABB", "NKE")` and would then use tidyquant to download the last 4 years worth of data.

```r
my_tickers <- c("AAPL", "MSFT", "IBM", "AMZN", "NVDA", "JLL", "INTC", "ABB", "NKE") # enter
chosen tickers here-- ENSURE TO USE MSFT and INTC (but not the others), since we will use
these two later on.
myStocks <- my_tickers %>%
tq_get(get  = "stock.prices",
from = "2017-10-01",
to  = "2021-10-01") %>%
group_by(symbol)
glimpse(myStocks) # examine the structure of the resulting data frame
```

Financial performance and CAPM analysis depend on returns; If I buy a stock today for 100 and I sell it tomorrow for 101.75, my one-day return, assuming no transaction costs, is 1.75%. So given the adjusted closing prices we downloaded, our first step is to calculate daily and monthly returns.

```r
#calculate monthly  returns
myStocks_returns_monthly <- myStocks %>%
tq_transmute(select  = adjusted, # want to work with adjusted closing price column
mutate_fun = periodReturn,
period  = "monthly",
type  = "arithmetic",
```
```r
col_rename = "monthly_returns",
cols = c(nested.col))
```

Create a table where you summarise monthly returns for each of the stocks: min, max, median, sample mean, sample SD.

```r
# YOUR CODE GOES HERE
```

Plot a faceted density plot, using `geom_density()`, for each of the stocks and drop the legend.

```r
# YOUR CODE GOES HERE
```

What can you infer from this plot? Which stock has the highest/lowest volatility?

> TYPE YOUR ANSWER AFTER (AND OUTSIDE!) THIS BLOCKQUOTE.

Finally, make a plot that shows the expected monthly return (sample mean) of a stock on the Y axis and the risk (sample standard deviation) in the X-axis. You can use different colours for different tickers, but more importantly please print the label of each ticker next to the stock, using `geom_text(aes(label = ticker))`.

```r
# YOUR CODE GOES HERE
```

What can you infer from this plot? Are there any stocks which, while being riskier, do not have a higher expected return?

> TYPE YOUR ANSWER AFTER (AND OUTSIDE!) THIS BLOCKQUOTE.

### Key Definitions

Provide an explanation for each of these terms:

- Sample Statistic : ???

- Standard Error : ???

- When should you use Standard Deviation of the sample? : ???

- t-Statistic : ???

- Critical level : ???

### Two separate CIs

Build two separate confidence intervals for monthly mean return: one for stock INTC and another for stock MSFT. Check if the two CIs overlap.

```r
stats <- myStocks_returns_monthly %>%
# YOUR CODE GOES HERE
print(stats)
```


[↑ Back to the source list](#source-documents)

---

<a name="source-4"></a>

## workshop_2_ANSWERS.Rmd

<small>File type: RMD · Reader pages 743–748 · [View source PDF](PDF%20Slides.pdf#page=743)</small>

```r
library(mosaic)
library(tidyverse)
library(tidyquant)
options(digits = 3)
# Some customization. You can alter or delete as desired (if you know what you are doing).
knitr::opts_chunk$set(
tidy = FALSE,  # display code as typed
size = "small")  # slightly smaller font for code
```

### Task 1: Confidence Intervals - Weather Anomalies

In the last workshop, you have worked with monthly weather anomalies.

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

[NASA points out on their website](https://earthobservatory.nasa.gov/world-of-change/decadaltemp.php) that a one-degree global change is significant because it takes a vast amount of heat to warm all the oceans, atmosphere, and land by that much. In the past, a one- to two-degree drop was all it took to plunge the Earth into the Little Ice Age.

We are going to work with the average temperature deviation (delta) since 2011. Construct a **90% confidence** interval for the average annual delta since 2011. Recall that the tibble `comparison` has already grouped temperature anomalies according to time intervals; we are only interested in what is happening between 2011-present.

Hints:
- this tibble contains missing values, however summarise() verb expects a tibble without

missing values. You could use na.omit() function before using summarise() in order to omit values that are not available.

- obtain the number of observations before deciding if you are allowed to use the z-value or

not (i.e. does CLT hold?)

- if CLT holds, then proceed to calculate the confidence interval

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
data_2011_to_present <- comparison %>%
filter(interval == "2011-present") %>%
na.omit() # alternatively use `na.rm=TRUE` inside each function to eliminate NA (not
available) values
# obtain number of delta observations
n <- length(data_2011_to_present$delta)
print(n)
# since n is larger than 30 we can use the z-value by CLT
formula_ci <- data_2011_to_present %>%
summarise(
mu = mean(delta),
sigma = sd(delta),
z_critical = qnorm(0.95), # for 90% CI we leave (100-90)/2 = 0.05% in each tail. Therefore
we pass in 0.95
se = sigma / sqrt(n),
margin_of_error = z_critical*se,
lower_ci = mu - margin_of_error,
upper_ci = mu + margin_of_error
)
formula_ci
```

> Explain the meaning of a confidence interval. Explain the effect of using a 90% Confidence vs a 95% confidence on the width of the constructed CI.

Loosely we can say that if 100 such intervals were constructed, 95 of them would contain the true population mean. A 90% confidence will result in a narrower CI (since we are using a smaller zvalue).

### Task 2 Confidence Intervals - Stock Returns

Calculate and plot risk/return profile of stocks

> You may find useful the material on [sources of data]().

We will use the `tidyquant` package to download historical data of stock prices, calculate returns, and examine the distribution of returns.
The `tidyquant` package allows us to download historical prices for many financial assets, most of them coming through Yahoo Finance. We must first identify which stocks we want to download data for, and for this we must know their **ticker** symbol; Apple is known as AAPL, Microsoft as MSFT, McDonald's as MCD, etc.

In September 2017, Samir Khan from the [investexcel.net website](http://investexcel.net/all-yahoo-finance-stock-tickers/) got a list of all Yahoo finance tickers, and we will use a modified version of that list of tickers.

```r
tickers <- read_csv("yahoo_finance_tickers.csv")
```

The `tickers` tibble contains 207,533 tickers of various instruments, the `name` of the instrument, the `exchange` it is traded at, which market sector it belongs to (`category_name`), and the `type` of the instrument, namely stocks, market indices, or ETFs.

Based on this dataset, please create two bar plots:

- A bar plot that shows the top 25 countries with respect to tickers. The bars should be

arranged with the first one being the largest (descending order).

- Similarly, produce a bar plot with the top 25 market sectors (`category_name`), again

arranged in descending order.

Hint: be mindful of missing observations.

```r
country_25 <- tickers %>%
group_by(country) %>%
summarise(count = n()) %>%
na.omit() %>%
arrange(desc(count)) %>%
head(25)
ggplot(country_25, aes(x = reorder(country, count), y = count, fill = country)) +
geom_col() +
coord_flip() +
theme_bw() +
theme(legend.position = "none") +
labs(title = "Top 25 Countries With Most Tickers",
x = "",
y = "Count")
sectors_25 <- tickers %>%
group_by(category_name) %>%
summarise(count = n()) %>%
na.omit() %>%
arrange(desc(count)) %>%
head(25)
ggplot(sectors_25, aes(x = reorder(category_name, count), y = count, fill = category_name)) +
geom_col() +
coord_flip() +
theme_bw() +
theme(legend.position = "none") +
labs(title="Top 25 Sectors With Most Tickers",
```
```r
x = "",
y = "Count")
```

Comment on your findings.

> TYPE YOUR ANSWER AFTER (AND OUTSIDE!) THIS BLOCKQUOTE.

Unsurprisingly, the above graphs show the US, Germany and France dominate the ranking of number of tickers by country. While these large economic players were to be expected, it is interesting to see India in front of countries like the UK. This can mean that Indian companies tend to trade more on the stock market than UK companies do (perhaps they prefer to be privately held).

As for sectors, the ranking is highly dominated by the Industrial Metals and Minerals industry, which is then followed by a variety of categories like Biotechnology or Diversified Machinery. It is interesting to note that most publicly traded companies seem to belong to the world of the industry rather than to the one of consumer goods.

Next, choose around a dozen stocks, preferably from your country, or a sector (`category_name`) that interests you. Create a new variable my_tickers with your chosen tickers, here are mine: `my_tickers <- c("AAPL", "MSFT", "IBM", "AMZN", "NVDA", "JLL", "INTC", "ABB", "NKE")` Use tidyquant to download the last 4 years worth of data.

```r
my_tickers <- c("AAPL", "MSFT", "IBM", "AMZN", "NVDA", "JLL", "INTC", "ABB", "NKE") # enter
chosen tickers here-- ENSURE TO USE MSFT and INTC (but not the others), since we will use
these two later on.
myStocks <- my_tickers %>%
tq_get(get  = "stock.prices",
from = "2017-10-01",
to  = "2021-10-01") %>%
group_by(symbol)
glimpse(myStocks) # examine the structure of the resulting data frame
```

Financial performance and CAPM analysis depend on returns. If I buy a stock today for 100 and I sell it tomorrow for 101.75, my one-day return, assuming no transaction costs, is 1.75%. So given the adjusted closing prices we downloaded, our first step is to calculate daily and monthly returns.

```r
#calculate monthly returns
myStocks_returns_monthly <- myStocks %>%
tq_transmute(select  = adjusted,
mutate_fun = periodReturn,
period  = "monthly",
type  = "arithmetic",
col_rename = "monthly_returns",
cols = c(nested.col))
```

Create a table where you summarise monthly returns for each of the stocks: min, max, median, sample mean, sample SD.

```r
summary_monthly_returns <- myStocks_returns_monthly %>%
group_by(symbol) %>%
summarise(minR  = min(monthly_returns), # R here stands for return
maxR  = max(monthly_returns),
```
```r
medianR = median(monthly_returns),
meanR  = mean(monthly_returns),
sdR  = sd(monthly_returns))
summary_monthly_returns
```

Plot a faceted density plot, using `geom_density()`, for each of the stocks and drop the legend.

```r
ggplot(myStocks_returns_monthly, aes(x = monthly_returns, fill = symbol)) +
geom_density() +
facet_wrap(~ symbol) +
theme_bw() +
theme(legend.position = "none") +
labs(title = "Monthy Returns by Stock",
x = "Monthly Returns",
y = "Density")
```

What can you infer from this plot? Which stock has the highest/lowest volatility?

> TYPE YOUR ANSWER AFTER (AND OUTSIDE!) THIS BLOCKQUOTE.

Finally, make a plot that shows the expected monthly return (sample mean) of a stock on the Yaxis and the risk (sample standard deviation) in the X-axis. You can use different colours for different tickers, but more importantly print the label of each ticker next to the stock, using `geom_text(aes(label = ticker))`.

```r
ggplot(summary_monthly_returns, aes(x = sdR, y = meanR, colour = symbol)) +
geom_point() +
geom_text(aes(label = symbol)) +
theme_bw() +
theme(legend.position = "none") +
labs(title = "Stock risks and returns",
x = "Risk (Standard Deviation)",
y = "Expected Monthly Return")
```

What can you infer from this plot? Are there any stocks which, while being riskier, do not have a higher expected return?

> TYPE YOUR ANSWER AFTER (AND OUTSIDE!) THIS BLOCKQUOTE.

### Key Definitions

Provide an explanation for each of these terms:

- Sample Statistic : value of interest obtained from a sample, e.g. xbar.

- Standard Error : is the standard deviation of the distribution of sample mean.

- When should you use Standard Deviation of the sample? : in cases where sigma of

population is not known.

- t-Statistic : standardized difference of the sample mean from the claim expressed in

measurement of standard error.

- Critical level : cut-off value of the hypothesis ---- (e.g. CI; t-critical; z-critical; significance

level)
### Two separate CIs

Build two separate 95% confidence intervals for monthly mean return: one for stock INTC and another for stock MSFT. Check if the two CIs overlap.

```r
stats <- myStocks_returns_monthly %>%
filter(symbol %in% c("MSFT", "INTC")) %>%
group_by(symbol) %>%
summarise(xbar = mean(monthly_returns),
sd = sd(monthly_returns),
n = n(),
# get t-critical value with (n-1) degrees of freedom
t_critical = qt(0.975, n-1),
SE = sd(monthly_returns) / sqrt(n),
margin_of_error = t_critical * SE,
CI_low = xbar - margin_of_error,
CI_high = xbar + margin_of_error)
print(stats)
```

INTC CI overlaps with MSFT CI, therefore we will need to carry out one of the 3 official statistical -----, which we will learn about in the next session on hypothesis -------.


[↑ Back to the source list](#source-documents)

---

<a name="source-5"></a>

## yahoo_finance_tickers.csv

<small>File type: CSV · Reader pages 749–750 · [View source PDF](PDF%20Slides.pdf#page=749)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

> Data preview (up to six records and twelve columns); the full CSV remains in the original files.

Table displayed as labelled records for readability (6 rows, 6 columns).

OEDV

name Osage Exploration and Development, Inc.

exchange PNK

country USA

type stock

AAPL

name Apple Inc.

exchange NMS

category_name Electronic Equipment

country USA

type stock

BAC

name Bank of America Corporation

exchange NYQ

category_name Money Center Banks

country USA

type stock

AMZN

name Amazon.com, Inc.

exchange NMS

category_name Catalog & Mail Order Houses

country USA

type stock
T

name AT&T Inc.

exchange NYQ

category_name Telecom Services - Domestic

country USA

type stock

GOOG

name Alphabet Inc.

exchange NMS

category_name Internet Information Providers

country USA

type stock

</details>


[↑ Back to the source list](#source-documents)

---

