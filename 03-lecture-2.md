# Lecture 2

**Distributions, sampling and uncertainty**

[← All chapters](README.md) · [Original PDF](PDF%20Slides.pdf#page=92)

## Overview

- Describing probability distributions: location, spread, skewness and kurtosis.
- Normal and standard normal distributions, z-scores, the sampling distribution and the central limit theorem.
- Confidence intervals, standard error, sample size and the t-distribution.

## Source documents

1. [session2_slides_pre_class.pdf](#source-1) — PDF, reader page 93
2. [session2_slides_post_class.pdf](#source-2) — PDF, reader page 119
3. [session2.Rmd](#source-3) — RMD, reader page 150
4. [movies.csv](#source-4) — CSV, reader page 160

---

<a name="source-1"></a>

## session2_slides_pre_class.pdf

<small>File type: PDF · Reader pages 93–118 · [View source PDF](PDF%20Slides.pdf#page=93)</small>

<small>Source Page 1 of 63</small>

### Lecture 2

Dr Helen Wang |

<small>Source Page 2 of 63</small>

### What is your best guess?

<small>Source Page 3 of 63</small>

### Uncertainty is challenging

<small>Source Page 4 of 63</small>

### Weeks 1-6 Outline

Week 01 | Exploratory Data Analysis

Week 02 | Statistics Foundation

Week 03 | Hypothesis -------

Week 04 | Regression, Part I

Week 05 | Regression, Part II

Week 06 | Risk Analysis, Part I

<small>Source Page 5 of 63</small>

01 | Distribution Parameters 02 | Normal and Standard Normal Distributions 03 | Sampling: Sampling Error and Standard Error 04 | Central Limit Theorem 05 | Confidence Intervals and Sample Size

Statistics Foundation
<small>Source Page 6 of 63</small>

### Nomenclature

Population mean: μ Sample mean: x̄

Population standard deviation: σ Sample standard deviation: s

Random variable: X Particular observation: x

Random variable of a Standard Normal: Z Particular observation of a Standard Normal (also known as ‘z-critical value’): z

Cumulative Density Function of Standard Normal: Φ z

Probability random variable Z takes on a value less than or equal to z: PZ≤z

Standard Error: SE

Parameter of t-distribution (also known as ‘degrees of freedom’): υ t-critical value: t

<small>Source Page 7 of 63</small>

01 | Distribution Parameters 02 | Normal and Standard Normal Distributions 03 | Sampling: Sampling Error and Standard Error 04 | Central Limit Theorem 05 | Confidence Intervals and Sample Size

Statistics Foundation

<small>Source Page 8 of 63</small>

### Probability Distributions

Definition

Probability Distribution:

Let’s roll dice!

- If an infinite number of observations was obtained, what would the frequency of data

be like?

- Expression that describes the relative frequency for every possible outcome or a range

of outcomes.

- Represents the real-world model “well enough” – even though nothing in the real world

is exactly distributed as the suspected probability distribution.

Describing Probability Distributions

- Shape: symmetry, modality, skewness
- Central Tendency: estimate of a typical observation in the distribution (mean, median,

mode)

- Spread: measure of variability in a distribution (range, variance, standard deviation,

IQR)

- Unusual Observations: observations that standout from the rest of the data that may

be suspected outliers

<small>Source Page 9 of 63</small>

### Describing Probability Distributions: Box Plot

Example: Box Plot of DJI returns

<small>Source Page 10 of 63</small>

### Unusual Observations

mean sd p0 p25 p50 p75 p100 169 28.3 1.78 166 174 178 191

mean sd p0 p25 p50 p75 p100

176. 9.06 160 169 176 183 203

After removing the outliers

Adult Height Distribution By Gender

<small>Source Page 11 of 63</small>

### Distribution Parameters

Central Tedency (1st Moment)

- Mean: 1

n xi typically used when

nσi=1

number of outliers is low and distribution is symmetrical

- Median: middle reading when data is ordered (50th percentile); typically used when

data is skewed

- Mode: most frequent reading; typically used for categorical data and data with more

than one peak
<small>Source Page 12 of 63</small>

### Income Distribution UK

Four highlighted sections of the distribution

- Benefits reliant individuals

- Low Middle Income (LMI)

- Higher Income

- 200K+

Q: What measure should be used to report the central tendency of this distribution?

A:

<small>Source Page 13 of 63</small>

### Income Distribution UK

Four highlighted sections of the distribution

- Benefits reliant individuals

- Low Middle Income (LMI)

- Higher Income

- 200K+

median

mean

Q: What measure should be used to report the central tendency of this distribution?

A: We will use the median since the distribution is skewed (right skewed in this case)

Income is typically not symmetric and is often skewed to the right.

<small>Source Page 14 of 63</small>

### Distribution Parameters

Central Tedency (1st Moment)

- Mean: 1

n xi typically used when

nσi=1

number of outliers is low and distribution is symmetrical
- Median: middle reading when data is ordered (50th percentile); typically used when

data is skewed

- Mode: most frequent reading; typically used for categorical data and data with more

than one peak

```r
Spread (2nd Moment)
```

- Mean Absolute Deviation (MAD) = 1

n xi−x̄

nσi=1

- Variance = 1

```r
n(xi−x̄)2
```

nσi=1

- Standard Deviation (SD) = Var

- Coefficient of Variation (CV) = SD

mean

- Range = largest – smallest reading

- Interquartile Range (IQR) = upper quartile – lower

quartile

<small>Source Page 15 of 63</small>

### Higher Moments

```r
Skewness (3rd Moment)
```

- Measure of asymmetry : a perfectly symmetrical distribution has skewness of 0.

- Positive Skew tail pointing to high values (body of the distribution is to the left)

- Negative Skew tail pointing to low values (body of the distribution is to the right)

```r
Kurtosis (4th Moment)
```

- Measure of heaviness of the tails: measures the peakedness of a distribution

- Leptokurtic : sharper peak, heavier tails, more

outliers.

- Platykurtic : flatter top, light tails, fewer
outliers.

<small>Source Page 16 of 63</small>

### Skewness: Right and Left

Rightskewed

Leftskewed

If coefficient of skewness is in the (-1,1) range, distribution is roughly bell-shaped and symmetrical.

<small>Source Page 17 of 63</small>

### Kurtosis: Heaviness of Tails

Excess Kurtosis = 0 Excess Kurtosis > 0 Excess Kurtosis < 0

<small>Source Page 18 of 63</small>

01 | Distribution Parameters 02 | Normal and Standard Normal Distributions 03 | Sampling: Sampling Error and Standard Error 04 | Central Limit Theorem 05 | Confidence Intervals and Sample Size

Statistics Foundation

<small>Source Page 19 of 63</small>

### Properties of Normal Distribution

Key Features

- Symmetric: scores are concentrated in the middle.

Skewness = 0, Kurtosis (excess) = 0

- Parameters: distribution can be described with the location (mean) and scale

(variance) parameters.

- Empirical rule for Normal Distributions: how likely is it to find a datapoint within

certain number of standard deviations from the mean?

χ Three-Sigma Rule

68% of the data lies within one standard deviation (±0.99σ) of the mean 95% of the data lies within two standard deviations (±1.96σ) of the mean 99.7% of the data lies within three standard deviations (±2.97σ) of the mean
<small>Source Page 20 of 63</small>

### Example: Normality Assumption

Pizza Delivery Times

Assuming Normally Distributed delivery times, the owner of Val’s Pizza decided to run an experiment. He found that sample mean delivery time was 30min and sample variance was 25min.

Q: Given this knowledge what range of delivery times can customers expect 68%, 95%, 99.7% of the time?

A:

<small>Source Page 21 of 63</small>

### Example: Normality Assumption

Pizza Delivery Times

Assuming Normally Distributed delivery times, the owner of Val’s Pizza decided to run an experiment. He found that sample mean delivery time was 30min and sample variance was 25min.

Q: Given this knowledge what range of delivery times can customers expect 68%, 95%, 99.7% of the time?

A:

68% of deliveries are 30min ± 1 ∗5min = 25-35 min 95% of deliveries are 30min ± 2 ∗5min = 20-40 min 99.7% of deliveries are 30min ± 3 ∗5min = 15-45 min

<small>Source Page 22 of 63</small>

### Standard Normal Distribution

z-score: number of standard deviations an observation falls above or below mean.

Z= X−μ

σ Key Features:

- A special case of the Normal Distribution where µ = 0 and σ= 1 i.e. Z∼N(µ = 0, σ2 =

1).

- Creates a common scale so you can access and compare different data without

depending on the specific unit it was measured in

- If population parameters are not known, use sample statistics, i.e., x̄and s.
- There is a 99.7% chance of being within ±2.97σof the mean, i.e. most values are

contained within [-3,+3]

<small>Source Page 23 of 63</small>

### Creating z-scores in R

Find z-values for return:

Each z is obtained as:

```r
data <- data %>% mutate(ret_z = (ret - mean(ret)) / sd(ret))
```

return~ N(0.913, 14.22)

Standardize 68%

13.3 0.913 15.1 X

zi= xi−0.913

14.2

return_z~ N(0, 1)

68%

Z

-1 0 1

<small>Source Page 24 of 63</small>

### Returns vs. Return z-Scores

In reality, the distribution is not quite Normal, therefore we use it as an approximation of the true distribution.

<small>Source Page 25 of 63</small>

### Cumulative Density Function

Cumulative Distribution Function (CDF) of a Standard Normal distribution, Φ z , provides the probability, p, that a Standard Normally distributed random variable (r.v.) Z, that has µ = 0 and σ= 1, is less than or equal to a particular value z

Φ z= PZ< z= PZ≤z

where PZ≤z equivalently:
PZ≤z= PZ≤X−μ

σ

Φ 0 is 0.5 for all symmetric distributions.

The CDF of a Standard Normal is available through a table or using mosaic::xpnorm() function in R.

Q: what is Φ 0 =?

<small>Source Page 26 of 63</small>

### Obtaining z-value in R

```r
p <- xpnorm(1.96, mean = 0, sd = 1) So far, we have used the above function to find the
probability of Z< z.
```

z= 1.96

p= ?

If X ~ N(0, 1), then P(X <= 1.96) = P(Z <= 1.96) = 0.975 P(X > 1.96) = P(Z > 1.96) = 0.025

```r
z <- qnorm(0.975, mean = 0, sd = 1) Provides the inverse operation, i.e. given a particular
probability of Z< z, what is the corresponding value z?
```

z=?

p= 0.975

[1] 1.96

<small>Source Page 27 of 63</small>

z-value one more decimal place 0.00 and 0.09

Increase

z-value between 0.0 and 3.0

e.g. PZ≤2.54 = 0.9945

Increase
<small>Source Page 28 of 63</small>

### Negative z

The table provides probability for z values from 0.00 to 3.00, PZ≤z (see next slide).

Therefore, for a negative value of z, we will use symmetry

Φ −z= 1 −Φ z

Φ z

<small>Source Page 29 of 63</small>

z-value one more decimal place 0.00 and 0.09

Increase

z-value between 0.0 and 3.0

e.g. PZ≤−2.54 = 1- PZ≤2.54 =1-0.9945 =0.0055

Increase

<small>Source Page 30 of 63</small>

### ZTel’s HR Hiring Policy:

Sample Statistics:

HR want to calculate the percentage of applicants who are automatic accepts and rejects.

- Let’s work with an example hiring policy.

- All applicants take a ----, and their hire or no-hire decision depends partly on the

results of the ----.

- Sample of past applicants and their hire decision

results have been collected.

- The applicants scores are Normally distributed with mean 525 and standard deviation

55.

Hiring Policy occurs in 2 phases:

- First phrase separates all applicants into three categories:

- automatic accepts with ---- score >= 600

- automatic rejects with ---- score <= 425

- “maybes”
- Second phase takes all ”maybes” and uses their previous job experience, special

talents and other factors as hiring criteria.

<small>Source Page 31 of 63</small>

### Why Convert Normal to Standard Normal?

Advantage of using z-values:

Any Normal distribution can be converted to Standard Normal, i.e. x observations converted to z-scores in range of approx. [-3, 3]. This results in:

- Values on a consistent scale irrespective of the original parameters

- Ability to use a table to find the probabilities associated with events, P(Z< z)

- Use of statistical methods that rely on properties of Standard Normal distribution, e.g.

Confidence Intervals, Hypothesis -------, Regression Parameters Estimation

- Easier understanding of how many σ a value is away from the mean, since z∗σ= z∗1

= z

<small>Source Page 32 of 63</small>

01 | Distribution Parameters 02 | Normal and Standard Normal Distributions 03 | Sampling: Sampling Error and Standard Error 04 | Central Limit Theorem 05 | Confidence Intervals and Sample Size

Statistics Foundation

<small>Source Page 33 of 63</small>

### Inferential Statistics

Descriptive Statistics:

- Describe the whole population (everyone we are interested in) – typically difficult to

obtain.

- Properties calculated (mean, standard deviation) are called parameters (the TRUTH).

- Population parameters refer to the perfect knowledge; we reserve Greek letters (μ, σ)

for them.

Inferential Statistics:

- Use a (random) sample to infer unknown population

parameters.
- Properties calculated are called sample statistics, e.g.

sample mean, x̄, sample standard deviation, s, which are used to estimate parameters of the population (i.e. make an inference).

- Different samples will typically have different sample

statistics.

- Applications using sampling: Finance, Healthcare,

Politics, Quality Control.

- Why sample? Cost efficiency, -----to-distruction,

Reduce risk to patients.

<small>Source Page 34 of 63</small>

### Statistics is a Science of Inference

Statistical Inference:

- Predict and forecast values of population parameters.

- ---- hypothesis about values of population parameters.

- Make decisions.

- Challenge: do this based on sample statistics derived from limited and incomplete

sample information.

Make generalizations about the characteristics of a population...

On the basis of observations of a sample, a part of a population.

<small>Source Page 35 of 63</small>

### Sampling Error

We are interested in the true mean of a population, μ.

Since populations are difficult to collect data on, we use sample statistics (sample mean, x̄) as point estimate for the unknown true population parameter.

Sample statistics vary from sample to sample due to sampling error, an error arising from the unrepresentativeness of sample taken (from observing a sample instead of whole population).

Quantifying sampling error (how sample statistics vary from sample to sample) provides a way to estimate the margin of error associated with our point estimate.

Sampling Error Example:

Assume population mean is unknown, and we want to get an estimate on it. Take a sample of size n = 5.
Population: μ= 32.0, σ= 3.3

x̄= 31.6 x̄= 33.0 x̄= 35.2

We see variation in sample means.

<small>Source Page 36 of 63</small>

### Quantifying Sampling Error

Measuring Variability Of Sample Statistic:

Standard Error measures the variability of a sample statistic from the true population parameter.

Standard Error Of Sample Mean

- measures the variability of a sample mean from the true population mean.

- represents the standard deviation of the sampling distribution of the sample mean.

x̄3

x̄1

Sampling distribution

x̄2

Standard Error (SE) Calculation:

For sample size n, the standard error of the sample mean is measured using the standard deviation of the population (if known), σ:

SE = σ

n

if not known use sample standard deviation, s:

SE = s

n

തX ~ Nμ, σ2

n

<small>Source Page 37 of 63</small>

### Standard Deviation vs. Standard Error

Standard Error (SE):

- SE is the standard deviation of the distribution of തX
Standard Deviation:

- Population standard deviation, σ

- Sample standard deviation, s

- തX ~ Nμ, σ2

Measures the amount of variability within a single dataset (amount of variation of individual data points).

Measures the amount of variability of a sample statistic (sample mean) across different samples from the same population.

n xi−μ2

σ= σi=1

n

Standard Error of Sample Mean (population standard

deviation known): SE = σ

n xi−x̄2

σi=1

s=

n−1

Standard Error of Sample Mean (population standard

deviation not known): SE = s

n and SE is just the name for the std dev of

this distribution i.e. σ

n

n

<small>Source Page 38 of 63</small>

01 | Distribution Parameters 02 | Normal and Standard Normal Distributions 03 | Sampling: Sampling Error and Standard Error 04 | Central Limit Theorem 05 | Confidence Intervals and Sample Size

Statistics Foundation
<small>Source Page 39 of 63</small>

### Central Limit Theorem

Start with a random variable X that belongs to some (any) distribution with known mean μ and std dev σ.

Obtain a large sample n of independent observations of a random variable X and find the sample mean x̄.

Central Limit Theorem states that: the distribution of sample mean, തX, will approach a Normal distribution as sample size n increases (n≥30), with mean μ and standard deviation σ

n, i.e.,

തX ~ Nμ, σ2

n.

Note: standard deviation of the distribution of sample means is known as the Standard Error,

σ

n.

Sampling distribution of the sample mean

σ2

r.v. തX ~Nμ,

n

Population distribution r.v. X ~ dist(μ, σ)

Simulation: https://onlinestatbook.com/stat_sim/samp ling_dist/

<small>Source Page 40 of 63</small>

### Central Limit Theorem Illustration

Distribution of sample mean tends to a Normal Distribution, and its dispersion is given by CLT.

Any starting population distribution

<small>Source Page 41 of 63</small>

### Pen and Paper Exercise

- Is the following statement True or False? “The Probability obtained from the Standard

Normal CDF evaluated at z value of 0 is 1, i.e. Φ(0) = 1”.
- The population mean and SD of the weight of coffee bags from a supplier are 1.5kg

and 0.1kg.

Assume an initial sample was ordered of 50 bags of coffee and weighed them for quality control. What is the distribution of the sample mean of the weight for the coffee bags?

- A random variable X has a uniform distribution with a population mean 35 and popu‐

lation std dev 4.7 both known to you. A random sample of 105 observations is taken from the distribution of X. The sample mean was found to be 33.8 and sample SD 6.3. Is the following statement correct: “In accordance with CLT you can conclude that the distribution of the sample mean is approximately Normal with parameters:

തX~N33.8, 6.3

<small>Source Page 42 of 63</small>

01 | Distribution Parameters 02 | Normal and Standard Normal Distributions 03 | Sampling: Sampling Error and Standard Error 04 | Central Limit Theorem 05 | Confidence Intervals and Sample Size

Statistics Foundation

<small>Source Page 43 of 63</small>

### Motivation: Communicating Uncertainty

Example, Apricot Company:

- You have recently joined the marketing department of Apricot, a mobile phone

competitor to iPhone.

- Your task is to find out how much people are willing to pay (WTP) on average for your

company’s new mobile phone, which is thinner and lighter than the iPhone.

- You conduct a quick survey and ask n= 100 people for their WTP and find that the

average amount is £200 (i.e. x̄= 200)

Task:

- Assumption: the amount people are willing to pay is approximately Normally

distributed (by the CLT).

- Assumption: population standard deviation of the amount is known to be £50 (i.e. σ=

50); in practice we will need to estimate it, but for now we assume it is given.

- You know that the true WTP is not likely to be exactly £200. How can you communicate

the uncertainty behind your estimate?
<small>Source Page 44 of 63</small>

### Confidence Interval Approximation

Why form Confidence Intervals?

Problem: often we don’t know the population mean, μ.

Solution: use sample mean and make an inference about the population mean.

Inference:

- We report an interval within which we are 95% confident that the true population

mean resides.

- Since distribution of sample means is Normal, and we want to be 95% certain, we use

properties of the Normal dist. to establish the confidence interval.

How to From Confidence Intervals?

Sample means distribution is Normal തX ~ Nμ, σ2

n,

σ

i.e. the distribution’s standard deviation is

n which

is also known as the Standard Error.

We can form an interval around the sample mean using the information about the margin of error (i.e. the Standard Error), using the following equation:

x̄ ± z∗Standard Error

What is the rational for doing this? We want to capture 95% body of the Normal Distribution, i.e. be 95% certain.

<small>Source Page 45 of 63</small>

### Confidence Interval Approximation

Confidence Interval (CI) is a range of values derived from a sample that is expected to contain the true population parameter μ.

- CI is expressed with a level of confidence, that is typically expressed as a percentage,

e.g. 95%.

- Level of confidence means if we were to take many samples and construct a CI for

each, approx. 95% of them would contain the true parameter.

CI Formula:

Point Estimate ± Margin of Error =
x̄ ± z∗Standard Error where z-value depends on the level of confidence.

Example: 95% Confidence Interval To build a CI around sample mean which leaves us 95% confident, we need to select the value of z such that in total 5% is left in the tails, i.e. z= 1.96

95% 2.5% 2.5%

x̄ – 1.96×SE x̄ x̄ + 1.96×SE

<small>Source Page 46 of 63</small>

### Establishing z-value for CI

```r
z <- qnorm(0.975, mean = 0, sd = 1)
```

The Quantile function qnrom() returns the zvalue corresponding to the specified probability p from the equation P(Z< z) = p.

If we would like 95% probability to be left in the body of the distribution, that means we need 2.5% to be left in each tail.

The qnorm() function returns z-value corresponding to the probability to the left of the z-value. Therefore p=0.975 is should be used.

z= 1.96

[1] 1.96

Thus, we can form a 95% CI using: x̄ ± 1.96×SE

<small>Source Page 47 of 63</small>

### Example CI Probabilities and z-values

The following probabilities would need to be specified to obtain the correct z-values for given confidence interval levels. All you must focus on is how much probability is left in the right tail:

Example:

You are given the following graph, where the body of the distribution contains 98% probability.

Q: What CI level does this correspond to?

- 90% CI

```r
z <- qnorm(0.95, mean = 0, sd = 1)
```

- 95% CI
```r
z <- qnorm(0.975, mean = 0, sd = 1)
```

- 98% CI

```r
z <- qnorm(0.99, mean = 0, sd = 1)
```

- 99% CI

```r
z <- qnorm(0.995, mean = 0, sd = 1)
```

<small>Source Page 48 of 63</small>

### CI for Large Samples, n≥30

Known Population Standard Deviation Assume unknown population mean.

Construct 95% CI:

x̄± 1.96 σ

n

Standard Error (SE)

x̄ is the sample average σ original population std dev

95%

Unknown Population Standard Deviation Assume unknown population mean.

Construct 95% CI:

x̄± 1.96 s

n

Standard Error (SE)

x̄ is the sample average s sample std dev; can be found in R using sd(), the function calculates the following equation:

n xi−x̄2

s= σi=1

n−1
<small>Source Page 49 of 63</small>

### Task: Communicating Uncertainty

Example, Apricot Company:

- You have recently joined the marketing department of Apricot, a mobile phone

competitor to iPhone.

- Your task is to find out how much people are willing to pay (WTP) on average for your

company’s new mobile phone, which is thinner and lighter than the iPhone.

- You conduct a quick survey and ask n = 100 people for their WTP and find that the

average amount is £200 (i.e. x̄= 200)

Task:

- Assumption: the amount people are willing to pay is approximately Normally

distributed (by the CLT).

- Assumption: population standard deviation of the amount is known to be £50 (i.e. σ=

50); in practice we will need to estimate it, but for now we assume it is given.

- You know that the true WTP is not likely to be exactly £200. How can you communicate

the uncertainty behind your estimate?

<small>Source Page 50 of 63</small>

### Sample Size

<small>Source Page 51 of 63</small>

### CI Interpretation

Confidence Intervals are like a net: if we took 100 samples, on average we expect 95 of those intervals to contain the true population parameter. Tempting, but wrong, to say “We’re 95% sure that the population parameter is X”.

95%

2.5% 2.5%

True mean

μ−2 × SE μ μ+2 × SE
<small>Source Page 52 of 63</small>

### Pen and Paper Exercise

With your classmate next to you, discuss the following:

- Assuming the population of interest is approximately normally distributed, construct a

95% confidence interval estimate for the population mean given the following values: x̄= 18.4, s= 4.2, n= 50

- What is the interpretation of this 95% confidence interval?

<small>Source Page 53 of 63</small>

### CI for Large Samples, n≥30

Known Population Standard Deviation Assume unknown population mean.

Construct 95% CI:

x̄± 1.96 σ

n

Standard Error (SE)

x̄ is the sample average σ original population std dev

Unknown Population Standard Deviation Assume unknown population mean.

Construct 95% CI:

x̄± 1.96 s

n

Standard Error (SE)

x̄ is the sample average s sample std dev; can be found in R using sd(), the function calculates the following equation:

n xi−x̄2

σi=1

s=

n−1

<small>Source Page 54 of 63</small>

### CI for Small Samples, n< 30

Motivating Example:
You took a sample with n= 2 observations from a uniform distribution in range [10, 30] (mean μ= 20 and std dev σ= 5.7735, both unknown to you).

Suppose observations are: x1 = 15.167 and x2 = 16.708, then the sample mean is x̄= 15.9375 and sample std dev is s= 1.09

If we apply the usual CI formula, we get: 15.9375

1.09

± 1.96 ×

2 = 15.9375 ± 1.5107 ≈[14.42, 17.45]

The range is far from true mean 20, what happened?

Solution:

How do we account for the fact we do not know the population standard deviation and instead used the sample standard deviation but with access to only a small sample size?

Make a larger confidence interval reflecting our uncertainty, i.e. instead of z= 1.96, we use another larger value.

Let’s introduce the -------’s t-distribution.

<small>Source Page 55 of 63</small>

### -------’s t-Distribution

t-distribution

- Has thicker tails than Normal (i.e. larger chance of extreme events).

- Its shape depends on a single parameter “nu” ν= n – 1, where n is the number of ob‐

servations.

- When n≥30 t-distribution is considered sufficiently close to Normal for practical

application purposes.

- Example: t11−1 is a t-distribution with ν= 10

t-distribution vs Standard Normal

```r
N(0, 1)
```

t4-1

n=4 n=11 t11-1

ν is also called “Degree of Freedom”.
<small>Source Page 56 of 63</small>

**t-values**

95% t-values

95% t-value: number of std. errors sample size n for 95% CI, tn-1

4.30

3.18

2.78

2.26

2.08

2.01 Normal Dist.

1.96

- The Standard Normal distribution has a single z-value for 95% CI, z= 1.96.

- The t-distribution has different t-values dependent on the number of observations.

Assumption: t-distribution assumes that the data originates from a Normal Distribution.

<small>Source Page 57 of 63</small>

### Visualize t-values

Shaded area under the curve corresponds to 2.5% probability for different distributions.

Observe larger t-values for smaller sample sizes and more probability in the tails than for Standard Normal.

```r
N(0, 1)
t(9)
t(2)
```

t= 4.30 (for n=3)

z= 1.96

t= 2.26 (for n=10)
<small>Source Page 58 of 63</small>

### CI with t-distribution

When sample size is small n< 30 and std dev is not known, the estimation of the mean of a Normally distributed population is performed using the t-distribution.

The standardized sample mean follows the tdistribution when standard deviation is not known, and sample size is small.

t= x̄−μ

s

n where t~ T(ν)

To form CI using t-distribution replace value of z with t.

+ −

n s t x n s t x , s= σi=1

n xi−x̄2 n−1

Margin of error

Use function sd() to calculate sample std dev. To obtain the t-value use function qt() e.g. for 95% CI

```r
t <- qt(0.975, sample_size-1) For smaller sample size, t-value is larger, which results in
wider confidence interval.
```

<small>Source Page 59 of 63</small>

**t-values Table**

<small>Source Page 60 of 63</small>

### Confidence Interval: Rule of Thumb

n x

z

Large Sample

Small Sample

n x

z
n t x s

Normal

Population Distribution:

non-Normal

Non-parametric ----- (bootstrapping)

Population Standard Deviation (σ) Known Unknown

n x s z

Open session2.Rmd

<small>Source Page 61 of 63</small>

### Pen and Paper Exercise

With your classmate next to you, discuss the following:

Q: Assuming the population of interest is approximately normally distributed, construct a 90% confidence interval estimate for the population mean given the following values

x̄= 18.4 s= 4.2 n= 5

<small>Source Page 62 of 63</small>

### Summary: Confidence Intervals

Sample statistic ≠ population parameter.

But if the sample is good, it can be a good estimate.

Report an estimate with a confidence interval Width of the interval depends on how variable sample statistics would be from different samples and the confidence level used (e.g. typical level is 95%).

95% Confidence Level If you take many samples and compute a CI around each sample mean, then 95% of those intervals would contain the true mean. It is not a statement about a single sample mean is the true mean, i.e. we are NOT saying that we are 95% certain that the population parameter is X.

<small>Source Page 63 of 63</small>

### Session Summary

Workshop Questions:

Look at the workshop questions in advance.
We covered:

Normal Distribution Confidence Intervalses

Attend workshop to go over the solutions.

Readings:

Modern Dives chapters 7, 8

Optional/ Extra practice: workshop2.Rmd


[↑ Back to the source list](#source-documents)

---

<a name="source-2"></a>

## session2_slides_post_class.pdf

<small>File type: PDF · Reader pages 119–149 · [View source PDF](PDF%20Slides.pdf#page=119)</small>

<small>Source Page 1 of 74</small>

### Lecture 2

Dr Helen Wang |

<small>Source Page 2 of 74</small>

### What is your best guess?

<small>Source Page 3 of 74</small>

### Uncertainty is challenging

<small>Source Page 4 of 74</small>

### Weeks 1-6 Outline

Week 01 | Exploratory Data Analysis

Week 02 | Statistics Foundation

Week 03 | Hypothesis -------

Week 04 | Regression, Part I

Week 05 | Regression, Part II

Week 06 | Risk Analysis, Part I

<small>Source Page 5 of 74</small>

01 | Distribution Parameters 02 | Normal and Standard Normal Distributions 03 | Sampling: Sampling Error and Standard Error 04 | Central Limit Theorem 05 | Confidence Intervals and Sample Size

Statistics Foundation
<small>Source Page 6 of 74</small>

### Nomenclature

Population mean: μ Sample mean: x̄

Population standard deviation: σ Sample standard deviation: s

Random variable: X Particular observation: x

Random variable of a Standard Normal: Z Particular observation of a Standard Normal (also known as ‘z-critical value’): z

Cumulative Density Function of Standard Normal: Φ z

Probability random variable Z takes on a value less than or equal to z: PZ≤z

Standard Error: SE

Parameter of t-distribution (also known as ‘degrees of freedom’): υ t-critical value: t

<small>Source Page 7 of 74</small>

01 | Distribution Parameters 02 | Normal and Standard Normal Distributions 03 | Sampling: Sampling Error and Standard Error 04 | Central Limit Theorem 05 | Confidence Intervals and Sample Size

Statistics Foundation

<small>Source Page 8 of 74</small>

### Probability Distributions

Definition

Probability Distribution:

Let’s roll dice!

- If an infinite number of observations was obtained, what would the frequency of data

be like?

- Expression that describes the relative frequency for every possible outcome or a range

of outcomes.

- Represents the real-world model “well enough” – even though nothing in the real world

is exactly distributed as the suspected probability distribution.

Describing Probability Distributions

- Shape: symmetry, modality, skewness
- Central Tendency: estimate of a typical observation in the distribution (mean, median,

mode)

- Spread: measure of variability in a distribution (range, variance, standard deviation,

IQR)

- Unusual Observations: observations that standout from the rest of the data that may

be suspected outliers

<small>Source Page 9 of 74</small>

### Describing Probability Distributions: Box Plot

Example: Box Plot of DJI returns

<small>Source Page 10 of 74</small>

### Unusual Observations

mean sd p0 p25 p50 p75 p100 169 28.3 1.78 166 174 178 191

mean sd p0 p25 p50 p75 p100

176. 9.06 160 169 176 183 203

After removing the outliers

Adult Height Distribution By Gender

<small>Source Page 11 of 74</small>

### Distribution Parameters

Central Tedency (1st Moment)

- Mean: 1

n xi typically used when

nσi=1

number of outliers is low and distribution is symmetrical

- Median: middle reading when data is ordered (50th percentile); typically used when

data is skewed

- Mode: most frequent reading; typically used for categorical data and data with more

than one peak
<small>Source Page 12 of 74</small>

### Income Distribution UK

Four highlighted sections of the distribution

- Benefits reliant individuals

- Low Middle Income (LMI)

- Higher Income

- 200K+

Q: What measure should be used to report the central tendency of this distribution?

A:

<small>Source Page 13 of 74</small>

### Income Distribution UK

Four highlighted sections of the distribution

- Benefits reliant individuals

- Low Middle Income (LMI)

- Higher Income

- 200K+

median

mean

Q: What measure should be used to report the central tendency of this distribution?

A: We will use the median since the distribution is skewed (right skewed in this case)

Income is typically not symmetric and is often skewed to the right.

<small>Source Page 14 of 74</small>

### Distribution Parameters

Central Tedency (1st Moment)

- Mean: 1

n xi typically used when

nσi=1

number of outliers is low and distribution is symmetrical
- Median: middle reading when data is ordered (50th percentile); typically used when

data is skewed

- Mode: most frequent reading; typically used for categorical data and data with more

than one peak

```r
Spread (2nd Moment)
```

- Mean Absolute Deviation (MAD) = 1

n xi−x̄

nσi=1

- Variance = 1

```r
n(xi−x̄)2
```

nσi=1

- Standard Deviation (SD) = Var

- Coefficient of Variation (CV) = SD

mean

- Range = largest – smallest reading

- Interquartile Range (IQR) = upper quartile – lower

quartile

<small>Source Page 15 of 74</small>

### Higher Moments

```r
Skewness (3rd Moment)
```

- Measure of asymmetry : a perfectly symmetrical distribution has skewness of 0.

- Positive Skew tail pointing to high values (body of the distribution is to the left)

- Negative Skew tail pointing to low values (body of the distribution is to the right)

```r
Kurtosis (4th Moment)
```

- Measure of heaviness of the tails: measures the peakedness of a distribution

- Leptokurtic : sharper peak, heavier tails, more

outliers.

- Platykurtic : flatter top, light tails, fewer
outliers.

<small>Source Page 16 of 74</small>

### Skewness: Right and Left

Rightskewed

Leftskewed

If coefficient of skewness is in the (-1,1) range, distribution is roughly bell-shaped and symmetrical.

<small>Source Page 17 of 74</small>

### Kurtosis: Heaviness of Tails

Excess Kurtosis = 0 Excess Kurtosis > 0 Excess Kurtosis < 0

<small>Source Page 18 of 74</small>

01 | Distribution Parameters 02 | Normal and Standard Normal Distributions 03 | Sampling: Sampling Error and Standard Error 04 | Central Limit Theorem 05 | Confidence Intervals and Sample Size

Statistics Foundation

<small>Source Page 19 of 74</small>

### Properties of Normal Distribution

Key Features

- Symmetric: scores are concentrated in the middle.

Skewness = 0, Kurtosis (excess) = 0

- Parameters: distribution can be described with the location (mean) and scale

(variance) parameters.

- Empirical rule for Normal Distributions: how likely is it to find a datapoint within

certain number of standard deviations from the mean?

χ Three-Sigma Rule

68% of the data lies within one standard deviation (±0.99σ) of the mean 95% of the data lies within two standard deviations (±1.96σ) of the mean 99.7% of the data lies within three standard deviations (±2.97σ) of the mean
<small>Source Page 20 of 74</small>

### Example: Normality Assumption

Pizza Delivery Times

Assuming Normally Distributed delivery times, the owner of Val’s Pizza decided to run an experiment. He found that sample mean delivery time was 30min and sample variance was 25min.

Q: Given this knowledge what range of delivery times can customers expect 68%, 95%, 99.7% of the time?

A:

<small>Source Page 21 of 74</small>

### Example: Normality Assumption

Pizza Delivery Times

Assuming Normally Distributed delivery times, the owner of Val’s Pizza decided to run an experiment. He found that sample mean delivery time was 30min and sample variance was 25min.

Q: Given this knowledge what range of delivery times can customers expect 68%, 95%, 99.7% of the time?

A:

68% of deliveries are 30min ± 1 ∗5min = 25-35 min 95% of deliveries are 30min ± 2 ∗5min = 20-40 min 99.7% of deliveries are 30min ± 3 ∗5min = 15-45 min

<small>Source Page 22 of 74</small>

### Standard Normal Distribution

z-score: number of standard deviations an observation falls above or below mean.

Z= X−μ

σ Key Features:

- A special case of the Normal Distribution where µ = 0 and σ= 1 i.e. Z∼N(µ = 0, σ2 =

1).

- Creates a common scale so you can access and compare different data without

depending on the specific unit it was measured in

- If population parameters are not known, use sample statistics, i.e., x̄and s.
- There is a 99.7% chance of being within ±2.97σof the mean, i.e. most values are

contained within [-3,+3]

<small>Source Page 23 of 74</small>

### Creating z-scores in R

Find z-values for return:

Each z is obtained as:

```r
data <- data %>% mutate(ret_z = (ret - mean(ret)) / sd(ret))
```

return~ N(0.913, 14.22)

Standardize 68%

13.3 0.913 15.1 X

zi= xi−0.913

14.2

return_z~ N(0, 1)

68%

Z

-1 0 1

<small>Source Page 24 of 74</small>

### Returns vs. Return z-Scores

In reality, the distribution is not quite Normal, therefore we use it as an approximation of the true distribution.

<small>Source Page 25 of 74</small>

### Cumulative Density Function

Cumulative Distribution Function (CDF) of a Standard Normal distribution, Φ z , provides the probability, p, that a Standard Normally distributed random variable (r.v.) Z, that has µ = 0 and σ= 1, is less than or equal to a particular value z

Φ z= PZ< z= PZ≤z

where PZ≤z equivalently:
PZ≤z= PZ≤X−μ

σ

Φ 0 is 0.5 for all symmetric distributions.

The CDF of a Standard Normal is available through a table or using mosaic::xpnorm() function in R.

Q: what is Φ 0 =?

<small>Source Page 26 of 74</small>

### Obtaining z-value in R

```r
p <- xpnorm(1.96, mean = 0, sd = 1) So far, we have used the above function to find the
probability of Z< z.
```

z= 1.96

p= ?

If X ~ N(0, 1), then P(X <= 1.96) = P(Z <= 1.96) = 0.975 P(X > 1.96) = P(Z > 1.96) = 0.025

```r
z <- qnorm(0.975, mean = 0, sd = 1) Provides the inverse operation, i.e. given a particular
probability of Z< z, what is the corresponding value z?
```

z=?

p= 0.975

[1] 1.96

<small>Source Page 27 of 74</small>

z-value one more decimal place 0.00 and 0.09

Increase

z-value between 0.0 and 3.0

e.g. PZ≤2.54 = 0.9945

Increase
<small>Source Page 28 of 74</small>

### Negative z

The table provides probability for z values from 0.00 to 3.00, PZ≤z (see next slide).

Therefore, for a negative value of z, we will use symmetry

Φ −z= 1 −Φ z

Φ z

<small>Source Page 29 of 74</small>

z-value one more decimal place 0.00 and 0.09

Increase

z-value between 0.0 and 3.0

e.g. PZ≤−2.54 = 1- PZ≤2.54 =1-0.9945 =0.0055

Increase

<small>Source Page 30 of 74</small>

### ZTel’s HR Hiring Policy:

Sample Statistics:

HR want to calculate the percentage of applicants who are automatic accepts and rejects.

- Let’s work with an example hiring policy.

- All applicants take a ----, and their hire or no-hire decision depends partly on the

results of the ----.

- Sample of past applicants and their hire decision

results have been collected.

- The applicants scores are Normally distributed with mean 525 and standard deviation

55.

Hiring Policy occurs in 2 phases:

- First phrase separates all applicants into three categories:

- automatic accepts with ---- score >= 600

- automatic rejects with ---- score <= 425

- “maybes”
- Second phase takes all ”maybes” and uses their previous job experience, special

talents and other factors as hiring criteria.

<small>Source Page 31 of 74</small>

### Pen and Paper (and R) Exercise

With your classmate next to you, work out the z-scores for automatic accepts / rejects of the hiring policy.

Check your results in R by using the MOSAIC function xpnorm(). Visualizing the task may help:

z = ?

z = ?

<small>Source Page 32 of 74</small>

### Solution

Write Down Information You Know First:

- Assumption: scores are Normally distributed

- Sample mean: x̄= 525

- Sample standard deviation: s = 55

- Automatic accept: x≥600

- Automatic reject: x≤425

Calculating z-values:

- Accept: z1 = X1−x̄

s = 600−525

≈1.36

- Reject: z2 = X2−x̄

s = 425−525

≈−1.82

R Syntax:

MOSAIC’s function xpnorm() returns the probability of a Normal distribution up to a certain x value.

mosaic::xpnorm(x_value, mean = mu_value, sd = std_dev_value)
<small>Source Page 33 of 74</small>

### Solution: Table

Automatic Accept:

Automatic Reject:

z1 = X1 −x̄

s = 600 −525

= 1.363636

We need to find PZ≥1.36 = 1 −Φ 1.36

Therefore, from the table:

PZ≥1.36 = 1 −Φ 1.36 = 1 −0.9131 = 0.0869

z2 = X2 −x̄

s = 425 −525

= −1.8181818

We need to find PZ≤−1.82 = 1 −Φ 1.82

Therefore, from the table:

PZ≤−1.82 = 1 −Φ 1.82 = 1 −0.9656 = 0.0344

<small>Source Page 34 of 74</small>

z-value one more decimal place 0.00 and 0.09

<small>Source Page 35 of 74</small>

### Solution: R

Automatic Reject:

Automatic Accept:

mosaic::xpnorm(425, mean = 525, sd = 55)

mosaic::xpnorm(600, mean = 525, sd = 55)
<small>Source Page 36 of 74</small>

### ZTel’s HR Hiring Policy:

Sample Statistics:

- Let’s work with an example hiring policy.

- All applicants take a ----, and their hire or no-hire decision depends partly on the

results of the ----.

- Sample of past applicants and their hire decision

results have been collected.

- The applicants scores are Normally distributed with mean 525 and standard deviation

55.

Hiring Policy is updated:

- automatic accepts with ---- score >= 580

- automatic rejects with ---- score <= 450

- The rest candidates fall into the “Maybe”

category.

Question: Calculate the percentage of applicants who fall into the “Maybe” category.

<small>Source Page 37 of 74</small>

### Hiring Policy:

- automatic accepts with ---- score > 580

- automatic rejects with ---- score <= 450

- The rest candidates fall into the “Maybe” category.

Question: Calculate the percentage of applicants who fall into the “Maybe” category.

```r
P(X <= 580) = mosaic::xpnorm(580,mean = 525, sd = 55) = 0.8413
P(X <= 450) = mosaic::xpnorm(450,mean = 525, sd = 55) = 0.0863
P(450 < X <= 580) = 0.8413 – 0.0863 = 75.5%, approximately 76%
```
<small>Source Page 38 of 74</small>

### Why Convert Normal to Standard Normal?

Advantage of using z-values:

Any Normal distribution can be converted to Standard Normal, i.e. x observations converted to z-scores in range of approx. [-3, 3]. This results in:

- Values on a consistent scale irrespective of the original parameters

- Ability to use a table to find the probabilities associated with events, P(Z< z)

- Use of statistical methods that rely on properties of Standard Normal distribution, e.g.

Confidence Intervals, Hypothesis -------, Regression Parameters Estimation

- Easier understanding of how many σ a value is away from the mean, since z∗σ= z∗1

= z

<small>Source Page 39 of 74</small>

01 | Distribution Parameters 02 | Normal and Standard Normal Distributions 03 | Sampling: Sampling Error and Standard Error 04 | Central Limit Theorem 05 | Confidence Intervals and Sample Size

Statistics Foundation

<small>Source Page 40 of 74</small>

### Inferential Statistics

Descriptive Statistics:

- Describe the whole population (everyone we are interested in) – typically difficult to

obtain.

- Properties calculated (mean, standard deviation) are called parameters (the TRUTH).

- Population parameters refer to the perfect knowledge; we reserve Greek letters (μ, σ)

for them.

Inferential Statistics:

- Use a (random) sample to infer unknown population

parameters.

- Properties calculated are called sample statistics, e.g.

sample mean, x̄, sample standard deviation, s, which are used to estimate parameters of the population (i.e. make an inference).

- Different samples will typically have different sample
statistics.

- Applications using sampling: Finance, Healthcare,

Politics, Quality Control.

- Why sample? Cost efficiency, -----to-distruction,

Reduce risk to patients.

<small>Source Page 41 of 74</small>

### Statistics is a Science of Inference

Statistical Inference:

- Predict and forecast values of population parameters.

- ---- hypothesis about values of population parameters.

- Make decisions.

- Challenge: do this based on sample statistics derived from limited and incomplete

sample information.

Make generalizations about the characteristics of a population...

On the basis of observations of a sample, a part of a population.

<small>Source Page 42 of 74</small>

### Sampling Error

We are interested in the true mean of a population, μ.

Since populations are difficult to collect data on, we use sample statistics (sample mean, x̄) as point estimate for the unknown true population parameter.

Sample statistics vary from sample to sample due to sampling error, an error arising from the unrepresentativeness of sample taken (from observing a sample instead of whole population).

Quantifying sampling error (how sample statistics vary from sample to sample) provides a way to estimate the margin of error associated with our point estimate.

Sampling Error Example:

Assume population mean is unknown, and we want to get an estimate on it. Take a sample of size n = 5.

Population: μ= 32.0, σ= 3.3

x̄= 31.6 x̄= 33.0 x̄= 35.2

We see variation in sample means.
<small>Source Page 43 of 74</small>

### Quantifying Sampling Error

Measuring Variability Of Sample Statistic:

Standard Error measures the variability of a sample statistic from the true population parameter.

Standard Error Of Sample Mean

- measures the variability of a sample mean from the true population mean.

- represents the standard deviation of the sampling distribution of the sample mean.

x̄3

x̄1

Sampling distribution

x̄2

Standard Error (SE) Calculation:

For sample size n, the standard error of the sample mean is measured using the standard deviation of the population (if known), σ:

SE = σ

n

if not known use sample standard deviation, s:

SE = s

n

തX ~ Nμ, σ2

n

<small>Source Page 44 of 74</small>

### Standard Deviation vs. Standard Error

Standard Error (SE):

- SE is the standard deviation of the distribution of തX

Standard Deviation:

- Population standard deviation, σ

- Sample standard deviation, s

- തX ~ Nμ, σ2
Measures the amount of variability within a single dataset (amount of variation of individual data points).

Measures the amount of variability of a sample statistic (sample mean) across different samples from the same population.

n xi−μ2

σ= σi=1

n

Standard Error of Sample Mean (population standard

deviation known): SE = σ

n xi−x̄2

σi=1

s=

n−1

Standard Error of Sample Mean (population standard

deviation not known): SE = s

n and SE is just the name for the std dev of

this distribution i.e. σ

n

n

<small>Source Page 45 of 74</small>

01 | Distribution Parameters 02 | Normal and Standard Normal Distributions 03 | Sampling: Sampling Error and Standard Error 04 | Central Limit Theorem 05 | Confidence Intervals and Sample Size

Statistics Foundation

<small>Source Page 46 of 74</small>

### Central Limit Theorem

Start with a random variable X that belongs to some (any) distribution with known mean μ and std dev σ.

Obtain a large sample n of independent observations of a random variable X and find the sample mean x̄.
Central Limit Theorem states that: the distribution of sample mean, തX, will approach a Normal distribution as sample size n increases (n≥30), with mean μ and standard deviation σ

n, i.e.,

തX ~ Nμ, σ2

n.

Note: standard deviation of the distribution of sample means is known as the Standard Error, σ

n.

Sampling distribution of the sample mean

σ2

r.v. തX ~Nμ,

n

Population distribution r.v. X ~ dist(μ, σ)

Simulation: https://onlinestatbook.com/stat_sim/samp ling_dist/

<small>Source Page 47 of 74</small>

### Central Limit Theorem Illustration

Distribution of sample mean tends to a Normal Distribution, and its dispersion is given by CLT.

Any starting population distribution

<small>Source Page 48 of 74</small>

### Pen and Paper Exercise

- Is the following statement True or False? “The Probability obtained from the Standard

Normal CDF evaluated at z value of 0 is 1, i.e. Φ(0) = 1”.

- The population mean and SD of the weight of coffee bags from a supplier are 1.5kg

and 0.1kg.

Assume an initial sample was ordered of 50 bags of coffee and weighed them for quality control. What is the distribution of the sample mean of the weight for the coffee bags?

- A random variable X has a uniform distribution with a population mean 35 and popu‐

lation std dev 4.7 both known to you. A random sample of 105 observations is taken from the distribution of X. The sample mean was found to be 33.8 and sample SD 6.3. Is the following statement correct: “In accordance with CLT you can conclude that the distribution of the sample mean is approximately Normal with parameters:

തX~N33.8, 6.3
<small>Source Page 49 of 74</small>

### Answers

- FALSE Φ(0) = 0.5 i.e. z value of 0 corresponds to exactly half of the Standard Normal

CDF.

- Calculation:

CLT applies in the present case since the sample size of 50 is large enough i.e. ≥30. Let തX denote the random variable representing mean weight (in kg) of the coffee bags. By CLT the distribution of the

- Indeed തX is Normally distributed by CLT (since a large enough sample sized was

used, 105 > 30).

However, the parameters used for the calculation of തX are not correct. By definition തX~Nμ, σ2 since population parameters of the original distribution are known, these parameters should be used in the expression for the sampling distribution തX (not the parameters of the collected sample) i.e.

sample mean is Normal: തX~Nμ, σ2

n. In this question, it becomes തX~N1.5, 0.12

തX~N35, 4.7

.

50 .

n and

<small>Source Page 50 of 74</small>

01 | Distribution Parameters 02 | Normal and Standard Normal Distributions 03 | Sampling: Sampling Error and Standard Error 04 | Central Limit Theorem 05 | Confidence Intervals and Sample Size

Statistics Foundation

<small>Source Page 51 of 74</small>

### Motivation: Communicating Uncertainty

Example, Apricot Company:

- You have recently joined the marketing department of Apricot, a mobile phone

competitor to iPhone.
- Your task is to find out how much people are willing to pay (WTP) on average for your

company’s new mobile phone, which is thinner and lighter than the iPhone.

- You conduct a quick survey and ask n = 100 people for their WTP and find that the

average amount is £200 (i.e. x̄= 200)

Task:

- Assumption: the amount people are willing to pay is approximately Normally

distributed (by the CLT).

- Assumption: population standard deviation of the amount is known to be £50 (i.e. σ=

50); in practice we will need to estimate it, but for now we assume it is given.

- You know that the true WTP is not likely to be exactly £200. How can you communicate

the uncertainty behind your estimate?

<small>Source Page 52 of 74</small>

### Confidence Interval Approximation

Why form Confidence Intervals?

Problem: often we don’t know the population mean, μ.

Solution: use sample mean and make an inference about the population mean.

Inference:

- We report an interval within which we are 95% confident that the true population

mean resides.

- Since distribution of sample means is Normal, and we want to be 95% certain, we use

properties of the Normal dist. to establish the confidence interval.

How to From Confidence Intervals?

Sample means distribution is Normal തX ~ Nμ, σ2

n,

i.e. the distribution’s standard deviation is σ

n which

is also known as the Standard Error.

We can form an interval around the sample mean using the information about the margin of error (i.e. the Standard Error), using the following equation:

x̄ ± z∗Standard Error

What is the rational for doing this? We want to capture 95% body of the Normal Distribution, i.e. be 95% certain.
<small>Source Page 53 of 74</small>

### Confidence Interval Approximation

Confidence Interval (CI) is a range of values derived from a sample that is expected to contain the true population parameter μ.

- CI is expressed with a level of confidence, that is typically expressed as a percentage,

e.g. 95%.

- Level of confidence means if we were to take many samples and construct a CI for

each, approx. 95% of them would contain the true parameter.

CI Formula:

Point Estimate ± Margin of Error =

x̄ ± z∗Standard Error where z-value depends on the level of confidence.

Example: 95% Confidence Interval To build a CI around sample mean which leaves us 95% confident, we need to select the value of z such that in total 5% is left in the tails, i.e. z= 1.96

95% 2.5% 2.5%

x̄ – 1.96×SE x̄ x̄ + 1.96×SE

<small>Source Page 54 of 74</small>

### Establishing z-value for CI

```r
z <- qnorm(0.975, mean = 0, sd = 1)
```

The Quantile function qnrom() returns the zvalue corresponding to the specified probability p from the equation P(Z< z) = p.

If we would like 95% probability to be left in the body of the distribution, that means we need 2.5% to be left in each tail.

The qnorm() function returns z-value corresponding to the probability to the left of the z-value. Therefore p=0.975 is should be used.

z= 1.96

[1] 1.96

Thus, we can form a 95% CI using: x̄ ± 1.96×SE
<small>Source Page 55 of 74</small>

### Example CI Probabilities and z-values

The following probabilities would need to be specified to obtain the correct z-values for given confidence interval levels. All you must focus on is how much probability is left in the right tail:

Example:

You are given the following graph, where the body of the distribution contains 98% probability.

Q: What CI level does this correspond to?

- 90% CI

```r
z <- qnorm(0.95, mean = 0, sd = 1)
```

- 95% CI

```r
z <- qnorm(0.975, mean = 0, sd = 1)
```

- 98% CI

```r
z <- qnorm(0.99, mean = 0, sd = 1)
```

- 99% CI

```r
z <- qnorm(0.995, mean = 0, sd = 1)
```

<small>Source Page 56 of 74</small>

### CI for Large Samples, n≥30

Known Population Standard Deviation Assume unknown population mean.

Construct 95% CI:

x̄± 1.96 σ

n

Standard Error (SE)

x̄ is the sample average σ original population std dev

95%

Unknown Population Standard Deviation Assume unknown population mean.

Construct 95% CI:

x̄± 1.96 s
n

Standard Error (SE)

x̄ is the sample average s sample std dev; can be found in R using sd(), the function calculates the following equation:

n xi−x̄2

s= σi=1

n−1

<small>Source Page 57 of 74</small>

### Task: Communicating Uncertainty

Example, Apricot Company:

- You have recently joined the marketing department of Apricot, a mobile phone

competitor to iPhone.

- Your task is to find out how much people are willing to pay (WTP) on average for your

company’s new mobile phone, which is thinner and lighter than the iPhone.

- You conduct a quick survey and ask n= 100 people for their WTP and find that the

average amount is £200 (i.e. x̄= 200)

Task:

- Assumption: the amount people are willing to pay is approximately Normally

distributed (by the CLT).

- Assumption: population standard deviation of the amount is known to be £50 (i.e. σ=

50); in practice we will need to estimate it, but for now we assume it is given.

- You know that the true WTP is not likely to be exactly £200. How can you communicate

the uncertainty behind your estimate?

<small>Source Page 58 of 74</small>

### Solution: Effect of Sample Size

For the Apricot company example, n> 30 is large, the CLT tells us the sample mean follows a Normal distribution. The approximate 95% confidence interval is defined as point estimate ± 2*SE

Sample size 100:

- Estimated mean: x̄= 200

- SE=

σ
100 = 5

n=

- qnorm(0.975) = 1.95996 ≈1.96 ≈ 2

95%

2.5% 2.5%

x̄−2 × 5 x̄ x̄+2 × 5

- You can be 95% confident that the true value of population mean is in range: [200 – 2

× 5, 200 + 2 × 5] [190, 210]

Sample size 400:

- Estimated mean: x̄= 200

- SE=

σ

400 = 2. 5

n=

- qnorm(0.975) = 1.95996 ≈1.96 ≈ 2

95%

2.5% 2.5%

x̄−2 × 5 x̄ x̄+2 × 5

- You can be 95% confident that the true value of population mean is in range: [200 – 2

× 2.5, 200 + 2 × 2.5] [195, 205]

<small>Source Page 59 of 74</small>

### Sample Size

<small>Source Page 60 of 74</small>

### CI Interpretation

Confidence Intervals are like a net: if we took 100 samples, on average we expect 95 of those intervals to contain the true population parameter. Tempting, but wrong, to say “We’re 95% sure that the population parameter is X”.

95%

2.5% 2.5%

True mean
μ−2 × SE μ μ+2 × SE

<small>Source Page 61 of 74</small>

### Pen and Paper Exercise

With your classmate next to you, discuss the following:

- Assuming the population of interest is approximately normally distributed, construct a

95% confidence interval estimate for the population mean given the following values: x̄= 18.4, s= 4.2, n= 50

- What is the interpretation of this 95% confidence interval?

<small>Source Page 62 of 74</small>

### Answers

- The population parameters μ and σ are not given, therefore we estimate sigma using

s.

The 95% confidence interval is constructed using the following equation:

x̄ ± 1.96 ∗s

n= 18.4 ± 1.96 ∗4.2

50 = 18.4 ± 1.164

[17.236, 19.564]

- If we take 100 random samples, on average we expect 95 of those intervals to con‐

tain the true population parameter. In other words, there is a 95% probability that this CI contains the true population mean.

<small>Source Page 63 of 74</small>

### CI for Large Samples, n≥30

Known Population Standard Deviation Assume unknown population mean.

Construct 95% CI:

x̄± 1.96 σ

n

Standard Error (SE)

x̄ is the sample average σ original population std dev
Unknown Population Standard Deviation Assume unknown population mean.

Construct 95% CI:

x̄± 1.96 s

n

Standard Error (SE)

x̄ is the sample average s sample std dev; can be found in R using sd(), the function calculates the following equation:

n xi−x̄2

σi=1

s=

n−1

<small>Source Page 64 of 74</small>

### CI for Small Samples, n< 30

Motivating Example:

You took a sample with n= 2 observations from a uniform distribution in range [10, 30] (mean μ= 20 and std dev σ= 5.7735, both unknown to you).

Suppose observations are: x1 = 15.167 and x2 = 16.708, then the sample mean is x̄= 15.9375 and sample std dev is s= 1.09

If we apply the usual CI formula, we get: 15.9375 ±

1.09

1.96 ×

2 = 15.9375 ± 1.5107 ≈[14.42, 17.45]

The range is far from true mean 20, what happened?

Solution:

How do we account for the fact we do not know the population standard deviation and instead used the sample standard deviation but with access to only a small sample size?

Make a larger confidence interval reflecting our uncertainty, i.e. instead of z= 1.96, we use another larger value.

Let’s introduce the -------’s t-distribution.
<small>Source Page 65 of 74</small>

### -------’s t-Distribution

t-distribution

- Has thicker tails than Normal (i.e. larger chance of extreme events).

- Its shape depends on a single parameter “nu” ν= n – 1, where n is the number of ob‐

servations.

- When n≥30 t-distribution is considered sufficiently close to Normal for practical

application purposes.

- Example: t11−1 is a t-distribution with ν= 10

t-distribution vs Standard Normal

```r
N(0, 1)
```

t4-1

n=4 n=11 t11-1

ν is also called “Degree of Freedom”.

<small>Source Page 66 of 74</small>

**t-values**

95% t-values

95% t-value: number of std. errors sample size n for 95% CI, tn-1

4.30

3.18

2.78

2.26

2.08

2.01 Normal Dist.

1.96

- The Standard Normal distribution has a single z-value for 95% CI, z= 1.96.

- The t-distribution has different t-values dependent on the number of observations.

Assumption: t-distribution assumes that the data originates from a Normal Distribution.
<small>Source Page 67 of 74</small>

### Visualize t-values

Shaded area under the curve corresponds to 2.5% probability for different distributions.

Observe larger t-values for smaller sample sizes and more probability in the tails than for Standard Normal.

```r
N(0, 1)
t(9)
t(2)
```

t= 4.30 (for n=3)

z= 1.96

t= 2.26 (for n=10)

<small>Source Page 68 of 74</small>

### CI with t-distribution

When sample size is small n< 30 and std dev is not known, the estimation of the mean of a Normally distributed population is performed using the t-distribution.

The standardized sample mean follows the tdistribution when standard deviation is not known, and sample size is small.

t= x̄−μ

s

n where t~ T(ν)

To form CI using t-distribution replace value of z with t.

+ −

n s t x n s t x , s= σi=1

n xi−x̄2 n−1

Margin of error

Use function sd() to calculate sample std dev. To obtain the t-value use function qt() e.g. for 95% CI
```r
t <- qt(0.975, sample_size-1) For smaller sample size, t-value is larger, which results in
wider confidence interval.
```

<small>Source Page 69 of 74</small>

**t-values Table**

<small>Source Page 70 of 74</small>

### Confidence Interval: Rule of Thumb

n x

z

Large Sample

Small Sample

n x

z

n t x s

Normal

Population Distribution:

non-Normal

Non-parametric ----- (bootstrapping)

Population Standard Deviation (σ) Known Unknown

n x s z

Open session2.Rmd

<small>Source Page 71 of 74</small>

### Pen and Paper Exercise

With your classmate next to you, discuss the following:

Q: Assuming the population of interest is approximately normally distributed, construct a 90% confidence interval estimate for the population mean given the following values

x̄= 18.4 s= 4.2 n= 5
<small>Source Page 72 of 74</small>

### Pen and Paper Exercise

The population parameters μ and σ are not given, therefore we estimate sigma using s. We have a small sample size, n= 5, therefore we need to account for a potential estimation error of the standard deviation. Therefore, we will use the t-value when forming CI.

z= 1.64

t= 2.13 t = qt(p, sample_size-1) t = qt(0.95, 4) [1] 2.13

[1] 2.13

The confidence interval is therefore:

x̄ ± 2.13 ∗s

n= 18.4 ± 2.13 ∗4.2

5 = 18.4 ± 4

[14.4, 22.4]

<small>Source Page 73 of 74</small>

### Summary: Confidence Intervals

Sample statistic ≠ population parameter.

But if the sample is good, it can be a good estimate.

Report an estimate with a confidence interval Width of the interval depends on how variable sample statistics would be from different samples and the confidence level used (e.g. typical level is 95%).

95% Confidence Level If you take many samples and compute a CI around each sample mean, then 95% of those intervals would contain the true mean. It is not a statement about a single sample mean is the true mean, i.e. we are NOT saying that we are 95% certain that the population parameter is X.

<small>Source Page 74 of 74</small>

### Session Summary

Workshop Questions:

Look at the workshop questions in advance.

We covered:

Normal Distribution Confidence Intervalses
Attend workshop to go over the solutions.

Readings:

Modern Dives chapters 7, 8

Optional/ Extra practice: workshop2.Rmd


[↑ Back to the source list](#source-documents)

---

<a name="source-3"></a>

## session2.Rmd

<small>File type: RMD · Reader pages 150–159 · [View source PDF](PDF%20Slides.pdf#page=150)</small>

```r
# include=FALSE means that the this particular code chunk and its output will not be included
in the knitted document
# echo = TRUE means code used in this document will be displayed along the output in the final
rendered document
knitr::opts_chunk$set(echo = TRUE)
# include=TRUE means that the code and its output will be included in the knitted document
# message=FALSE means that messages produced during the execution of the code chunk will not
be displayed in the output
# warning=FALSE means that any warnings produced by the code chunk will be suppressed and not
shown in the document
#install.packages("gamlss")
#install.packages("gamlss.dist")
library(tidyverse)
library(tidyquant)
library(kableExtra)
library(tseries)
library(gamlss)
library(gamlss.dist)
library(ggridges)
library(viridis)
```

### Yield Curve

The yield curve is a graph that shows the relationship between the interest rates (yields) of U.S. Treasury securities and their time to maturity.

Let's set up and load the data.

```r
maturity <- c('3m', '6m', '1y', '2y','3y','5y','7y','10y','20y','30y')
# List of FRED codes for US rates
tickers <- c('TB3MS', # 3-month Treasury bill (or T-bill)
'TB6MS', # 6-month
'GS1',  # 1-year2
'GS2',  # 2-year, etc....
'GS3',
'GS5',
'GS7',
'GS10',
'GS20',
'GS30')  #.... all the way to the 30-year rate
#  FRED codes as human readable names
myvars <- c('3-Month Treasury Bill',
'6-Month Treasury Bill',
'1-Year Treasury Rate',
'2-Year Treasury Rate',
```
```r
'3-Year Treasury Rate',
'5-Year Treasury Rate',
'7-Year Treasury Rate',
'10-Year Treasury Rate',
'20-Year Treasury Rate',
'30-Year Treasury Rate')
# By default R will sort these maturities alphabetically; but since we want to keep them in
that exact order, we recast maturity as a factor with the levels defined in the order of the
maturity variable elements
maturity <- factor(maturity, levels = maturity)
# create a look up container
mylookup <- tibble(symbol = tickers,
var = myvars,
maturity = maturity)
# examine as a table
mylookup %>%
kable("html", col.names = c("Symbol", "Description", "Maturity")) %>%
kable_styling(bootstrap_options = c("striped", "hover", "condensed", "responsive"),
full_width = FALSE) %>%
column_spec(1, bold = TRUE) %>%
row_spec(0, bold = TRUE, background = "#D3D3D3") %>%
add_header_above(c("Treasury Data" = 3))
```

Next let's download the historical data from TidyQuant library, starting from 1990s. Note that the resulting output is already in a long tidy format.

```r
treasury_data <- tickers %>%
tq_get(get = "economic.data",
from = "1990-01-01")
glimpse(treasury_data)
```

Combine the downloaded data with our lookup table.

Note that here we use the left_join() verb because we judge that the treasury_data contains the most important information (data), all of which should be kept. While the lookup table is simply a reference table of names hence only the matching names should be attached into treasury_data.

```r
yield_curve <- left_join(treasury_data, mylookup, by = "symbol") %>%
rename(value = price) %>%
mutate(duration = factor(var, levels = myvars)) # also create a duration as a factor rather
than string (var)
```

### Always Visualize Your Data

Let's plot time series of the different maturities.

```r
ggplot(data=yield_curve, aes(x=date, y=value, colour= duration)) +
geom_line() +
facet_wrap(~duration, nrow=5) +
theme_bw() +
theme(legend.position="none") +
labs(title="Yields on U.S. Treasury rates since 1960",
```
```r
x = NULL, y = "%",
caption="Source: St. Louis Federal Reserve Economic Database (FRED)")
```

Let's plot each day's Yield Curve on a single plot for each year.

```r
yield_curve %>%
mutate(year = factor(year(date))) %>% # create a column year as a factor
filter(date >='2000-01-01')  %>%
ggplot(aes(x = maturity, y = value, group = date, colour = year)) + # group data by date
geom_line() +
theme_bw() +
facet_wrap(~year, nrow = 6) + # create subplots by year
theme(legend.position = "none") +
labs(title = "US Yield Curve - Daily Per Year",
x = "Maturity",
y = "Yield (%)",
caption = "Source: St. Louis Federal Reserve Economic Database (FRED)")
```

Let's plot one Yield Curve for each year by finding the average of one year's worth of yield curve data.

```r
yield_curve %>%
mutate(year = factor(year(date))) %>%
filter(date >= '2000-01-01') %>%
# Group by year and maturity, then calculate the average yield per maturity per year
group_by(year, maturity) %>%
summarize(avg_yield = mean(value, na.rm = TRUE)) %>%
# Plot the yield curve for each year
ggplot(aes(x = maturity, y = avg_yield, group = year, colour = year)) +
geom_line() +
theme_bw() +
facet_wrap(~year, nrow = 6) +
theme(legend.position = "none") +
labs(title = "US Yield Curve - Average Per Year",
x = "Maturity",
y = "Yield (%)",
caption = "Source: St. Louis Federal Reserve Economic Database (FRED)")
```

Let's observe the series plots of 3months and 10 year maturities.

```r
yield_curve %>%
# to filter several tickers at the same time use %in% membership check, together with c()
concatenation function
filter(symbol %in% c('TB3MS', 'GS10')) %>%
filter(date >= '2000-01-01')%>%
ggplot(aes(x = date, y = value, colour = duration)) +
geom_line() +
facet_wrap(~duration) +
theme_bw() +
theme(legend.position="none") +
labs(title="Yields on 3-month and 10-year US Treasury rates since 1999",
x = NULL, y = "%",
caption="Source: St. Louis Federal Reserve Economic Database (FRED)")
```
Do we see a (partial) Yield Curve inversion? Examine 2-year and 5-year maturities.

```r
yield_curve %>%
filter(symbol %in% c('GS2', 'GS5')) %>%
filter(date >= '2000-01-01') %>%
ggplot(aes(x = date, y = value, colour = duration)) +
geom_line() +
# facet_wrap(~duration) +
theme_bw() +
# Remove title for fill legend
guides(colour = guide_legend(title = NULL)) + # remove legend title
labs(title="Yields on 2- and 5-year US Treasury rates since 1999",
x = NULL, y = "%",
caption="Source: St. Louis Federal Reserve Economic Database (FRED)")
```

### Feature Engineering for a Trading Signal

As part of building a trading model, we may include variables which indicate to the model whether an 'extreme / unexpected' value is being observed. As such let's calculate a dummy variable which will indicate to us if the contract's value is more/less than 2 standard deviations away from the mean.

To do this calculation, we first need to use group_by() the data by symbol (which corresponds maturity). Next we calculate the returns for each maturity, and then convert to our data to z-scores.

Remember since we group_by() first, the subsequent verb operations are performed on the group rather than on the whole column.

Note that our data is in the tidy long format ready for dplyr verb application.

```r
yield_curve_z <- yield_curve %>%
group_by(symbol) %>%
mutate(ret = (value / lag(value) - 1) * 100) %>%
filter(!is.na(ret)) %>%
mutate(ret_z = (ret - mean(ret)) / sd(ret)) %>%
ungroup()
```

Q: Why are we working with returns rather than prices?

Let's plot the distribution of returns vs the distribution of the z-scores for 2 year maturity.

```r
# First plot for the returns distribution (`ret`)
yield_curve_z %>%
filter(symbol %in% c('GS2')) %>%
filter(date >= '2000-01-01') %>%
ggplot(aes(x = ret, fill = symbol)) +
geom_density(alpha = 0.4, colour = "red") +
theme_bw() +
labs(title = "Distribution of Returns", x = "Return (%)", y = "Density") +
theme(legend.position="none") +
theme(
plot.title = element_text(size = 16, face = "bold"),
axis.title = element_text(size = 14),
axis.text = element_text(size = 12, face = "bold")
)
```
Get the statistics of the distribution.

```r
ret_2yr_stats <- yield_curve_z %>%
filter(symbol %in% c('GS2')) %>%
filter(date >= '2000-01-01') %>%
summarise(mu_r = mean(ret),
std_dev_r = sd(ret))
print(ret_2yr_stats)
```

Now let's plot the distribution of z-scores.

```r
# Second plot for the z-scores of returns distribution (`ret_z`)
yield_curve_z %>%
filter(symbol %in% c('GS2')) %>%
filter(date >= '2000-01-01') %>%
ggplot(aes(x = ret_z, fill = symbol)) +
geom_density(alpha = 0.4, colour = "red") +
stat_function(fun = dnorm, args = list(mean = 0, sd = 1),  # Overlay standard normal curve
color = "blue", linetype = "dashed", size = 1) +
theme_bw() +
labs(title = "Distribution of Z-Scores of Returns", x = "Z-Score", y = "Density") +
theme(legend.position="none") +
theme(
plot.title = element_text(size = 16, face = "bold"),
axis.title = element_text(size = 14),
axis.text = element_text(size = 12, face = "bold")
)
```

We can see that the distributions look similar to Normal but with more probability in the tails than the Standard Normal. How do I know that? (What values does the Standard Normal typically cut off at?)

[EXTRA]: We can perform an official statistical significance ---- to see if a given dataset is Normally distributed. This is called the Shapiro-Wilk ----. We assume by default (H0, null hypothesis), that the data is Normally distributed. The alternative belief then is that it is not Normal (H1, alternative hypothesis). We uphold the null hypothesis unless we can reject it beyond reasonable doubt (which is if the p-value < 0.05). We can see that the result shows p-value of much less than 0.05, therefore Normality can be rejected.

```r
sw_---- <- yield_curve_z %>%
filter(symbol %in% c('GS2')) %>%
filter(date >= '2000-01-01') %>%
select(ret_z) %>%
pull(ret_z) %>% # extract ret_z values as a numeric vector, which is required by
shapiro.----()
shapiro.----()
print(sw_----)
```

[EXTRA]: Also we can do a Jarque-Bera ---- to examine if data set has skewness and kurtosis of the values expected for a Normal distribution. We assume by default (H0, null hypothesis), that the data is Normally distributed. The alternative belief then is that it is not Normal (H1, alternative
hypothesis). We uphold the null hypothesis unless we can reject it beyond reasonable doubt (which is if the p-value < 0.05). We can see that the result shows p-value of much less than 0.05, therefore Normality can be rejected.

```r
jb_---- <- yield_curve_z %>%
filter(symbol %in% c('GS2')) %>%
filter(date >= '2000-01-01') %>%
select(ret_z) %>%
pull(ret_z) %>% # extract ret_z values as a numeric vector, which is required by
jarque.bera.----()
jarque.bera.----()
print(jb_----)
```

[EXTRA]: You could make a check to see which distribution fits your data best. You can do this with a package called GAMLSS. Fit several distributions to the data and compare them using AIC (Akaike Information Criterion). The best fit will have the lowest AIC value.

```r
ret_z_data <- yield_curve_z %>%
filter(symbol == 'GS2') %>%
filter(date >= '2000-01-01') %>%
select(ret_z) %>%
pull(ret_z) # convert from tibble to a vector
# Fit different distributions
fit_normal  <- gamlss(ret_z_data ~ 1, family = NO, trace = FALSE)  # Normal
fit_t  <- gamlss(ret_z_data ~ 1, family = TF, trace = FALSE)  # t-Distribution
fit_skewed_t  <- gamlss(ret_z_data ~ 1, family = SST, trace = FALSE) # Skewed t-distribution
# Compare models using AIC
models <- list(Normal = fit_normal,
t_Distribution = fit_t,
skewed_t = fit_skewed_t)
# Extract AIC values for comparison
model_aic <- sapply(models, AIC)
print(model_aic)
# Identify the best-fitting distribution
best_fit <- names(which.min(model_aic))
print(best_fit)
```

### Normal Distribution / z-scores

---- scores are normally distributed with a mean of 525 and standard deviation of 55. Automatic accepts have ---- score >= 600 and automatic rejects score <= 425 Calculate the percentage of applicants who are automatic accepted and rejected

```r
mosaic::xpnorm(600, mean = 525, sd = 55, xlab = "---- Scores", ylab = "Probability")
mosaic::xpnorm(425, mean = 525, sd = 55, xlab = "---- Scores", ylab = "Probability")
# Define the parameters of the standard normal distribution
mean_val <- 0
sd_val <- 1
z_value <- 1.36
```
```r
# Create a sequence of x values for the normal curve
x <- seq(mean_val - 4 * sd_val, mean_val + 4 * sd_val, length.out = 1000)
y <- dnorm(x, mean = mean_val, sd = sd_val)
# Create a data frame for ggplot
data <- data.frame(x = x, y = y)
# Plot the normal distribution and shade the area to the left of z = 1.65
ggplot(data, aes(x, y)) +
geom_line() +  # Normal distribution curve
geom_area(data = subset(data, x >= z_value), aes(y = y), fill = "magenta", alpha = 0.5) +  #
Shaded area to the left of z = 1.65
labs(x = "z", y = "Density", title = "Standard Normal Distribution") +  # Labels for axes
and title
theme_minimal() +  # Minimal theme
theme(
text = element_text(size = 16),  # Set font size
axis.title.x = element_text(size = 18),  # Customize x-axis label size
axis.title.y = element_text(size = 18)  # Customize y-axis label size
) +
geom_vline(xintercept = z_value, linetype = "dashed", color = "red")  # Add a dashed line at
z = 1.65
```

If we wanted to automatically accept 15% and automatically reject 10%, we are doing the inverse calculation, namely finding the Z that corresponds to the 85th and 10th percentile, respectively.

Find the z-value that corresponds to the 85th percentile.

```r
# by default value is TRUE i.e. p(Z<z) = 0.85
qnorm(0.85, lower.tail = TRUE)
# if FALSE is used then gives symmetrical value on the other side of the distribution
qnorm(0.85)
# But if use FALSE then gives same value as the 15th percentile i.e. P(Z>z) = 0.85
qnorm(0.85, lower.tail = FALSE)
qnorm(0.15)
```

If the mean = 525, and the sd = 55, the X values for automatically accepting 15% and automatically rejecting 10% of candidates can be found as:

```r
qnorm(0.85, mean = 525, sd = 55)
qnorm(0.10, mean = 525, sd = 55)
```

**t-Distribution**

Produce a table of t-values for varying number of observations:

```r
t_critical <- tibble(
sample_size = c(3:100),
degrees_of_freedom = sample_size - 1,
t_critical = qt(0.975, degrees_of_freedom) # qt is t distribution quantile function
)
print(t_critical)
```
### Reproducing plots from the slides:

PLOT A

```r
x <- seq(-10, 10, by = 0.01)
df2 <- dt(x, df = 2)
df9 <- dt(x, df = 9)
norm <- dnorm(x)
# Plot the distributions
df2 <- dt(x, df=2)
df9 <- dt(x, df=9)
norm <- dnorm(x)
# Create the plot
ggplot(data.frame(x=x, df2=df2, df9=df9, norm=norm), aes(x=x)) +
geom_area(aes(y=df2, fill=(x > 4.30)), data=subset(data.frame(x=x, df2=df2), x > 4.30),
fill="blue") +
geom_area(aes(y=df9, fill=(x > 2.26)), data=subset(data.frame(x=x, df9=df9), x > 2.26),
fill="green") +
geom_area(aes(y=norm, fill=(x > 1.96)), data=subset(data.frame(x=x, norm=norm), x > 1.96),
fill="red") +
geom_line(aes(y=df2, color="t (df=2)"), size=1.2) +
geom_line(aes(y=df9, color="t (df=9)"), size=1.2) +
geom_line(aes(y=norm, color="Standard Normal"), linetype="solid", size=1.2) +
geom_vline(aes(xintercept=4.30, color="t (df=2)"), linetype="solid", size=1) +
geom_vline(aes(xintercept=2.26, color="t (df=9)"), linetype="solid", size=1) +
geom_vline(aes(xintercept=1.96, color="Standard Normal"), linetype="solid", size=1) +
scale_x_continuous(breaks=seq(-10, 10, by=1), limits=c(-10,10), expand = c(0, 0)) +
scale_y_continuous(breaks=seq(0, 0.4, by=0.1), limits=c(0,0.4), expand = c(0, 0)) +
theme_minimal() +
theme(
axis.text.x=element_text(size=14),
axis.text.y=element_text(size=14),
axis.title=element_text(size=14),
legend.title=element_text(size=14),
legend.text=element_text(size=12),
plot.margin = margin(10, 10, 10, 10)
) +
labs(x = "value",
y = "density",
color="Distribution") +
scale_color_manual(values=c("t (df=2)"="blue", "t (df=9)"="green", "Standard Normal"="red"))
```

PLOT B

Example, generate a plot for qt(0.95, 4)

```r
# Define t and normal values for plotting
x_vals <- seq(-5, 5, by = 0.01)
t_vals <- dt(x_vals, df=4)
norm_vals <- dnorm(x_vals)
# Calculate the t-value for P(T < t) = 0.95 with df=4
t_critical <- qt(0.95, df=4)
# Create the plot
ggplot(data.frame(x_vals, t_vals, norm_vals), aes(x = x_vals)) +
geom_area(aes(y = t_vals, fill = x_vals < t_critical),
data = subset(data.frame(x_vals, t_vals), x_vals < t_critical),
```
```r
fill = "blue", alpha = 0.5) +
geom_line(aes(y = t_vals), size = 1) +
geom_line(aes(y = norm_vals, color = "Standard Normal"), size = 1, color = "red") +
geom_vline(aes(xintercept = t_critical), linetype = "dashed", color = "black") +
geom_vline(aes(xintercept = 1.64), linetype = "dashed", color = "red") +
labs(title = "t-Distribution (df=4) vs. Standard Normal Distribution",
y = "Density",
x = "Value") +
scale_color_manual(name = "Distribution", values = c("Standard Normal" = "red")) +
theme_minimal() +
theme(
axis.text.x=element_text(size=14),
axis.text.y=element_text(size=14),
axis.title=element_text(size=14),
legend.title=element_text(size=14),
legend.text=element_text(size=12)
)
```

### Confidence Intervals

Let's examine movie ratings for different genres.

```r
movies <- read_csv('movies.csv')
glimpse(movies)
```

Choose genres that have at least 5 movies (there are 12 of them)

```r
genres_to_choose <- movies %>%
group_by(genre) %>%
summarise(count = n()) %>%
filter(count > 5) %>%
select(genre) %>%
pull() # creates a vector of characters vs without pull would create a tibble
# tibble is not an acceptable data type for filtering genre below - you need to
# specify a vector; if not would get an empty movies tibble)
glimpse(genres_to_choose)
```

Plot distributions of ratings, faceted by genre

```r
movies %>%
filter(genre %in% genres_to_choose) %>% # genres_to_choose is a vector of genre names
ggplot(aes(x = rating, colour = genre)) +
geom_density() +
facet_wrap(~ genre)+
theme_bw() +
theme(legend.position = "none") +
labs(title = "Distribution of IMDB ratings by film genre",x = "Film Rating",y = " ") +
NULL
```

Confidence Interval (CI) using the $point estimate +/- t_{critical} * SE$

```r
genre_formula_ci <- movies %>%
filter(genre %in% genres_to_choose) %>%
group_by(genre) %>%
summarise(mean_rating = mean(rating),
```
```r
sd_rating = sd(rating),
count = n(),
# get t-critical value with (n-1) degrees of freedom
t_critical = qt(0.975, count-1),  # 95% confidence level
se_rating = sd(rating) / sqrt(count), # Standard Error
margin_of_error = t_critical * se_rating,
rating_low = mean_rating - margin_of_error,
rating_high = mean_rating + margin_of_error) %>%
arrange(desc(mean_rating)) # arrange by best mean rating first
# View CIs for all genres
print(genre_formula_ci)
```

Visualise CIs for all genres

```r
ggplot(genre_formula_ci, aes(x = reorder(genre, mean_rating), y = mean_rating, colour =
genre)) +
geom_point() +
geom_errorbar(width = 0.5, aes(ymin = rating_low, ymax = rating_high)) +
labs(x = " ",
y = "Mean IMDB Rating",
title = "Which film genres have the highest mean IMDB ratings?") +
theme_bw() +
coord_flip() +
theme(legend.position = "none") +
NULL
```

[EXTRA] Some more pretty plotting using violin plots. We will draw a violin plot and then use position="jitter" or geom_jitter() to see how spread out the actual points are. We can also superimpose the means as a big orange dot, first create a tibble that with two columns: genre and rating.

```r
mean_rating_tibble <- genre_formula_ci %>%
select(genre, mean_rating) %>%
rename(rating=mean_rating)
ratings_tibble <- movies %>%
filter(genre %in% genres_to_choose)
movies %>%
filter(genre %in% genres_to_choose) %>%
ggplot(aes(x = genre, y = rating, colour=genre)) +
geom_violin()+
geom_point(position = "jitter", size = 0.8, alpha = 0.95) +
geom_point(data = mean_rating_tibble, colour = "orange", size = 5)+
labs(x=" ",
y= "Mean IMDB Rating",
title="Which film genres have the highest mean IMDB ratings?") +
coord_flip()+
theme_bw()+
labs(x="")+
theme(legend.position = 'none')+
NULL
```


[↑ Back to the source list](#source-documents)

---

<a name="source-4"></a>

## movies.csv

<small>File type: CSV · Reader pages 160–161 · [View source PDF](PDF%20Slides.pdf#page=160)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

> Data preview (up to six records and twelve columns); the full CSV remains in the original files.

Table displayed as labelled records for readability (6 rows, 11 columns).

Avatar

genre Action

director James Cameron

year 2009

duration 178

gross 760505847

budget 237000000

cast_facebook_likes 4834

votes 886204

reviews 3777

rating 7.9

Titanic

genre Drama

director James Cameron

year 1997

duration 194

gross 658672302

budget 200000000

cast_facebook_likes 45223

votes 793059

reviews 2843

rating 7.7

Jurassic World

genre Action

director Colin Trevorrow

year 2015

duration 124

gross 652177271

budget 150000000

cast_facebook_likes 8458

votes 418214

reviews 1934

rating 7
The Avengers

genre Action

director Joss Whedon

year 2012

duration 173

gross 623279547

budget 220000000

cast_facebook_likes 87697

votes 995415

reviews 2425

rating 8.1

The Dark Knight

genre Action

director Christopher Nolan

year 2008

duration 152

gross 533316061

budget 185000000

cast_facebook_likes 57802

votes 1676169

reviews 5312

rating 9

Star Wars: Episode I - The Phantom Menace

genre Action

director George Lucas

year 1999

duration 136

gross 474544677

budget 115000000

cast_facebook_likes 37723

votes 534658

reviews 3917

rating 6.5

</details>


[↑ Back to the source list](#source-documents)

---

