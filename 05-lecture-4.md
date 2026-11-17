# Lecture 4

**Correlation, causation and simple regression**

[← All chapters](README.md) · [Original PDF](PDF%20Slides.pdf#page=227)

## Overview

- Correlation is not automatically evidence of causation; the materials discuss observational and experimental evidence.
- Ordinary least squares, coefficients, fitted values, residuals and predictions.
- Model evaluation: R², adjusted R², standard errors, residual patterns and influential observations.

## Source documents

1. [session4_slides_pre_class.pdf](#source-1) — PDF, reader page 228
2. [session4_slides_post_class.pdf](#source-2) — PDF, reader page 250
3. [session4.Rmd](#source-3) — RMD, reader page 274
4. [beerhall.csv](#source-4) — CSV, reader page 279
5. [toyota_prius_jun18.csv](#source-5) — CSV, reader page 281

---

<a name="source-1"></a>

## session4_slides_pre_class.pdf

<small>File type: PDF · Reader pages 228–249 · [View source PDF](PDF%20Slides.pdf#page=228)</small>

<small>Source Page 1 of 59</small>

### Lecture 4

Dr Helen Wang |

<small>Source Page 2 of 59</small>

### Three coffees a day keep the doctor away… Really?

Source: the Guardian

<small>Source Page 3 of 59</small>

### Weeks 1-6 Outline

Week 01 | Exploratory Data Analysis

Week 02 | Statistics Foundation

Week 03 | Hypothesis -------

Week 04 | Regression, Part I

Week 05 | Regression, Part II

Week 06 | Risk Analysis, Part I

<small>Source Page 4 of 59</small>

### 01 | Correlation 02 | Simple Linear Regression 03 | Model Evaluation 04 |

### Model Inadequacies

Regression Part I
<small>Source Page 5 of 59</small>

### Nomenclature

Sample Correlation Coefficient rxy

True Dependent Variable Yi Estimated Dependent Variable ෢Yi

Independent Variable x

True Coefficient βi Estimated Coefficient መβi

Residual Error Ƹεt= Yt−෢Yt Residual Standard Error S, se

Coefficient of Determination / R Squared R2 Adjusted R Squared Radj

Number of observations n Number of independent variables p

Coefficient i’s Standard Error S෢β1

Q-Q Plot: Quantile Quantile Plot

<small>Source Page 6 of 59</small>

### 01 | Correlation vs Causation 02 | Simple Linear Regression 03 | Model

### Evaluation 04 | Model Inadequacies 05 | Nonlinear Transformations

Regression Part I

<small>Source Page 7 of 59</small>

### Correlation Definition

Correlation: is a numerical measure of a degree of linear relationship between two variables X and Y.

- X interest rates and Y bond prices

- X GDP and Y stock prices

- X crude oil prices and Y airline stock prices

(-) (+)

(-)

Sample Correlation Coefficient (r): is a common correlation measure.

In R, use function cor(X,Y).

Correlation Properties

- Range: −1 ≤ rxy≤+1
- It is symmetrical: rxy= ryx

- It does not imply causation, only association

- Unitless measure

- Sensitive to outliers

Degree of strength Range Perfect |r| = 1 Very strong

- 9≤|r| < 1. 0 Strong

- 7≤|r| < 0. 9 Moderate

- 5≤|r| < 0. 7 Weak

- 3≤|r| < 0. 5 Negligible 0≤|r| < 0. 3

<small>Source Page 8 of 59</small>

### Correlation Illustration

Negative Correlation: increasing values in one variable are associated with decreasing values of the other.

Positive Correlation: increasing values of one variable are associated with increasing values of the other.

rxy= +1 indicates a perfect positive linear relationship rxy= −1 indicates a perfect decreasing linear relationship rxy= 0 indicates no linear relationship −1 < rxy< 0 indicates a decreasing linear relationship 0 < rxy< 1 indicates a positive linear relationship

<small>Source Page 9 of 59</small>

### Anscombe’s quartet

Anscombe’s quartet is a dataframe with 4 datasets, each with n = 11 datapoints, and all datasets have the same mean and standard deviation for both x and y.

Would you expect to have any differences among the data in the 4 datasets? After all, they all have the same mean, sd, and cor(x, y).

<small>Source Page 10 of 59</small>

### Anscombe’s quartet

Even though the correlation coefficients are identical, data has different distributions and are very different when plotted.

- Correlation does not reflect nonlinear relationships.

- Correlation coefficient is sensitive to outliers.
<small>Source Page 11 of 59</small>

### Correlation Interpretation

Remember: correlation measures only the degree of linear relationships!

Correlation reflects noisiness and direction of a linear relationship.

Correlation does not reflect the slope of a linear relationship.

Correlation does not reflect nonlinear relationships.

<small>Source Page 12 of 59</small>

### Three coffees a day keep the doctor away… Really?

Source: the Guardian

<small>Source Page 13 of 59</small>

### Correlation vs Causation

Shoe sizes vs. Grades:

Consider elementary school --------' shoe sizes and scores on a standard reading ----. They are correlated but saying that larger shoe size causes higher reading scores is as absurd.

Ice cream sales vs Shark attacks:

Ice cream sales correlate with shark attacks. So are some types of crime rates in certain areas. But you cannot reduce shark attacks or crime by reducing the consumption of ice cream.

Confounding/Lurking/Common Response Variable

A typical reason for why variables are correlated but do not have a causal relationship is a confounding variable that creates a spurious (false) correlation.

Confound variable is an external variable / factor that influences both X and Y variables thus making it seem like there is a statistical relationship between X and Y, but it is caused by a third variable.

e.g. older -------- had more practice with ----- and -------- thus do better e.g. due to it being the summer time more swimmers are in the water
<small>Source Page 14 of 59</small>

### London Cholera Outbreaks in the 1850s

miasma or ‘bad air’: Bad smells given off by waste and rotting matter and believed to be the main source of cholera

Source: John Leech's cartoon in Punch, 23 (25 September 1852): 139 http://www.victorianweb.org/science/health/cholera/cholera.html

<small>Source Page 15 of 59</small>

### John Snow

John Snow is regarded as one of the founding fathers of modern epidemiology who believed that cholera spread through contaminated water. This contradicted the prevailing theory that diseases were spread by miasma in the air.

The September 1854 cholera outbreak was centered in the Soho district, close to Snow's house. Snow mapped the 13 public wells and all the known cholera deaths around Soho, and noted the spatial clustering of cases around one particular water pump on the southwest corner of the intersection of Broad (now Broadwick) Street and Cambridge (now Lexington) Street.

He examined water samples from various wells under a microscope, and confirmed the presence of an unknown bacterium in the Broad Street samples. Despite strong scepticism from the local authorities, he had the pump handle removed from the Broad Street pump and the outbreak quickly subsided.

<small>Source Page 16 of 59</small>

### Soho map

<small>Source Page 17 of 59</small>

<small>Source Page 18 of 59</small>

### London Water Supply

Red: Lambeth

Green:

Southwark & Vauxhall
Snow, J., "On the Mode of Communication of Cholera," 1855. The overlapping area (purple but faded to gray-red on the map) is where John Snow analyzed the results of a natural experiment.

<small>Source Page 19 of 59</small>

### John Snow’s Experiment

“… there is no difference whatever in the houses or the people receiving the supply of the two Water Companies, or in any of the physical conditions with which they are surrounded …”

The two groups were similar except for the treatment.

Supply Area

Number of Houses

Cholera Deaths

Death rate per 10,000 houses

Southwark & Vauxhall

40,046 1,263

Lambeth 26,107

Rest of London

256,423 1,422

Causality can be inferred from random assignment: If the treatment and control groups are similar apart from the treatment, then differences between the outcomes in the two groups can be ascribed to the treatment.

<small>Source Page 20 of 59</small>

### Experimentation Benefits vs. Cost

Experimentation = Actively generate new data at small scale to learn about a new business process, customer behaviour, product feature,

etc.

<small>Source Page 21 of 59</small>

### Analyzing causality through observational data is a HUGE subject in

**statistics and social sciences…**

Source: the Nobel Prize
<small>Source Page 22 of 59</small>

### 01 | Correlation vs Causation 02 | Simple Linear Regression 03 | Model

### Evaluation 04 | Model Inadequacies

Regression Part I

<small>Source Page 23 of 59</small>

### Modeling

Analyzing Individual Variables So far, we have analyzed individual variables by forming confidence intervals and hypothesis -------.

Analyzing Relationships Between Variables Next, we will analyze relationships between one or more variables. Our goal is to build models with explanatory power to predict performance.

Applications:

- Understanding factors that drive financial index/ ETF performance

- Forecast investment return or business sales

Why Analyze Relationships?

In Finance we want to know how are stock prices affected by market movements?

What is the impact of mergers on stockholder’s value?

In Marketing, how affective are different type of advertising?

Do promotions simply shift sales without affecting the overall volume?

In Economics how do interest rates affect consumer behavior?

How do trade policies influence imports/exports?

<small>Source Page 24 of 59</small>

**outcomei= modeli+ errori**

Modeling Recipe

Scatter plots Examine the plot between the variable you are trying to predict and the independent variable.

Correlation Analysis Which variables are related to each other?

How strong are the relationships?

Regression Models What are the actual relationships?
Forecasting.

Regression Diagnostics ------- for “significant” relationships.

Anything left out?

yi

xi Systematic

ei Unsystematic

Part

Part

Y x

Variable you want to explain or predict

Variable to help you explain changes in Y

Outcome variable Explanatory variable Response variable Regressor Predictor variable

Label Feature Target variable Factor Dependent variable Independent variable

<small>Source Page 25 of 59</small>

### Two Purposes of Regression

Statistics / Econometrics: you should have theoretical reason to include each variable in your equation.

Machine Learning: automatic selection of the best independent variables from the ones provided.

Prediction Explanation Focus on Y Focus on x Predict the future Explain effect of x on Y

You try to make the best prediction of Y e.g. Predicting the price of a used Prius e.g. Netflix trying to guess your next show

You try to explain the effect that specific variables, x′s, have on Y e.g. Looking at the effect of mileage on the price of a used Prius e.g. Netflix looking at the effect of time of day on show selection

<small>Source Page 26 of 59</small>

### Simple Linear Regression

Simple Linear Regression / Ordinary Least Squares (OLS) Models the variation in the dependent variable Y as a linear function of the independent variable x.

Assumed True Model Salesi= a+ bAdvertisingi+ ei where a and b are termed coefficients.
Fitted Model: Cross Sectional Data Sales data from several outlets, i, in one month:

෢ Salesi= ොa+ ෢bAdvertisingi where ොa and ෢b are the estimated coefficients.

Fitted Model: Time-Series Data Sales data from one outlet over consecutive months, t

෢ Salest= ොa+ ෢bAdvertisingt

More Time-Series Data Models

Fitted Model: Time-Series With Lagged Variables ෢ Salest= ොa+ ෢bAdvertisingt+ ƸcAdvertisingt−1

Fitted Model: Autoregression ෢ Salest= ොa+ ෢bSalest−1

<small>Source Page 27 of 59</small>

### OLS Formal Definition

https://mlu-explain.github.io/linear-regression/

https://mlu-explain.github.io/linear-regression/

Assumed True Model

Yt= β0 + β1xt+ εt where εt is the true unobserved error εt~N(0, σ2)

Linear Regression finds the line of best fit to the data, by projecting the data onto a line that minimizes the sum of squared errors Ƹεt= Yt−෢Yt.

(yt, xt)

Fitted Value We find the fitted dependent variable value as:

Ƹεt

෢Yt= መβ0 + መβ1xt where ෢Yt is the predicted value of Yt positioned on the fitted regression line for a given value of xt

(੸ᖽොyt, xt)

<small>Source Page 28 of 59</small>

### Residuals / Estimate of Errors

Residual Error Error between estimated value of the dependent variable on the line of best fit, ෢Yt, and the true value of the dependent variable, Yt, at observation t

Ƹεt= yt−ොyt

OLS minimizes the Sum of Squared Errors (SSE) with respect to regression coefficients β0, β1

n
n

2 = ෢

SSE = ෢

Ƹεt

(yt−ොyt)2

t=1

t=1

results in their optimal values መβ0 (slope), መβ1 (intercept) which we call fitted coefficients.

<small>Source Page 29 of 59</small>

### Unconditional vs. Conditional Forecast

Unconditional Forecast

n yi n−1

෢Yt= തY= σi=1

Estimate sales without regression: we’d have to estimate sales by the overall average sales i.e. the unconditional forecast.

n yi−തy2

sy= sොy= σi=1

n−1

Conditional Forecast

෢Yt= መβ0 + መβ1xt

With regression, we’d make the conditional forecast which depends on values of xi. We’d build the line of best fit as ොa+ ෢bxi and build a distribution around mean predicted values, using the residual standard error (std dev of residual variation).

n yi−ොyi2

n−p−1 = ei2

σi=1

se=

n−2
<small>Source Page 30 of 59</small>

### Understanding Relationships

In 1856, the Reverend John Clay felt that it was time to figure out what factors were playing a role in the incidence of criminal behavior in Britain. He stated that:

“It is a mere truism to say that the progress of popular education, and the formation of religious habits, are fatally opposed by the temptations to animal pleasures, which abound wherever BEERHOUSES and low ALE-HOUSES abound.”

Education Religion

Beer Houses Crime

+

<small>Source Page 31 of 59</small>

### English Data on Criminals

Church, x3 Edu, x2 Pubs, x1 Crime, Y

Open session4.rmd

<small>Source Page 32 of 59</small>

### Exploratory Analysis on Crime Data

Exploratory Data Analysis

- Favourite statistics of Mosaic Package

- Bar plot of total number of crimes per region

<small>Source Page 33 of 59</small>

### Exploratory Analysis on Crime Data

- Matrix of density plots, scatterplots and correlations using ggpairs() function:

```r
library(GGally) crime %>% dplyr::select(public_houses, criminals) %>% ggpairs()
```

We can see that rcrime,pubs= 0.463, the two variables are weakly correlated.

Q: How would you predict criminality if you had a new region for which you know the number of public houses?
<small>Source Page 34 of 59</small>

### Line of Best Fit

Let's investigate how well we can predict criminals given the number of public houses using simple linear regression, (per 100k population).

```r
ggplot(crime, aes(x=public_houses, y=criminals)) + geom_point() + geom_smooth(method=lm,
se=FALSE, color="red")
```

where lm stands for linear model.

Correlation coefficient was indicating a weak positive linear relationship, r= 0.46.

For OLS, the slope and the correlation

σy σx

coefficient are related as: መβ1 = r

The fitted regression line equation is:

෢ criminalsi= መβ0 + መβ1 ∗pubsi

መβ1 (slope)

መβ0 (intercept)

<small>Source Page 35 of 59</small>

### Estimates of Residual Errors

We want to make the residuals:

We can visualize residuals using a Residual Error Plot.

- Have an average of zero (this is equivalent to saying ‘there is no bias’)

- Be “as small as possible” (by minimizing the squares of the errors with respect to

coefficients). This is equivalent to saying “we want to minimize the standard deviation of the residual errors”.

<small>Source Page 36 of 59</small>

### Build and Evaluate OLS Model

OLS Model in R:

Obtain simple linear regression model to find the line of best fit for relationship: ෢ criminalsi= መβ0 + መβ1 ∗pubsi
```r
model1 <- lm(criminals ~ public_houses, data = crime) summary(model1)
```

To evaluate the model, observe the following output:

- Estimated values of the coefficients

- p-values of the coefficients

- Standard error of the regression residuals

- R-squared

<small>Source Page 37 of 59</small>

### Significance of Coefficients

We have found the coefficients of the equation:

෢ criminalsi= መβ0 + መβ1 ∗pubsi

Rule is:

- Always keep the intercept in the equation as it allows the regression line to not be

fixed at the origin

- Decide if coefficient of the x variable is significantly different from 0.

Q: Why do we need to decide that?

<small>Source Page 38 of 59</small>

### Significance of Coefficients

We have found the coefficients of the equation:

෢ criminalsi= መβ0 + መβ1 ∗pubsi

If መβ1 = 0, then pubs has no influence on criminals since the equation becomes: ෢ criminalsi= መβ0.

Let’s establish whether the public_houses variable has predictive power on the crime variable at α= 5%.

Hypothesis ------- for Regression Coefficients H0: መβ1 = 0 implies no relationship between x and Y H1: መβ1 ≠0 coefficient is significant

- Since the public_houses p-value 0.0026 < 0.05 we can reject H0 and conclude the

coefficient is significant.

- Alternatively, you can base your decision on the t-stat, since |3.22| > 2, reject the null

hypothesis.
Therefore, pubs does have predictive power on crime and we can write down the equation of regression line:

෢ criminalsi= 109.34 + 0.1162 ∗pubsi

<small>Source Page 39 of 59</small>

### Point Prediction and Prediction Interval

Valid Model: all coefficients are significant (except the intercept which we always keep).

Once we ensure the model is valid, we can write down the equation of the fitted regression line as:

෢ criminalsi= 109.34 + 0.1162 ∗pubsi

This equation can be used to make a point prediction. A single-valued estimate of ෢Yt for a given value of xt is obtained by inserting the value of xt:

෢ criminalsi= 109.34 + 0.1162 ∗72 = 117.98

However, how certain are we about this value?

Prediction Interval Use the residual standard error to form approximate prediction interval for ෢Yt for the given value of xt.

෢Yt± 1.96 ∗S

Example: for xt= 72, ෢Yt= 117.98, the interval is:

117.98 1.96 ∗37.2 = [45.07, 190.89]

<small>Source Page 40 of 59</small>

### 01 | Correlation vs Causation 02 | Simple Linear Regression 03 | Model

### Evaluation 04 | Model Inadequacies

Regression Part I

<small>Source Page 41 of 59</small>

### Residual Standard Error

Residual Standard Error (RSE) is the square root of the average squared residuals:

n yi−ොyi2

RSE= se= σi=1

n−p−1
where n is the number of observations and p number of independent variables.

Importance of RSE:

Measure of Model Accuracy: how well model predicts the observed data (smaller se means better line fit).

Comparison: compare the fit of different models by selecting the one with the smaller se

Model Adequacy: compare RSE to standard deviation of the dependent variable (if se ≫σY then model is not capturing the data patterns well).

<small>Source Page 42 of 59</small>

### R2

Coefficient of Determination, R2 = corr2 describes ‘goodness of fit’ of a regression model i.e. how well does the line fit the data?

- Model is never perfect

- Model captures part of the variability of the data

R2 = 1 line fits the data perfectly R2 = 0 model explains none of the variability in Y

It is calculated as:

σ ෢Yi−തY

R2 = Explained Variation

σ Yi−തY2 = corr2

Total Variation =

2 is the variance of the fitted ෢Yi points and σ Yi−തY2 is the variance of the original Y points

where σ ෢Yi−തY

Interpretation of R2

- R2 shows how much better your model is compared to the unconditional forecast

(naïve model) that predicts every value of Y to be the mean(Y)?

n yi n−1

෢Yt= തY= σi=1

- R2 shows the proportion of total variation of Y that is explained by the model (i.e. by

the independent variable(s))
<small>Source Page 43 of 59</small>

### R2

The higher the R2 the greater the explanatory power of the model.

<small>Source Page 44 of 59</small>

### Adjusted R2

Adjusted R2

Adjusts the R2 statistic for the number of independent variables present in the model.

- As the number of inputs (x’s) increases, R2 typically increases regardless of whether

the variables are useful for prediction.

- Adjusted R2 will only increase if the new x variable improves the model more than

would be expected by chance.

= 1 −(n−1)

n−p−1 1 −R2

Radj

where n is the number of observations and p number of independent variables. If n is very large and p is very small, the ratio is close to zero, and R2 ≈Radj

Negative Adj R2:

which means that the model fits worse than the naïve model.

It is possible to have negative values of Radj

It can happen because:

- No intercept was used (forcing the line to go through origin doesn’t make sense for

many real-life tasks)

- Overfitting (great performance on training data with

but poor out-of-sample prediction with

high Radj

)

low/negative Radj

Model Selection:

When selecting among competing models, select the one where all variables are significant, the model has the largest Adj R2, and smallest RSE.
<small>Source Page 45 of 59</small>

### Example: Used Prius Car Price

Miles and Car Price Are miles related to car price? Let’s observe ggpairs() plot.

Initial Relationship Analysis

Are miles and car prices related?

Yes: the scatterplot shows that as miles increase, price decreases.

How are miles and car prices related?

Negatively.

How strongly are they related?

The coefficient of correlation shows a strong decreasing linear relationship, rmiles,prices= −0.756

<small>Source Page 46 of 59</small>

### Example: Used Prius Car Price

Modelling Relationship of Prices vs Miles

Useful Questions:

- What is the price likely to be when miles = 0?

- How much is the price likely to decrease for an

extra mile of driving?

We use Simple Linear Regression:

- The dependent variable is price, variable we want to model, Y= price

- The model is ‘Simple’ because we only have 1 independent variable, x= miles

- The model is ‘Linear’ because it is linear in the parameters β (i.e. parameters are not

raised to a power, or divided by each other etc)

Visualize Simple Linear Regression with ggplot

Start by visualizing what the regression line would be using ggplot’s function geom_smooth(method='lm')
<small>Source Page 47 of 59</small>

### Regression Coding Exercise

Using RStudio create a regression model to predict Prius used prices based on milage. Use the function

```r
lm(y ~ x, data = name) Obtain regression summary using summary() function
```

Report using pen and paper: - Write down the true model describing the relationship between the car price and the milage. - Check whether the coefficient of milage is significant and provide reasoning - Write down the fitted model - What is the R2? - Given another car with miles=105500 what is your point prediction for the car price? - Provide a 95% confidence interval around your prediction - What is the price likely to be when miles=0? - How much is the price likely to decrease for an extra mile of driving? What bout 10000 miles of

driving?

<small>Source Page 48 of 59</small>

### 01 | Correlation vs Causation 02 | Simple Linear Regression 03 | Model

### Evaluation 04 | Model Inadequacies

Regression Part I

<small>Source Page 49 of 59</small>

### Linear Regression Model Assumptions

Assumptions:

[A1] Relationship between x and Y is linear.

[A2] Randomness in Y values comes purely from the error term ε. Values of the independent variable x are assumed fixed and not random.

[A3] Errors are uncorrelated with independent variables, x.

[A4] Errors are uncorrelated with each other in successive observations i.e. errors are independent of each other.

Assumptions:

[A5] Errors are Normally distributed with mean 0 and variance σ2, ε~N(0, σ2). Note: constant, time independent variance is called homoscedasticity.

ε~N(0, σ2) assumption is essential for:

- Hypothesis ------- of regression coefficients.

- Interval estimation around point prediction.
- Model validity: “are residuals Normally distributed?” ➢Normal residuals: model cor‐

rectly specified ➢Nonnormal residuals: nonlinearity present, interactions between independent variables, outliers

<small>Source Page 50 of 59</small>

### How Residuals Should Look

Random scatter with no visible pattern.

Constant variance of the residuals

<small>Source Page 51 of 59</small>

### Regression Error Analysis

We should not be making systematic errors.

Systematic error: means errors exhibit some consistent, non-random pattern, rather than being distributed randomly around the regression line.

Systematic error presence means regression model is not fully capturing the relationship between Y and x’s.

Any systematic component should be in the model rather than in the error.

By including the systematic error in the model, the model should improve.

outcomei= modeli+ errori

yi

xi Systematic part

εi Unsystematic part

Possible Reasons For Systematic Errors:

- Nonlinearity: systematic pattern in the residuals

- Heteroscedasticity: variance of errors changes across levels of independent variable

- Autocorrelation: errors in one period are correlated

with errors in another period

<small>Source Page 52 of 59</small>

### Systematic Errors: Nonlinear Relationship

True underlying relationship is nonlinear, however a line was fitted
A systematic patter can by seen due to errors above and below the fitted line

Remedy: nonlinear transformation (next session)

<small>Source Page 53 of 59</small>

### Systematic Errors: Heteroscedasticity

Variance of residuals is not constant.

Non-consistent standard deviation of the variable over time.

Remedy: standard error clustering

<small>Source Page 54 of 59</small>

### Systematic Errors: Autocorrelation

Serial correlation / autocorrelation: means errors are correlated with each other over time. It violates the assumption of independence of errors.

The residual plot shows a clear linear pattern.

You may also see a wave-like or cyclical pattern.

Remedy: introduce lags.

Example:

෢ Salest= ොa+ ෢bAdvertisingt+ ƸcAdvertisingt−1

<small>Source Page 55 of 59</small>

### Outliers and Influential Observations

. . .

.

Regression line without outlier

y

. . . . . .. . .

.

Regression line with outlier

.

.
- Outlier

x

Outlier: observation that is extreme with respect to other y observations.

If an observation has an unusually large residual error, it is often an indication that the data point is wrong in some way.

Point with a large value of xi *

y

Regression line when all data are included

.. . . ... .. . ... . .

No relationship in this cluster

x

Influential: observation that is extreme w.r.t. other x observations.

Some observations might have an undue influence on the model.

<small>Source Page 56 of 59</small>

### Examine residuals using Autoplot

If something goes wrong in our model, it will show up in the residuals. Therefore, always plot the residuals.

Use the ggfortify library to plot 3 essential plots for residuals.

```r
library(ggfortify) model1 %>% autoplot(which = 1:3) + theme_bw()
```

The Three Plots Show:

- Residuals vs Fitted Values (i.e. ε vs ෢Y, the plot on pp. 51).

Want to see: a horizontal straight line.

- Normal Q-Q Plot (i.e. quantile quantile plot of theoretical normal distribution vs the

quantiles of the residuals) Want to see: a 45-degree line.

- Spread-Location (i.e. sqrt of absolute values of standardized residuals) Want to see: a

horizontal straight line.

<small>Source Page 57 of 59</small>

### Q-Q Plot Examples:

Normal Data:
Non-Normal Data:

Non-Normal Data:

<small>Source Page 58 of 59</small>

### Residuals Autoplot: Crime Example

Plot 1: Are the residuals random with mean 0, or does there seem to be a consistent pattern in the residuals?

Plot 2: Do residuals follow a Normal distribution? Is the Q-Q (Quantile-Quantile) Plot nearly a 45-degree line?

Plot 3: Do residuals have constant variance? Is blue line approx. horizontal / does the spread around the line not vary much?

<small>Source Page 59 of 59</small>

### Session Summary

We covered:

Correlation Simple Linear Regression

Readings:

Modern Dives chapter 5

Optional/ Extra practice: workshop4.Rmd Coding questions ---- practice.

Workshop Questions:

Look at the workshop questions in advance.

Attend optional workshop to go over the solutions.

Group Assignment 1:

Start looking at it in Canvas → Files → Group Assignment 1


[↑ Back to the source list](#source-documents)

---

<a name="source-2"></a>

## session4_slides_post_class.pdf

<small>File type: PDF · Reader pages 250–273 · [View source PDF](PDF%20Slides.pdf#page=250)</small>

<small>Source Page 1 of 64</small>

### Lecture 4

Dr Helen Wang |

<small>Source Page 2 of 64</small>

### Three coffees a day keep the doctor away… Really?

Source: the Guardian

<small>Source Page 3 of 64</small>

### Weeks 1-6 Outline

Week 01 | Exploratory Data Analysis

Week 02 | Statistics Foundation

Week 03 | Hypothesis -------

Week 04 | Regression, Part I

Week 05 | Regression, Part II

Week 06 | Risk Analysis, Part I

<small>Source Page 4 of 64</small>

### 01 | Correlation 02 | Simple Linear Regression 03 | Model Evaluation 04 |

### Model Inadequacies

Regression Part I
<small>Source Page 5 of 64</small>

### Nomenclature

Sample Correlation Coefficient rxy

True Dependent Variable Yi Estimated Dependent Variable ෢Yi

Independent Variable x

True Coefficient βi Estimated Coefficient መβi

Residual Error Ƹεt= Yt−෢Yt Residual Standard Error S, se

Coefficient of Determination / R Squared R2 Adjusted R Squared Radj

Number of observations n Number of independent variables p

Coefficient i’s Standard Error S෢β1

Q-Q Plot: Quantile Quantile Plot

<small>Source Page 6 of 64</small>

### 01 | Correlation vs Causation 02 | Simple Linear Regression 03 | Model

### Evaluation 04 | Model Inadequacies 05 | Nonlinear Transformations

Regression Part I

<small>Source Page 7 of 64</small>

### Correlation Definition

Correlation: is a numerical measure of a degree of linear relationship between two variables X and Y.

- X interest rates and Y bond prices

- X GDP and Y stock prices

- X crude oil prices and Y airline stock prices

(-) (+)

(-)

Sample Correlation Coefficient (r): is a common correlation measure.

In R, use function cor(X,Y).

Correlation Properties

- Range: −1 ≤ rxy≤+1
- It is symmetrical: rxy= ryx

- It does not imply causation, only association

- Unitless measure

- Sensitive to outliers

Degree of strength Range Perfect |r| = 1 Very strong

- 9≤|r| < 1. 0 Strong

- 7≤|r| < 0. 9 Moderate

- 5≤|r| < 0. 7 Weak

- 3≤|r| < 0. 5 Negligible 0≤|r| < 0. 3

<small>Source Page 8 of 64</small>

### Correlation Illustration

Negative Correlation: increasing values in one variable are associated with decreasing values of the other.

Positive Correlation: increasing values of one variable are associated with increasing values of the other.

rxy= +1 indicates a perfect positive linear relationship rxy= −1 indicates a perfect decreasing linear relationship rxy= 0 indicates no linear relationship −1 < rxy< 0 indicates a decreasing linear relationship 0 < rxy< 1 indicates a positive linear relationship

<small>Source Page 9 of 64</small>

### Anscombe’s quartet

Anscombe’s quartet is a dataframe with 4 datasets, each with n = 11 datapoints, and all datasets have the same mean and standard deviation for both x and y.

Would you expect to have any differences among the data in the 4 datasets? After all, they all have the same mean, sd, and cor(x, y).

<small>Source Page 10 of 64</small>

### Anscombe’s quartet

Even though the correlation coefficients are identical, data has different distributions and are very different when plotted.

- Correlation does not reflect nonlinear relationships.

- Correlation coefficient is sensitive to outliers.
<small>Source Page 11 of 64</small>

### Correlation Interpretation

Remember: correlation measures only the degree of linear relationships!

Correlation reflects noisiness and direction of a linear relationship.

Correlation does not reflect the slope of a linear relationship.

Correlation does not reflect nonlinear relationships.

<small>Source Page 12 of 64</small>

### Three coffees a day keep the doctor away… Really?

Source: the Guardian

<small>Source Page 13 of 64</small>

### Correlation vs Causation

Shoe sizes vs. Grades:

Consider elementary school --------' shoe sizes and scores on a standard reading ----. They are correlated but saying that larger shoe size causes higher reading scores is as absurd.

Ice cream sales vs Shark attacks:

Ice cream sales correlate with shark attacks. So are some types of crime rates in certain areas. But you cannot reduce shark attacks or crime by reducing the consumption of ice cream.

Confounding/Lurking/Common Response Variable

A typical reason for why variables are correlated but do not have a causal relationship is a confounding variable that creates a spurious (false) correlation.

Confound variable is an external variable / factor that influences both X and Y variables thus making it seem like there is a statistical relationship between X and Y, but it is caused by a third variable.

e.g. older -------- had more practice with ----- and -------- thus do better e.g. due to it being the summer time more swimmers are in the water
<small>Source Page 14 of 64</small>

### London Cholera Outbreaks in the 1850s

miasma or ‘bad air’: Bad smells given off by waste and rotting matter and believed to be the main source of cholera

Source: John Leech's cartoon in Punch, 23 (25 September 1852): 139 http://www.victorianweb.org/science/health/cholera/cholera.html

<small>Source Page 15 of 64</small>

### John Snow

John Snow is regarded as one of the founding fathers of modern epidemiology who believed that cholera spread through contaminated water. This contradicted the prevailing theory that diseases were spread by miasma in the air.

The September 1854 cholera outbreak was centered in the Soho district, close to Snow's house. Snow mapped the 13 public wells and all the known cholera deaths around Soho, and noted the spatial clustering of cases around one particular water pump on the southwest corner of the intersection of Broad (now Broadwick) Street and Cambridge (now Lexington) Street.

He examined water samples from various wells under a microscope, and confirmed the presence of an unknown bacterium in the Broad Street samples. Despite strong scepticism from the local authorities, he had the pump handle removed from the Broad Street pump and the outbreak quickly subsided.

<small>Source Page 16 of 64</small>

### Soho map

<small>Source Page 17 of 64</small>

<small>Source Page 18 of 64</small>

### London Water Supply

Red: Lambeth

Green:

Southwark & Vauxhall
Snow, J., "On the Mode of Communication of Cholera," 1855. The overlapping area (purple but faded to gray-red on the map) is where John Snow analyzed the results of a natural experiment.

<small>Source Page 19 of 64</small>

### John Snow’s Experiment

“… there is no difference whatever in the houses or the people receiving the supply of the two Water Companies, or in any of the physical conditions with which they are surrounded …”

The two groups were similar except for the treatment.

Supply Area

Number of Houses

Cholera Deaths

Death rate per 10,000 houses

Southwark & Vauxhall

40,046 1,263

Lambeth 26,107

Rest of London

256,423 1,422

Causality can be inferred from random assignment: If the treatment and control groups are similar apart from the treatment, then differences between the outcomes in the two groups can be ascribed to the treatment.

<small>Source Page 20 of 64</small>

### Experimentation Benefits vs. Cost

Experimentation = Actively generate new data at small scale to learn about a new business process, customer behaviour, product feature,

etc.

<small>Source Page 21 of 64</small>

### Analyzing causality through observational data is a HUGE subject in

**statistics and social sciences…**

Source: the Nobel Prize
<small>Source Page 22 of 64</small>

### 01 | Correlation vs Causation 02 | Simple Linear Regression 03 | Model

### Evaluation 04 | Model Inadequacies

Regression Part I

<small>Source Page 23 of 64</small>

### Modeling

Analyzing Individual Variables So far, we have analyzed individual variables by forming confidence intervals and hypothesis -------.

Analyzing Relationships Between Variables Next, we will analyze relationships between one or more variables. Our goal is to build models with explanatory power to predict performance.

Applications:

- Understanding factors that drive financial index/ ETF performance

- Forecast investment return or business sales

Why Analyze Relationships?

In Finance we want to know how are stock prices affected by market movements?

What is the impact of mergers on stockholder’s value?

In Marketing, how affective are different type of advertising?

Do promotions simply shift sales without affecting the overall volume?

In Economics how do interest rates affect consumer behavior?

How do trade policies influence imports/exports?

<small>Source Page 24 of 64</small>

**outcomei= modeli+ errori**

Modeling Recipe

Scatter plots Examine the plot between the variable you are trying to predict and the independent variable.

Correlation Analysis Which variables are related to each other?

How strong are the relationships?

Regression Models What are the actual relationships?
Forecasting.

Regression Diagnostics ------- for “significant” relationships.

Anything left out?

yi

xi Systematic

ei Unsystematic

Part

Part

Y x

Variable you want to explain or predict

Variable to help you explain changes in Y

Outcome variable Explanatory variable Response variable Regressor Predictor variable

Label Feature Target variable Factor Dependent variable Independent variable

<small>Source Page 25 of 64</small>

### Two Purposes of Regression

Statistics / Econometrics: you should have theoretical reason to include each variable in your equation.

Machine Learning: automatic selection of the best independent variables from the ones provided.

Prediction Explanation Focus on Y Focus on x Predict the future Explain effect of x on Y

You try to make the best prediction of Y e.g. Predicting the price of a used Prius e.g. Netflix trying to guess your next show

You try to explain the effect that specific variables, x′s, have on Y e.g. Looking at the effect of mileage on the price of a used Prius e.g. Netflix looking at the effect of time of day on show selection

<small>Source Page 26 of 64</small>

### Simple Linear Regression

Simple Linear Regression / Ordinary Least Squares (OLS) Models the variation in the dependent variable Y as a linear function of the independent variable x.

Assumed True Model Salesi= a+ bAdvertisingi+ ei where a and b are termed coefficients.
Fitted Model: Cross Sectional Data Sales data from several outlets, i, in one month:

෢ Salesi= ොa+ ෢bAdvertisingi where ොa and ෢b are the estimated coefficients.

Fitted Model: Time-Series Data Sales data from one outlet over consecutive months, t

෢ Salest= ොa+ ෢bAdvertisingt

More Time-Series Data Models

Fitted Model: Time-Series With Lagged Variables ෢ Salest= ොa+ ෢bAdvertisingt+ ƸcAdvertisingt−1

Fitted Model: Autoregression ෢ Salest= ොa+ ෢bSalest−1

<small>Source Page 27 of 64</small>

### OLS Formal Definition

https://mlu-explain.github.io/linear-regression/

https://mlu-explain.github.io/linear-regression/

Assumed True Model

Yt= β0 + β1xt+ εt where εt is the true unobserved error εt~N(0, σ2)

Linear Regression finds the line of best fit to the data, by projecting the data onto a line that minimizes the sum of squared errors Ƹεt= Yt−෢Yt.

(yt, xt)

Fitted Value We find the fitted dependent variable value as:

Ƹεt

෢Yt= መβ0 + መβ1xt where ෢Yt is the predicted value of Yt positioned on the fitted regression line for a given value of xt

(੸ᖽොyt, xt)

<small>Source Page 28 of 64</small>

### Residuals / Estimate of Errors

Residual Error Error between estimated value of the dependent variable on the line of best fit, ෢Yt, and the true value of the dependent variable, Yt, at observation t

Ƹεt= yt−ොyt

OLS minimizes the Sum of Squared Errors (SSE) with respect to regression coefficients β0, β1

n
n

2 = ෢

SSE = ෢

Ƹεt

(yt−ොyt)2

t=1

t=1

results in their optimal values መβ0 (slope), መβ1 (intercept) which we call fitted coefficients.

<small>Source Page 29 of 64</small>

### Unconditional vs. Conditional Forecast

Unconditional Forecast

n yi n−1

෢Yt= തY= σi=1

Estimate sales without regression: we’d have to estimate sales by the overall average sales i.e. the unconditional forecast.

n yi−തy2

sy= sොy= σi=1

n−1

Conditional Forecast

෢Yt= መβ0 + መβ1xt

With regression, we’d make the conditional forecast which depends on values of xi. We’d build the line of best fit as ොa+ ෢bxi and build a distribution around mean predicted values, using the residual standard error (std dev of residual variation).

n yi−ොyi2

n−p−1 = ei2

σi=1

se=

n−2
<small>Source Page 30 of 64</small>

### Understanding Relationships

In 1856, the Reverend John Clay felt that it was time to figure out what factors were playing a role in the incidence of criminal behavior in Britain. He stated that:

“It is a mere truism to say that the progress of popular education, and the formation of religious habits, are fatally opposed by the temptations to animal pleasures, which abound wherever BEERHOUSES and low ALE-HOUSES abound.”

Education Religion

Beer Houses Crime

+

<small>Source Page 31 of 64</small>

### English Data on Criminals

Church, x3 Edu, x2 Pubs, x1 Crime, Y

Open session4.rmd

<small>Source Page 32 of 64</small>

### Exploratory Analysis on Crime Data

Exploratory Data Analysis

- Favourite statistics of Mosaic Package

- Bar plot of total number of crimes per region

<small>Source Page 33 of 64</small>

### Exploratory Analysis on Crime Data

- Matrix of density plots, scatterplots and correlations using ggpairs() function:

```r
library(GGally) crime %>% dplyr::select(public_houses, criminals) %>% ggpairs()
```

We can see that rcrime,pubs= 0.463, the two variables are weakly correlated.

Q: How would you predict criminality if you had a new region for which you know the number of public houses?
<small>Source Page 34 of 64</small>

### Line of Best Fit

Let's investigate how well we can predict criminals given the number of public houses using simple linear regression, (per 100k population).

```r
ggplot(crime, aes(x=public_houses, y=criminals)) + geom_point() + geom_smooth(method=lm,
se=FALSE, color="red")
```

where lm stands for linear model.

Correlation coefficient was indicating a weak positive linear relationship, r= 0.46.

For OLS, the slope and the correlation

σy σx

coefficient are related as: መβ1 = r

The fitted regression line equation is:

෢ criminalsi= መβ0 + መβ1 ∗pubsi

መβ1 (slope)

መβ0 (intercept)

<small>Source Page 35 of 64</small>

### Estimates of Residual Errors

We want to make the residuals:

We can visualize residuals using a Residual Error Plot.

- Have an average of zero (this is equivalent to saying ‘there is no bias’)

- Be “as small as possible” (by minimizing the squares of the errors with respect to

coefficients). This is equivalent to saying “we want to minimize the standard deviation of the residual errors”.

<small>Source Page 36 of 64</small>

### Build and Evaluate OLS Model

OLS Model in R:

Obtain simple linear regression model to find the line of best fit for relationship: ෢ criminalsi= መβ0 + መβ1 ∗pubsi
```r
model1 <- lm(criminals ~ public_houses, data = crime) summary(model1)
```

To evaluate the model, observe the following output:

- Estimated values of the coefficients

- p-values of the coefficients

- Standard error of the regression residuals

- R-squared

<small>Source Page 37 of 64</small>

### Significance of Coefficients

We have found the coefficients of the equation:

෢ criminalsi= መβ0 + መβ1 ∗pubsi

Rule is:

- Always keep the intercept in the equation as it allows the regression line to not be

fixed at the origin

- Decide if coefficient of the x variable is significantly different from 0.

Q: Why do we need to decide that?

<small>Source Page 38 of 64</small>

### Significance of Coefficients

We have found the coefficients of the equation:

෢ criminalsi= መβ0 + መβ1 ∗pubsi

If መβ1 = 0, then pubs has no influence on criminals since the equation becomes: ෢ criminalsi= መβ0.

Let’s establish whether the public_houses variable has predictive power on the crime variable at α= 5%.

Hypothesis ------- for Regression Coefficients H0: መβ1 = 0 implies no relationship between x and Y H1: መβ1 ≠0 coefficient is significant

- Since the public_houses p-value 0.0026 < 0.05 we can reject H0 and conclude the

coefficient is significant.

- Alternatively, you can base your decision on the t-stat, since |3.22| > 2, reject the null

hypothesis.
Therefore, pubs does have predictive power on crime and we can write down the equation of regression line:

෢ criminalsi= 109.34 + 0.1162 ∗pubsi

<small>Source Page 39 of 64</small>

### In-class Quiz 4 (2.5% of Grade)

You have run a regression ොyi= መβ0 + መβ1x1 and found the following results. Select the one option below that is incorrect:

A. The null hypothesis of the coefficient of x1 is: H0: መβ1 = 0

B. If መβ1 = 0, it means that the independent variable has no effect on the dependent variable and the regression equation reduces down to ොyi= መβ0.

C. The t-stat for መβ0 is approximately 0.968, meaning that we cannot reject መβ0 = 0 at 5% level.

Therefore we drop the intercept from the model.

D. The t-stat for መβ1 is approximately 0.433, meaning that we cannot reject መβ1 = 0 at 5% level.

Therefore the prediction model ොyi= 52.7877 + 0.2814x1 is invalid.

<small>Source Page 40 of 64</small>

### Answers

The intercept: is the expected value of the dependent variable yt when the independent variable xt is zero.

The coefficient: change in the expected value of yt corresponding to 1 unit increase in xt.

The hypothesis is:

H0: መβ1 = 0 Ha: መβ1 ≠0 If መβ1 = 0 it means that the independent variable has no effect on the dependent variable and the regression equation reduces down to ෢ criminalsi= መβ0

The variable xt has a relationship with the variable we are trying to predict.

෢β1−0

t-stat =

S෢β1

We only need the t-stat of መβ1 since we always keep the intercept regardless if it is significant or not. The tstat of መβ1 is 0.2814−0

0.6505 = 0.433
<small>Source Page 41 of 64</small>

### Point Prediction and Prediction Interval

Valid Model: all coefficients are significant (except the intercept which we always keep).

Once we ensure the model is valid, we can write down the equation of the fitted regression line as:

෢ criminalsi= 109.34 + 0.1162 ∗pubsi

This equation can be used to make a point prediction. A single-valued estimate of ෢Yt for a given value of xt is obtained by inserting the value of xt:

෢ criminalsi= 109.34 + 0.1162 ∗72 = 117.98

However, how certain are we about this value?

Prediction Interval Use the residual standard error to form approximate prediction interval for ෢Yt for the given value of xt.

෢Yt± 1.96 ∗S

Example: for xt= 72, ෢Yt= 117.98, the interval is:

117.98 1.96 ∗37.2 = [45.07, 190.89]

<small>Source Page 42 of 64</small>

### 01 | Correlation vs Causation 02 | Simple Linear Regression 03 | Model

### Evaluation 04 | Model Inadequacies

Regression Part I

<small>Source Page 43 of 64</small>

### Residual Standard Error

Residual Standard Error (RSE) is the square root of the average squared residuals:

n yi−ොyi2

RSE= se= σi=1

n−p−1

where n is the number of observations and p number of independent variables.

Importance of RSE:

Measure of Model Accuracy: how well model predicts the observed data (smaller se means better line fit).
Comparison: compare the fit of different models by selecting the one with the smaller se

Model Adequacy: compare RSE to standard deviation of the dependent variable (if se ≫σY then model is not capturing the data patterns well).

<small>Source Page 44 of 64</small>

### R2

Coefficient of Determination, R2 = corr2 describes ‘goodness of fit’ of a regression model i.e. how well does the line fit the data?

- Model is never perfect

- Model captures part of the variability of the data

R2 = 1 line fits the data perfectly R2 = 0 model explains none of the variability in Y

It is calculated as:

σ ෢Yi−തY

R2 = Explained Variation

σ Yi−തY2 = corr2

Total Variation =

2 is the variance of the fitted ෢Yi points and σ Yi−തY2 is the variance of the original Y points

where σ ෢Yi−തY

Interpretation of R2

- R2 shows how much better your model is compared to the unconditional forecast

(naïve model) that predicts every value of Y to be the mean(Y)?

n yi n−1

෢Yt= തY= σi=1

- R2 shows the proportion of total variation of Y that is explained by the model (i.e. by

the independent variable(s))

<small>Source Page 45 of 64</small>

### R2

The higher the R2 the greater the explanatory power of the model.
<small>Source Page 46 of 64</small>

### Adjusted R2

Adjusted R2

Adjusts the R2 statistic for the number of independent variables present in the model.

- As the number of inputs (x’s) increases, R2 typically increases regardless of whether

the variables are useful for prediction.

- Adjusted R2 will only increase if the new x variable improves the model more than

would be expected by chance.

= 1 −(n−1)

n−p−1 1 −R2

Radj

where n is the number of observations and p number of independent variables. If n is very large and p is very small, the ratio is close to zero, and R2 ≈Radj

Negative Adj R2:

which means that the model fits worse than the naïve model.

It is possible to have negative values of Radj

It can happen because:

- No intercept was used (forcing the line to go through origin doesn’t make sense for

many real-life tasks)

- Overfitting (great performance on training data with

but poor out-of-sample prediction with

high Radj

)

low/negative Radj

Model Selection:

When selecting among competing models, select the one where all variables are significant, the model has the largest Adj R2, and smallest RSE.

<small>Source Page 47 of 64</small>

### Example: Used Prius Car Price

Miles and Car Price Are miles related to car price? Let’s observe ggpairs() plot.

Initial Relationship Analysis
Are miles and car prices related?

Yes: the scatterplot shows that as miles increase, price decreases.

How are miles and car prices related?

Negatively.

How strongly are they related?

The coefficient of correlation shows a strong decreasing linear relationship, rmiles,prices= −0.756

<small>Source Page 48 of 64</small>

### Example: Used Prius Car Price

Modelling Relationship of Prices vs Miles

Useful Questions:

- What is the price likely to be when miles = 0?

- How much is the price likely to decrease for an

extra mile of driving?

We use Simple Linear Regression:

- The dependent variable is price, variable we want to model, Y= price

- The model is ‘Simple’ because we only have 1 independent variable, x= miles

- The model is ‘Linear’ because it is linear in the parameters β (i.e. parameters are not

raised to a power, or divided by each other etc)

Visualize Simple Linear Regression with ggplot

Start by visualizing what the regression line would be using ggplot’s function geom_smooth(method='lm')

<small>Source Page 49 of 64</small>

### Regression Coding Exercise

Using RStudio create a regression model to predict Prius used prices based on milage. Use the function

```r
lm(y ~ x, data = name) Obtain regression summary using summary() function
```

Report using pen and paper: - Write down the true model describing the relationship between the car price and the milage. - Check whether the coefficient of milage is significant and provide reasoning - Write down the fitted model - What is the R2? - Given another car with
miles=105500 what is your point prediction for the car price? - Provide a 95% confidence interval around your prediction - What is the price likely to be when miles=0? - How much is the price likely to decrease for an extra mile of driving? What bout 10000 miles of

driving?

<small>Source Page 50 of 64</small>

### Answers

```r
car_model1 <- lm(price ~ miles, data = prius) summary(car_model1)
```

True Model: price= β0 + β1miles+ εt

Model is valid: coefficients are significant, since p<0.05

Fitted Model:

෢ price= ෢β0 + ෢β1miles= 14,734 −0.065 ∗miles

<small>Source Page 51 of 64</small>

### Answers

True Model: price= β0 + β1miles+ εt

Significance: coefficients are significant, since p<0.05

Fitted Model:

෢ price= ෢β0 + ෢β1miles= 14,734 −0.065 ∗miles

R2:

0.5721

Car Price Prediction if miles=105500:

෢ price= 14,734 −0.065 ∗105500 = 7876.5

95% CI around point prediction:

෢Yt± 1.96 ∗s = 7876.5 ± 1.96 ∗3280 = 7876.5 ± 6428.8 = [1448, 14305]

Price when miles= 0:

We look at the intercept, ෢β0 = £14730

Price decrease per extra mile of driving:

We look at the slope, ෢β1 = −0.0645, therefore price will decrease by £0.065 per mile, therefore if you drive 10000 miles care will decrease by 10000*(0.065)=£650
<small>Source Page 52 of 64</small>

### 01 | Correlation vs Causation 02 | Simple Linear Regression 03 | Model

### Evaluation 04 | Model Inadequacies

Regression Part I

<small>Source Page 53 of 64</small>

### Linear Regression Model Assumptions

Assumptions:

[A1] Relationship between x and Y is linear.

[A2] Randomness in Y values comes purely from the error term ε. Values of the independent variable x are assumed fixed and not random.

[A3] Errors are uncorrelated with independent variables, x.

[A4] Errors are uncorrelated with each other in successive observations i.e. errors are independent of each other.

Assumptions:

[A5] Errors are Normally distributed with mean 0 and variance σ2, ε~N(0, σ2). Note: constant, time independent variance is called homoscedasticity.

ε~N(0, σ2) assumption is essential for:

- Hypothesis ------- of regression coefficients.

- Interval estimation around point prediction.

- Model validity: “are residuals Normally distributed?” ➢Normal residuals: model cor‐

rectly specified ➢Nonnormal residuals: nonlinearity present, interactions between independent variables, outliers

<small>Source Page 54 of 64</small>

### How Residuals Should Look

Random scatter with no visible pattern.

Constant variance of the residuals
<small>Source Page 55 of 64</small>

### Regression Error Analysis

We should not be making systematic errors.

Systematic error: means errors exhibit some consistent, non-random pattern, rather than being distributed randomly around the regression line.

Systematic error presence means regression model is not fully capturing the relationship between Y and x’s.

Any systematic component should be in the model rather than in the error.

By including the systematic error in the model, the model should improve.

outcomei= modeli+ errori

yi

xi Systematic part

εi Unsystematic part

Possible Reasons For Systematic Errors:

- Nonlinearity: systematic pattern in the residuals

- Heteroscedasticity: variance of errors changes across levels of independent variable

- Autocorrelation: errors in one period are correlated

with errors in another period

<small>Source Page 56 of 64</small>

### Systematic Errors: Nonlinear Relationship

True underlying relationship is nonlinear, however a line was fitted

A systematic patter can by seen due to errors above and below the fitted line

Remedy: nonlinear transformation (next session)

<small>Source Page 57 of 64</small>

### Systematic Errors: Heteroscedasticity

Variance of residuals is not constant.

Non-consistent standard deviation of the variable over time.

Remedy: standard error clustering
<small>Source Page 58 of 64</small>

### Systematic Errors: Autocorrelation

Serial correlation / autocorrelation: means errors are correlated with each other over time. It violates the assumption of independence of errors.

The residual plot shows a clear linear pattern.

You may also see a wave-like or cyclical pattern.

Remedy: introduce lags.

Example:

෢ Salest= ොa+ ෢bAdvertisingt+ ƸcAdvertisingt−1

<small>Source Page 59 of 64</small>

### Outliers and Influential Observations

. . .

.

Regression line without outlier

y

. . . . . .. . .

.

Regression line with outlier

.

.

- Outlier

x

Outlier: observation that is extreme with respect to other y observations.

If an observation has an unusually large residual error, it is often an indication that the data point is wrong in some way.

Point with a large value of xi *

y

Regression line when all data are included

.. . . ... .. . ... . .

No relationship in this cluster
x

Influential: observation that is extreme w.r.t. other x observations.

Some observations might have an undue influence on the model.

<small>Source Page 60 of 64</small>

### Examine residuals using Autoplot

If something goes wrong in our model, it will show up in the residuals. Therefore, always plot the residuals.

Use the ggfortify library to plot 3 essential plots for residuals.

```r
library(ggfortify) model1 %>% autoplot(which = 1:3) + theme_bw()
```

The Three Plots Show:

- Residuals vs Fitted Values (i.e. ε vs ෢Y, the plot on pp. 51).

Want to see: a horizontal straight line.

- Normal Q-Q Plot (i.e. quantile quantile plot of theoretical normal distribution vs the

quantiles of the residuals) Want to see: a 45-degree line.

- Spread-Location (i.e. sqrt of absolute values of standardized residuals) Want to see: a

horizontal straight line.

<small>Source Page 61 of 64</small>

### Q-Q Plot Examples:

Normal Data:

Non-Normal Data:

Non-Normal Data:

<small>Source Page 62 of 64</small>

### Residuals Autoplot: Crime Example

Plot 1: Are the residuals random with mean 0, or does there seem to be a consistent pattern in the residuals?

Plot 2: Do residuals follow a Normal distribution? Is the Q-Q (Quantile-Quantile) Plot nearly a 45-degree line?
Plot 3: Do residuals have constant variance? Is blue line approx. horizontal / does the spread around the line not vary much?

<small>Source Page 63 of 64</small>

### Residuals Autoplot: Car Example

Distribution of residuals compared to Normal Distribution

Plot 1: Residuals show nonlinear pattern i.e. residuals are not random (some systematic component was left in the residuals rather than in the model).

Plot 2: Normality check shows that most points are on the 45degree line, therefore supporting the condition that residuals are Normally distributed.

Plot 3: Residual variance is not quite constant.

<small>Source Page 64 of 64</small>

### Session Summary

We covered:

Correlation Simple Linear Regression

Readings:

Modern Dives chapter 5

Optional/ Extra practice: workshop4.Rmd Coding questions ---- practice.

Workshop Questions:

Look at the workshop questions in advance.

Attend optional workshop to go over the solutions.

Group Assignment 1:

Start looking at it in Canvas → Files → Group Assignment 1


[↑ Back to the source list](#source-documents)

---

<a name="source-3"></a>

## session4.Rmd

<small>File type: RMD · Reader pages 274–278 · [View source PDF](PDF%20Slides.pdf#page=274)</small>

```r
knitr::opts_chunk$set(echo = TRUE)
library(tidyverse)
library(tidyquant)
library(dplyr)
library(ggplot2)
library(MASS)  # For generating multivariate normal data
library(gridExtra)  # For arranging multiple plots
library(mosaic)
library(GGally)
library(ggfortify) # residual plots
```

### Correlation

Find correlation between variables X and Y:

```r
# Correlation Class Exercise
X <- c( 12, 33,  4,  -7.5, 5.9)
Y <- c(-10, 27, -6.6, 5.4, 8  )
var1 <- tibble(X, Y)
cor1 <- cor(var1)
print(cor1)
```

Find correlation between variables X, Y, Z:

```r
# Correlation Class Exercise
X <- c( 12, 33,  4,  -7.5, 5.9)
Y <- c(-10, 27, -6.6, 5.4, 8  )
Z <- c(1, 3.3,  -14,  7.5, 21)
var2 <- tibble(X, Y, Z)
cor2 <- cor(var2)
print(cor2)
```

Examine correlation between X and Y when they relate as $y=x^2$

```r
X <- c(-12, 12, -15, 15, 4, 0, -4, 7.5, -7.5, 5.9, -5.9)
Y <- X^2
plot(X,Y)
# Obtain the correlation between X and Y
cor3 <- cor(X,Y)
print(cor3)
# Do you think there is no relationship between x and y?
```
### Beer House Crime Investigation

```r
crime <- read_csv('beerhall.csv')
```

### Exploratory Data Analysis

Let's examine a new function skim() of the skimr package. skimr is designed to provide summary statistics about variables in tibbles. skim() works with (grouped) tibbles. It presents results for every column; the statistics it provides depend on the class of the variable. https://cran.r-project.org/web/packages/skimr/vignettes/skimr.htmlhttps://cran.r-project.org/web/packages/skimr/ vignettes/skimr.html

```r
crime %>% skimr::skim()
```

Alternatively use favstats()

```r
favstats(~ criminals, data=crime)
```

Boxplot of criminals by region sorted from greatest to smallest number of criminals.

```r
ggplot(crime, aes(x = reorder(region_name, -criminals), y = criminals)) +
labs(y = "criminals (per 100k population)", x = "") +
geom_boxplot() +
theme(axis.text.x = element_text(angle = 45))
```

Barplot using ordered data. Refer to the following link on Palettes: https://gka.github.io/palettes Let's look at total number of criminals per region (i.e. region_name variable).

The follow code reproduces the barplot figure on the slide.

```r
my_Palette = c('#00429d', '#2e59a8', '#4771b2', '#5d8abd', '#73a2c6', '#8abccf', '#a5d5d8',
'#c5eddf', '#ffffe0')
crime %>%
group_by(region_name) %>%
summarise(total_crime = sum(criminals)) %>%
ggplot(aes(x = reorder(region_name, total_crime), y = total_crime, fill = region_name)) +
geom_col() +
coord_flip() +
theme_bw() +
theme(legend.position = "none") +
labs(title = 'Total Crime in England, 1856',
y = "criminals (per 100k population)",
x = "") +
scale_fill_manual(values = my_Palette) # use my specified palette to color the bars
```

Get a matrix of density plots, scatterplots + correlations
```r
crime %>%
dplyr::select(public_houses, criminals) %>%
ggpairs()
```

### Line of Best Fit

```r
ggplot(crime, aes(x = public_houses, y = criminals)) +
geom_point() +
geom_smooth(method = lm, se = FALSE, color = "red") + # where se is confidence intervals
around the prediction, by default se=True
theme_bw() +
#geom_hline(yintercept = 152.9, size = 1.1, colour = "red") + # mean of criminals col
labs(title= "Relationship between Crime and Pubs, England 1856",
x = "Pubs per 100K population",
y = "Criminals per 100K population") +
NULL
```

### Estiamtes of Residual Errors

We can visualize residuals on a Residual Error Plot. It is nothing else but the errors themselves, plotted using the regression line plot, which has been turned around to make it visually more accessible.

```r
# ---------- Model 1 (Simple Linear Regression) -----------
model1 <- lm(criminals ~ public_houses, data = crime) # single x
crime$predicted <- predict(model1)  # Y_hat values that will sit on the regression line
crime$residuals <- residuals(model1) # error between Ys and Y_hats
# Plot 1
ggplot(crime, aes(x = public_houses, y = criminals)) +
geom_smooth(method = "lm", se = FALSE, color = "blue") +
geom_segment(aes(xend = public_houses, yend = predicted), colour = "red") +
geom_point() +
geom_point(aes(y = predicted), shape = 1) +
labs(title = "Relationship between Crime and Pubs, England 1856",
x = "Pubs per 100K population",
y = "Criminals per 100K population")
# Plot 2
crime$predicted_zero <- c(0)
ggplot(crime, aes(x = public_houses, y = residuals)) +
geom_hline(yintercept = 0, colour = "blue") +
geom_point(aes(y = predicted_zero), shape = 1) +
geom_segment(aes(xend = public_houses, yend = predicted_zero), colour = "red") +
geom_point() +
labs(title = "Relationship between Crime and Pubs, England 1856",
x = "Pubs per 100K population",
y = "Distance from line")
```

Observe model output:

```r
summary(model1)
```
### What drives used Prius prices?

A recent article in the UK claimed that [your Uber cab is most likely to be a Toyota Prius](https:// www.motoringresearch.com/car-news/your-uber-cab-is-most-likely-to-be-a-toyota-prius-and-whythats-a-good-thing/).

Let's carry out analyses of the relationships between price and mileage.

### Loading the data set, summary statistics

```r
prius <- read_csv("toyota_prius_jun18.csv")
glimpse(prius)
```

The prius tibble contains prices of used Toyota Prius in the UK that were gathered in June 2018. `town`, `region` and `colour` are categorical variables (character data type <chr>), whereas `miles` and `price` are numerical variables (numeric data type <dbl>). `year` and `engine` are treated as numerical variables, but in reality are categorical variables.

Turn 'engine' into categorical variable (factor), and create a new column for the car age:

```r
prius <- prius %>%
mutate(engine = factor(engine), # turn it to a factor
car_age = 2018 - year)
favstats(price ~ year,  data=prius)
favstats(price ~ engine, data=prius)
favstats(price ~ colour, data=prius)
```

First we will obtain the scatter plot to see the potential relationship between price and miles. Then we will add the line of the best fit (visually this is the regression line, but you will create the actual regression model yourself below).

```r
# plot scatter plot
ggplot(prius, aes(x = miles, y = price)) +
geom_point() +
theme_bw()
# examine correlation between
prius %>%
dplyr::select(price, miles) %>%
ggpairs()
# plot scatter plot and add the best straight line
ggplot(prius, aes(x = miles, y = price)) +
geom_point() +
theme_bw() +
geom_smooth(method = "lm", se = FALSE)
```

### Simple Regression: Relationship between price and miles

```r
# run linear regression to create a variable called car_model1, using lm() model
car_model1 <- lm(price ~ miles, data = prius)
```
```r
# get regression summary table, using summary()
summary(car_model1)
```

### Residuals Plots

Residuals from crime example.

```r
model1 %>%
autoplot(which = 1:3) +
theme_bw()
```

Residuals from car example.

```r
car_model1 <- lm(price ~ miles, data = prius)
car_model1 %>%
autoplot(which = 1:3) +
theme_bw()
```


[↑ Back to the source list](#source-documents)

---

<a name="source-4"></a>

## beerhall.csv

<small>File type: CSV · Reader pages 279–280 · [View source PDF](PDF%20Slides.pdf#page=279)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

> Data preview (up to six records and twelve columns); the full CSV remains in the original files.

Table displayed as labelled records for readability (6 rows, 7 columns).

Middlesex

region_name South Eastern

region_code 1

criminals 200

public_houses 541

school_attendance 560

worship_attendance 434

Surrey

region_name South Eastern

region_code 1

criminals 160

public_houses 504

school_attendance 630

worship_attendance 482

Kent

region_name South Eastern

region_code 1

criminals 160

public_houses 552

school_attendance 790

worship_attendance 680

Sussex

region_name South Eastern

region_code 1

criminals 147

public_houses 295

school_attendance 820

worship_attendance 678
Hants

region_name South Eastern

region_code 1

criminals 178

public_houses 409

school_attendance 990

worship_attendance 798

Berks

region_name South Eastern

region_code 1

criminals 205

public_houses 568

school_attendance 930

worship_attendance 698

</details>


[↑ Back to the source list](#source-documents)

---

<a name="source-5"></a>

## toyota_prius_jun18.csv

<small>File type: CSV · Reader pages 281–282 · [View source PDF](PDF%20Slides.pdf#page=281)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

> Data preview (up to six records and twelve columns); the full CSV remains in the original files.

Table displayed as labelled records for readability (6 rows, 7 columns).

2017

engine 1798

miles 3200

price 20995

town Hornchurch

region London

colour white

2015

engine 1798

miles 50000

price 12950

town Wembley Park

region London

colour white

2009

engine 1497

miles 130000

price 3495

town Romford

region London

colour silver

2013

engine 1798

miles 66000

price 10400

town Seven Sisters

region London

colour white
2010

engine 1798

miles 160164

price 5990

town Shepherd's Bush

region London

colour white

2007

engine 1497

miles 175000

price 1700

town Southwark

region London

colour white

</details>


[↑ Back to the source list](#source-documents)

---

