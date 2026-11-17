# Workshop 5

**Regression practice**

[← All chapters](README.md) · [Original PDF](PDF%20Slides.pdf#page=784)

## Overview

- Further coding and regression questions.
- Companion answers and worked solution materials.
- Practice applying regression concepts to numerical examples.

## Source documents

1. [coding_practice_----_qns2.pdf](#source-1) — PDF, reader page 785
2. [coding_practice_----_qns2_ANSWERS.pdf](#source-2) — PDF, reader page 787
3. [Practice_Regression.pdf](#source-3) — PDF, reader page 789
4. [Practice_Regression_Answers.pdf](#source-4) — PDF, reader page 792

---

<a name="source-1"></a>

## coding_practice_----_qns2.pdf

<small>File type: PDF · Reader pages 785–786 · [View source PDF](PDF%20Slides.pdf#page=785)</small>

<small>Source Page 1 of 3</small>

### Programming Comprehension Questions

Answer the following R language-based questions. Briefly justify your answers. (i) The below tibble, called athletics, is showing information for the Olympic games that occurred in London and Brazil in years 2012 and 2016. The dataframe has 4 columns in the following format: host (string), year (numeric), discipline (string) and rate (string) which is the number of false starts over total number of athletes participating in the event.

Statement: “This tibble is in tidy format”. Is the statement True or False? Justify your answer. If false, select one suggested line of code that you believe will make the tibble tidy ensuring meaningful datatypes for each column. tb1 <- pivot_longer(athletics, cols = c('host', 'year'), names_to = "games", values_to = "value") tb2 <- pivot_wider(athletics, names_from = year, values_from = rate) tb3 <- separate(athletics, rate, into = c("count", "total"), convert = TRUE)

<small>Source Page 2 of 3</small>

(ii) The babynames dataset, available in library(babynames), contains data on names of babies from 1880 – 2017. The following summary gives details on variable names and shows some of the data of the tibble babynames

You are given the following code:

- result <-

- babynames %>%

- filter(sex == "F") %>%

- group_by(year) %>%

- mutate(total = sum(n)) %>%

- filter(name %in% c("Mary", "Jane")) %>%

- mutate(proportion = n / total)

Answer the following questions:

o Explain what is a tibble? o Explain what the pipe operator does (i.e. how does it work)? o Identify dplyr verbs in the above code do and explain what they do? o Does the mutate() verb generate an output that contains the same number of rows as the input data? What about the summarise() verb? o State what columns do you expect the output result to contain?
<small>Source Page 3 of 3</small>

(iii) [5 points] Explain what the t.----() R function is used for. What key pieces of information can be seen in the table it outputs? If you have a numerical and a categorical variable, in what order should they be passed into the t.----() function?

(iv) [5 points] Explain what the code snippets below do and highlight key differences between them?

code 1: tb1 <- data %>% group_by(x) %>% mutate(new_y = y – mean(y)) code 2: tb2 <- data %>% group_by(x) %>% arrange(z, .by_group = TRUE)


[↑ Back to the source list](#source-documents)

---

<a name="source-2"></a>

## coding_practice_----_qns2_ANSWERS.pdf

<small>File type: PDF · Reader pages 787–788 · [View source PDF](PDF%20Slides.pdf#page=787)</small>

<small>Source Page 1 of 3</small>

### Programming Comprehension Questions

Answer the following R language-based questions. Briefly justify your answers. (i) The below tibble, called athletics, is showing information for the Olympic games that occurred in London and Brazil in years 2012 and 2016. The dataframe has 4 columns in the following format: host (string), year (numeric), discipline (string) and rate (string) which is the number of false starts over total number of athletes participating in the event.

Statement: “This tibble is in tidy format”. Is the statement True or False? Justify your answer. If false, select one suggested line of code that you believe will make the tibble tidy ensuring meaningful datatypes for each column. tb1 <- pivot_longer(athletics, cols = c('host', 'year'), names_to = "games", values_to = "value") tb2 <- pivot_wider(athletics, names_from = year, values_from = rate) tb3 <- separate(athletics, rate, into = c("count", "total"), convert = TRUE)

The dataframe is not tidy since the rate column contains observations that need their own columns, that could be titled ‘count’ and ‘total’. This is the correct choice of code to separate(rate, into = c("count", "total"), convert = TRUE)

<small>Source Page 2 of 3</small>

(ii) The babynames dataset, available in library(babynames), contains data on names of babies from 1880 – 2017. The following summary gives details on variable names and shows some of the data of the tibble babynames

You are given the following code:

- result <-

- babynames %>%

- filter(sex == "F") %>%

- group_by(year) %>%

- mutate(total = sum(n)) %>%

- filter(name %in% c("Mary", "Jane")) %>%

- mutate(proportion = n / total)

Answer the following questions:
o Explain what is a tibble? o Explain what the pipe operator does (i.e. how does it work)? o Identify dplyr verbs in the above code do and explain what they do? o Does the mutate() verb generate an output that contains the same number of rows as the input data? What about the summarise() verb? o State what columns do you expect the output result to contain?

[1 pt] Tibble is a data container/storage unit etc (that is similar to dataframes/derived from a dataframe class). [1 pt] The pipe operator takes the output of one function and feeds it as the input to the next. [Also ok, takes data/object from the left of the pipe and passes it as input into the function on the right of the pipe]. [3 pts] filter() selects rows; group_by() groups by a

given column; mutate() creates a new column with the result of the transform on existing columns; [2 pts]. Yes mutate keeps all original columns. No summarise collapses the column down to a single summarised value. [3 pts] All original columns (year, sex, name, n, prop) as well as the 2 new columns created (total, proportion).

<small>Source Page 3 of 3</small>

(iii) [5 points] Explain what the t.----() R function is used for. What key pieces of information can be seen in the table it outputs? If you have a numerical and a categorical variable, in what order should they be passed into the t.----() function?

(iv) [5 points] Explain what the code snippets below do and highlight key differences between them?

t.----() is used to ---- hypothesis.

It provides information on:

Confidence Interval

t-stat

p-value t.----(numeric ~ binary) i.e. numeric variable goes first.

code 1: tb1 <- data %>% group_by(x) %>% mutate(new_y = y – mean(y)) code 2: tb2 <- data %>% group_by(x) %>% arrange(z, .by_group = TRUE)

In code 1 the code results in a data that has been grouped by the x variable and then the column y has been centered by group (i.e. every value of y had the average value of its respective group taken away from it). In code 2 the code results in a data that has been grouped by the x variable and then column z has been arranged in ascending order for each group, therefore the final tibble

tb2 has visibly grouped data by column x, with rows reshuffled such that values of z increase within each group of x. Key difference is the dplyr verb mutate vs arrange. Visually mutate will not order the rows.


[↑ Back to the source list](#source-documents)

---

<a name="source-3"></a>

## Practice_Regression.pdf

<small>File type: PDF · Reader pages 789–791 · [View source PDF](PDF%20Slides.pdf#page=789)</small>

<small>Source Page 1 of 5</small>

CA09 Regression Practice Question State the linear regression model assumptions as it relates to the regression errors. Explain the difference between simple and multiple linear regression formulation. Explain what ‘linear’ refers to when we work with multiple regression. You have been given a dataset which contains 100 observations on the dependent variable Y, and on 3 independent

variables x1, x2, x3. The task is to build the best possible linear model for predicting variable Y using the relevant information available to you. The descriptive statistics and the correlation matrix for all of the variables are given below:

Table 2: Descriptive statistics of the data

Table 3: Correlation matrix of the data

Using information in Table 2 and/or Table 3 comment on the suitability of the variables x1, x2, x3 for building an accurate regression model. Provide a definition for the term ‘multicollinearity’ and comment on whether you expect to see multicollinearity effects in your dataset, giving your reasoning.

<small>Source Page 2 of 5</small>

Table 4: Model1 Multiple linear regression of Y on x$, x%, x&

To start, a multiple linear regression model was built (called Model1) using all of the independent variables to predict variable Y. The results of the regression are given in Table

- Note that the outputs of the t-values and p-values are hidden.

Write down the general equation that can be used to calculate the hidden t-values. Calculate the tvalues for coefficients of x1, x2, x3 accurate to 3 decimal places. Comment on which independent variables form significant (at a = 5%) predictors of Y. Comment on whether it is necessary to calculate the t-value for the Intercept in order to decide whether the Intercept should be kept in the regression model or not. Comment on whether this regression model (Model1) is a valid model giving your reasoning and provide suggestion(s) for any remedial action you feel may be necessary.

<small>Source Page 3 of 5</small>

Table 5: Model2 Multiple linear regression of Y on x%, and x% ∗x&
Next, another model, called Model2, is built using only variable x2 and an interaction term between variables x2 and x3, the results of running this model are displayed in Table 5.

Write down the equation for the assumed true model for the independent variable of the above multiple regression (i.e. Model2)? What is the fitted model provided by the linear regression? Comment on which independent variables form significant (at a = 5%) predictors of Y. Evaluate the predictive power of the above model. Decide which of the two models (Model1 or Model2) you should use to

obtain a forecast for the dependent variable using new values of independent variables: x% = 144.05 and x& = −5.21 and obtain that forecast. Write down the expression you would use to calculate the approximate 95% prediction interval around the forecasted value.

<small>Source Page 4 of 5</small>

dTable 1: The standard Normal distribution P(Z> z)

```r
N(µ, s)
```

µ

X

Z = (X - μ)/σ 0.00 0.01 0.02 0.03 0.04 0.05 0.06 0.07 0.08 0.09 0.00 0.5000 0.4960 0.4920 0.4880 0.4840 0.4801 0.4761 0.4721 0.4681 0.4641 0.10 0.4602 0.4562 0.4522 0.4483 0.4443 0.4404 0.4364 0.4325 0.4286 0.4247 0.20 0.4207 0.4168 0.4129 0.4090 0.4052 0.4013 0.3974 0.3936 0.3897 0.3859 0.30 0.3821 0.3783 0.3745 0.3707 0.3669 0.3632 0.3594 0.3557 0.3520 0.3483 0.40 0.3446 0.3409 0.3372

0.3336 0.3300 0.3264 0.3228 0.3192 0.3156 0.3121 0.50 0.3085 0.3050 0.3015 0.2981 0.2946 0.2912 0.2877 0.2843 0.2810 0.2776 0.60 0.2743 0.2709 0.2676 0.2643 0.2611 0.2578 0.2546 0.2514 0.2483 0.2451 0.70 0.2420 0.2389 0.2358 0.2327 0.2296 0.2266 0.2236 0.2206 0.2177 0.2148 0.80 0.2119 0.2090 0.2061 0.2033 0.2005 0.1977 0.1949 0.1922 0.1894 0.1867 0.90 0.1841 0.1814 0.1788 0.1762 0.1736

0.1711 0.1685 0.1660 0.1635 0.1611 1.00 0.1587 0.1562 0.1539 0.1515 0.1492 0.1469 0.1446 0.1423 0.1401 0.1379 1.10 0.1357 0.1335 0.1314 0.1292 0.1271 0.1251 0.1230 0.1210 0.1190 0.1170 1.20 0.1151 0.1131 0.1112 0.1093 0.1075 0.1056 0.1038 0.1020 0.1003 0.0985 1.30 0.0968 0.0951 0.0934 0.0918 0.0901 0.0885 0.0869 0.0853 0.0838 0.0823 1.40 0.0808 0.0793 0.0778 0.0764 0.0749 0.0735 0.0721

0.0708 0.0694 0.0681 1.50 0.0668 0.0655 0.0643 0.0630 0.0618 0.0606 0.0594 0.0582 0.0571 0.0559 1.60 0.0548 0.0537 0.0526 0.0516 0.0505 0.0495 0.0485 0.0475 0.0465 0.0455 1.70 0.0446 0.0436 0.0427 0.0418 0.0409 0.0401 0.0392 0.0384 0.0375 0.0367 1.80 0.0359 0.0351 0.0344 0.0336 0.0329 0.0322 0.0314 0.0307 0.0301 0.0294 1.90 0.0287 0.0281 0.0274 0.0268 0.0262 0.0256 0.0250 0.0244 0.0239
0.0233 2.00 0.0228 0.0222 0.0217 0.0212 0.0207 0.0202 0.0197 0.0192 0.0188 0.0183 2.10 0.0179 0.0174 0.0170 0.0166 0.0162 0.0158 0.0154 0.0150 0.0146 0.0143 2.20 0.0139 0.0136 0.0132 0.0129 0.0125 0.0122 0.0119 0.0116 0.0113 0.0110 2.30 0.0107 0.0104 0.0102 0.0099 0.0096 0.0094 0.0091 0.0089 0.0087 0.0084 2.40 0.0082 0.0080 0.0078 0.0075 0.0073 0.0071 0.0069 0.0068 0.0066 0.0064 2.50

0.0062 0.0060 0.0059 0.0057 0.0055 0.0054 0.0052 0.0051 0.0049 0.0048 2.60 0.0047 0.0045 0.0044 0.0043 0.0041 0.0040 0.0039 0.0038 0.0037 0.0036 2.70 0.0035 0.0034 0.0033 0.0032 0.0031 0.0030 0.0029 0.0028 0.0027 0.0026 2.80 0.0026 0.0025 0.0024 0.0023 0.0023 0.0022 0.0021 0.0021 0.0020 0.0019 2.90 0.0019 0.0018 0.0018 0.0017 0.0016 0.0016 0.0015 0.0015 0.0014 0.0014 3.00 0.0013 0.0013

0.0013 0.0012 0.0012 0.0011 0.0011 0.0011 0.0010 0.0010

<small>Source Page 5 of 5</small>

Table 2: The standard Normal distribution P(Z< z)


[↑ Back to the source list](#source-documents)

---

<a name="source-4"></a>

## Practice_Regression_Answers.pdf

<small>File type: PDF · Reader pages 792–795 · [View source PDF](PDF%20Slides.pdf#page=792)</small>

<small>Source Page 1 of 5</small>

CA09 Regression Practice Question State the linear regression model assumptions as it relates to the regression errors. Explain the difference between simple and multiple linear regression formulation. Explain what ‘linear’ refers to when we work with multiple regression. You have been given a dataset which contains 100 observations on the dependent variable Y, and on 3 independent

variables x1, x2, x3. The task is to build the best possible linear model for predicting variable Y using the relevant information available to you. The descriptive statistics and the correlation matrix for all of the variables are given below:

Assumptions for regression errors are:

(i) normally distributed (ii) have 0 mean (iii) have constant variance, σ$ (iv) uncorrelated with x’s (v) uncorrelated with each other

Some -------- may mention an assumption: that in linear regression, an underlying assumption is that the population mean of the dependent variable is equal to a linear function of the independent variables.

Simple linear regression uses a single independent variable to predict the dependent variable.

Multiple linear regression uses 2 or more independent variables to predict the dependent variable.

Linear: we fit a line in 2D, a plane (to data in 3D) / hyperplane (to data in higher-D) to the data.

Table 2: Descriptive statistics of the data

Table 3: Correlation matrix of the data

Using information in Table 2 and/or Table 3 comment on the suitability of the variables x1, x2, x3 for building an accurate regression model. Provide a definition for the term ‘multicollinearity’ and comment on whether you expect to see multicollinearity effects in your dataset, giving your reasoning.

-------- should only refer to Table 3 to answer the question. The correlation matrix shows strong correlation between Y and x3 (nearly 1 i.e. nearly a straight line relationship). The other two correlations between Y and x1 and x2 respectively show correlation of nearly 0. Therefore, one does not expect for x1 or x2 to be useful when building a linear regression model (upon initial
analysis based on the correlation matrix). Multicollinearity occurs when independent variables have high correlation between each other. In Table 3 we see that the independent variables do not have high correlation amongst each other (check column 3, where cor(x3,x1) is nearly 0 and cor(x3,x2) is also nearly zero). Therefore, we do not expect to have multicollinearity problems when

building a regression model.

<small>Source Page 2 of 5</small>

Table 4: Model1 Multiple linear regression of Y on x%, x$, x&

To start, a multiple linear regression model was built (called Model1) using all of the independent variables to predict variable Y. The results of the regression are given in Table

- Note that the outputs of the t-values and p-values are hidden.

Write down the general equation that can be used to calculate the hidden t-values. Calculate the tvalues for coefficients of x1, x2, x3 accurate to 3 decimal places. Comment on which independent variables form significant (at a = 5%) predictors of Y. Comment on whether it is necessary to calculate the t-value for the Intercept in order to decide whether the Intercept should be kept in the regression model or not. Comment on whether this regression model (Model1) is a valid model giving your reasoning and provide suggestion(s) for any remedial action you feel may be necessary.

'(!)*

t-value =

+,"#!

The t-values for each coefficient are calculated as follows:

t-value x1 =

*.$.%/)*

*.01*1 = 0.433 t-value x2 =

*.0$12)*

*.&*00 = 2.041 t-value x3 =

%00..3/2)*

$.012. = 62.794

For 5% significance level we can use the value of 2. Therefore, we can see that x1 is not significant since |tvalue x1 = 0.433| < 2, while for x2 and x3 the t-values are greater than 2 and therefore are significant. In conclusion using the t-values we see that variables x2, x3 should be included in the model. We always keep the intercept in the model and therefore there is no need to calculate its t-value. This regression model is not valid since it contains an insignificant variable x1. This variable needs to be deleted from the model and model re-estimated.
<small>Source Page 3 of 5</small>

Table 5: Model2 Multiple linear regression of Y on x$, and x$ ∗x&

Next, another model, called Model2, is built using only variable x2 and an interaction term between variables x2 and x3, the results of running this model are displayed in Table 5.

Write down the equation for the assumed true model for the independent variable of the above multiple regression (i.e. Model2)? What is the fitted model provided by the linear regression? Comment on which independent variables form significant (at a = 5%) predictors of Y. Evaluate the predictive power of the above model. Decide which of the two models (Model1 or Model2) you should use to

obtain a forecast for the dependent variable using new values of independent variables: x$ = 144.05 and x& = −5.21 and obtain that forecast. Write down the expression you would use to calculate the approximate 95% prediction interval around the forecasted value.

The population model: (ok if they don’t use time subscript here) Y = beta0 + beta1 ∗x2 + beta2 ∗x2 ∗x3 + error Alternatively -------- may write:

Y4 = β* + β%x$,4 + β$x$,4x&,4 + ε4 The fitted model: (note no error term and hat on Y; ok if they don’t use time subscript here) Y= = 0.5372 + x$ + x$ ∗x& Alternatively -------- may

write:

Y=4 = 0.5372 + x$,4 + x$,4x&,4 Both x2 and the interaction term form significant predictors of Y (since p value is nearly 0). The predictive power of the above model is Adj R2 = 1, meaning that the model provides the best explanatory power possible. -------- should use only Model2 since it is the only valid model with all indep vars significant. Forecasted value Y=4 = 0.5372 + 144.05 +

144.05 ∗(−5.21) = −605.9133. The margin of error is estimated by 2 ∗standard error = 2 ∗0.3017 = 0.6034 (-------- may use 1.96 instead of 2). 95% prediction interval for the dep. variable is = −605.9133 ± 0.6034 ie [−606.5167, −605.3099]

<small>Source Page 4 of 5</small>

dTable 1: The standard Normal distribution P(Z> z)

```r
N(µ, s)
```

µ

X

Z = (X - μ)/σ 0.00 0.01 0.02 0.03 0.04 0.05 0.06 0.07 0.08 0.09 0.00 0.5000 0.4960 0.4920 0.4880 0.4840 0.4801 0.4761 0.4721 0.4681 0.4641 0.10 0.4602 0.4562 0.4522 0.4483 0.4443 0.4404 0.4364 0.4325 0.4286 0.4247 0.20 0.4207 0.4168 0.4129 0.4090 0.4052 0.4013 0.3974 0.3936 0.3897 0.3859 0.30 0.3821 0.3783 0.3745 0.3707 0.3669 0.3632 0.3594 0.3557 0.3520 0.3483 0.40 0.3446 0.3409 0.3372
0.3336 0.3300 0.3264 0.3228 0.3192 0.3156 0.3121 0.50 0.3085 0.3050 0.3015 0.2981 0.2946 0.2912 0.2877 0.2843 0.2810 0.2776 0.60 0.2743 0.2709 0.2676 0.2643 0.2611 0.2578 0.2546 0.2514 0.2483 0.2451 0.70 0.2420 0.2389 0.2358 0.2327 0.2296 0.2266 0.2236 0.2206 0.2177 0.2148 0.80 0.2119 0.2090 0.2061 0.2033 0.2005 0.1977 0.1949 0.1922 0.1894 0.1867 0.90 0.1841 0.1814 0.1788 0.1762 0.1736

0.1711 0.1685 0.1660 0.1635 0.1611 1.00 0.1587 0.1562 0.1539 0.1515 0.1492 0.1469 0.1446 0.1423 0.1401 0.1379 1.10 0.1357 0.1335 0.1314 0.1292 0.1271 0.1251 0.1230 0.1210 0.1190 0.1170 1.20 0.1151 0.1131 0.1112 0.1093 0.1075 0.1056 0.1038 0.1020 0.1003 0.0985 1.30 0.0968 0.0951 0.0934 0.0918 0.0901 0.0885 0.0869 0.0853 0.0838 0.0823 1.40 0.0808 0.0793 0.0778 0.0764 0.0749 0.0735 0.0721

0.0708 0.0694 0.0681 1.50 0.0668 0.0655 0.0643 0.0630 0.0618 0.0606 0.0594 0.0582 0.0571 0.0559 1.60 0.0548 0.0537 0.0526 0.0516 0.0505 0.0495 0.0485 0.0475 0.0465 0.0455 1.70 0.0446 0.0436 0.0427 0.0418 0.0409 0.0401 0.0392 0.0384 0.0375 0.0367 1.80 0.0359 0.0351 0.0344 0.0336 0.0329 0.0322 0.0314 0.0307 0.0301 0.0294 1.90 0.0287 0.0281 0.0274 0.0268 0.0262 0.0256 0.0250 0.0244 0.0239

0.0233 2.00 0.0228 0.0222 0.0217 0.0212 0.0207 0.0202 0.0197 0.0192 0.0188 0.0183 2.10 0.0179 0.0174 0.0170 0.0166 0.0162 0.0158 0.0154 0.0150 0.0146 0.0143 2.20 0.0139 0.0136 0.0132 0.0129 0.0125 0.0122 0.0119 0.0116 0.0113 0.0110 2.30 0.0107 0.0104 0.0102 0.0099 0.0096 0.0094 0.0091 0.0089 0.0087 0.0084 2.40 0.0082 0.0080 0.0078 0.0075 0.0073 0.0071 0.0069 0.0068 0.0066 0.0064 2.50

0.0062 0.0060 0.0059 0.0057 0.0055 0.0054 0.0052 0.0051 0.0049 0.0048 2.60 0.0047 0.0045 0.0044 0.0043 0.0041 0.0040 0.0039 0.0038 0.0037 0.0036 2.70 0.0035 0.0034 0.0033 0.0032 0.0031 0.0030 0.0029 0.0028 0.0027 0.0026 2.80 0.0026 0.0025 0.0024 0.0023 0.0023 0.0022 0.0021 0.0021 0.0020 0.0019 2.90 0.0019 0.0018 0.0018 0.0017 0.0016 0.0016 0.0015 0.0015 0.0014 0.0014 3.00 0.0013 0.0013

0.0013 0.0012 0.0012 0.0011 0.0011 0.0011 0.0010 0.0010

<small>Source Page 5 of 5</small>

Table 2: The standard Normal distribution P(Z< z)


[↑ Back to the source list](#source-documents)

---

