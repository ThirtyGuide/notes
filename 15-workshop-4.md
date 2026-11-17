# Workshop 4

**Regression and data-manipulation exercises**

[← All chapters](README.md) · [Original PDF](PDF%20Slides.pdf#page=765)

## Overview

- R coding questions and explanatory solutions.
- Exercises with carseats, BMI/NHANES and SAT/GPA datasets.
- Data filtering, modelling and interpretation.

## Source documents

1. [coding_practice_----_qns.pdf](#source-1) — PDF, reader page 766
2. [coding_practice_----_qns_ANSWERS.pdf](#source-2) — PDF, reader page 768
3. [workshop_4.Rmd](#source-3) — RMD, reader page 770
4. [workshop_4_ANSWERS.Rmd](#source-4) — RMD, reader page 774
5. [carseats.csv](#source-5) — CSV, reader page 780
6. [sat_gpa.csv](#source-6) — CSV, reader page 782

---

<a name="source-1"></a>

## coding_practice_----_qns.pdf

<small>File type: PDF · Reader pages 766–767 · [View source PDF](PDF%20Slides.pdf#page=766)</small>

<small>Source Page 1 of 2</small>

### Programming Comprehension Questions

Answer the following R language-based questions. Briefly justify your answers. (i) A data set is stored in a tibble called crime. This data provides information about criminality registered in particular regions of the UK. You are also given the code below which contains line numbers at the start of each line. Answer the following questions:

o Explain what is a tibble? o Given the code below can you infer two column names present in the crime tibble? o Explain what the pipe operator does (i.e. how does it work)? o State what reorder() function does within the aes() function of the ggplot?

- crime %>%

- group_by(region_name) %>%

- summarise(total_crime = sum(criminals)) %>%

- ggplot(aes(x = reorder(region_name, total_crime),

- y = total_crime,

- fill = region_name))

(ii) Explain what the verbs group_by()and summarise() do. In the code provided above,

explain the result of performing operations on lines 2, 3, 4:

(iii) Explain what the functions xpnorm() and qnorm() do? Explain what the :: operator does in the code below? Given three function calls in the code below, which function call is correct when wanting to obtain a z-value corresponding to a 95% confidence level? What does the function qt() provide as its output? mosaic::xpnorm(0.975, mean = 0, sd = 1) qnorm(0.95) qnorm(0.975)

<small>Source Page 2 of 2</small>

(iv) You have two tibbles A and B. What xxx_join() function should be used (out of the four provided below) when you want to join all of the data from tibble A and tibble B into a single tibble? Explain how the xxx_join() function you chose combines the 2 tibbles? What happens where there are no matching values? Assume that tibble A and tibble B both contain a column called colName. inner_join(A,B) full_join(A,B) left_join(A,B) right_join(A,B)
(v) Discuss the plots that allow you to check whether assumptions of a Linear Regression model have been satisfied (i.e. ----------- of the behavior of the residuals for model inadequacies). Write down the name of the R function that allows you to obtain those plots?


[↑ Back to the source list](#source-documents)

---

<a name="source-2"></a>

## coding_practice_----_qns_ANSWERS.pdf

<small>File type: PDF · Reader pages 768–769 · [View source PDF](PDF%20Slides.pdf#page=768)</small>

<small>Source Page 1 of 2</small>

### Programming Comprehension Questions

Answer the following R language-based questions. Briefly justify your answers. (i) A data set is stored in a tibble called crime. This data provides information about criminality registered in particular regions of the UK. You are also given the code below which contains line numbers at the start of each line. Answer the following questions:

o Explain what is a tibble? o Given the code below can you infer two column names present in the crime tibble? o Explain what the pipe operator does (i.e. how does it work)? o State what reorder() function does within the aes() function of the ggplot?

- crime %>%

- group_by(region_name) %>%

- summarise(total_crime = sum(criminals)) %>%

- ggplot(aes(x = reorder(region_name, total_crime),

- y = total_crime,

- fill = region_name))

Tibble is a data container/storage unit etc (that is similar to dataframes).

Column names visible in the code are region_name and criminals The pipe operator takes the output of one function and feeds it as the input to the next. [Also ok: takes data from the left of the pipe and passes it as input into the function on the right of the pipe]. The reorder() function reorders categories (region_names) based on the numerical data provided (total_crime) (ii) Explain what the verbs group_by()and summarise() do. In the code provided above,

explain the result of performing operations on lines 2, 3, 4:

group_by() is used for grouping the data for a given column summarise() is used to generate summary statistics of a given column Line 2. Crime data is grouped by region name Line 3. Total crime is obtained per each region. Line 4. ggplot is used for plotting specifically here we specify how the x-axis should be ordered: we reorder the categorical data of region_name based on the values of the total_crime.

(iii) Explain what the functions xpnorm() and qnorm() do? Explain what the :: operator does in the code below? Given three function calls in the code below, which function call is correct when wanting to obtain a z-value corresponding to a 95% confidence level? What does the function qt() provide as its output? mosaic::xpnorm(0.975, mean = 0, sd = 1) qnorm(0.95) qnorm(0.975)
<small>Source Page 2 of 2</small>

(iv) You have two tibbles A and B. What xxx_join() function should be used (out of the four

xpnorm() provides probability to the left and to the right of a specific z value in a Standard Normal distribution, i.e. P(Z< z) as well as P(Z> z) for a normally distributed standardized random variable z. qnorm() for a given probability what is the corresponding z value of P(Z< z) :: operator says package::function i.e. from the stated package, use the stated function. qnorm(0.975) qt() provides the t-critical value (-------- may also talk about the probability that it expects, and the degrees of freedom).

provided below) when you want to join all of the data from tibble A and tibble B into a single tibble? Explain how the xxx_join() function you chose combines the 2 tibbles? What happens where there are no matching values? Assume that tibble A and tibble B both contain a column called colName. inner_join(A,B) full_join(A,B) left_join(A,B) right_join(A,B)

(v) Discuss the plots that allow you to check whether assumptions of a Linear Regression model have

```r
full_join(A,B).
```

It joins tibble A and tibble B by a common column called colName automatically and results in all rows from both tibbles where matching rows are combined. In the case where there are no matching values the result is NA for the missing ones. Some -------- may report that matching rows data will be on top in the resulting tibble.

been satisfied (i.e. ----------- of the behavior of the residuals for model inadequacies). Write down the name of the R function that allows you to obtain those plots?

The function name is autoplot().

Some -------- may report that it is called using autoplot(which=1:3) There are 3 plots for ------- the residual behavior and they are:

Residuals vs Fitted: shows if residuals are randomly scattered (have an average of zero).

This is shown with the blue line which should be horizontal at 0.

Normal Q-Q plot (points should be located on the diagonal – this would mean residuals are normally distributed.

Scale location – should have horizontal blue line which would mean new have a case of constant variance with time.


[↑ Back to the source list](#source-documents)

---

<a name="source-3"></a>

## workshop_4.Rmd

<small>File type: RMD · Reader pages 770–773 · [View source PDF](PDF%20Slides.pdf#page=770)</small>

```r
options("huxtable.knit_print_df" = FALSE)
library(here)
library(moderndive)
library(tidyverse)
library(infer)
library(mosaic)
library(huxtable)
library(kableExtra)
library(skimr)
library(ggfortify)
library(GGally) # to use ggpairs() function
library(NHANES)
require(knitr)
opts_chunk$set(
tidy = FALSE,  # display code as typed
size = "small" # slightly smaller font for code
)
```

### TASK 1 CARSEATS DATA ANALYSIS

We will use the `carseats` dataset which comes from the textbook [An Introduction to Statistical Learning: with Applications in R – Gareth James, Daniela Witten, Trevor Hastie, and Robert Tibshirani](http://faculty.marshall.usc.edu/gareth-james/ISL/)

```r
# load data
carseats <- read_csv("carseats.csv")
glimpse(carseats)
```

Each row in this tibble represents a store that sells car seats. The `Sales` column measures the number of car seats sold at that location. There are also some qualitative predictors, such as `Shelveloc`, an indicator of the quality of the shelving location—that is, the space within a store in which the car seat is displayed—at each location. The predictor `Shelveloc` takes on three possible values, Bad, Medium, and Good. The predictor `Urban` takes on two possible values: Yes and No.

Given a Simple Linear Regression setting: $Sales_i = \beta_0 + \beta_1 Advertising + \epsilon_i$ answer the following questions:

**Obtain a scatter plot of Advertising vs. Sales and fit a linear method to the data.**

```r
# ggplot
```

**Obtain correlation between Advertising and Sales.**

```r
# correlation between Adv and Sales:
```
**Write down the null hypothesis to checck if Advertising has no effect on predicting Sales.**

- H~0~:

- H~A~:

**---- the above hypothesis to see if Advertising can be used to predict Sales by analysing the slope coefficient of simple linear regression between Adv and Sales.**

```r
model_carseats_1 <-
summary()
get_regression_table()
```

**Confirm the value of the t-statistic using the equation with values for $\hat{\beta_1}$, standard error, and the information from the null hypothesis (never mind the small rounding error).**

**State your conclusion on whether the coefficient for Advertising is significant or not. State your decision from the perspective of all 3 approaches i.e.: CI, t-stat, p-value (that you can see in the table generated by get_regression_table().**

- CI limits:

- t-stat:

- p-value:

### TASK 2 dplyr BMI Model

### NHANES modeling

### Introduction

Let's consider modelling BMI (body mass index) of 18-20 year olds as a function of other predictors in the NHANES (National Health and Nutrition ----------- Survey). To keep things simpler, let's only consider subjects without missing data on a key set of variables (this has been created for you as a tibble `smaller`).

a) How many 18-20 year olds have measurements of BMI?

Hint:

- obtain favstats for BMI variable only and observe how many missing values are present

```r
smaller <- NHANES %>%
filter(Age >= 18, Age <= 20) %>%
select(Diabetes, Gender, BMI, Height, Weight, TotChol, HHIncome)
# favstats
```

SOLUTION: There are n = 387 18-20 year olds in the dataset: n = 383 have no missing values for BMI.

Next, we will get rid of missing values (delete row with even a single NA for any column), code

provided:
```r
smaller <- smaller %>%
na.omit()
dim(smaller)
```

**Describe the location (i.e. mean) and spread (i.e. standard deviation) of the BMI variable by Gender for this sample. Plot the the BMI density by gender (i.e. obtain 2 densities overlaid on a single plot). Discuss your finding for the distribution (is it skewed?). If the distribution is skewed do we use mean or median for reporting the central tendency?**

Hints:

- favstats

- ggplot with fill

- report on skewness

- report on mean/median?

**Repeat the above for cholesterol.**

Let us look at statistics for total cholesterol

**What is the BMI for the subject with the lowest total cholesterol level? For the highest cholesterol level?**

**Generate and interpret a scatterplot of BMI as a function of total cholesterol.**

**Calculate and interpret a 95% confidence interval for the mean total cholesterol level.**

**Fit a model for BMI as a function of total cholesterol. Comment on the validity of the model. How much of the variance of the BMI is explained by the model? Report what 3 stars mean next to a p-value?**

**Given a new cholesterol reading of 3.98 (mmol/L), predict the BMI off that individual.**

**Form a prediction interval around this value.**

**Is the width of the confidence interval surprising given the observed R-squared?**

### TASK 3 SAT GPA

```r
# I pre-wrangled and pre-manipulated this data for you so you only have to load it here
sat_gpa <- read_csv("sat_gpa.csv")
```

### Answer questions

**How well do SAT scores correlate with freshman GPA?** Hint:

- read online about how to use the function get_correlation() from library moderndive.

How well does high school GPA correlate with freshman GPA?

Is the correlation between SAT scores and freshman GPA stronger for men or for women?
```r
# The get_correlation() function that comes with library(moderndive) can't work
# with groups. Instead, you'll need to use group_by() and summarize() and use
# the cor() function, which is R's official function for calculating correlation
```

**Is the correlation between high school GPA and freshman GPA stronger for men or for women?**

Use `GGally::ggpairs()` to get a scatterplot-correlation matrix (code provided)

```r
library(GGally)
sat_gpa %>%
ggpairs(aes(colour=sex, alpha =0.3))
```

**Are there any gender-based differences in SAT scores? Are gender-based score differences larger in the verbal ---- or the math ----?**

Hint:

- group by gender and use summarize() to calculate the average verbal SAT score and

math SAT score for each gender

**Do SAT scores predict (or explain variation in) freshman GPAs? If so, how much college GPA change is associated with changes in SAT scores? (i.e. interpret the slope for the SAT coefficient). How much of the variation in college GPA is explained by this model?**

**Does a certain type of SAT score have a larger effect on freshman GPAs?**

Hint:

- instead of including `sat_total`, use `sat_math` and `sat_verbal` as your explanatory vari‐

ables

**Do high school GPAs predict (or explain variation in) freshman GPAs? If so, how much?** **How much of the variation in college GPA is explained by this model?**


[↑ Back to the source list](#source-documents)

---

<a name="source-4"></a>

## workshop_4_ANSWERS.Rmd

<small>File type: RMD · Reader pages 774–779 · [View source PDF](PDF%20Slides.pdf#page=774)</small>

```r
options("huxtable.knit_print_df" = FALSE)
library(here)
library(moderndive)
library(tidyverse)
library(infer)
library(mosaic)
library(huxtable)
library(kableExtra)
library(skimr)
library(ggfortify)
library(GGally) # to use ggpairs() function
library(NHANES)
require(knitr)
opts_chunk$set(
tidy = FALSE,  # display code as typed
size = "small" # slightly smaller font for code
)
```

We will use the `carseats` dataset which comes from the textbook [An Introduction to Statistical Learning: with Applications in R – Gareth James, Daniela Witten, Trevor Hastie, and Robert Tibshirani](http://faculty.marshall.usc.edu/gareth-james/ISL/)

```r
# load data
carseats <- read_csv("carseats.csv")
glimpse(carseats)
```

Each row in this tibble represents a store that sells car seats. The `Sales` column measures the number of car seats sold at that location. There are also some qualitative predictors, such as `Shelveloc`, an indicator of the quality of the shelving location—that is, the space within a store in which the car seat is displayed—at each location. The predictor `Shelveloc` takes on three possible values, Bad, Medium, and Good. The predictor `Urban` takes on two possible values: Yes and No.

Given a Simple Linear Regression setting: $Sales_i = \beta_0 + \beta_1 Advertising + \epsilon_i$ answer the following questions:

**Obtain a scatter plot of Advertising vs. Sales and fit a linear method to the data.**

```r
# ggplot
ggplot(carseats, aes(x=Advertising, y=Sales)) +
geom_point() +
stat_smooth(method="lm")
```

**Obtain correlation between Advertising and Sales.**

```r
# correlation between Adv and Sales:
X <- carseats %>% dplyr::select(Sales)
```
```r
Y <- carseats %>% dplyr::select(Advertising)
cor(X,Y) # 0.27 negligible
```

**Write down the null hypothesis to check if Advertising has no effect on predicting Sales.**

- H~0~: $\beta_1 = 0$

- H~A~: $\beta_1 \neq 0$

**---- the above hypothesis to see if Advertising can be used to predict Sales by analysing the slope coefficient of simple linear regression between Adv and Sales.**

```r
model_carseats_1 <- lm(Sales ~  Advertising, data = carseats)
summary(model_carseats_1)
model_carseats_1 %>% get_regression_table()
```

**Confirm the value of the t-statistic using the equation with values for $\hat{\beta_1}$, standard error, and the information from the null hypothesis (never mind the small rounding error).** $tstat = \frac{\hat{\beta_1} - 0}{SE} = \frac{0.114 - 0}{0.02}$

**State your conclusion on whether the coefficient for Advertising is significant or not. State your decision from the perspective of all 3 approaches i.e.: CI, t-stat, p-value (that you can see in the table generated by get_regression_table().**

- CI limits: Limits found are [0.074, 0.155]. The hypothesis is $\hat{\beta_1} = 0$, there‐

fore since 0 is not inside the CI, we reject the null hypothesis, i.e. coefficient $\beta_1$ is significant.

- t-stat: The t-stat was found to be 5.583, since |5.583|>2, we reject the null hypothesis.

- p-value: The p-value was found to be 4.38e-08 (i.e. 0) and therefore < 0.05, hence we

reject the null hypothesis.

All 3 approaches agree on the result of the null hypothesis.

### TASK 2 dplyr BMI Model

### NHANES modeling

### Introduction

Let's consider modelling BMI (body mass index) of 18-20 year olds as a function of other predictors in the NHANES (National Health and Nutrition ----------- Survey). To keep things simpler, let's only consider subjects without missing data on a key set of variables (this has been created for you as a tibble `smaller`).

**How many 18-20 year olds have measurements of BMI?**

Hint:

- obtain favstats for BMI variable only and observe how many missing values are present

```r
smaller <- NHANES %>%
dplyr::filter(Age >= 18, Age <= 20) %>%
```
```r
dplyr::select(Diabetes, Gender, BMI, Height, Weight, TotChol, HHIncome)
# favstats
dim(smaller)
favstats(~ BMI, data = smaller)
```

**SOLUTION** There are n = 387 18-20 year olds in the dataset: n = 383 have no missing values for BMI.

Next, we will get rid of missing values (delete row with even a single NA for any column).

```r
smaller <- smaller %>%
na.omit()
dim(smaller)
```

**Describe the location (i.e. mean/median) and spread (i.e. standard deviation) of the BMI variable by Gender for this sample. Plot the the BMI density by gender (i.e. obtain 2 densities overlaid on a single plot). Discuss your finding for the distribution (is it skewed?). If the distribution is skewed do we use mean or median for reporting the central tendency?**

Hints:

- favstats

- ggplot with fill

```r
# option 1
favstats(BMI ~ Gender, data = smaller)
# option 2
smaller %>%
group_by(Gender) %>%
summarize(meanval = mean(BMI), n = n())
# plot
ggplot(smaller, aes(x = BMI, fill = Gender))+
geom_density(alpha=0.3)
```

SOLUTION: The distribution of BMI is right skewed, with a median of 24.0 points (half higher, half less). Note that 25 is the threshold for overweight. There are a small number of subjects with very large values (>50).

**Repeat the above for cholesterol.**

Let us look at statistics for total cholesterol

```r
favstats(~ TotChol, data = smaller)
favstats(TotChol ~ Gender, data = smaller)
ggplot(smaller, aes(x = TotChol, fill = Gender))+
geom_density(alpha = 0.3)
```

SOLUTION: The distribution of total cholesterol is also right skewed, with a median of 4.22 mmol/ L.
**What is the BMI for the subject with the lowest total cholesterol level? For the highest cholesterol level?**

```r
ordered <- smaller %>%
arrange(TotChol) %>%
filter(!is.na(TotChol))
head(ordered, 1)
tail(ordered, 1)
```

SOLUTION: The lowest cholesterol value is 2.38: this female subject had a BMI of 42.4 points. The highest cholesterol value is 7.19: this female subject had a BMI of 54.4 points.

**Generate and interpret a scatterplot of BMI as a function of total cholesterol.**

```r
ggplot(smaller, aes(x = TotChol, y = BMI, colour = Gender))+
geom_point() +
geom_smooth(method = "lm", se = FALSE)
```

**Calculate and interpret a 95% confidence interval for the mean total cholesterol level.**

```r
t.----(~ TotChol, data = smaller)
```

SOLUTION: We are 95% confident that the true mean cholesterol for 18-20 year olds is between 4.27 and 4.46 points (mmol/L).

**Fit a model for BMI as a function of total cholesterol. Comment on the validity of the model. How much of the variance of the BMI is explained by the model? Report what 3 stars mean next to a p-value?**

```r
mod1 <- lm(BMI ~ TotChol, data=smaller)
summary(mod1)
```

**Given a new cholesterol reading of 3.98 (mmol/L), predict the BMI off that individual.**

$\hat{chol} = 17.2948 + 1.9628*3.98 = 25.10674$

**Form a prediction interval around this value.**

$25.10674 +/- 2*6.869 = [11.36874, 38.84474]$

**Is the width of the confidence interval surprising given the observed R-squared?**

The interval is rather wide, however it is not surprising given that only 5% of the variance in the BMI is explained by cholesterol, therefore much information is still left over in the residual.

### TASK 3 SAT GPA

```r
# I pre-wrangled and pre-manipulated this data for you so you only have to load it here
sat_gpa <- read_csv("sat_gpa.csv")
```

### Answer questions

**How well do SAT scores correlate with freshman GPA?** Hint:
- read online about how to use the function get_correlation() from library moderndive.

```r
sat_gpa %>%
get_correlation(gpa_fy ~ sat_total)
```

**How well does high school GPA correlate with freshman GPA?**

```r
sat_gpa %>%
get_correlation(gpa_hs ~ gpa_fy)
```

**Is the correlation between SAT scores and freshman GPA stronger for men or for women?**

```r
# The get_correlation() function that comes with library(moderndive) can't work
# with groups. Instead, you'll need to use group_by() and summarize() and use
# the cor() function, which is R's official function for calculating correlation
sat_gpa %>%
group_by(sex) %>%
summarize(correlation = cor(sat_total, gpa_fy))
```

**Is the correlation between high school GPA and freshman GPA stronger for men or for women?**

```r
sat_gpa %>%
group_by(sex) %>%
summarize(correlation = cor(gpa_hs, gpa_fy))
```

Use `GGally::ggpairs()` to get a scatterplot-correlation matrix (code provided)

```r
library(GGally)
sat_gpa %>%
ggpairs(aes(colour=sex, alpha =0.3))
```

**Are there any gender-based differences in SAT scores? Are gender-based score differences larger in the verbal ---- or the math ----?**

Hint:

- group by gender and use summarize() to calculate the average verbal SAT score and

math SAT score for each gender

```r
sat_gpa %>%
group_by(sex) %>%
summarize(mean_sat_verbal = mean(sat_verbal),
mean_sat_math = mean(sat_math))
female_sat_gpa <- sat_gpa %>%
filter(sex == 'Female')
male_sat_gpa <- sat_gpa %>%
filter(sex == 'Male')
t.----(female_sat_gpa$sat_math, male_sat_gpa$sat_math)
t.----(female_sat_gpa$sat_verbal, male_sat_gpa$sat_verbal)
```
**Do SAT scores predict (or explain variation in) freshman GPAs? If so, how much college GPA change is associated with changes in SAT scores? (i.e. interpret the slope for the SAT coefficient). How much of the variation in college GPA is explained by this model?**

```r
model_sat_gpa <- lm(gpa_fy ~ sat_total, data = sat_gpa)
model_sat_gpa %>% get_regression_table()
model_sat_gpa %>% get_regression_summaries()
```

**Does a certain type of SAT score have a larger effect on freshman GPAs?**

Hint:

- instead of including `sat_total`, use `sat_math` and `sat_verbal` as your explanatory vari‐

ables

```r
model_sat_math_verbal <- lm(gpa_fy ~ sat_math + sat_verbal, data = sat_gpa)
model_sat_math_verbal %>% get_regression_table()
model_sat_math_verbal %>% get_regression_summaries()
```

**Do high school GPAs predict (or explain variation in) freshman GPAs? If so, how much?** **How much of the variation in college GPA is explained by this model?**

```r
model_hs_college_gap <- lm(gpa_fy ~ gpa_hs, data = sat_gpa)
model_hs_college_gap %>% get_regression_table()
model_hs_college_gap %>% get_regression_summaries()
```


[↑ Back to the source list](#source-documents)

---

<a name="source-5"></a>

## carseats.csv

<small>File type: CSV · Reader pages 780–781 · [View source PDF](PDF%20Slides.pdf#page=780)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

> Data preview (up to six records and twelve columns); the full CSV remains in the original files.

Table displayed as labelled records for readability (6 rows, 11 columns).

9.5

CompPrice 138

Income 73

Advertising 11

Population 276

Price 120

ShelveLoc Bad

Age 42

Education 17

Urban Yes

US Yes

11.22

CompPrice 111

Income 48

Advertising 16

Population 260

Price 83

ShelveLoc Good

Age 65

Education 10

Urban Yes

US Yes

10.06

CompPrice 113

Income 35

Advertising 10

Population 269

Price 80

ShelveLoc Medium

Age 59

Education 12

Urban Yes

US Yes
7.4

CompPrice 117

Income 100

Advertising 4

Population 466

Price 97

ShelveLoc Medium

Age 55

Education 14

Urban Yes

US Yes

4.15

CompPrice 141

Income 64

Advertising 3

Population 340

Price 128

ShelveLoc Bad

Age 38

Education 13

Urban Yes

US No

10.81

CompPrice 124

Income 113

Advertising 13

Population 501

Price 72

ShelveLoc Bad

Age 78

Education 16

Urban No

US Yes

</details>


[↑ Back to the source list](#source-documents)

---

<a name="source-6"></a>

## sat_gpa.csv

<small>File type: CSV · Reader pages 782–783 · [View source PDF](PDF%20Slides.pdf#page=782)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

> Data preview (up to six records and twelve columns); the full CSV remains in the original files.

Table displayed as labelled records for readability (6 rows, 6 columns).

Male

sat_verbal 65

sat_math 62

sat_total 127

gpa_hs 3.4

gpa_fy 3.18

Female

sat_verbal 58

sat_math 64

sat_total 122

gpa_hs 4

gpa_fy 3.33

Female

sat_verbal 56

sat_math 60

sat_total 116

gpa_hs 3.75

gpa_fy 3.25

Male

sat_verbal 42

sat_math 53

sat_total 95

gpa_hs 3.75

gpa_fy 2.42
Male

sat_verbal 55

sat_math 52

sat_total 107

gpa_hs 4

gpa_fy 2.63

Female

sat_verbal 55

sat_math 56

sat_total 111

gpa_hs 4

gpa_fy 2.91

</details>


[↑ Back to the source list](#source-documents)

---

