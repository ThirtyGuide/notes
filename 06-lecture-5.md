# Lecture 5

**Multiple regression and extensions**

[← All chapters](README.md) · [Original PDF](PDF%20Slides.pdf#page=283)

## Overview

- Nonlinear transformations, additional predictors and interaction terms.
- Dummy variables, multicollinearity, distributed lags and model selection.
- Worked applications involving car prices, salaries and other business cases.

## Source documents

1. [session5_slides_pre_class.pdf](#source-1) — PDF, reader page 284
2. [session5_slides_post_class.pdf](#source-2) — PDF, reader page 304
3. [session5.html](#source-3) — HTML, reader page 325
4. [session5.Rmd](#source-4) — RMD, reader page 367
5. [beerhall.csv](#source-5) — CSV, reader page 378
6. [bonds.csv](#source-6) — CSV, reader page 380
7. [toyota_prius_jun18.csv](#source-7) — CSV, reader page 381
8. [winner.csv](#source-8) — CSV, reader page 383

---

<a name="source-1"></a>

## session5_slides_pre_class.pdf

<small>File type: PDF · Reader pages 284–303 · [View source PDF](PDF%20Slides.pdf#page=284)</small>

<small>Source Page 1 of 56</small>

### Lecture 5

Dr Helen Wang |

<small>Source Page 2 of 56</small>

### Weeks 1-6 Outline

Week 01 | Exploratory Data Analysis

Week 02 | Statistics Foundation

Week 03 | Hypothesis -------

Week 04 | Regression, Part I

Week 05 | Regression, Part II

<small>Source Page 3 of 56</small>

### Recap Simple Linear Regression: Crime ~ Pubs, England 1856

<small>Source Page 4 of 56</small>

### Recap Systematic Errors: Nonlinear Relationship

True underlying relationship is nonlinear, however a line was fitted

A systematic patter can by seen due to errors above and below the fitted line

Remedy: nonlinear transformation (next session)

<small>Source Page 5 of 56</small>

01 | Nonlinear Transformations 02 | Multiple Linear Regression 03 | Variations of Multiple Linear Regression 04 | Dummy Variables 05 | Multiple Linear Regression Examples
Regression Part II

<small>Source Page 6 of 56</small>

### Nonlinear Transformations

Suppose there is a nonlinear relationship, y= 5 + 3

Plot of y vs x Nonlinear relationship

y

x

x. Let’s plot y vs. x, and y vs. 1/x.

Plot of y vs 1

x Linear relationship

y

1/x

<small>Source Page 7 of 56</small>

### Nonlinear Transformations

Suppose there is a nonlinear relationship, y= 5 + 3

Plot of y vs x Nonlinear relationship

y

x A line is a poor fit to a y= 5 + 3 1

x relationship, since the true relationship is non-linear.

x. Let’s plot y vs. x, and y vs. 1/x.

Plot of y vs 1

x Linear relationship

y

1/x

If you transform your x variable by creating a new variable z, with the suitable transformation (in this case we can visually see that the nonlinear relationship is a 1/x type), then you will get a much better fit using a line.
<small>Source Page 8 of 56</small>

### Common Nonlinear Transformations

Many nonlinear relationships can be transformed into linear ones, making it possible to use linear regression.

1/x Relationship

Example: sales volume (Y) is inversely related to price (x)

<small>Source Page 9 of 56</small>

### Common Nonlinear Transformations

Many nonlinear relationships can be transformed into linear ones, making it possible to use linear regression.

1/x Relationship

x

Example: sales volume (Y) is inversely related to price (x) , i.e. y=

<small>Source Page 10 of 56</small>

### Common Nonlinear Transformations

x Relationship

Example: stock volatility (Y) increases with a decreasing rate of volume (x).

<small>Source Page 11 of 56</small>

### Common Nonlinear Transformations

x Relationship

Example: stock volatility (Y) increases with a decreasing rate of volume (x), i.e. y = x

<small>Source Page 12 of 56</small>

### Common Nonlinear Transformations

x2 Relationship
Example: return from an investment (Y), increases quadratically (exponentially) with an increasing investment (x). This could happen due to aggressive reinvestment and compounding returns.

<small>Source Page 13 of 56</small>

### Common Nonlinear Transformations

x2 Relationship

Example: return from an investment (Y), increases quadratically (exponentially) with an increasing investment (x). This could happen due to aggressive reinvestment and compounding returns.

<small>Source Page 14 of 56</small>

### Common Nonlinear Transformations

Exponential xb Relationship

y= axb ln y= ln axb ln y= ln a+ ln xb ln y= ln a+ b∗ln(x)

Exponential ebx Relationship

y= aebx ln y= ln aebx ln y= ln a+ ln ebx ln y= ln a+ bx

<small>Source Page 15 of 56</small>

01 | Nonlinear Transformations 02 | Multiple Linear Regression 03 | Variations of Multiple Linear Regression 04 | Dummy Variables 05 | Multiple Linear Regression Examples

Regression Part II

<small>Source Page 16 of 56</small>

### Multiple Linear Regression

Multiple Linear Regression: generalize simple linear regression to deal with a set of independent variables that helps to predict Y.

- build more powerful model by taking other relevant

inputs into account

- produce better forecasts with smaller confidence
```r
intervals (smaller errors)
```

- examine which independent variables have a significant impact on Y (coefficient

hypothesis -------)

Choose A Model Which

- Has all coefficients as significant (except the intercept, which we always keep)

- Has the highest adjusted R2

- Has the smallest residual standard error

<small>Source Page 17 of 56</small>

### Multiple vs. Simple Linear Regression

Multiple Regression Simple Regression

One dependent variable (Yt) One dependent variable (Yt) One independent variable used to build the model xt The intercept β0 is the “baseline” scenario: what happens to Yt in the case where all xt’s are 0

True Model: Yt= β0 + β1x1,t+, … , +βmxm,t+ εt Fitted Model: ෢Yt= መβ0 + መβ1x1,t+, … , + መβmxm,t

m independent variables used to build the model x1,t,…, xm,t

The slope βi provides the value for the change in Yt per unit increase in xi,t while other independent variables are kept fixed

True Model: Yt= β0 + β1xt+ εt Fitted Model: ෢Yt= መβ0 + መβ1xt

The intercept β0 is a “baseline” scenario: what happens to Yt in the case where xt is

The slope β1 provides the value for the change in Yt per unit increase in xt

<small>Source Page 18 of 56</small>

### Education Religion

Beer Houses Crime

Example: Crime

+
<small>Source Page 19 of 56</small>

### Reminder: Model 1 (Simple Regression)

```r
True (Assumed) Model: criminals= β0 + β1pubs+ εt
```

Model Evaluation

Coefficient β1 is significant, since p=0.0026<0.05.

This means that pubs has predictive power for criminals.

Fitted model:

෢ criminalsi= 109.34 + 0.116 ∗pubsi

R squared: 0.214, which means that approx. 21% of the total variance in crime is explained by model 1.

<small>Source Page 20 of 56</small>

### Residual Analysis Model 1

Q: Evaluate each plot?

<small>Source Page 21 of 56</small>

### Multiple Regression: Model 2

```r
True (Assumed) Model: criminals= β0 + β1pubs+ β2edu+ β3religion+ εt
model2 <- lm(criminal ~ public_houses + school_attendance + worship_attendance)
```

Q: Evaluate this model’s coefficients?

<small>Source Page 22 of 56</small>

### Multiple Regression: Model 2

```r
True (Assumed) Model: criminals= β0 + β1pubs+ β2edu+ β3religion+ εt
```

Model Overview:
```r
model2 <- lm(criminal ~ public_houses + school_attendance + worship_attendance)
```

- The coefficient of worship_attendance is not significant (p-value 0.348 not less than

0.05).

- This means that the current model is invalid.

- Rule: remove insignificant variables 1-by-1 starting with least significant one and re-

estimate the model.

Let’s delete worship attendance from the regression equation and re-fit.

<small>Source Page 23 of 56</small>

### Multiple Regression: Model 3

```r
True (Assumed) Model: criminals= β0 + β1pubs+ β2edu+ εt
```

Model Evaluation

```r
model3 <- lm(criminal ~ public_houses + school_attendance)
```

Coefficient β1 is significant at α≈0% Coefficient β2 is significant at α= 5%.

All coefficients are significant therefore this model is valid. Both pubs and school have predictive power for criminals.

Since the model is valid, we can write down the equation of the fitted model:

෢ criminalsi= 178.8 + 0.126 ∗pubsi−0.0765 ∗scℎooli

R2adj: 0.26, which means that approx. 26% of the total variance in crime is explained model 3.

<small>Source Page 24 of 56</small>

### Multiple Regression: Model 3

Fitted Model: ෢ criminalsi= መβ0 + መβ1 ∗pubsi + መβ2 ∗scℎooli

This is a 3D example (One Y variable and two X variables). In this case:

- The regression model fits a plane (i.e. a flat 2D surface) to the data points

- It is a plane of best fit that minimizes the SSE

- Red points are the original Y data points

- The fitted values, ෢Yi, of dependent variable are located on

Scℎool
the plane.

For higher dimensional cases we term it a hyperplane.

Pubs

<small>Source Page 25 of 56</small>

### Residual Analysis Model 3 vs Model 1

Model 3 Model 1

<small>Source Page 26 of 56</small>

### Selecting The Best Model

Comparing Valid Models You can compare valid models to chose the best one using huxreg() table.

The table allows for an easier comparison.

```r
library(huxtable) huxtable::huxreg(model1, model3, number_format = "%.3f", bold_signif =
0.05, statistics = c('adj.r.squared', 'sigma'))
```

Comma separated models.

Number of decimal places.

Significance level α= 5%.

Display adjusted R2, and RSE.

<small>Source Page 27 of 56</small>

### Selecting The Best Model

Comparing model 1 and model 3.

The table displays model numbering in the order in which models were passed into the huxreg() function.

Coefficient’s estimated value and stars as significance level.

(Coefficient’s standard errors)

Model3 has a higher Adj R2 and lower residual standard error.

Therefore, we pick it over model1.
<small>Source Page 28 of 56</small>

01 | Nonlinear Transformations 02 | Multiple Linear Regression 03 | Variations of Multiple Linear Regression 04 | Dummy Variables 05 | Multiple Linear Regression Examples

Regression Part II

<small>Source Page 29 of 56</small>

### Interaction Terms

Example:

Does a drug have more effect on women (0) than men (1) in cholesterol prediction?

Cℎolesterol= β0 + β1drug+ β2gender+ β3drug∗gender+ e

Drug

Cℎolesterol 0 (No drug) 1 (Use drug)

```r
0 (Women) β0
```

Gender

```r
1 (Men)
```

Questions

What is the baseline difference of the average cholesterol level between men and women?

What is the effect of the drug on women?

What is the effect of the drug on men?

What’s the meaning of β3?

<small>Source Page 30 of 56</small>

### Interaction Terms

Interaction Term an independent variable in a regression model that is a product of two independent variables.

Sometimes the partial effect of the dependent variable with respect to independent variable can depend on magnitude of yet another independent variable.

Forming An Interaction Term

Does the effect x1 on Y depend on the level of x2?
Y= β0 + β1x1 + β2x2 + β3x1 ∗x2 + e

Example:

Does a drug have more effect on women (0) than men (1) in cholesterol prediction?

Cℎolesterol = β0 + β1drug+ β2gender+ β3drug∗gender+ e

If መβ3 < 0 and significant, it means that the drug lowers cholesterol by more units in men than in women.

Hierarchy Principle:

If you include the interaction term β3x1 ∗x2, you should also include the main effects of the involved variables, i.e. include β1x1 and β2x2 in the fitted equation as well, even if they are not significant. This ensures the model is hierarchically well-specified.

<small>Source Page 31 of 56</small>

### Interaction Terms: Example Prius Car Price

Example: Prius Car Price

Qn: “Does car price drop more for a particular engine for milage?

price = β0 + β1miles+ β2engine+ β3miles∗engine+ e

Interaction term lets us examine whether:

- The effect of miles on price, depends not only on the miles itself, but also on the type

of engine the car has.

- The mileage impact on price might be different for a small-engine car versus a large-

engine car.

- If መβ3 < 0 this means, there is a negative impact on car price when both high milage

and large engine size are present.

<small>Source Page 32 of 56</small>

### Interaction Terms Example: Prius Car Price

So far we have run a model of miles being predictor of Prius car price:

Can we improve the model?
<small>Source Page 33 of 56</small>

### Multicollinearity

Multicollinearity appears when independent variables used inside the regression equation are highly correlated.

Effects:

- Not much added predictive power.

- Additional variables add little information.

- Magnitude/signs of regression coefficients are different from expected.

- May cause two or more variables to become insignificant but significance may be high

if one variable is dropped.

- Parameter estimates are unreliable.

Remedial Action:

- Remove one of the correlated variables.

- Check for correlations between independent variables in advance of running the re‐

gression

---- in RStudio:

Variance Inflation Factor (VIF) assess multicollinearity in regression models, providing a value for each independent variable.

```r
library(car) car::vif(model)
```

- VIF > 10: high multicollinearity, attend to it - VIF 5 -10: moderate multicollinearity, keep an

eye - VIF < 5: no multicollinearity, acceptable

<small>Source Page 34 of 56</small>

### Distributed Lag Model

Distributed lag model is a model for time series data in which a regression equation is used to predict current values of a dependent variable based on both the current values of an independent variable and/or its lagged (past period) values.

```r
True (Assumed) Model:
```

Yt= β0 + β1xt+ β2xt−1 + β3xt−2 + ⋯+ εt

Assume a finite number of lags (e.g. 2-5) and run the multiple regression model as usual.

Remove insignificant lags one by one starting with least significant first and re-run the model.

Data Preparation:
Create an extra column for each lag, as:

t Yt xt

t Yt xt xt−1

NA

13.3 3.4

13.3 3.4

10.2 5.1

10.2 5.1 3.4

1.3

1.3 5.1

After creating the required columns, remove any rows with NA.

To create lags with dplyr, read here.

<small>Source Page 35 of 56</small>

### Event -----

Event ----- is a model applied when you are interested in the dynamic treatment effect, i.e., how does an outcome change several periods before and after an event?

Analysis setup: two (groups of) observations i are both observed for multiple periods before and after time t, when group A is treated (experienced an event), while group B is not treated.

```r
True (Assumed) Model:
```

Yit= β0 + βt−2Ιt−2Ti+ βtΙtTi+ βt+1Ιt+1Ti… + εit

The t-1 period is omitted as the reference period.

Data Preparation:

Create extra columns for each lead and lag, as (suppose the event took place at time period 3):

i t Yt Ti

i t Yt Ti Ιt−2 Ιt Ιt+1

11.3

11.3

10.5

10.5
10.8

10.8

18.7

18.7

24.5

24.5

27.8

27.8

Examples:

How does the target firm stock price respond to M&A announcements?

How does the stock price of Tesla change before vs. after the US president election?

<small>Source Page 36 of 56</small>

### Event -----: From Red Tape to RegTech (Cui, Wang, Wu 2025)

Q: How does regional export volume change before and after the entry of OneTouch?

No OneTouch Receive order

Submit rebate filing to local tax office

OneTouch

Submit rebate filing through OneTouch

Receive order

Long waiting time Incorrect filing Back and forth Limited cashflow

Receive rebate in 2-3 months

Lower compliance cost Micro financing

Credit rebate in 3 days

Reinvest in production

Receive more orders

……
<small>Source Page 37 of 56</small>

### Rollout of OneTouch Branches

<small>Source Page 38 of 56</small>

### Rollout of OneTouch Branches

<small>Source Page 39 of 56</small>

### Rollout of OneTouch Branches

<small>Source Page 40 of 56</small>

### Event -----: From Red Tape to RegTech (Cui, Wang, Wu 2025)

The differences of export volume between treated and untreated cities were not significantly different from 0 BEFORE the entry of OneTouch.

However, such difference became significant and increasingly large AFTER the entry of OneTouch, meaning that OneTouch can facilitate export.

<small>Source Page 41 of 56</small>

01 | Nonlinear Transformations 02 | Multiple Linear Regression 03 | Variations of Multiple Linear Regression 04 | Dummy Variables 05 | Multiple Linear Regression Examples

Regression Part II

<small>Source Page 42 of 56</small>

### Qualitative Variables

Dummy Variable: a variable that takes on a value of 0 or 1. Examples:

Gender:

- Create a column ‘gender’

- gender=0 if male, gender=1 if female

```r
Seasons (halves):
```
- Create a column ‘season’

- season=0 for Q1 and Q2, season=1 if

Q3 and Q4

```r
Seasons (quarters):
```

- Create 3 columns:

- q1=1 if it is Q1, 0 otherwise

- q2=1 if it is Q2 , 0 otherwise

- q3=1 if it is Q3 , 0 otherwise

Example: Bond Prices and National Income

Create a dummy variable W encoded as:

- 1 war year

- 0 no war year, treated as a reference group (usually the majority of the data in the

sample)

B: Bond purchases Y: GNP (Gross National Product) W: Dummy variable of war year

<small>Source Page 43 of 56</small>

### Example: Bond Prices and National Income

<small>Source Page 44 of 56</small>

### Regression with Dummy Variable: War

Dummy variable can be used in regression analysis just like any other quantitative variable. We have 2 categories: war / no war and a single dummy variable to represent it.

Fitted Model:

෢ bond= መβ0 + መβ1GNP+ መβ2WAR = 1.02 + 0.72 ∗GNP+ 2 ∗War

Interpretation:

Intercept is the bond price for the reference group

Positive β2 coefficient (+2.0 in this case) means that bond price was higher for the dummy variable (war) than the reference group (no war).

Negative β2 coefficient would have meant that bond price would have been lower.
<small>Source Page 45 of 56</small>

### Conceptual Visualization

෢ bond= 1.02 + 0.72 ∗GNP+ 2.0 ∗1

෢ bond= 1.02 + 0.72 ∗GNP+ 0

<small>Source Page 46 of 56</small>

### Regression with Dummy Variable: Season

Seasonality is usually a strong predictor of product demand (and price).

Demand

Price

Season Dummy

(Y)

(x1)

(x2)

1.5 1.6 1.3 1.4

Winter Summer Winter Summer

Q: Write down regression equation to model the demand using available information?

Demand

Summer: x2 = 1

Winter: x2 = 0

1.1 1.2 1.3 1.4 1.5 1.6 1.7 1.8

Price

<small>Source Page 47 of 56</small>

### Effect on Intercept

The fitted regression model equation would look as:

෢ demandt= ෢ β0 + ෢ β1pricet+ ෢ β2dummyt

Think of this regression as a two-case scenario:

Summer: ෢ demandt= ෢ β0 + ෢ β1pricet+ ෢ β21 = (෢ β0 + ෢ β2) + ෢ β1pricet
Winter: ෢ demandt= ෢ β0 + ෢ β1pricet+ ෢ β20 = ෢ β0 + ෢ β1pricet

Demand

Summer: x2 = 1

Winter: x2 = 0

1.1 1.2 1.3 1.4 1.5 1.6 1.7 1.8

Price

<small>Source Page 48 of 56</small>

### Regression with k-levels

When a categorical variable has k categories (we call them ‘levels), we include only k-1 dummy variables in the regression model.

The category that is left out is usually the one with the most frequent observations and it acts as a reference.

Example:

- 3 movie categories: adventure, romance, drama.

- If drama has the most obs, leave it out as a reference and create 2 dummies for

adventure and romance.

salest= β0 + β1promot+ β2adventuret+ β3romancet+ εt

Dummies

k-th category is redundant information:

Obs promo adventure romance drama

12.5

10.2

14.5

… … … … …

Obs1: if its not adventure or romance then those 2 pieces of information tell us it must be drama.

Obs2: if it is not adventure but it is romance, then automatically we know it is not drama, etc.
<small>Source Page 49 of 56</small>

### Example: k=3 levels

Fitted Model:

෢Yt= ෢ β0 + ෢ β1promot+ ෢ β2adventuret+ ෢ β3romancet

Model’s intercept ෢ β0 is the ticket sales for the reference group (drama).

If ෢ β2 > 0 then ticket sales were higher for the dummy variable adventure, than the reference group drama.

adventure=0 romance=1

sales

adventure=1 romance=0

෢ β0 + ෢ β3

adventure=0 romance=0

෢ β0 + ෢ β2

෢ β0

Promotion

<small>Source Page 50 of 56</small>

### Example: The Impact of Seat Location on UM Ross MBA -------

### Performance (Orhun, Sivadasan, Li, Wang 2025)

From Fall 2014 till now, Ross has been randomly assigning seats to MBA --------.

Research Question: Do -------- randomly assigned to row 1,2,3 and 4 perform differently?

Q: How would you design your regression model?

<small>Source Page 51 of 56</small>

### Example: The Impact of Seat Location on MBA ------- Performance

### (Orhun, Sivadasan, Li, Wang 2025)

Ytc= β0 + β1Rtc+ γXt+ μc+ εtc

Row 4 is omitted (so we set Row 4 as the reference) Interpretation: Holding all the other explanatory variables constant, -------- in row 1 receive 0.0522 SD higher score than those in row 4.

Pairwise comparison of coefficients (---- for difference)
<small>Source Page 52 of 56</small>

### Regression Check List

Set up the model, choose the data - Which variables to include - Generate dummy variables where appropriate - What do expect (from practice, theory,

anecdotal evidence)?

Check scatter plots and correlations - Identify any obvious nonlinearities (transform variables)

- Beware of high correlations between explanatory factors (multicollinearility)

Carry out the regression - Drop insignificant variables (one-by-one starting with least significant first) and re-model - Ensure the model is valid (i.e. all coefficients are significant; always keep the intercept) - Check residual plots with autoplot() function

Choose the best model - Compare models with huxreg() function - Highest Adjusted R2, and lowest standard error of

residuals - Compare to initial expectations

Use the model to create forecasts

<small>Source Page 53 of 56</small>

01 | Nonlinear Transformations 02 | Multiple Linear Regression 03 | Variations of Multiple Linear Regression 04 | Dummy Variables 05 | Multiple Linear Regression Examples

Regression Part II
<small>Source Page 54 of 56</small>

### Case: Winner Plc

Question: ”Is the company guilty of gender discrimination?”

Descriptive Statistics

Data: random sample of 50 employees (24 male and 26 female).

Analysis:

- Descriptive Stats

- Histograms

- Confidence intervals

- Hypothesis -------

- Regression analysis (simple; multiple;

transformations)

<small>Source Page 55 of 56</small>

### Session Summary

We covered:

Multiple Linear Regression

Workshop Questions:

Look at the workshop questions in advance.

Attend optional workshop to go over the solutions.

Readings:

Modern Dives chapter 6,10

Congratulations on completing the

first part of CA09!

<small>Source Page 56 of 56</small>

### Please complete the 1-minute course survey.


[↑ Back to the source list](#source-documents)

---

<a name="source-2"></a>

## session5_slides_post_class.pdf

<small>File type: PDF · Reader pages 304–324 · [View source PDF](PDF%20Slides.pdf#page=304)</small>

<small>Source Page 1 of 60</small>

### Lecture 5

Dr Helen Wang |

<small>Source Page 2 of 60</small>

### Weeks 1-6 Outline

Week 01 | Exploratory Data Analysis

Week 02 | Statistics Foundation

Week 03 | Hypothesis -------

Week 04 | Regression, Part I

Week 05 | Regression, Part II

<small>Source Page 3 of 60</small>

### Recap Simple Linear Regression: Crime ~ Pubs, England 1856

<small>Source Page 4 of 60</small>

### Recap Systematic Errors: Nonlinear Relationship

True underlying relationship is nonlinear, however a line was fitted

A systematic patter can by seen due to errors above and below the fitted line

Remedy: nonlinear transformation (next session)

<small>Source Page 5 of 60</small>

01 | Nonlinear Transformations 02 | Multiple Linear Regression 03 | Variations of Multiple Linear Regression 04 | Dummy Variables 05 | Multiple Linear Regression Examples
Regression Part II

<small>Source Page 6 of 60</small>

### Nonlinear Transformations

Suppose there is a nonlinear relationship, y= 5 + 3

Plot of y vs x Nonlinear relationship

y

x

x. Let’s plot y vs. x, and y vs. 1/x.

Plot of y vs 1

x Linear relationship

y

1/x

<small>Source Page 7 of 60</small>

### Nonlinear Transformations

Suppose there is a nonlinear relationship, y= 5 + 3

Plot of y vs x Nonlinear relationship

y

x A line is a poor fit to a y= 5 + 3 1

x relationship, since the true relationship is non-linear.

x. Let’s plot y vs. x, and y vs. 1/x.

Plot of y vs 1

x Linear relationship

y

1/x

If you transform your x variable by creating a new variable z, with the suitable transformation (in this case we can visually see that the nonlinear relationship is a 1/x type), then you will get a much better fit using a line.
<small>Source Page 8 of 60</small>

### Common Nonlinear Transformations

Many nonlinear relationships can be transformed into linear ones, making it possible to use linear regression.

1/x Relationship

Example: sales volume (Y) is inversely related to price (x)

<small>Source Page 9 of 60</small>

### Common Nonlinear Transformations

Many nonlinear relationships can be transformed into linear ones, making it possible to use linear regression.

1/x Relationship

x

Example: sales volume (Y) is inversely related to price (x) , i.e. y=

<small>Source Page 10 of 60</small>

### Common Nonlinear Transformations

x Relationship

Example: stock volatility (Y) increases with a decreasing rate of volume (x).

<small>Source Page 11 of 60</small>

### Common Nonlinear Transformations

x Relationship

Example: stock volatility (Y) increases with a decreasing rate of volume (x), i.e. y = x

<small>Source Page 12 of 60</small>

### Common Nonlinear Transformations

x2 Relationship
Example: return from an investment (Y), increases quadratically (exponentially) with an increasing investment (x). This could happen due to aggressive reinvestment and compounding returns.

<small>Source Page 13 of 60</small>

### Common Nonlinear Transformations

x2 Relationship

Example: return from an investment (Y), increases quadratically (exponentially) with an increasing investment (x). This could happen due to aggressive reinvestment and compounding returns.

<small>Source Page 14 of 60</small>

### Common Nonlinear Transformations

Exponential xb Relationship

y= axb ln y= ln axb ln y= ln a+ ln xb ln y= ln a+ b∗ln(x)

Exponential ebx Relationship

y= aebx ln y= ln aebx ln y= ln a+ ln ebx ln y= ln a+ bx

<small>Source Page 15 of 60</small>

01 | Nonlinear Transformations 02 | Multiple Linear Regression 03 | Variations of Multiple Linear Regression 04 | Dummy Variables 05 | Multiple Linear Regression Examples

Regression Part II

<small>Source Page 16 of 60</small>

### Multiple Linear Regression

Multiple Linear Regression: generalize simple linear regression to deal with a set of independent variables that helps to predict Y.

- build more powerful model by taking other relevant

inputs into account

- produce better forecasts with smaller confidence
```r
intervals (smaller errors)
```

- examine which independent variables have a significant impact on Y (coefficient

hypothesis -------)

Choose A Model Which

- Has all coefficients as significant (except the intercept, which we always keep)

- Has the highest adjusted R2

- Has the smallest residual standard error

<small>Source Page 17 of 60</small>

### Multiple vs. Simple Linear Regression

Multiple Regression Simple Regression

One dependent variable (Yt) One dependent variable (Yt) One independent variable used to build the model xt The intercept β0 is the “baseline” scenario: what happens to Yt in the case where all xt’s are 0

True Model: Yt= β0 + β1x1,t+, … , +βmxm,t+ εt Fitted Model: ෢Yt= መβ0 + መβ1x1,t+, … , + መβmxm,t

m independent variables used to build the model x1,t,…, xm,t

The slope βi provides the value for the change in Yt per unit increase in xi,t while other independent variables are kept fixed

True Model: Yt= β0 + β1xt+ εt Fitted Model: ෢Yt= መβ0 + መβ1xt

The intercept β0 is a “baseline” scenario: what happens to Yt in the case where xt is

The slope β1 provides the value for the change in Yt per unit increase in xt

<small>Source Page 18 of 60</small>

### Education Religion

Beer Houses Crime

Example: Crime

+
<small>Source Page 19 of 60</small>

### Reminder: Model 1 (Simple Regression)

```r
True (Assumed) Model: criminals= β0 + β1pubs+ εt
```

Model Evaluation

Coefficient β1 is significant, since p=0.0026<0.05.

This means that pubs has predictive power for criminals.

Fitted model:

෢ criminalsi= 109.34 + 0.116 ∗pubsi

R squared: 0.214, which means that approx. 21% of the total variance in crime is explained by model 1.

<small>Source Page 20 of 60</small>

### Residual Analysis Model 1

Q: Evaluate each plot?

<small>Source Page 21 of 60</small>

### Multiple Regression: Model 2

```r
True (Assumed) Model: criminals= β0 + β1pubs+ β2edu+ β3religion+ εt
model2 <- lm(criminal ~ public_houses + school_attendance + worship_attendance)
```

Q: Evaluate this model’s coefficients?

<small>Source Page 22 of 60</small>

### Multiple Regression: Model 2

```r
True (Assumed) Model: criminals= β0 + β1pubs+ β2edu+ β3religion+ εt
```

Model Overview:
```r
model2 <- lm(criminal ~ public_houses + school_attendance + worship_attendance)
```

- The coefficient of worship_attendance is not significant (p-value 0.348 not less than

0.05).

- This means that the current model is invalid.

- Rule: remove insignificant variables 1-by-1 starting with least significant one and re-

estimate the model.

Let’s delete worship attendance from the regression equation and re-fit.

<small>Source Page 23 of 60</small>

### Multiple Regression: Model 3

```r
True (Assumed) Model: criminals= β0 + β1pubs+ β2edu+ εt
```

Model Evaluation

```r
model3 <- lm(criminal ~ public_houses + school_attendance)
```

Coefficient β1 is significant at α≈0% Coefficient β2 is significant at α= 5%.

All coefficients are significant therefore this model is valid. Both pubs and school have predictive power for criminals.

Since the model is valid, we can write down the equation of the fitted model:

෢ criminalsi= 178.8 + 0.126 ∗pubsi−0.0765 ∗scℎooli

R2adj: 0.26, which means that approx. 26% of the total variance in crime is explained model 3.

<small>Source Page 24 of 60</small>

### Multiple Regression: Model 3

Fitted Model: ෢ criminalsi= መβ0 + መβ1 ∗pubsi + መβ2 ∗scℎooli

This is a 3D example (One Y variable and two X variables). In this case:

- The regression model fits a plane (i.e. a flat 2D surface) to the data points

- It is a plane of best fit that minimizes the SSE

- Red points are the original Y data points

- The fitted values, ෢Yi, of dependent variable are located on

Scℎool
the plane.

For higher dimensional cases we term it a hyperplane.

Pubs

<small>Source Page 25 of 60</small>

### Residual Analysis Model 3 vs Model 1

Model 3 Model 1

<small>Source Page 26 of 60</small>

### Selecting The Best Model

Comparing Valid Models You can compare valid models to chose the best one using huxreg() table.

The table allows for an easier comparison.

```r
library(huxtable) huxtable::huxreg(model1, model3, number_format = "%.3f", bold_signif =
0.05, statistics = c('adj.r.squared', 'sigma'))
```

Comma separated models.

Number of decimal places.

Significance level α= 5%.

Display adjusted R2, and RSE.

<small>Source Page 27 of 60</small>

### Selecting The Best Model

Comparing model 1 and model 3.

The table displays model numbering in the order in which models were passed into the huxreg() function.

Coefficient’s estimated value and stars as significance level.

(Coefficient’s standard errors)

Model3 has a higher Adj R2 and lower residual standard error.

Therefore, we pick it over model1.
<small>Source Page 28 of 60</small>

01 | Nonlinear Transformations 02 | Multiple Linear Regression 03 | Variations of Multiple Linear Regression 04 | Dummy Variables 05 | Multiple Linear Regression Examples

Regression Part II

<small>Source Page 29 of 60</small>

### Interaction Terms

Example:

Does a drug have more effect on women (0) than men (1) in cholesterol prediction?

Cℎolesterol= β0 + β1drug+ β2gender+ β3drug∗gender+ e

Drug

Cℎolesterol 0 (No drug) 1 (Use drug)

```r
0 (Women) β0
```

Gender

```r
1 (Men)
```

Questions

What is the baseline difference of the average cholesterol level between men and women?

What is the effect of the drug on women?

What is the effect of the drug on men?

What’s the meaning of β3?

<small>Source Page 30 of 60</small>

### Interaction Terms

Example:

Does a drug have more effect on women (0) than men (1) in cholesterol prediction?

Cℎolesterol= β0 + β1drug+ β2gender+ β3drug∗gender+ e

Drug

Cℎolesterol 0 (No drug) 1 (Use drug)
```r
0 (Women) β0 β0 + β1
```

Gender

```r
1 (Men) β0 + β2 β0 + β1 + β2 + β3
```

Questions

What is the baseline difference of the average cholesterol level between men and women?

β2

What is the effect of the drug on women?

β1

What is the effect of the drug on men?

β1+ β3

What’s the meaning of β3?

<small>Source Page 31 of 60</small>

### Interaction Terms

Interaction Term an independent variable in a regression model that is a product of two independent variables.

Sometimes the partial effect of the dependent variable with respect to independent variable can depend on magnitude of yet another independent variable.

Forming An Interaction Term

Does the effect x1 on Y depend on the level of x2?

Y= β0 + β1x1 + β2x2 + β3x1 ∗x2 + e

Example:

Does a drug have more effect on women (0) than men (1) in cholesterol prediction?

Cℎolesterol = β0 + β1drug+ β2gender+ β3drug∗gender+ e

If መβ3 < 0 and significant, it means that the drug lowers cholesterol by more units in men than in women.

Hierarchy Principle:

If you include the interaction term β3x1 ∗x2, you should also include the main effects of the involved variables, i.e. include β1x1 and β2x2 in the fitted equation as well, even if they are not significant. This ensures the model is hierarchically well-specified.
<small>Source Page 32 of 60</small>

### Interaction Terms: Example Prius Car Price

Example: Prius Car Price

Qn: “Does car price drop more for a particular engine for milage?

price = β0 + β1miles+ β2engine+ β3miles∗engine+ e

Interaction term lets us examine whether:

- The effect of miles on price, depends not only on the miles itself, but also on the type

of engine the car has.

- The mileage impact on price might be different for a small-engine car versus a large-

engine car.

- If መβ3 < 0 this means, there is a negative impact on car price when both high milage

and large engine size are present.

<small>Source Page 33 of 60</small>

### Interaction Terms Example: Prius Car Price

So far we have run a model of miles being predictor of Prius car price:

Can we improve the model?

<small>Source Page 34 of 60</small>

### In-class Quiz 5 (2.5% of Grade)

Using the template of session5.Rmd code line 232 through 317 to create the following regression models:

- Simple Linear Regression: car_model1 with one independent variable: miles

- Multiple Linear Regression: car_model2 with more independent variables: miles,

engine, car_age

- Interaction Term: car_model3 with an interaction: miles, engine, car_age, en‐

gine_miles

- Nonlinear Transformation: car_model4 with a nonlinear transformation:

one_over_miles, engine, car_age, engine_miles

Question: Which model is the best prediction model? Use the best model to make a point prediction for a used Prius with 1798 engine, 5600 miles, and 1.5 years’ age.

Please complete a 1-minute short course survey
<small>Source Page 35 of 60</small>

### Multicollinearity

Multicollinearity appears when independent variables used inside the regression equation are highly correlated.

Effects:

- Not much added predictive power.

- Additional variables add little information.

- Magnitude/signs of regression coefficients are different from expected.

- May cause two or more variables to become insignificant but significance may be high

if one variable is dropped.

- Parameter estimates are unreliable.

Remedial Action:

- Remove one of the correlated variables.

- Check for correlations between independent variables in advance of running the re‐

gression

---- in RStudio:

Variance Inflation Factor (VIF) assess multicollinearity in regression models, providing a value for each independent variable.

```r
library(car) car::vif(model)
```

- VIF > 10: high multicollinearity, attend to it - VIF 5 -10: moderate multicollinearity, keep an

eye - VIF < 5: no multicollinearity, acceptable

<small>Source Page 36 of 60</small>

### Distributed Lag Model

Distributed lag model is a model for time series data in which a regression equation is used to predict current values of a dependent variable based on both the current values of an independent variable and/or its lagged (past period) values.

```r
True (Assumed) Model:
```

Yt= β0 + β1xt+ β2xt−1 + β3xt−2 + ⋯+ εt

Assume a finite number of lags (e.g. 2-5) and run the multiple regression model as usual.

Remove insignificant lags one by one starting with least significant first and re-run the model.

Data Preparation:
Create an extra column for each lag, as:

t Yt xt

t Yt xt xt−1

NA

13.3 3.4

13.3 3.4

10.2 5.1

10.2 5.1 3.4

1.3

1.3 5.1

After creating the required columns, remove any rows with NA.

To create lags with dplyr, read here.

<small>Source Page 37 of 60</small>

### Event -----

Event ----- is a model applied when you are interested in the dynamic treatment effect, i.e., how does an outcome change several periods before and after an event?

Analysis setup: two (groups of) observations i are both observed for multiple periods before and after time t, when group A is treated (Ti=1), while group B is not treated (Ti=0).

```r
True (Assumed) Model:
```

Yit= β0 + βt−2Ιt−2Ti+ βtΙtTi+ βt+1Ιt+1Ti… + εit

The t-1 period is omitted as the reference period.

Data Preparation:

Create extra columns for each lead and lag, as (suppose the event took place at time period 3 and the event happened to unit 2 but not unit 1):

i t Yt Ti

i t Yt Ti Ιt−2 Ιt Ιt+1

11.3

11.3

10.5

10.5
10.8

10.8

18.7

18.7

24.5

24.5

27.8

27.8

Examples:

How does the target firm stock price respond to M&A announcements?

How does the stock price of Tesla change before vs. after the US president election?

<small>Source Page 38 of 60</small>

### Event -----: From Red Tape to RegTech (Cui, Wang, Wu 2025)

Q: How does regional export volume change before and after the entry of OneTouch?

No OneTouch Receive order

Submit rebate filing to local tax office

OneTouch

Submit rebate filing through OneTouch

Receive order

Long waiting time Incorrect filing Back and forth Limited cashflow

Receive rebate in 2-3 months

Lower compliance cost Micro financing

Credit rebate in 3 days

Reinvest in production

Receive more orders

……
<small>Source Page 39 of 60</small>

### Rollout of OneTouch Branches

<small>Source Page 40 of 60</small>

### Rollout of OneTouch Branches

<small>Source Page 41 of 60</small>

### Rollout of OneTouch Branches

<small>Source Page 42 of 60</small>

### Event -----: From Red Tape to RegTech (Cui, Wang, Wu 2025)

The differences of export volume between treated and untreated cities were not significantly different from 0 BEFORE the entry of OneTouch.

However, such difference became significant and increasingly large AFTER the entry of OneTouch, meaning that OneTouch can facilitate export.

<small>Source Page 43 of 60</small>

01 | Nonlinear Transformations 02 | Multiple Linear Regression 03 | Variations of Multiple Linear Regression 04 | Dummy Variables 05 | Multiple Linear Regression Examples

Regression Part II

<small>Source Page 44 of 60</small>

### Qualitative Variables

Dummy Variable: a variable that takes on a value of 0 or 1. Examples:

Gender:

- Create a column ‘gender’

- gender=0 if male, gender=1 if female

```r
Seasons (halves):
```
- Create a column ‘season’

- season=0 for Q1 and Q2, season=1 if

Q3 and Q4

```r
Seasons (quarters):
```

- Create 3 columns:

- q1=1 if it is Q1, 0 otherwise

- q2=1 if it is Q2 , 0 otherwise

- q3=1 if it is Q3 , 0 otherwise

Example: Bond Prices and National Income

Create a dummy variable W encoded as:

- 1 war year

- 0 no war year, treated as a reference group (usually the majority of the data in the

sample)

B: Bond purchases Y: GNP (Gross National Product) W: Dummy variable of war year

<small>Source Page 45 of 60</small>

### Example: Bond Prices and National Income

<small>Source Page 46 of 60</small>

### Regression with Dummy Variable: War

Dummy variable can be used in regression analysis just like any other quantitative variable. We have 2 categories: war / no war and a single dummy variable to represent it.

Fitted Model:

෢ bond= መβ0 + መβ1GNP+ መβ2WAR = 1.02 + 0.72 ∗GNP+ 2 ∗War

Interpretation:

Intercept is the bond price for the reference group

Positive β2 coefficient (+2.0 in this case) means that bond price was higher for the dummy variable (war) than the reference group (no war).

Negative β2 coefficient would have meant that bond price would have been lower.
<small>Source Page 47 of 60</small>

### Conceptual Visualization

෢ bond= 1.02 + 0.72 ∗GNP+ 2.0 ∗1

෢ bond= 1.02 + 0.72 ∗GNP+ 0

<small>Source Page 48 of 60</small>

### Regression with Dummy Variable: Season

Seasonality is usually a strong predictor of product demand (and price).

Demand

Price

Season Dummy

(Y)

(x1)

(x2)

1.5 1.6 1.3 1.4

Winter Summer Winter Summer

Q: Write down regression equation to model the demand using available information?

Demand

Summer: x2 = 1

Winter: x2 = 0

1.1 1.2 1.3 1.4 1.5 1.6 1.7 1.8

Price

<small>Source Page 49 of 60</small>

### Effect on Intercept

The fitted regression model equation would look as:

෢ demandt= ෢ β0 + ෢ β1pricet+ ෢ β2dummyt

Think of this regression as a two-case scenario:

Summer: ෢ demandt= ෢ β0 + ෢ β1pricet+ ෢ β21 = (෢ β0 + ෢ β2) + ෢ β1pricet
Winter: ෢ demandt= ෢ β0 + ෢ β1pricet+ ෢ β20 = ෢ β0 + ෢ β1pricet

Demand

Summer: x2 = 1

Winter: x2 = 0

1.1 1.2 1.3 1.4 1.5 1.6 1.7 1.8

Price

<small>Source Page 50 of 60</small>

### Regression with k-levels

When a categorical variable has k categories (we call them ‘levels), we include only k-1 dummy variables in the regression model.

The category that is left out is usually the one with the most frequent observations and it acts as a reference.

Example:

- 3 movie categories: adventure, romance, drama.

- If drama has the most obs, leave it out as a reference and create 2 dummies for

adventure and romance.

salest= β0 + β1promot+ β2adventuret+ β3romancet+ εt

Dummies

k-th category is redundant information:

Obs promo adventure romance drama

12.5

10.2

14.5

… … … … …

Obs1: if its not adventure or romance then those 2 pieces of information tell us it must be drama.

Obs2: if it is not adventure but it is romance, then automatically we know it is not drama, etc.
<small>Source Page 51 of 60</small>

### Example: k=3 levels

Fitted Model:

෢Yt= ෢ β0 + ෢ β1promot+ ෢ β2adventuret+ ෢ β3romancet

Model’s intercept ෢ β0 is the ticket sales for the reference group (drama).

If ෢ β2 > 0 then ticket sales were higher for the dummy variable adventure, than the reference group drama.

adventure=0 romance=1

sales

adventure=1 romance=0

෢ β0 + ෢ β3

adventure=0 romance=0

෢ β0 + ෢ β2

෢ β0

Promotion

<small>Source Page 52 of 60</small>

### Example: The Impact of Seat Location on UM Ross MBA -------

### Performance (Orhun, Sivadasan, Li, Wang 2025)

From Fall 2014 till now, Ross has been randomly assigning seats to MBA --------.

Research Question: Do -------- randomly assigned to row 1,2,3 and 4 perform differently?

Q: How would you design your regression model?

<small>Source Page 53 of 60</small>

### Example: The Impact of Seat Location on MBA ------- Performance

### (Orhun, Sivadasan, Li, Wang 2025)

Ytc= β0 + β1Rtc+ γXt+ μc+ εtc

Row 4 is omitted (so we set Row 4 as the reference) Interpretation: Holding all the other explanatory variables constant, -------- in row 1 receive 0.0522 SD higher score than those in row 4.

Pairwise comparison of coefficients (---- for difference)
<small>Source Page 54 of 60</small>

### Regression Check List

Set up the model, choose the data - Which variables to include - Generate dummy variables where appropriate - What do expect (from practice, theory,

anecdotal evidence)?

Check scatter plots and correlations - Identify any obvious nonlinearities (transform variables)

- Beware of high correlations between explanatory factors (multicollinearility)

Carry out the regression - Drop insignificant variables (one-by-one starting with least significant first) and re-model - Ensure the model is valid (i.e. all coefficients are significant; always keep the intercept) - Check residual plots with autoplot() function

Choose the best model - Compare models with huxreg() function - Highest Adjusted R2, and lowest standard error of

residuals - Compare to initial expectations

Use the model to create forecasts

<small>Source Page 55 of 60</small>

When we raise money it’s AI, when we hire it's machine learning, and when we do the work it's logistic regression. (Juan Miguel Lavista @BDataScientist).

<small>Source Page 56 of 60</small>

### Predictive Analytics

Transparent Models:

Supervised Learning

Black Box Models:

Unsupervised learning Reinforcement learning

Statistical models and theory Algorithmic model

<small>Source Page 57 of 60</small>

01 | Nonlinear Transformations 02 | Multiple Linear Regression 03 | Variations of Multiple Linear Regression 04 | Dummy Variables 05 | Multiple Linear Regression Examples

Regression Part II
<small>Source Page 58 of 60</small>

### Case: Winner Plc

Question: ”Is the company guilty of gender discrimination?”

Descriptive Statistics

Data: random sample of 50 employees (24 male and 26 female).

Analysis:

- Descriptive Stats

- Histograms

- Confidence intervals

- Hypothesis -------

- Regression analysis (simple; multiple;

transformations)

<small>Source Page 59 of 60</small>

### Session Summary

We covered:

Multiple Linear Regression

Workshop Questions:

Look at the workshop questions in advance.

Attend optional workshop to go over the solutions.

Readings:

Modern Dives chapter 6,10

Congratulations on completing the

first part of CA09!

<small>Source Page 60 of 60</small>

### Please complete the 1-minute course survey.


[↑ Back to the source list](#source-documents)

---

<a name="source-3"></a>

## session5.html

<small>File type: HTML · Reader pages 325–366 · [View source PDF](PDF%20Slides.pdf#page=325)</small>

> This source was converted from HTML to PDF before upload; some inline code is fragmented. Use an adjacent `.Rmd` source when provided.

### Session 5, In-Class Project

```text
library(tidyverse)
library(tidyquant)
library(dplyr)
library(ggplot2)
library(MASS)
# For generating multivariate normal data
library(gridExtra)
# For arranging multiple plots
library(mosaic)
library(GGally)
library(ggfortify)
# residual plots
library(ggrepel)
library(car)
library(plyr)
```

### Nonlinear Transformations

I provide 3 toy datasets of x and y variables.

### Data 1

```text
set.seed
(
123
)
x
<-
c
(
1
:
10
)
y
<-
+
```
```text
3
*
x
^
2
+
rnorm
(
10
,
mean =
2
,
sd =
5
)
data1
<-
tibble
(x, y)
%>%
dplyr
::
select
(y, x)
# Sometimes multiple R packages have functions with the same name. Use "dplyr::" to specify
the package that the function "select" belongs to.
# visualize the data and the fitted regression line
ggplot
(data1,
aes
(
x=
x,
y=
y))
+
geom_point
()
+
geom_line
()
+
geom_smooth
(
method=
'lm'
,
se=
FALSE
)
+
labs
(
x=
"x"
,
y=
"y"
)
```
```text
## `geom_smooth()` using formula = 'y ~ x'
# create an initial regression model between y and x
model1_data1
<-
lm
(y
~
x)
summary
(model1_data1)
##
## Call:
## lm(formula = y ~ x)
##
## Residuals:
##  Min  1Q  Median  3Q  Max
## -23.932 -15.558  -5.639  9.481  35.243
##
## Coefficients:
##  Estimate Std. Error t value Pr(>|t|)
## (Intercept)  -56.373  15.111  -3.73  0.00578 **
## x  32.590  2.435  13.38 9.31e-07 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
##
## Residual standard error: 22.12 on 8 degrees of freedom
## Multiple R-squared:  0.9572, Adjusted R-squared:  0.9519
## F-statistic: 179.1 on 1 and 8 DF,  p-value: 9.306e-07
```

We can see that the first dataset looks like an x^2 relationship. Therefore perform the transformation and create a new variable, \(z=x^2\) and re-run the linear regression:

```text
data1_transformed
<-
data1
%>%
dplyr
::
mutate
(
z =
x
^
2
)
%>%
dplyr
::
select
(y, z)
model2_data1
<-
lm
(y
~
```
```text
z,
data=
data1_transformed)
summary
(model2_data1)
##
## Call:
## lm(formula = y ~ z, data = data1_transformed)
##
## Residuals:
##  Min  1Q  Median  3Q  Max
## -5.3803 -2.8832 -0.8041  2.0001  8.0730
##
## Coefficients:
##  Estimate Std. Error t value Pr(>|t|)
## (Intercept)  9.36326  2.30664  4.059  0.00364 **
## z  2.94831  0.04583  64.333 3.79e-12 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
##
## Residual standard error: 4.698 on 8 degrees of freedom
## Multiple R-squared:  0.9981, Adjusted R-squared:  0.9978
## F-statistic:  4139 on 1 and 8 DF,  p-value: 3.791e-12
ggplot
(data1_transformed,
aes
(
x=
z,
y=
y))
+
geom_point
()
+
geom_line
()
+
geom_smooth
(
method=
'lm'
,
se=
FALSE
)
+
labs
(
x=
"x^2"
,
y=
"y"
)
```
```text
## `geom_smooth()` using formula = 'y ~ x'
```

We can see that the transformation improved the regression model fit (using R2) from 0.957 to 0.998.

### Data 2

```text
set.seed
(
123
)
x
<-
c
(
1
:
10
)
y
<-
5
+
3
*
(
1
/
x)
+
rnorm
(
10
,
mean =
0
,
sd =
0.15
)
data2
<-
tibble
(x, y)
%>%
dplyr
::
select
(y, x)
%>%
round
(
2
)
# visualise the data and the fitted regression line
ggplot
(data2,
aes
(
```
```text
x=
x,
y=
y))
+
geom_point
()
+
geom_line
()
+
geom_smooth
(
method=
'lm'
,
se=
FALSE
)
+
labs
(
x=
"x"
,
y=
"y"
)
## `geom_smooth()` using formula = 'y ~ x'
# create an initial regression model between y and x
model1_data2
<-
lm
(y
~
x)
summary
(model1_data2)
##
## Call:
## lm(formula = y ~ x)
##
## Residuals:
##  Min  1Q  Median  3Q  Max
## -0.4810 -0.2443 -0.0795  0.1169  0.9710
##
## Coefficients:
##  Estimate Std. Error t value Pr(>|t|)
## (Intercept)  7.1794  0.3096  23.185 1.27e-08 ***
## x  -0.2344  0.0499  -4.698  0.00155 **
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
##
## Residual standard error: 0.4533 on 8 degrees of freedom
```
```text
## Multiple R-squared:  0.734,  Adjusted R-squared:  0.7007
## F-statistic: 22.07 on 1 and 8 DF,  p-value: 0.001545
```

We can see that the second dataset looks like an 1/x relationship. Therefore perform the transformation and create a new variable, \(z=1/x\) and re-run the linear regression:

```text
data2_transformed
<-
data2
%>%
dplyr
::
mutate
(
z =
1
/
x)
%>%
dplyr
::
select
(y, z)
model2_data2
<-
lm
(y
~
z,
data=
data2_transformed)
summary
(model2_data2)
##
## Call:
## lm(formula = y ~ z, data = data2_transformed)
##
## Residuals:
##  Min  1Q  Median  3Q  Max
## -0.20603 -0.08314 -0.01804  0.03921  0.24113
##
## Coefficients:
##  Estimate Std. Error t value Pr(>|t|)
## (Intercept)  5.02753  0.07096  70.85 1.75e-12 ***
## z  2.94803  0.18024  16.36 1.97e-07 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
##
## Residual standard error: 0.1499 on 8 degrees of freedom
## Multiple R-squared:  0.971,  Adjusted R-squared:  0.9673
## F-statistic: 267.5 on 1 and 8 DF,  p-value: 1.967e-07
ggplot
(data2_transformed,
aes
(
```
```text
x=
z,
y=
y))
+
geom_point
()
+
geom_line
()
+
geom_smooth
(
method=
'lm'
,
se=
FALSE
)
+
labs
(
x=
"1/x"
,
y=
"y"
)
## `geom_smooth()` using formula = 'y ~ x'
```

We can see that the transformation improved the regression model fit (using R2) from 0.734 to 0.971.

### Data 3

```text
set.seed
(
123
)
x
<-
c
(
1
:
10
)
y
<-
5
+
3
*
sqrt
(x)
+
rnorm
```
```text
(
10
,
mean =
0
,
sd =
0.15
)
data3
<-
tibble
(x, y)
%>%
dplyr
::
select
(y, x)
%>%
round
(
2
)
# visualise the data and the fitted regression line
ggplot
(data3,
aes
(
x=
x,
y=
y))
+
geom_point
()
+
geom_line
()
+
geom_smooth
(
method=
'lm'
,
se=
FALSE
)
+
labs
(
x=
"x"
,
y=
"y"
)
## `geom_smooth()` using formula = 'y ~ x'
```
```text
# create an initial regression model between y and x
model1_data3
<-
lm
(y
~
x)
summary
(model1_data3)
##
## Call:
## lm(formula = y ~ x)
##
## Residuals:
##  Min  1Q  Median  3Q  Max
## -0.76615 -0.22200  0.03771  0.30826  0.51299
##
## Coefficients:
##  Estimate Std. Error t value Pr(>|t|)
## (Intercept)  7.99995  0.29591  27.04 3.77e-09 ***
## x  0.68213  0.04769  14.30 5.57e-07 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
##
## Residual standard error: 0.4332 on 8 degrees of freedom
## Multiple R-squared:  0.9624, Adjusted R-squared:  0.9577
## F-statistic: 204.6 on 1 and 8 DF,  p-value: 5.568e-07
```

We can see that the third dataset looks like an sqrt(x) relationship. Therefore perform the transformation and create a new variable, \(z=\sqrt(x)\) and re-run the linear regression:

```text
data3_transformed
<-
data3
%>%
dplyr
::
mutate
(
z =
sqrt
(x))
%>%
dplyr
::
select
(y, z)
model2_data3
<-
lm
(y
~
z,
data=
data3_transformed)
```
```text
summary
(model2_data3)
##
## Call:
## lm(formula = y ~ z, data = data3_transformed)
##
## Residuals:
##  Min  1Q  Median  3Q  Max
## -0.17841 -0.08417 -0.03021  0.05689  0.25512
##
## Coefficients:
##  Estimate Std. Error t value Pr(>|t|)
## (Intercept)  5.09229  0.16451  30.95 1.29e-09 ***
## z  2.96494  0.07015  42.27 1.08e-10 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
##
## Residual standard error: 0.1491 on 8 degrees of freedom
## Multiple R-squared:  0.9955, Adjusted R-squared:  0.995
## F-statistic:  1787 on 1 and 8 DF,  p-value: 1.082e-10
ggplot
(data3_transformed,
aes
(
x=
z,
y=
y))
+
geom_point
()
+
geom_line
()
+
geom_smooth
(
method=
'lm'
,
se=
FALSE
)
+
labs
(
x=
"sqrt(x)"
,
y=
"y"
)
## `geom_smooth()` using formula = 'y ~ x'
```
We can see that the transformation improved the regression model fit (using R2) from 0.9624 to 0.9955.

### Crime

### ———- Model 1 (Simple Linear Regression) ———–

```text
crime
<-
read_csv
(
'beerhall.csv'
)
## Rows: 40 Columns: 7
## ── Column specification ────────────────────────────────────────────────────────
## Delimiter: ","
## chr (2): county, region_name
## dbl (5): region_code, criminals, public_houses, school_attendance, worship_a...
##
## ℹ Use `spec()` to retrieve the full column specification for this data.
## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
crime_model1
<-
lm
(criminals
~
public_houses,
data =
crime)
# single x
crime
$
predicted
<-
predict
(crime_model1)
# Y_hat values that will sit on the regression line
crime
$
residuals
<-
residuals
(crime_model1)
# error between Ys and Y_hats
summary
(crime_model1)
##
## Call:
## lm(formula = criminals ~ public_houses, data = crime)
##
## Residuals:
##  Min  1Q  Median  3Q  Max
## -78.517 -25.704  -1.653  22.592  90.988
```
```text
##
## Coefficients:
##  Estimate Std. Error t value Pr(>|t|)
## (Intercept)  109.3400  14.7553  7.410  6.9e-09 ***
## public_houses  0.1162  0.0361  3.219  0.00263 **
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
##
## Residual standard error: 37.19 on 38 degrees of freedom
## Multiple R-squared:  0.2142, Adjusted R-squared:  0.1936
## F-statistic: 10.36 on 1 and 38 DF,  p-value: 0.002635
crime_model1
%>%
autoplot
(
which =
1
:
3
)
+
theme_bw
()
## Warning: `fortify(<lm>)` was deprecated in ggplot2 4.0.0.
## ℹ Please use `broom::augment(<lm>)` instead.
## ℹ The deprecated feature was likely used in the ggfortify package.
##  Please report the issue at <https://github.com/sinhrks/ggfortify/issues>.
## This warning is displayed once per session.
## Call `lifecycle::last_lifecycle_warnings()` to see where this warning was
## generated.
## Warning: Using `size` aesthetic for lines was deprecated in ggplot2 3.4.0.
## ℹ Please use `linewidth` instead.
## ℹ The deprecated feature was likely used in the ggfortify package.
##  Please report the issue at <https://github.com/sinhrks/ggfortify/issues>.
## This warning is displayed once per session.
## Call `lifecycle::last_lifecycle_warnings()` to see where this warning was
## generated.
```

### ———- Model 2 (Multiple Linear Regression) ———–

Let’s evaluate all of the independent variables and add them into the model:

```text
crime_model2
<-
lm
(criminals
~
public_houses
+
school_attendance
+
worship_attendance,
data =
```
```text
crime)
summary
(crime_model2)
##
## Call:
## lm(formula = criminals ~ public_houses + school_attendance +
##  worship_attendance, data = crime)
##
## Residuals:
##  Min  1Q  Median  3Q  Max
## -55.049 -21.551  -8.064  23.067  94.381
##
## Coefficients:
##  Estimate Std. Error t value Pr(>|t|)
## (Intercept)  172.88613  35.83854  4.824 2.57e-05 ***
## public_houses  0.12333  0.03501  3.523  0.00118 **
## school_attendance  -0.10115  0.04405  -2.296  0.02761 *
## worship_attendance  0.03930  0.04135  0.951  0.34819
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
##
## Residual standard error: 35.58 on 36 degrees of freedom
## Multiple R-squared:  0.3187, Adjusted R-squared:  0.2619
## F-statistic: 5.612 on 3 and 36 DF,  p-value: 0.002911
```

Note that if we try to include worship_attendance instead of school_attendance, the result for its coefficient is still insignificant. Therefore worship_attendance will not be present in our final model.

```text
crime_model2_b
<-
lm
(criminals
~
public_houses
+
worship_attendance,
data =
crime)
# many xs
summary
(crime_model2_b)
##
## Call:
## lm(formula = criminals ~ public_houses + worship_attendance,
##  data = crime)
##
## Residuals:
##  Min  1Q  Median  3Q  Max
## -78.749 -24.947  -0.206  21.408  93.203
##
## Coefficients:
##  Estimate Std. Error t value Pr(>|t|)
## (Intercept)  121.26228  29.47442  4.114 0.000208 ***
## public_houses  0.11886  0.03691  3.220 0.002671 **
```
```text
## worship_attendance  -0.01656  0.03531  -0.469 0.641884
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
##
## Residual standard error: 37.58 on 37 degrees of freedom
## Multiple R-squared:  0.2189, Adjusted R-squared:  0.1767
## F-statistic: 5.184 on 2 and 37 DF,  p-value: 0.01036
# remember that the correlation between worship_attendance and criminals is nearly 0
# therefore we do not expect it to form a good predictor of criminals in a regression.
```

### ———- Model 3 (Multiple Linear Regression) ———–

```text
crime_model3
<-
lm
(criminals
~
public_houses
+
school_attendance,
data=
crime)
# many xs
summary
(crime_model3)
##
## Call:
## lm(formula = criminals ~ public_houses + school_attendance, data = crime)
##
## Residuals:
##  Min  1Q Median  3Q  Max
## -59.97 -22.93  -5.92  18.77  97.53
##
## Coefficients:
##  Estimate Std. Error t value Pr(>|t|)
## (Intercept)  178.81261  35.24595  5.073 1.12e-05 ***
## public_houses  0.12635  0.03482  3.629 0.000854 ***
## school_attendance  -0.07651  0.03557  -2.151 0.038108 *
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
##
## Residual standard error: 35.54 on 37 degrees of freedom
## Multiple R-squared:  0.3016, Adjusted R-squared:  0.2638
## F-statistic: 7.987 on 2 and 37 DF,  p-value: 0.001308
```

Residual analysis of model 3:

```text
crime_model3
%>%
autoplot
(
which =
:
```
```text
3
)
+
theme_bw
()
```

Compare valid models using huxreg() function that produces a table for ease of comparison.

```text
# compare the two models
huxtable
::
huxreg
(crime_model1, crime_model3,
number_format =
"%.3f"
,
bold_signif =
0.05
,
statistics =
c
(
'adj.r.squared'
,
'sigma'
))
```

(1)

(2)

(Intercept)

109.340 ***

178.813 ***

(14.755)

(35.246)

public_houses

0.116 **

0.126 ***

(0.036)

(0.035)

school_attendance

-0.077 *

(0.036)

adj.r.squared

0.194

0.264

sigma

37.193

35.536

*** p < 0.001; ** p < 0.01; * p < 0.05.

```text
# alternatively use c(NULL) to reveal all stats
```

On line 1 above I use comma separated models. On line 2 I use 3 significant figures to display the results. On line 3 I have added for convenience argument that will make all 95% significant coefficients bold. On line 4 we specify that we want to have adj R2 and the residual standard error displayed.
### Class Exercise: Multiple Linear Regression Prius Car Price

Let’s load the data and create a few extra independent variables from the data that we already

have:

```text
prius
<-
read_csv
(
"toyota_prius_jun18.csv"
)
## Rows: 234 Columns: 7
## ── Column specification ────────────────────────────────────────────────────────
## Delimiter: ","
## chr (3): town, region, colour
## dbl (4): year, engine, miles, price
##
## ℹ Use `spec()` to retrieve the full column specification for this data.
## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
prius
<-
prius
%>%
mutate
(
engine =
factor
(engine),
# turn it to a factor
car_age =
2018
-
year)
```

You already have created the following model in the previous class:

```text
car_model1
<-
lm
(price
~
miles,
data =
prius)
car_model1
%>%
autoplot
(
which =
1
:
3
)
+
```
```text
theme_bw
()
```

Let’s build multivariate models. Your task is to create the following multiple regression models to predict price:

car_model2, with independent variables: miles, engine, car_age

car_model3, with independent variables: miles, engine, car_age, miles*engine

car_model4, with independent variables: 1/miles, engine, car_age, miles*engine

Compare the models and select the best one, giving reasoning. For the best model provide residual analysis and comment.

### Include More Independent Variables

```text
# Model 2: Xs: miles, engine, car_age
car_model2
<-
lm
(price
~
miles
+
engine
+
car_age,
data =
prius)
summary
(car_model2)
##
## Call:
## lm(formula = price ~ miles + engine + car_age, data = prius)
##
## Residuals:
##  Min  1Q  Median  3Q  Max
## -5283.5  -953.1  -113.0  820.7  4536.3
##
## Coefficients:
##  Estimate Std. Error t value Pr(>|t|)
## (Intercept)  1.763e+04  4.915e+02  35.873  <2e-16 ***
## miles  -2.681e-02  2.204e-03 -12.163  <2e-16 ***
## engine1798  7.440e+02  3.094e+02  2.405  0.017 *
## car_age  -9.755e+02  5.007e+01 -19.482  <2e-16 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
##
## Residual standard error: 1543 on 230 degrees of freedom
## Multiple R-squared:  0.9061, Adjusted R-squared:  0.9049
## F-statistic: 739.6 on 3 and 230 DF,  p-value: < 2.2e-16
```
### Include Interaction Term:

This means that the effect of mileage depends on engine size. If we have two explanatory variables, and the value of one (effect of mileage) depends on the other (engine size), then besides the two variables, we also introduce an interaction variable, which is the product of the two.

```text
# Model 3: Xs: miles, engine, car_age, miles*engine
prius_transformed1
<-
prius
%>%
mutate
(
engine_miles =
as.integer
(engine
==
1798
)
*
miles)
car_model3
<-
lm
(price
~
miles
+
engine
+
car_age
+
engine_miles,
data =
prius_transformed1)
# Note this is the same as running below as x*y, the x and y will be added automatically as
separate indep vars.
# model3 <- lm(price ~ car_age + miles*engine, data = prius)
summary
(car_model3)
##
## Call:
## lm(formula = price ~ miles + engine + car_age + engine_miles,
##  data = prius_transformed1)
##
## Residuals:
##  Min  1Q  Median  3Q  Max
## -5622.9  -963.9  96.0  685.0  4121.4
##
## Coefficients:
##  Estimate Std. Error t value Pr(>|t|)
## (Intercept)  1.507e+04  7.354e+02  20.494  < 2e-16 ***
## miles  -1.759e-02  2.933e-03  -5.998 7.74e-09 ***
## engine1798  3.488e+03  6.737e+02  5.177 4.92e-07 ***
## car_age  -8.535e+02  5.507e+01 -15.498  < 2e-16 ***
## engine_miles -1.923e-02  4.239e-03  -4.538 9.18e-06 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
```
```text
##
## Residual standard error: 1481 on 229 degrees of freedom
## Multiple R-squared:  0.9138, Adjusted R-squared:  0.9123
## F-statistic: 607.1 on 4 and 229 DF,  p-value: < 2.2e-16
```

### Include Nonlinear Transformation

```text
# Prep data for Model4 by mutating miles
prius_transformed2
<-
prius
%>%
mutate
(
one_over_miles =
1
/
miles,
engine_miles =
as.integer
(engine
==
1798
)
*
miles)
# Model 4: Xs: 1/miles, engine, car_age, miles*engine
car_model4
<-
lm
(price
~
one_over_miles
+
engine
+
car_age
+
engine_miles,
data =
prius_transformed2)
summary
(car_model4)
##
## Call:
## lm(formula = price ~ one_over_miles + engine + car_age + engine_miles,
##  data = prius_transformed2)
##
## Residuals:
##  Min  1Q  Median  3Q  Max
## -5178.4  -894.8  -41.8  845.4  4846.7
##
## Coefficients:
##  Estimate Std. Error t value Pr(>|t|)
## (Intercept)  1.179e+04  6.160e+02  19.137  < 2e-16 ***
## one_over_miles  1.540e+07  2.113e+06  7.286 5.12e-12 ***
## engine1798  5.223e+03  5.375e+02  9.716  < 2e-16 ***
## car_age  -7.808e+02  5.429e+01 -14.382  < 2e-16 ***
```
```text
## engine_miles  -2.953e-02  3.129e-03  -9.436  < 2e-16 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
##
## Residual standard error: 1436 on 229 degrees of freedom
## Multiple R-squared:  0.9191, Adjusted R-squared:  0.9176
## F-statistic:  650 on 4 and 229 DF,  p-value: < 2.2e-16
```

### Huxreg Table For Comparison!

It is much easier to compare results using the HuxReg Table:

```text
# Compare models 1,2,3,4
huxtable
::
huxreg
(car_model1, car_model2, car_model3, car_model4,
number_format =
"%.2f"
,
bold_signif =
0.05
,
statistics =
c
(
'adj.r.squared'
,
'sigma'
))
```

(1)

(2)

(3)

(4)

(Intercept)

14734.09 ***

17630.42 ***

15070.69 ***

11788.58 ***

(434.64)

(491.46)

(735.37)

(616.02)

miles

-0.06 ***

-0.03 ***

-0.02 ***

(0.00)

(0.00)

(0.00)

engine1798

743.99 *

3488.08 ***

5222.52 ***

(309.36)

(673.70)

(537.54)

car_age

-975.51 ***

-853.51 ***

-780.83 ***

(50.07)

(55.07)

(54.29)

engine_miles

-0.02 ***

-0.03 ***

(0.00)

(0.00)

one_over_miles

15397474.62 ***

(2113306.22)

adj.r.squared

0.57

0.90

0.91

0.92

sigma

3279.86

1543.26

1481.45

1435.80
(1)

(2)

(3)

(4)

*** p < 0.001; ** p < 0.01; * p < 0.05.

```text
autoplot
(car_model4,
which =
1
:
3
)
+
theme_bw
()
```

### Mutlicollinearity

The code library(car) and car::vif(model1) is used in R to assess multicollinearity in regression models by calculating the Variance Inflation Factor (VIF) for each predictor variable in the model.

Interpret the VIF values:

VIF > 10: Indicates high multicollinearity, which could make your model unstable.

VIF between 5 and 10: Moderate multicollinearity, something to keep an eye on.

VIF < 5: Low or no multicollinearity, typically acceptable.

```text
model2
<-
lm
(criminals
~
public_houses
+
school_attendance
+
worship_attendance,
data =
crime)
summary
(model2)
##
## Call:
## lm(formula = criminals ~ public_houses + school_attendance +
##  worship_attendance, data = crime)
##
## Residuals:
##  Min  1Q  Median  3Q  Max
## -55.049 -21.551  -8.064  23.067  94.381
##
## Coefficients:
##  Estimate Std. Error t value Pr(>|t|)
## (Intercept)  172.88613  35.83854  4.824 2.57e-05 ***
## public_houses  0.12333  0.03501  3.523  0.00118 **
```
```text
## school_attendance  -0.10115  0.04405  -2.296  0.02761 *
## worship_attendance  0.03930  0.04135  0.951  0.34819
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
##
## Residual standard error: 35.58 on 36 degrees of freedom
## Multiple R-squared:  0.3187, Adjusted R-squared:  0.2619
## F-statistic: 5.612 on 3 and 36 DF,  p-value: 0.002911
car
::
vif
(model2)
##  public_houses  school_attendance worship_attendance
##  1.027194  1.558182  1.566320
# cor(crime$worship_attendance, crime$school_attendance) # 0.60
```

Based on the correlation of 0.6 and the VIF values, you do not have a multicollinearity problem. While the correlation between school_attendance and worship_attendance is moderate, the VIF values suggest that multicollinearity is not significantly affecting the model. The worship_attendance is not statistically significant (p-value = 0.34819), indicating that it may not be a strong predictor in this model.

### Dummy Variables

```text
bonds
<-
read_csv
(
'bonds.csv'
)
## Rows: 17 Columns: 4
## ── Column specification ────────────────────────────────────────────────────────
## Delimiter: ","
## dbl (4): Year, B, Y, W
##
## ℹ Use `spec()` to retrieve the full column specification for this data.
## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
ggplot
(bonds,
aes
(
x =
Y,
y =
B))
+
```
```text
geom_point
()
# regression of Bond price = Intercept + b1*GNP + b2*WAR + e
model_war1
<-
lm
(B
~
Y
+
W,
data =
bonds)
summary
(model_war1)
##
## Call:
## lm(formula = B ~ Y + W, data = bonds)
##
## Residuals:
##  Min  1Q  Median  3Q  Max
## -1.64212 -0.03572  0.10349  0.27538  0.44802
##
## Coefficients:
##  Estimate Std. Error t value Pr(>|t|)
## (Intercept)  1.0226  0.2981  3.430  0.00406 **
## Y  0.7190  0.0383  18.774 2.53e-11 ***
## W  1.9998  0.2627  7.613 2.43e-06 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
##
## Residual standard error: 0.5279 on 14 degrees of freedom
## Multiple R-squared:  0.9704, Adjusted R-squared:  0.9662
## F-statistic: 229.4 on 2 and 14 DF,  p-value: 1.995e-11
ggplot
(bonds,
aes
(
x =
Y,
y =
B))
+
scale_x_continuous
(
limits =
c
(
0
,
13
),
expand =
c
(
```
```text
0
,
0
))
+
scale_y_continuous
(
limits =
c
(
0
,
12
),
expand =
c
(
0
,
0
))
+
geom_point
()
+
labs
(
x =
"Y, GNP ($ billions)"
,
y =
"B, Bond Price ($ hundred millions)"
,
title =
"Effect of Dummy Variable, War"
)
+
geom_text_repel
(
data =
bonds,
mapping =
aes
(
label =
Year))
```

Note this is not the same as running separate regressions on war and no war data

```text
dataWar
<-
filter
(bonds, W
==
1
)
dataNowar
<-
filter
(bonds, W
```
```text
==
0
)
# war
model_war2
<-
lm
(B
~
Y,
data =
dataWar)
summary
(model_war2)
##
## Call:
## lm(formula = B ~ Y, data = dataWar)
##
## Residuals:
##  1  2  3  4  5  6  7
## -1.07574  0.81789  0.64272 -0.07004  0.10278 -0.11400 -0.30360
##
## Coefficients:
##  Estimate Std. Error t value Pr(>|t|)
## (Intercept)  1.7126  0.9741  1.758  0.13906
## Y  0.8960  0.1269  7.062  0.00088 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
##
## Residual standard error: 0.687 on 5 degrees of freedom
## Multiple R-squared:  0.9089, Adjusted R-squared:  0.8907
## F-statistic: 49.87 on 1 and 5 DF,  p-value: 0.0008803
# no war
model_war3
<-
lm
(B
~
Y,
data =
dataNowar)
summary
(model_war3)
##
## Call:
## lm(formula = B ~ Y, data = dataNowar)
##
## Residuals:
##  Min  1Q  Median  3Q  Max
## -0.37110 -0.14244  0.04391  0.13139  0.32759
##
## Coefficients:
##  Estimate Std. Error t value Pr(>|t|)
## (Intercept)  1.23088  0.14290  8.614 2.56e-05 ***
## Y  0.68669  0.01882  36.493 3.48e-10 ***
```
```text
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
##
## Residual standard error: 0.2385 on 8 degrees of freedom
## Multiple R-squared:  0.994,  Adjusted R-squared:  0.9933
## F-statistic:  1332 on 1 and 8 DF,  p-value: 3.485e-10
```

EXPLANATION Model 1 assumes a common slope, while Model 2/3 do not assume that. Implicitly Model 1 assumes the error term has the same distribution for both d=0 and d=1, while Model 2/3 do not assume that. The implicit or explicit assumptions on the error distributions affect the finitesample distribution of the estimators of intercepts and slopes.

### Winner Case -----

At the last board meeting of Winner Plc., the headquarters of a large multinational company, the issue was raised that women were being discriminated in the company, in the sense that the salaries were not the same for male and female executives. A quick analysis of a sample of 50 employees (of which 24 men and 26 women) revealed that the average salary for men was about 8,400 higher than for women. This seemed like a considerable difference, so it was decided that a further analysis of the company salaries was warranted.

The objective is to find out whether there is indeed a significant difference between the salaries of men and women, and whether the difference is due to discrimination or whether it is based on another determining factor.

```text
winner
<-
read_csv
(
"winner.csv"
)
## Rows: 50 Columns: 3
## ── Column specification ────────────────────────────────────────────────────────
## Delimiter: ","
## chr (1): gender
## dbl (2): salary, experience
##
## ℹ Use `spec()` to retrieve the full column specification for this data.
## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
glimpse
(winner)
# examine the data frame
## Rows: 50
## Columns: 3
## $ salary  <dbl> 79400, 67400, 66500, 72600, 63600, 74500, 76400, 67900, 616…
## $ gender  <chr> "male", "male", "male", "male", "male", "male", "male", "ma…
## $ experience <dbl> 16, 25, 15, 33, 16, 19, 32, 34, 1, 44, 7, 14, 33, 19, 24, 3…
```
### Relationship Salary - Gender ?

The data frame winner contains the salaries for the sample of 50 executives in the company. Can you conclude that there is a significant difference between the salaries of the male and female executives?

Let’s perform different types of analyses, and check whether they all lead to the same conclusion.

. Confidence intervals . Hypothesis ------- . Correlation analysis . Regression

```text
# Summary Statistics of salary by gender
favstats
(salary
~
gender,
data =
winner)
##  gender  min  Q1 median  Q3  max  mean  sd  n missing
## 1 female 45600 58500  62650 67900 76400 62576.92 7336.774 26  0
## 2  male 53100 66250  72400 76175 82000 71008.33 7235.295 24  0
ggplot
(winner,
aes
(
x =
salary,
fill =
factor
(gender)))
+
geom_histogram
(
bins =
10
)
+
facet_wrap
(
~
gender)
+
scale_fill_brewer
(
type =
'qual'
)
+
theme
(
legend.position =
'none'
)
+
geom_vline
(
data =
```
```text
ddply
(winner,
"gender"
, summarize,
wavg =
mean
(salary)),
aes
(
xintercept=
wavg),
color =
"red"
)
+
labs
(
x =
"Sarlary"
,
y =
""
)
# t-Critical values for 95% intervals for male (n=24) and female (n=26) salaries
qt
(
0.975
,
23
)
# t-critical for male (2.07)
## [1] 2.068658
qt
(
0.975
,
25
)
# t-critical for female (2.06)
## [1] 2.059539
# CIs 'by hand'
winner
%>%
group_by
(gender)
%>%
dplyr
::
summarise
(
```
```text
mean_salary =
mean
(salary),
sd_salary =
sd
(salary),
count =
n
(),
se_salary =
sd_salary
/
sqrt
(count),
t_critical =
qt
(
0.975
, count
-1
),
margin_of_error =
t_critical
*
se_salary,
salary_low_95 =
mean_salary
-
margin_of_error,
salary_high_95 =
mean_salary
+
margin_of_error,
)
%>%
#select fewer variables to show
dplyr
::
select
(gender, mean_salary, se_salary, t_critical, salary_low_95, salary_high_95)
## # A tibble: 2 × 6
##  gender mean_salary se_salary t_critical salary_low_95 salary_high_95
##  <chr>  <dbl>  <dbl>  <dbl>  <dbl>  <dbl>
## 1 female  62577.  1439.  2.06  59614.  65540.
## 2 male  71008.  1477.  2.07  67953.  74064.
```

We can also run a a hypothesis ----, assuming as a null hypothesis that the mean difference in salaries is zero, or that, on average, men and women make the same amount of money.

```text
t.----
(salary
~
gender,
data =
winner)
```
```text
##
##  Welch Two Sample t-----
##
## data:  salary by gender
## t = -4.0891, df = 47.78, p-value = 0.0001651
## alternative hypothesis: true difference in means between group female and group male is not
equal to 0
## 95 percent confidence interval:
##  -12577.686  -4285.134
## sample estimates:
## mean in group female  mean in group male
##  62576.92  71008.33
```

### Relationship Experience - Gender?

At the board meeting, someone raised the issue that there was indeed a substantial difference between male and female salaries, but that this was attributable to other reasons such as differences in experience. A questionnaire send out to the 50 executives in the sample reveals that the average experience of the men is approximately 21 years, whereas the women only have about 7 years experience on average (see table below).

```text
# Summary Statistics of experience by gender
favstats
(experience
~
gender,
data =
winner)
##  gender min  Q1 median  Q3 max  mean  sd  n missing
## 1 female  0  0.25  3.0 14.00  29  7.384615  8.51388 26  0
## 2  male  1 15.75  19.5 31.25  44 21.125000 10.91593 24  0
ggplot
(winner,
aes
(
x =
experience,
fill =
factor
(gender)))
+
geom_histogram
(
bins =
10
)
+
facet_wrap
(
~
gender)
+
scale_fill_brewer
(
```
```text
type =
'qual'
)
+
theme
(
legend.position =
'none'
)
+
geom_vline
(
data =
ddply
(winner,
"gender"
, summarize,
wavg =
mean
(experience)),
aes
(
xintercept=
wavg),
color =
"red"
)
+
labs
(
x =
"Experience"
,
y =
""
)
```

Based on this evidence, can you conclude that there is a significant difference between the experience of the male and female executives? Does your conclusion validate or endanger your conclusion about the difference in male and female salaries?

### Relationship Salary - Experience ?

Someone at the meeting argues that clearly, a more thorough analysis of the relationship between salary and experience is required before any conclusion can be drawn about whether there is any gender-based salary discrimination in the company.

```text
ggplot
(winner,
aes
(
x =
experience,
y =
salary))
+
geom_point
()
+
```
```text
geom_smooth
(
method =
"lm"
,
se =
F)
+
labs
(
x =
'Experience'
,
y =
'Salary'
,
title =
'Regression of Salary on Experience'
)
## `geom_smooth()` using formula = 'y ~ x'
```

### Check correlations between the data

```text
winner
%>%
ggpairs
()
## `stat_bin()` using `bins = 30`. Pick better value `binwidth`.
## `stat_bin()` using `bins = 30`. Pick better value `binwidth`.
```

### Regression: Salary on Experience

```text
model0
<-
lm
(salary
~
gender,
data =
winner)
summary
(model0)
##
## Call:
## lm(formula = salary ~ gender, data = winner)
##
## Residuals:
##  Min  1Q  Median  3Q  Max
## -17908.3  -4634.8  123.1  5316.7  13823.1
##
## Coefficients:
##  Estimate Std. Error t value Pr(>|t|)
```
```text
## (Intercept)  62577  1429  43.780  < 2e-16 ***
## gendermale  8431  2063  4.087 0.000165 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
##
## Residual standard error: 7288 on 48 degrees of freedom
## Multiple R-squared:  0.2581, Adjusted R-squared:  0.2427
## F-statistic:  16.7 on 1 and 48 DF,  p-value: 0.0001655
model1
<-
lm
(salary
~
experience,
data =
winner)
summary
(model1)
##
## Call:
## lm(formula = salary ~ experience, data = winner)
##
## Residuals:
##  Min  1Q Median  3Q  Max
## -13105  -2837  615  2862  11632
##
## Coefficients:
##  Estimate Std. Error t value Pr(>|t|)
## (Intercept) 58704.76  1107.81  52.99  < 2e-16 ***
## experience  566.47  60.65  9.34 2.26e-12 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
##
## Residual standard error: 5041 on 48 degrees of freedom
## Multiple R-squared:  0.6451, Adjusted R-squared:  0.6377
## F-statistic: 87.23 on 1 and 48 DF,  p-value: 2.257e-12
autoplot
(model1,
which=
1
:
3
)
+
theme_bw
()
# You can also do it manually
res
<-
resid
(model1)
# equivalently model1$residuals
```
```text
me
<-
mean
(res)
# calculate mean error, or mean residual
std
<-
sd
(res)
# calculate the SD of residuals. This should equal the 'Residual Standard Error' in the
regression summary
# You can also do it manually
ggplot
(model1,
aes
(
x=
fitted
(model1),
y=
resid
(model1)))
+
geom_point
()
+
geom_smooth
(
method=
"loess"
,
se =
FALSE
)
+
labs
(
x=
"Fitted"
,
y=
"Residuals"
,
title =
"Residuals vs Fitted"
)
+
theme_minimal
()
## `geom_smooth()` using formula = 'y ~ x'
#Histogram of the residuals vs a Normal distribution
gf_dhistogram
(
~
resid
(model1),
fill=
```
```text
"lightsteelblue3"
,
apha=
0.8
,
col=
TRUE
)
%>%
gf_dist
(
"norm"
,
mean =
me,
sd =
std,
col=
"red"
)
%>%
gf_labs
(
x=
"Residuals"
,
y=
"Density"
,
title =
"Distribution of residuals compared to a Normal distribution"
)
%>%
gf_theme
(
theme =
theme_minimal
())
## `stat_bin()` using `bins = 30`. Pick better value `binwidth`.
#QQ plot of the residuals
gf_qq
(
~
resid
(model1),
alpha=
0.8
,
col=
"royalblue2"
)
%>%
gf_labs
(
x =
"qnorm"
,
```
```text
y =
"resid(model1)"
)
%>%
gf_labs
(
x =
"Residuals"
,
y=
"Density"
,
title =
"QQ Plot of residuals"
)
%>%
gf_theme
(
theme =
theme_minimal
())
```

### Relationship Salary - Gender and Experience ?

Extend your analysis of the previous section to investigate whether there is salary discrimination based on gender or not.

### Multiple regression in R

To run a multiple regression model in R, use lm( Y ~ X1 + X2 + X3, data= .)

```text
model2
<-
lm
(salary
~
experience
+
gender,
data =
winner)
summary
(model2)
##
## Call:
## lm(formula = salary ~ experience + gender, data = winner)
##
## Residuals:
##  Min  1Q Median  3Q  Max
## -12974  -3073  1066  3042  11170
##
## Coefficients:
##  Estimate Std. Error t value Pr(>|t|)
## (Intercept) 58573.98  1140.47  51.360  < 2e-16 ***
## experience  542.07  75.26  7.203 4.03e-09 ***
## gendermale  983.22  1770.76  0.555  0.581
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
```
```text
##
## Residual standard error: 5078 on 47 degrees of freedom
## Multiple R-squared:  0.6474, Adjusted R-squared:  0.6324
## F-statistic: 43.14 on 2 and 47 DF,  p-value: 2.302e-11
car
::
vif
(model2)
## experience  gender
##  1.51753  1.51753
# If gender is a factor
cor
(
as.numeric
(
as.factor
(winner
$
gender)), winner
$
experience)
## [1] 0.5839817
```

Gender is correlated with experience, however upon running the official ---- with VIF we conclude that there is no multicollinearity issue.

### Improving the Model

Again at the meeting, someone was looking at the results of the analysis of salary versus experience, and said that it was to be expected that an employee with more experience than another employee would have a higher salary. However, he argued that the difference in salary between two people with 2 and 4 years experience would be higher than the difference in salary between two people with 26 and 28 years experience!

Can you find any indication that this is the case? If yes, how can you modify your analysis to take this into account?

The makeFun() function from the mosaic package can be used to display the predicted values from a regression model.

```text
#let us look at the scatterplot of experience on salary, and add a linear trendline
ggplot
(winner,
aes
(
x=
experience,
y =
salary))
```
```text
+
geom_point
()
+
geom_smooth
(
method=
"lm"
,
se=
FALSE
)
## `geom_smooth()` using formula = 'y ~ x'
#let us look at the scatterplot of experience on salary, coloured by gender
ggplot
(winner,
aes
(
x=
experience,
y =
salary,
colour=
gender))
+
geom_point
()
+
geom_smooth
(
method=
"lm"
,
se=
FALSE
)
## `geom_smooth()` using formula = 'y ~ x'
#Assuming a linear model...
predict_model1
<-
makeFun
(model1)
predict_model1
(
experience =
4
)
```
```text
##  1
## 60970.64
#calculate difference from 2 to 4 years of experience
imaginary_person
<-
data_frame
(
experience =
c
(
2
,
4
))
## Warning: `data_frame()` was deprecated in tibble 1.1.0.
## ℹ Please use `tibble()` instead.
## This warning is displayed once per session.
## Call `lifecycle::last_lifecycle_warnings()` to see where this warning was
## generated.
predict.lm
(model1, imaginary_person,
interval =
"prediction"
)
##  fit  lwr  upr
## 1 59837.70 49496.82 70178.58
## 2 60970.64 50661.39 71279.89
#calculate difference from 26 to 28 years of experience
imaginary_person
<-
data_frame
(
experience =
c
(
26
,
28
))
predict.lm
(model1, imaginary_person,
interval =
"prediction"
)
```
```text
##  fit  lwr  upr
## 1 73432.96 63091.39 83774.53
## 2 74565.90 64186.95 84944.85
#Obviously, there is no difference if we assume a linear model.
#We can create a scatterplot and use geom_smooth() without method="lm"
# to let R fit what it thinks looks like the best line
ggplot
(winner,
aes
(
x=
experience,
y =
salary))
+
geom_point
()
+
geom_smooth
(
se=
FALSE
)
## `geom_smooth()` using method = 'loess' and formula = 'y ~ x'
```

### Tranforming Expereince

```text
model3
<-
lm
(salary
~
sqrt
(experience),
data =
winner)
summary
(model3)
##
## Call:
## lm(formula = salary ~ sqrt(experience), data = winner)
##
## Residuals:
##  Min  1Q  Median  3Q  Max
## -9160.0 -3396.2  286.3  3095.1  9830.2
##
## Coefficients:
##  Estimate Std. Error t value Pr(>|t|)
## (Intercept)  54760.0  1183.6  46.27  < 2e-16 ***
## sqrt(experience)  3702.4  316.6  11.70 1.18e-15 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
```
```text
##
## Residual standard error: 4313 on 48 degrees of freedom
## Multiple R-squared:  0.7403, Adjusted R-squared:  0.7348
## F-statistic: 136.8 on 1 and 48 DF,  p-value: 1.176e-15
autoplot
(model3,
which=
1
:
3
)
+
theme_bw
()
```


[↑ Back to the source list](#source-documents)

---

<a name="source-4"></a>

## session5.Rmd

<small>File type: RMD · Reader pages 367–377 · [View source PDF](PDF%20Slides.pdf#page=367)</small>

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
library(ggrepel)
library(car)
library(plyr)
```

### Nonlinear Transformations

I provide 3 toy datasets of x and y variables.

### Data 1

```r
set.seed(123)
x <- c(1:10)
y <- 5 + 3*x^2 + rnorm(10, mean = 2, sd = 5)
data1 <- tibble(x, y) %>%
dplyr::select(y, x)
# Sometimes multiple R packages have functions with the same name. Use "dplyr::" to specify
the package that the function "select" belongs to.
# visualize the data and the fitted regression line
ggplot(data1, aes(x=x, y=y)) +
geom_point() +
geom_line() +
geom_smooth(method='lm', se=FALSE) +
labs(x="x", y="y")
# create an initial regression model between y and x
model1_data1 <- lm(y ~ x)
summary(model1_data1)
```

We can see that the first dataset looks like an x^2 relationship. Therefore perform the transformation and create a new variable, $z=x^2$ and re-run the linear regression:

```r
data1_transformed <- data1 %>%
dplyr::mutate(z = x^2) %>%
dplyr::select(y, z)
model2_data1 <- lm(y ~ z, data=data1_transformed)
```
```r
summary(model2_data1)
ggplot(data1_transformed, aes(x=z, y=y)) +
geom_point() +
geom_line() +
geom_smooth(method='lm', se=FALSE) +
labs(x="x^2", y="y")
```

We can see that the transformation improved the regression model fit (using R2) from 0.957 to 0.998.

### Data 2

```r
set.seed(123)
x <- c(1:10)
y <- 5 + 3*(1/x) + rnorm(10, mean = 0, sd = 0.15)
data2 <- tibble(x, y) %>%
dplyr::select(y, x) %>%
round(2)
# visualise the data and the fitted regression line
ggplot(data2, aes(x=x, y=y)) +
geom_point() +
geom_line() +
geom_smooth(method='lm', se=FALSE) +
labs(x="x", y="y")
# create an initial regression model between y and x
model1_data2 <- lm(y ~ x)
summary(model1_data2)
```

We can see that the second dataset looks like an 1/x relationship. Therefore perform the transformation and create a new variable, $z=1/x$ and re-run the linear regression:

```r
data2_transformed <- data2 %>%
dplyr::mutate(z = 1/x) %>%
dplyr::select(y, z)
model2_data2 <- lm(y ~ z, data=data2_transformed)
summary(model2_data2)
ggplot(data2_transformed, aes(x=z, y=y)) +
geom_point() +
geom_line() +
geom_smooth(method='lm', se=FALSE) +
labs(x="1/x", y="y")
```

We can see that the transformation improved the regression model fit (using R2) from 0.734 to 0.971.

### Data 3

```r
set.seed(123)
x <- c(1:10)
y <- 5 + 3*sqrt(x) + rnorm(10, mean = 0, sd = 0.15)
```
```r
data3 <- tibble(x, y) %>%
dplyr::select(y, x) %>%
round(2)
# visualise the data and the fitted regression line
ggplot(data3, aes(x=x, y=y)) +
geom_point() +
geom_line() +
geom_smooth(method='lm', se=FALSE) +
labs(x="x", y="y")
# create an initial regression model between y and x
model1_data3 <- lm(y ~ x)
summary(model1_data3)
```

We can see that the third dataset looks like an sqrt(x) relationship. Therefore perform the transformation and create a new variable, $z=\sqrt(x)$ and re-run the linear regression:

```r
data3_transformed <- data3 %>%
dplyr::mutate(z = sqrt(x)) %>%
dplyr::select(y, z)
model2_data3 <- lm(y ~ z, data=data3_transformed)
summary(model2_data3)
ggplot(data3_transformed, aes(x=z, y=y)) +
geom_point() +
geom_line() +
geom_smooth(method='lm', se=FALSE) +
labs(x="sqrt(x)", y="y")
```

We can see that the transformation improved the regression model fit (using R2) from 0.9624 to 0.9955.

### Crime

### ---------- Model 1 (Simple Linear Regression) -----------

```r
crime <- read_csv('beerhall.csv')
crime_model1 <- lm(criminals ~ public_houses, data = crime) # single x
crime$predicted <- predict(crime_model1)  # Y_hat values that will sit on the regression line
crime$residuals <- residuals(crime_model1) # error between Ys and Y_hats
summary(crime_model1)
crime_model1 %>%
autoplot(which = 1:3) +
theme_bw()
```

### ---------- Model 2 (Multiple Linear Regression) -----------

Let's evaluate all of the independent variables and add them into the model:
```r
crime_model2 <- lm(criminals ~ public_houses + school_attendance + worship_attendance, data =
crime)
summary(crime_model2)
```

Note that if we try to include worship_attendance instead of school_attendance, the result for its coefficient is still insignificant. Therefore worship_attendance will not be present in our final model.

```r
crime_model2_b <- lm(criminals ~ public_houses + worship_attendance, data = crime) # many xs
summary(crime_model2_b)
# remember that the correlation between worship_attendance and criminals is nearly 0
# therefore we do not expect it to form a good predictor of criminals in a regression.
```

### ---------- Model 3 (Multiple Linear Regression) -----------

```r
crime_model3 <- lm(criminals ~ public_houses + school_attendance, data= crime) # many xs
summary(crime_model3)
```

Residual analysis of model 3:

```r
crime_model3 %>%
autoplot(which = 1:3) +
theme_bw()
```

Compare valid models using huxreg() function that produces a table for ease of comparison.

```r
# compare the two models
huxtable::huxreg(crime_model1, crime_model3,
number_format = "%.3f",
bold_signif = 0.05,
statistics = c('adj.r.squared', 'sigma'))
# alternatively use c(NULL) to reveal all stats
```

On line 1 above I use comma separated models. On line 2 I use 3 significant figures to display the results. On line 3 I have added for convenience argument that will make all 95% significant coefficients bold. On line 4 we specify that we want to have adj R2 and the residual standard error displayed.

### Class Exercise: Multiple Linear Regression Prius Car Price

Let's load the data and create a few extra independent variables from the data that we already

have:

```r
prius <- read_csv("toyota_prius_jun18.csv")
prius <- prius %>%
mutate(engine = factor(engine), # turn it to a factor
car_age = 2018 - year)
```

You already have created the following model in the previous class:
```r
car_model1 <- lm(price ~ miles, data = prius)
car_model1 %>%
autoplot(which = 1:3) +
theme_bw()
```

Let's build multivariate models. Your task is to create the following multiple regression models to predict price:

- car_model2, with independent variables: miles, engine, car_age

- car_model3, with independent variables: miles, engine, car_age, miles*engine

- car_model4, with independent variables: 1/miles, engine, car_age, miles*engine

Compare the models and select the best one, giving reasoning. For the best model provide residual analysis and comment.

### Include More Independent Variables

```r
# Model 2: Xs: miles, engine, car_age
car_model2 <- lm(price ~ miles + engine + car_age, data = prius)
summary(car_model2)
```

### Include Interaction Term:

This means that the effect of mileage depends on engine size. If we have two explanatory variables, and the value of one (effect of mileage) depends on the other (engine size), then besides the two variables, we also introduce an interaction variable, which is the product of the two.

```r
# Model 3: Xs: miles, engine, car_age, miles*engine
prius_transformed1 <- prius %>%
mutate(engine_miles = as.integer(engine == 1798) * miles)
car_model3 <- lm(price ~ miles + engine + car_age + engine_miles, data = prius_transformed1)
# Note this is the same as running below as x*y, the x and y will be added automatically as
separate indep vars.
# model3 <- lm(price ~ car_age + miles*engine, data = prius)
summary(car_model3)
```

### Include Nonlinear Transformation

```r
# Prep data for Model4 by mutating miles
prius_transformed2 <- prius %>%
mutate(one_over_miles = 1 / miles,
engine_miles = as.integer(engine == 1798) * miles)
# Model 4: Xs: 1/miles, engine, car_age, miles*engine
car_model4 <- lm(price ~ one_over_miles + engine + car_age + engine_miles, data =
prius_transformed2)
summary(car_model4)
```
### Huxreg Table For Comparison!

It is much easier to compare results using the HuxReg Table:

```r
# Compare models 1,2,3,4
huxtable::huxreg(car_model1, car_model2, car_model3, car_model4,
number_format = "%.2f",
bold_signif = 0.05,
statistics = c('adj.r.squared', 'sigma'))
autoplot(car_model4, which = 1:3) +
theme_bw()
```

### Mutlicollinearity

The code library(car) and car::vif(model1) is used in R to assess multicollinearity in regression models by calculating the Variance Inflation Factor (VIF) for each predictor variable in the model.

Interpret the VIF values:

- VIF > 10: Indicates high multicollinearity, which could make your model unstable.

- VIF between 5 and 10: Moderate multicollinearity, something to keep an eye on.

- VIF < 5: Low or no multicollinearity, typically acceptable.

```r
model2 <- lm(criminals ~ public_houses + school_attendance + worship_attendance, data =
crime)
summary(model2)
car::vif(model2)
# cor(crime$worship_attendance, crime$school_attendance) # 0.60
```

Based on the correlation of 0.6 and the VIF values, you do not have a multicollinearity problem. While the correlation between school_attendance and worship_attendance is moderate, the VIF values suggest that multicollinearity is not significantly affecting the model. The worship_attendance is not statistically significant (p-value = 0.34819), indicating that it may not be a strong predictor in this model.

### Dummy Variables

```r
bonds <- read_csv('bonds.csv')
ggplot(bonds, aes(x = Y, y = B)) +
geom_point()
# regression of Bond price = Intercept + b1*GNP + b2*WAR + e
model_war1 <- lm(B ~ Y + W, data = bonds)
summary(model_war1)
ggplot(bonds, aes(x = Y, y = B)) +
scale_x_continuous(limits = c(0,13), expand = c(0, 0)) +
```
```r
scale_y_continuous(limits = c(0,12), expand = c(0, 0)) +
geom_point() +
labs(x = "Y, GNP ($ billions)", y = "B, Bond Price ($ hundred millions)",
title = "Effect of Dummy Variable, War") +
geom_text_repel(data = bonds, mapping = aes(label = Year))
```

Note this is not the same as running separate regressions on war and no war data

```r
dataWar <- filter(bonds, W == 1)
dataNowar <- filter(bonds, W == 0)
# war
model_war2 <- lm(B ~ Y, data = dataWar)
summary(model_war2)
# no war
model_war3 <- lm(B ~ Y, data = dataNowar)
summary(model_war3)
```

EXPLANATION Model 1 assumes a common slope, while Model 2/3 do not assume that. Implicitly Model 1 assumes the error term has the same distribution for both d=0 and d=1, while Model 2/3 do not assume that. The implicit or explicit assumptions on the error distributions affect the finitesample distribution of the estimators of intercepts and slopes.

### Winner Case -----

At the last board meeting of Winner Plc., the headquarters of a large multinational company, the issue was raised that women were being discriminated in the company, in the sense that the salaries were not the same for male and female executives. A quick analysis of a sample of 50 employees (of which 24 men and 26 women) revealed that the average salary for men was about 8,400 higher than for women. This seemed like a considerable difference, so it was decided that a further analysis of the company salaries was warranted.

The objective is to find out whether there is indeed a significant difference between the salaries of men and women, and whether the difference is due to discrimination or whether it is based on another determining factor.

```r
winner <- read_csv("winner.csv")
glimpse(winner) # examine the data frame
```

### Relationship Salary - Gender ?

The data frame `winner` contains the salaries for the sample of 50 executives in the company. Can you conclude that there is a significant difference between the salaries of the male and female executives?

Let's perform different types of analyses, and check whether they all lead to the same conclusion.

. Confidence intervals . Hypothesis ------- . Correlation analysis . Regression

```r
# Summary Statistics of salary by gender
favstats (salary ~ gender, data = winner)
ggplot(winner, aes(x = salary, fill = factor(gender))) +
geom_histogram(bins = 10) +
```
```r
facet_wrap(~ gender) +
scale_fill_brewer(type = 'qual') +
theme(legend.position = 'none') +
geom_vline(data = ddply(winner, "gender", summarize, wavg = mean(salary)),
aes(xintercept=wavg), color = "red") +
labs(x = "Sarlary", y = "")
# t-Critical values for 95% intervals for male (n=24) and female (n=26) salaries
qt(0.975, 23)  # t-critical for male (2.07)
qt(0.975, 25)  # t-critical for female (2.06)
# CIs 'by hand'
winner %>%
group_by(gender) %>%
dplyr::summarise(
mean_salary = mean(salary),
sd_salary = sd(salary),
count = n(),
se_salary = sd_salary / sqrt(count),
t_critical = qt(0.975, count-1),
margin_of_error = t_critical * se_salary,
salary_low_95 = mean_salary - margin_of_error,
salary_high_95 = mean_salary + margin_of_error,
) %>%
#select fewer variables to show
dplyr::select(gender, mean_salary, se_salary, t_critical, salary_low_95, salary_high_95)
```

We can also run a a hypothesis ----, assuming as a null hypothesis that the mean difference in salaries is zero, or that, on average, men and women make the same amount of money.

```r
t.----(salary ~ gender, data = winner)
```

### Relationship Experience - Gender?

At the board meeting, someone raised the issue that there was indeed a substantial difference between male and female salaries, but that this was attributable to other reasons such as differences in experience. A questionnaire send out to the 50 executives in the sample reveals that the average experience of the men is approximately 21 years, whereas the women only have about 7 years experience on average (see table below).

```r
# Summary Statistics of experience by gender
favstats (experience ~ gender, data = winner)
ggplot(winner, aes(x = experience, fill = factor(gender))) +
geom_histogram(bins = 10) +
facet_wrap(~ gender) +
scale_fill_brewer(type = 'qual') +
theme(legend.position = 'none') +
geom_vline(data = ddply(winner, "gender", summarize, wavg = mean(experience)),
aes(xintercept=wavg), color = "red") +
labs(x = "Experience", y = "")
```

Based on this evidence, can you conclude that there is a significant difference between the experience of the male and female executives? Does your conclusion validate or endanger your conclusion about the difference in male and female salaries?
### Relationship Salary - Experience ?

Someone at the meeting argues that clearly, a more thorough analysis of the relationship between salary and experience is required before any conclusion can be drawn about whether there is any gender-based salary discrimination in the company.

```r
ggplot(winner, aes(x = experience, y = salary)) +
geom_point() +
geom_smooth(method = "lm", se = F) +
labs(x = 'Experience', y = 'Salary', title = 'Regression of Salary on Experience')
```

Check correlations between the data

```r
winner %>% ggpairs()
```

Regression: Salary on Experience

```r
model0 <- lm(salary ~ gender, data = winner)
summary(model0)
model1 <- lm(salary ~ experience, data = winner)
summary(model1)
autoplot(model1, which=1:3) +
theme_bw()
# You can also do it manually
res <- resid(model1) # equivalently model1$residuals
me  <- mean(res)  # calculate mean error, or mean residual
std <- sd(res)  # calculate the SD of residuals. This should equal the 'Residual Standard
Error' in the regression summary
# You can also do it manually
ggplot(model1, aes(x=fitted(model1), y= resid(model1)))+
geom_point()+
geom_smooth(method="loess", se = FALSE)+
labs(x="Fitted", y="Residuals", title = "Residuals vs Fitted") +
theme_minimal()
#Histogram of the residuals vs a Normal distribution
gf_dhistogram(~resid(model1), fill="lightsteelblue3", apha=0.8, col=TRUE) %>%
gf_dist("norm", mean = me, sd = std, col="red") %>%
gf_labs(x="Residuals", y="Density", title = "Distribution of residuals compared to a Normal
distribution") %>%
gf_theme(theme = theme_minimal())
#QQ plot of the residuals
gf_qq(~resid(model1), alpha=0.8, col="royalblue2") %>%
gf_labs(x = "qnorm", y = "resid(model1)") %>%
gf_labs(x = "Residuals", y="Density", title = "QQ Plot of residuals") %>%
gf_theme(theme = theme_minimal())
```

### Relationship Salary - Gender and Experience ?

Extend your analysis of the previous section to investigate whether there is salary discrimination based on gender or not.
Multiple regression in R

To run a multiple regression model in R, use `lm( Y ~ X1 + X2 + X3, data= .)`

```r
model2 <- lm(salary ~ experience + gender, data = winner)
summary(model2)
car::vif(model2)
# If gender is a factor
cor(as.numeric(as.factor(winner$gender)), winner$experience)
```

Gender is correlated with experience, however upon running the official ---- with VIF we conclude that there is no multicollinearity issue.

### Improving the Model

Again at the meeting, someone was looking at the results of the analysis of salary versus experience, and said that it was to be expected that an employee with more experience than another employee would have a higher salary. However, he argued that the difference in salary between two people with 2 and 4 years experience would be higher than the difference in salary between two people with 26 and 28 years experience!

Can you find any indication that this is the case? If yes, how can you modify your analysis to take this into account?

The `makeFun()` function from the `mosaic` package can be used to display the predicted values from a regression model.

```r
#let us look at the scatterplot of experience on salary, and add a linear trendline
ggplot(winner, aes(x=experience, y = salary))+
geom_point()+
geom_smooth(method="lm", se=FALSE)
#let us look at the scatterplot of experience on salary, coloured by gender
ggplot(winner, aes(x=experience, y = salary, colour=gender))+
geom_point()+
geom_smooth(method="lm", se=FALSE)
#Assuming a linear model...
predict_model1 <- makeFun(model1)
predict_model1(experience = 4)
#calculate difference from 2 to 4 years of experience
imaginary_person <- data_frame(experience = c(2,4))
predict.lm(model1, imaginary_person, interval = "prediction")
#calculate difference from 26 to 28 years of experience
imaginary_person <- data_frame(experience = c(26,28))
predict.lm(model1, imaginary_person, interval = "prediction")
#Obviously, there is no difference if we assume a linear model.
#We can create a scatterplot and use geom_smooth() without method="lm"
# to let R fit what it thinks looks like the best line
ggplot(winner, aes(x=experience, y = salary))+
```
```r
geom_point()+
geom_smooth(se=FALSE)
```

### Tranforming Expereince

```r
model3 <- lm(salary ~ sqrt(experience), data = winner)
summary(model3)
autoplot(model3, which=1:3) +
theme_bw()
```


[↑ Back to the source list](#source-documents)

---

<a name="source-5"></a>

## beerhall.csv

<small>File type: CSV · Reader pages 378–379 · [View source PDF](PDF%20Slides.pdf#page=378)</small>

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

<a name="source-6"></a>

## bonds.csv

<small>File type: CSV · Reader pages 380–380 · [View source PDF](PDF%20Slides.pdf#page=380)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

> Data preview (up to six records and twelve columns); the full CSV remains in the original files.

Year

B

Y

W

1933

2.6

2.4

0

1934

3

2.8

0

1935

3.6

3.1

0

1936

3.7

3.4

0

1937

3.8

3.9

0

1938

4.1

4

0

</details>


[↑ Back to the source list](#source-documents)

---

<a name="source-7"></a>

## toyota_prius_jun18.csv

<small>File type: CSV · Reader pages 381–382 · [View source PDF](PDF%20Slides.pdf#page=381)</small>

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

<a name="source-8"></a>

## winner.csv

<small>File type: CSV · Reader pages 383–383 · [View source PDF](PDF%20Slides.pdf#page=383)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

> Data preview (up to six records and twelve columns); the full CSV remains in the original files.

salary

gender

experience

79400

male

16

67400

male

25

66500

male

15

72600

male

33

63600

male

16

74500

male

19

</details>


[↑ Back to the source list](#source-documents)

---

