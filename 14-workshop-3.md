# Workshop 3

**Inference exercises**

[← All chapters](README.md) · [Original PDF](PDF%20Slides.pdf#page=751)

## Overview

- Intervals and statistics for differences between samples.
- Worked calculations and R-based approaches.
- Stock risk/return calculations using ticker data.

## Source documents

1. [Practice_questions_Hypothesis_-------.pdf](#source-1) — PDF, reader page 752
2. [Solutions_practice_questions_Hypothesis_-------.pdf](#source-2) — PDF, reader page 754
3. [workshop_3.Rmd](#source-3) — RMD, reader page 757
4. [workshop_3_ANSWERS.Rmd](#source-4) — RMD, reader page 760
5. [yahoo_finance_tickers.csv](#source-5) — CSV, reader page 763

---

<a name="source-1"></a>

## Practice_questions_Hypothesis_-------.pdf

<small>File type: PDF · Reader pages 752–753 · [View source PDF](PDF%20Slides.pdf#page=752)</small>

<small>Source Page 1 of 2</small>

Q1. XtraNet, an Internet service provider (ISP), has experienced rapid growth in the past five years. As a part of its marketing strategy, XtraNet promises fast connections and dependable service. To achieve its objectives, XtraNet constantly evaluates the capacity of its servers. One component of its evaluation is an analysis of the average amount of time a customer is connected and using the Internet daily. A random sample of 12 customer records shows the following daily usage times, in minutes,

and the following sample statistics were obtained: x̅ = 318, s= 37.214, n= 12.

a) Assume that before the sample was taken, Xtranet’s marketing staff believed that mean daily usage for its customers was 267 minutes. Does their assumption concerning mean daily usage seem reasonable – come to your decision by carrying out the hypothesis ---- using the p-value approach with significance level of 5%.

Q2. The director of a state agency believes that the average starting salary for clerical employees in the state is equal to $30,000 per year. To ---- her hypothesis, she has collected a simple random sample of 100 starting clerical salaries from across the state and found that the sample mean is $29,750.

a) State the appropriate null and alternative hypotheses.

b) Assuming the population standard deviation is known to be $2,500 and the significance level for the ---- is to be 0.05, what is the critical value (stated in dollars)?

c) Referring to your answer in part b, what conclusion should be reached with respect to the null hypothesis?

d) Referring to your answer in part c, which of the two statistical errors (Type I, Type II) might have been made in this case? Explain.

Q3. The marketing managers at Capital One Credit Cards are planning to roll out a new marketing campaign addressed at increasing bank card use. As one part of the campaign, the company will be offering a low interest rate incentive to induce people to spend more money using its charge cards. However, the company is concerned whether this plan will have a different impact on married card

holders than on unmarried card holders. So, prior to starting the marketing campaign nationwide, the company ----- it on a random sample of 30 unmarried and 25 married customers. The managers wish to estimate the difference in mean credit card spending for unmarried versus married for a two-week period immediately after being exposed to the marketing campaign. The following sample

results were observed:
<small>Source Page 2 of 2</small>

Based on past data, the managers have reason to believe the spending distributions for unmarried and married will be approximately normally distributed, but they are unwilling to conclude the population variances for spending are equal for the two populations.

a) Develop a 95% confidence interval estimate for the difference in population means.

You can assume that the degrees of freedom for the t-distribution (if you use it) is 52.53 (i.e. θ= 52.53).

b) Now that you have created a joint confidence interval, establish whether the following null hypothesis should be rejected or not:

H!: μ"#$%&&'() −μ$%&&'() = 0 H*: μ"#$%&&'() −μ$%&&'() ≠0

Q4. You are given a coin. You toss it 80 times and you get 54 heads. Is this coin fair? (Use s = 0.466)

Q5. Now, you are given a fair coin. You toss it 100 times and you get 60 heads. Using a = 0.05, would you come to the same conclusion that the coin is fair? (Use s = 0.5)


[↑ Back to the source list](#source-documents)

---

<a name="source-2"></a>

## Solutions_practice_questions_Hypothesis_-------.pdf

<small>File type: PDF · Reader pages 754–756 · [View source PDF](PDF%20Slides.pdf#page=754)</small>

<small>Source Page 1 of 4</small>

**and the following sample statistics were obtained: x**

¯ = 318, s= 37.214, n= 12.

a) Assume that before the sample was taken, Xtranet’s marketing staff believed that mean daily usage for its customers was 267 minutes. Does their assumption concerning mean daily usage seem reasonable – come to your decision by carrying out the hypothesis ---- using the p-value approach with significance level of 5%.

Solution:

a) We are looking for the following hypothesis ----:

H0: µ = 267; Ha: µ ¹ 267 Standardised difference:

(xbar-267)/[s/sqrt(n)] = (318-267)/[37.124/sqrt(12)] = 51/10.71678 = 4.759 Find the p-value:

2 * pt(-abs(4.759), 12-1) = 0.00059 = 0.059% We conclude that for the common threshold of 5%, the hypothesis needs to be rejected. Q2. The director of a state agency believes that the average starting salary for clerical employees in the state is equal to $30,000 per year. To ---- her hypothesis, she has collected a simple random sample of 100 starting clerical salaries from across the state and found that the sample mean is $29,750.

a) State the appropriate null and alternative hypotheses.

b) Assuming the population standard deviation is known to be $2,500 and the significance level for the ---- is to be 0.05, what is the critical value (stated in dollars)?

c) Referring to your answer in part b, what conclusion should be reached with respect to the null hypothesis?

d) Referring to your answer in part c, which of the two statistical errors (Type I, Type II) might have been made in this case? Explain.

Solution:

a) H0: µ=$30,000, Ha: µ≠$30,000.

<small>Source Page 2 of 4</small>

b) a = 0.05, s = $2,500. Note that because CLT applies (n=100>30), we do not need to

c) Given the significance level, we cannot reject the null hypothesis, since the value of xbar($29,750) is not below the cut-off point of $29510.
d) Since we decided not to reject the null hypothesis, the error we could have made is of type II error (not rejecting while the null hypothesis is false).

assume that the population distribution is normal. The z-value is obtained from qnorm(0.975) = 1.96 in R.

This can be transformed to a cut off value in dollars as follows: µ0 - 1.96*s/SQRT(100) = $30,000 - 1.96*2500/sqrt(100) = $30,000 – $490 = $29,510

Q3. The marketing managers at Capital One Credit Cards are planning to roll out a new marketing campaign addressed at increasing bank card use. As one part of the campaign, the company will be offering a low interest rate incentive to induce people to spend more money using its charge cards. However, the company is concerned whether this plan will have a different impact on married card

holders than on unmarried card holders. So, prior to starting the marketing campaign nationwide, the company ----- it on a random sample of 30 unmarried and 25 married customers. The managers wish to estimate the difference in mean credit card spending for unmarried versus married for a two-week period immediately after being exposed to the marketing campaign. The following sample

results were observed:

Based on past data, the managers have reason to believe the spending distributions for unmarried and married will be approximately normally distributed, but they are unwilling to conclude the population variances for spending are equal for the two populations.

a) Develop a 95% confidence interval estimate for the difference in population means. You can assume that the degrees of freedom for the t-distribution (if you use it) is 52.53 (i.e. θ= 52.53).

b) Now that you have created a joint confidence interval, establish whether the following null hypothesis should be rejected or not:

H": μ#$%&''()* −μ%&''()* = 0 H+: μ#$%&''()* −μ%&''()* ≠0

<small>Source Page 3 of 4</small>

Solution:

a) Inspect the data:

1 = unmarried, 2 = married. n1 = 30, xbar1 = 455.10, s1 = 102.40 n2 = 25, xbar2 = 268.90, s2 = 77.25 Both populations are normally distributed but the variances are not necessarily the same, this is often called the case of “unequal variance”. Start constructing the CI for µ1-µ2: Step 1 – calculate the point estimate for the difference: xbar1 – xbar2 = $455.10 - $268.90 = $186.20 Step 2 – calculate the standard error (SE):

4,!"

$" = 4+"-./""

,""
11.-2"

$! +

0" +

-2 = 24.70

Step 3 – calculate the degrees of freedom using the Welch-Satterthwaite method, but in this case the degrees of freedom is stated in the question (it will also be stated in the ----, you will not need to calculate this) as 52.53. If you are curious here is how this number was calculated.

Step 4 – calculate the t value in R: qt(0.975, 52.53) = 2.006 Step 5 – the confidence interval:

CI = $186.20 ± 2.006 * 24.7 = [$136.65, $235.74]

b) The CI range provides evidence to conclude that unmarried customers, after being introduced to the marketing program, spend more than married customers, i.e. we reject the null hypothesis that there is no difference between true population mean spending of married and unmarried customers. The reason we can conclude this is because the joint CI does not include the null hypothesis value of 0. Therefore we reject the null hypothesis. Q4. You are given a coin. You toss it 80 times and you get 54 heads. Is this coin fair? (Use s = 0.466)

The true mu = 0.5 H0 µ =0.5 H1 µ≠ 0.5 heads = 54 n = 80 s = 0.466 x_bar = 54/80 = 0.68

<small>Source Page 4 of 4</small>

z-stat = (x_bar - m ) / (s/ sqrt(n) ) = 3.45

I set α = 0.05 -> z_critical = 1.96 As the z_stat > z_critical I reject H0. The coin is not fair.

H0 µ =0.5 ; H1 µ ≠ 0.5 heads = 60 n = 100 s = 0.5 x_bar = 60/100 = 0.6

Q5. Now, you are given a fair coin. You toss it 100 times and you get 60 heads. Using a = 0.05, would you come to the same conclusion that the coin is fair? (Use s = 0.5)

z-stat (x_bar - µ )/(s/= sqrt(n) ) = 2.00

I set a = 0.05 -> z_critical = 1.96 As the z_score > z_critical , I reject H0. The coin is not fair.

Due to random fluctuations, you got 60 heads, assessing that the coin is not fair. However, the coin is actually fair.

a represents the Type I error: the probability of rejecting H0 when H0 is actually true. Whe n you perform a ----, you decide the Type I error, which is the error you are willing to toller

ate with respect to the null hypothesis.

In this case, we’ve made a Type I error rejecting the hypothesis of fairness although the c

oin is actually fair.


[↑ Back to the source list](#source-documents)

---

<a name="source-3"></a>

## workshop_3.Rmd

<small>File type: RMD · Reader pages 757–759 · [View source PDF](PDF%20Slides.pdf#page=757)</small>

```r
library(mosaic)  # Load additional packages here
library(tidyverse)
library(tidyquant)
options(digits=5)
# Some customization.  You can alter or delete as desired (if you know what you are doing).
knitr::opts_chunk$set(
tidy=FALSE,  # display code as typed
size="small")  # slightly smaller font for code
```

Calculate and plot risk/return profile of stocks

```r
tickers  <- read_csv(here::here("Data","yahoo_finance_tickers.csv"))
```

The `tickers` tibble contains 207,533 tickers of various instruments, the `name` of the instrument, the `exchange` it is traded at, which market sector it belongs to (`category_name`), and the `type` of the instrument, namely stocks, market indices, or ETFs.

Choose around a dozen stocks, preferably from your country, or a sector (`category_name`) that interests you. Create a new variable my_tickers with your chosen tickers, here are mine: `my_tickers <- c("AAPL", "MSFT", "IBM", "AMZN", "NVDA", "JLL", "INTC", "ABB", "NKE")` Use tidyquant to download the last 4 years worth of data.

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
summary_monthly_returns <- myStocks_returns_monthly %>%
group_by(symbol) %>%
summarise(minR  = min(monthly_returns), # R here stands for return
maxR  = max(monthly_returns),
medianR = median(monthly_returns),
meanR  = mean(monthly_returns),
sdR  = sd(monthly_returns))
summary_monthly_returns
```

### ------- For Differences (Formula Approach)

Let's ---- hypothesis for difference between INTC (Intel stock) and MSFT (Microsoft stock) population mean returns (monthly), with the null hypothesis that this mean is 0, i.e. H0: (mu1 - mu2) = 0 Ha: (mu1 - mu2) != 0

Build two separate confidence intervals for monthly mean return: one for stock INTC and another for stock MSFT. Check if the two CIs overlap. Comment on your findings with respect to the above null hypothesis ------- for differences in population mean monthly return.

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

### Joint CI

Calculate a joint CI for the mean difference in monthly returns and provide your conclusion on the null hypothesis for stocks: INTC and MSFT. What is your conclusion about the null hypothesis?

```r
intc <- stats[1, ] # select 1st row with INTC information
print(intc)
msft <- stats[2, ] # select 2nd row with MSFT information
print(msft)
# YOUR CODE GOES HERE
delta_star <-
z <-
SE <-
# Now let's build the single confidence interval (xbar1 - xbar2) +- z*SE
```
```r
upper_CI <-
lower_CI <-
print(paste('[', round(lower_CI,2),", ", round(upper_CI,2), ']', sep=""), quote = FALSE)
```

### Calculations t-stat

Find the standardized difference between the sample statistic (xbar1 - xbar2) and the hypothesized value (0) calculated in terms of standard errors. Comment on the decision with respect to the null hypothesis. Is the ---- statistic surprising?

```r
# YOUR CODE GOES HERE
t_stat <-
reject <-
```

### Calculations automated

Since we agreed that the p-value will be too hard to calculate from first principles, use the t.----() function to obtain the p-value and also confirm your above calculations with the one CI and t-stat produced by the function.

Perform the Two-Sample t----- and comment on the p-value. State your decision about the null hypothesis that there is no difference in population mean monthly return of stock INTC vs MSFT.

```r
# YOUR CODE GOES HERE
```


[↑ Back to the source list](#source-documents)

---

<a name="source-4"></a>

## workshop_3_ANSWERS.Rmd

<small>File type: RMD · Reader pages 760–762 · [View source PDF](PDF%20Slides.pdf#page=760)</small>

```r
library(mosaic)  # Load additional packages here
library(tidyverse)
library(tidyquant)
options(digits = 3)
# Some customization. You can alter or delete as desired (if you know what you are doing).
knitr::opts_chunk$set(
tidy = FALSE,  # display code as typed
size = "small")  # slightly smaller font for code
```

### Calculate and plot risk/return profile of stocks

```r
tickers <- read_csv("yahoo_finance_tickers.csv")
```

The `tickers` tibble contains 207,533 tickers of various instruments, the `name` of the instrument, the `exchange` it is traded at, which market sector it belongs to (`category_name`), and the `type` of the instrument, namely stocks, market indices, or ETFs.

Choose around a dozen stocks, preferably from your country, or a sector (`category_name`) that interests you. Create a new variable my_tickers with your chosen tickers, here are mine: `my_tickers <- c("AAPL", "MSFT", "IBM", "AMZN", "NVDA", "JLL", "INTC", "ABB", "NKE")` Use tidyquant to download the last 4 years worth of data.

```r
my_tickers <- c("AAPL", "MSFT", "IBM", "AMZN", "NVDA", "JLL", "INTC", "ABB", "NKE")
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
medianR = median(monthly_returns),
meanR  = mean(monthly_returns),
sdR  = sd(monthly_returns))
summary_monthly_returns
```

### ------- For Differences (Formula Approach)

Let's ---- hypothesis for difference between INTC (Intel stock) and MSFT (Microsoft stock) population mean returns (monthly), with the null hypothesis that this mean is 0, i.e. H0: (mu1 - mu2) = 0 Ha: (mu1 - mu2) != 0

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

### Joint CI

Calculate a joint CI for the mean difference in monthly returns and provide your conclusion on the null hypothesis for stocks: INTC and MSFT. What is your conclusion about the null hypothesis?

```r
intc <- stats[1, ] # select 1st row with INTC information
print(intc)
msft <- stats[2, ] # select 2nd row with MSFT information
print(msft)
delta_star <- intc$xbar - msft$xbar
z <- 2 # approx value (can also use 1.96)
SE <- sqrt(intc$sd**2 / intc$n + msft$sd**2 / msft$n )
# Now let's build the single confidence interval (xbar1 - xbar2) +- z*SE
upper_CI <- delta_star + z*SE
lower_CI <- delta_star - z*SE
print(paste('[', round(lower_CI,3),", ", round(upper_CI,3), ']', sep=""), quote = FALSE) #
[-0.046, 0.008]
```

Since 0 is included in the confidence interval, we cannot reject the null hypothesis. Therefore we continue to hold the null hypothesis as our ground belief.
### Calculations t-stat

Find the standardized difference between the sample statistic (xbar1 - xbar2) and the hypothesized value (0) calculated in terms of standard errors. Comment on the decision with respect to the null hypothesis. Is the ---- statistic surprising?

```r
# -------- should refer to slide 22 formula for t-stat
# We already calculated all of the variables needed for the eq.
t_stat <- (delta_star - 0) / (SE) # -1.4125
print(t_stat)
reject <- abs(t_stat) > 2 # FALSE
print(reject)
```

Fail to reject the null hypothesis since absolute value of the t-stat is not greater than 2. i.e. the sample statistic is not a surprise if null hypothesis is true.

### Calculations automated

Since we agreed that the p-value will be too hard to calculate from first principles, use the t.----() function to obtain the p-value and also confirm your above calculations with the one CI and t-stat produced by the function.

Perform the Two-Sample t----- using t.----() function and comment on the p-value. State your decision about the null hypothesis that there is no difference in population mean monthly return of stock INTC vs MSFT.

```r
intc_msft <- myStocks_returns_monthly %>%
filter(symbol %in% c("INTC", "MSFT")) %>%
select(symbol, monthly_returns)
options(digits = 5)
t.----(monthly_returns ~ symbol, data = intc_msft) # numeric ~ categorical
```


[↑ Back to the source list](#source-documents)

---

<a name="source-5"></a>

## yahoo_finance_tickers.csv

<small>File type: CSV · Reader pages 763–764 · [View source PDF](PDF%20Slides.pdf#page=763)</small>

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

