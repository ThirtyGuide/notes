# Lecture 3

**Statistical inference and decisions**

[← All chapters](README.md) · [Original PDF](PDF%20Slides.pdf#page=162)

## Overview

- Null and alternative hypotheses; confidence-interval, statistic and p-value approaches.
- Differences between groups, statistical significance, false positives and false negatives.
- Worked conversion-rate and movie-rating examples, plus R methods.

## Source documents

1. [session3_slides_pre_class.pdf](#source-1) — PDF, reader page 163
2. [session3_slides_post_class.pdf](#source-2) — PDF, reader page 190
3. [session3.Rmd](#source-3) — RMD, reader page 220
4. [CVR.csv](#source-4) — CSV, reader page 224
5. [movies.csv](#source-5) — CSV, reader page 225

---

<a name="source-1"></a>

## session3_slides_pre_class.pdf

<small>File type: PDF · Reader pages 163–189 · [View source PDF](PDF%20Slides.pdf#page=163)</small>

<small>Source Page 1 of 56</small>

### Lecture 3

Dr Helen Wang |

<small>Source Page 2 of 56</small>

### New $7 Cup of Coffee at Starbucks

Source: Kimmy Kimmel Live

<small>Source Page 3 of 56</small>

### Weeks 1-6 Outline

Week 01 | Exploratory Data Analysis

Week 02 | Statistics Foundation

Week 03 | Hypothesis -------

Week 04 | Regression, Part I

Week 05 | Regression, Part II

<small>Source Page 4 of 56</small>

01 | Hypothesis -------: Confidence Interval Approach 02 | Hypothesis -------: z/t-statistic Approach 03 | Hypothesis -------: p-value Approach 04 | Automating Hypothesis ------- 05 | ------- for Differences 06 | Statistical Errors

Hypothesis -------

07 | What α to pick?
<small>Source Page 5 of 56</small>

### Nomenclature

Null Hypothesis: H0 belief about true population parameter value Sample mean: H1 alternative

Significance Level: α α= 5% (corresponds to confidence level 1 − α = 95%) is the probability of rejecting the null hypothesis when it is true

Critical value / Cutoff point: z−critical value or t−critical value ±z/t-value which act as cutoff points beyond which the null hypothesis should be rejected

Statistic: z−stat or t−stat standardized value of the sample statistic obtained from the sample

p-value: p probability of obtaining a value of the ---- statistic as extreme as, or more extreme than, the actual value obtained, when the null hypothesis is true

<small>Source Page 6 of 56</small>

01 | Hypothesis -------: Confidence Interval Approach 02 | Hypothesis -------: z/t-statistic Approach 03 | Hypothesis -------: p-value Approach 04 | Automating Hypothesis ------- 05 | ------- for Differences 06 | Statistical Errors

Hypothesis -------

07 | What α to pick?

<small>Source Page 7 of 56</small>

### What is the null hypothesis in these contexts?

Court

H0: The defendant is not guilty

The defendant is assumed to be not guilty until proven guilty beyond a

reasonable doubt.

Production Line

H0: The machine is in normal condition

The machine is assumed to be in normal condition until proven abnormal beyond a reasonable doubt.

Drug Approval

H0: The drug is unsafe

The drug is assumed to be unsafe until proven to be safe beyond a reasonable doubt.
<small>Source Page 8 of 56</small>

### Statistical Hypothesis -------

Hypothesis: is a statement of assertion about the true value of an unknown population parameter (e.g. μ= 100).

Every hypothesis implies its contradiction or an alternative, (e.g. μ≠100).

The validity of a hypothesis is ------ based on sample data and you may “reject it” or “fail to reject it”

How to report results:

“we accept the null hypothesis as truth” “we cannot reject the null hypothesis”

Formulating Hypothesis

- The null hypothesis, H0, is assumed to hold unless we obtain significant evidence

from sample data that suggests otherwise.

- The alternative hypothesis, H1, specifies the range of values that excludes the values

specified by the null.

- Hypothesis notation:

H0: μ= μ0 H1: μ≠μ0

<small>Source Page 9 of 56</small>

### Formulating Hypothesis

Null Hypothesis is typically:

Represents the status quo situation or an existing belief. It is typically a:

- Value that happened in the past (thus you

expect it to reoccur)

- Value claimed (by a company about their

product or service)

- Value meant to occur e.g. based on regulation (a manufactured item with an

expectation of a true mean)

Examples:

- Mutual fund was observed to have average annual return of 5%. Null hypothesis could

state that 5% will continue to be delivered to customers in the future.

- Arla Protein Yogurt is claimed to contain an average of 20g of protein per pot. Null

hypothesis would ---- that claim (i.e. H0: μ= 20).

- A blue-chip company makes a forward-looking statement that a $2 dividend is meant

to occur.
Perform a hypothesis ---- based on past values.

<small>Source Page 10 of 56</small>

### Example

Portfolio Manager’s Decision:

You are a portfolio manager for an investment fund, and your goal is to maintain an average annual return of 8% for your clients.

Use hypothesis ------- at monthly or quarterly interval to examine if your strategy is on track to meet the target average, or if adjustments are needed.

H0: μ= 0.08 H1: μ≠0.08

Steps Needed:

- Data Collection: at the end of each quarter collect monthly return data for the last 12

months.

What you see

- Hypothesis ----: Calculate annualized sample mean return and std dev, then perform

the ----.

What you believe

- Decision: if the sample statistic is significantly different from the hypothesized value,

investment strategy will need to be adjusted.

How different they are

<small>Source Page 11 of 56</small>

### Example: Web Conversion Rate

Default Belief:

```r
CVR (1 for conversion)
```

… …

Customer

Management believes that the mean Conversion Rate (CVR) for Robinhood online brokerage website is 30%, i.e. from all the customers that visited the website 30% performed a desired action (e.g. signed up).

ID

We can write down this hypothesis as:
H0: μ= 0.3 (claim) H1: μ≠0.3 (alternative)

We have a sample of n= 100 observations.

The sample mean is 0.2, i.e. x̄= 0.2.

<small>Source Page 12 of 56</small>

### Example: CVR Hypothesis ----

Setup the Hypothesis ----:

Claim, null hypothesis: H0: μ= 0.3

- A default belief that holds unless we obtain sufficient statistical

95% 2.5% 2.5%

evidence to reject it

- Statistical evidence is to be based on a sample of data

0.3 – 1.96 × SE 0.3 0.3 + 1.96 × SE

Alternative hypothesis: H1: μ≠0.3 We choose significance level of 5% and build a confidence interval around the hypothesized mean.

Hint: Form a confidence interval around the hypothesized mean using formula CI= μ0 ± z s

n.

Open the CVR.csv data in RStudio and find the values you need.

Open session3.Rmd

<small>Source Page 13 of 56</small>

### Example: CVR Hypothesis ----

Perform Hypothesis ----:

Claim, null hypothesis: H0: μ= 0.3

- A default belief that holds unless we obtain sufficient statistical evidence to reject it

- Statistical evidence is to be based on a sample of data Alternative hypothesis: H1:

μ≠0.3

We choose significance level of 5% and build a confidence interval around the hypothesized mean. x̄= 0.2 is NOT within the CI, so we have sufficient evidence to reject the null hypothesis beyond a reasonable doubt.

Conclusion:

Confidence Interval:
CI= μ0 ± z s

n = 0.3 ± 0.0788 = [0.221, 0.378]

95% 2.5% 2.5%

0.3 – 1.96 × 0.402 0.3 0.3 + 1.96 × 0.402

<small>Source Page 14 of 56</small>

### Hypothesis -------: CI Approach

Null hypothesis: H0: μ= μ0

- Claims a value for population mean Alternative hypothesis: H1: μ≠μ0

- Population mean does not equal the claim

Hypothesis ------- Idea:

- Assume hypothesized mean μ0 is true

- Form CI around μ0 (i.e. obtain cutoff points: upper and lower CI bounds)

- Examine whether the sample mean falls within the formed CI

- If it does, do not reject the null hypothesis

Most likely values of x̄, given null hypothesis is correct

μ0 − z s

n μ0 + z s

n

<small>Source Page 15 of 56</small>

### Build CI Around the Claim

Construct CI around μ0

- Form a 95% CI around the claim μ0. For CVR example, n> 30 therefore CLT holds, and

we use the z-value:

C.I.= μ0 ± 1.96 s

n = 0.3 ± 0.0788 = [0.22, 0.38]

- Obtain the sample mean x̄ (i.e., the evidence)

- Check if sample mean is contained inside the CI

Decision:
- Reject the null hypothesis since the sample mean (evidence) is outside of the con‐

structed CI (cutoff points). We reject the null, H0, in favour of the alternative, H1.

- If distance was less than 1.96 × SE, we would not be

able to reject the null hypothesis

95% 2.5% 2.5%

0.22 0.3 0.38

x̄= 0.2

Sample mean is outside!

<small>Source Page 16 of 56</small>

### Build CI Around the Evidence

Construct CI around x̄

- Obtain the sample mean x̄ (i.e., the evidence)

- Form a 95% CI around the evidence, x̄. For CVR example, n> 30 therefore CLT holds,

and we use the z-value:

s

C.I.= x̄± 1.96

n= 0.2 ± 0.0788 = [0.12, 0.28]

- Check if claimed mean is contained inside the CI

Decision:

- Reject the null hypothesis since the claimed mean is outside of the constructed CI

(cutoff points). We reject the null, H0, in favour of the alternative, H1.

- If distance was less than 1.96 × SE, we would not be

able to reject the null hypothesis

95% 2.5% 2.5%

0.12 0.2 0.28

μ0 = 0.3

Claimed value outside!
<small>Source Page 17 of 56</small>

### Hypothesis ------- Cookbook: CI Approach

Step 1 Step 2 Step 2 Step 3

Form a hypothesis H0: μ= μ0

Pick a confidence level

Build CI around the hypothesized mean μ0.

Reject H0 if the sample mean x̄ is outside of the CI.

Build CI around the sample mean

Reject H0 if the hypothesized mean μ0 is outside of the CI.

x̄.

<small>Source Page 18 of 56</small>

### CI Approach: Illustration

Null Hypothesis: true mean is exactly equal to asserted value μ0. If x̄ falls above upper cutoff point or below lower cutoff point, we reject the H0.

Calculating CI Cutoff Points Use t-dist when n< 30 and σ is unknown, otherwise use z. In practice, we can use t for all cases.

- Standard Normal Distribution:

z

α

σ

μ0 ± qnorm 1 −

2 ×

n

- t-Distribution:

t

α

s

μ0 ± qt 1 −

2 , n−1 ×

n
Most likely values of x̄, given null hypothesis is correct

Example CI for 95% (significance level α= 5%)

- z= 1.96 obtained from qnorm(0.975) i.e. 2.5% in each tail

- t obtained from qt(0.975, n-1) i.e. 2.5% in each tail (reminder: t-value depends on the

number of obs, n)

<small>Source Page 19 of 56</small>

### Pen and Paper Exercise

With your classmate next to you, calculate and discuss the following:

Assume the population of interest is approximately Normally distributed, with the population mean unknown. You would like to make an inference about the population mean which you expect takes on the value of 20.9.

---- your above hypothesis using confidence interval approach, assuming a significance level of 10% and the following sample statistics:

x̄= 18.4 s= 4.2 n= 13

Suggested Steps To Consider:

- Write down the hypothesis

- Will you use z or t distribution?

- Build a confidence interval

- Make a decision based on CI

What you see What you believe How different they are

<small>Source Page 20 of 56</small>

01 | Hypothesis -------: Confidence Interval Approach 02 | Hypothesis -------: z/t-statistic Approach 03 | Hypothesis -------: p-value Approach 04 | Automating Hypothesis ------- 05 | ------- for Differences 06 | Statistical Errors

Hypothesis -------

07 | What α to pick?
<small>Source Page 21 of 56</small>

**z/t-stat Approach**

The ---- is performed using a ---- statistic, which is the standardized value derived from sample data, e.g. the standardized value of the sample mean.

x̄−μ0

~N(0,1) use when n≥30 and σ (un)known

z-stat

s n

x̄−μ0

~ T(ν) use when n< 30 and σ unknown

t-stat

s n

If the ---- statistic lands in the rejection region, then the null hypothesis is rejected in favour of the alternative.

Example:

Large sample size with unknown σ, i.e. use a Normal Distribution. Examine how far away is the sample evidence from the claim in terms of standard errors?

Most likely values of z−stat given null hypothesis is correct

−z critical value

+z critical value

= -1.96

= +1.96

<small>Source Page 22 of 56</small>

### CVR Hypothesis -------

- Cutoff points:

Calculate the cutoff points by finding the critical value for significance level of α = 5%. Since n= 100 we use the z-critical value of 1.96, obtained as

0.05

z = qnorm 1−

= qnorm(0.975) = 1.96

If you were using the t-dist you’d obtain the t-critical value as
t = qt 1−0.05

2, 100−1= qt 0. 975, 99= 1.98

- z-stat:

Calculate the z-stat using sample mean and

x̄−μ0

= 0.2−0.3

claim: z−stat=

0.04 = −2.5

s n

see slide 13, where SE = 0.0402

Decision:

Reject the null hypothesis since the absolute value of the statistic exceeds the critical value, i.e. |t-stat| > critical value since we have: |-2.5| > 1.96

Explanation:

The calculated z-stat falls outside the 95% body of the Normal distribution, therefore it’s an unlikely value for the sample mean if the null hypothesis was true.

<small>Source Page 23 of 56</small>

### Example: CVR ---- Illustration

Most likely values of z−stat given null hypothesis is correct

z-stat = -2.5

−z critical value

+z critical value

= -1.96

= +1.96

Decision: Reject H0: μ= 0.3 since |-2.5| > 1.96

<small>Source Page 24 of 56</small>

### Pen and Paper Exercise

With your classmate next to you, calculate and discuss the following:
Assume the population of interest is approximately Normally distributed, with the population mean unknown. You would like to make an inference about the population mean which you expect takes on the value of 20.9.

---- your above hypothesis using z/t-stat approach, assuming a significance level of 5% and the following sample statistics:

x̄= 18.4 s= 4.2 n= 13

Suggested Steps To Consider:

- Write down the hypothesis

- Will you use z or t critical value?

- Calculate z/t-stat

- Make a decision based on how the statistic compares to the critical level

What you see What you believe How different they are

<small>Source Page 25 of 56</small>

01 | Hypothesis -------: Confidence Interval Approach 02 | Hypothesis -------: z/t-statistic Approach 03 | Hypothesis -------: p-value Approach 04 | Automating Hypothesis ------- 05 | ------- for Differences 06 | Statistical Errors

Hypothesis -------

07 | What α to pick?

<small>Source Page 26 of 56</small>

**p-value Approach**

p-value Definition:

- p-value is the probability of obtaining a value of the ---- statistic (z/t-stat) as extreme

as, or more extreme than, the actual value obtained from the sample, when the null hypothesis is true

- p-value gives the probability of observing the ---- statistic (z/t-stat) if the hypothesis

was true.

Significance level is the minimum p-value that we allow if the hypothesis was true (e.g. α= 5%)

Example:

- If we found z-stat = -2.5, we can mark this on the Normal distribution as before, and

find the probability P(Z< −2.5) + P(Z> 2.5) which in total equals to the p-value.

Standard Normal distribution if using z-statistic
(t-distribution if using t-statistic)

more extreme than -2.5

more extreme than 2.5

<small>Source Page 27 of 56</small>

### Hypothesis ------- with p-value

p-value Calculation Steps:

Step1: Calculate the z/t-stat using the formula (use σ if

x̄−μ0

it is known):

s n

Step 2: Calculate the total probability in the tails to the left and right of the z/t-stat using a function in R

Step 3: Compare the total probability (also known as the p-value, e.g. p= 1.2%) with the significance level (e.g. α= 5%)

Step 4: Decision, reject H0 if the p-value < α

Surprising:

p< 0.05

2.5% 2.5%

Not surprising:

p> 0.05

95%

<small>Source Page 28 of 56</small>

**p-value Calculation**

Using R obtain the tail probability to the left of the negative statistic and multiply it by 2, since this probability is equal in both tails by symmetry.

We formulate a general syntax, that always uses notation –abs() to avoid mistakes:

p-value Calculation for z-stat: p <- 2 * mosaic::xpnorm(abs(z_statistic))

p-value Calculation for t-stat: p <- 2 * pt(-abs(t_statistic), n-1)

p-value CVR Example:
We use z-stat since n=100 is >30. Hence:

z −stat= x̄−μ0

SE = 0.2 −0.3

0.0402 = −2.49

```r
p <- 2 * mosaic::xpnorm(-abs(-2.49))
```

p-value = 2 × 0.00639 = 1.28%, i.e.

2 x

<small>Source Page 29 of 56</small>

**p-value Approach: Overall Steps**

- Write down the hypothesis

H0: μ= μ0 H1: μ≠μ0

- Choose significance level, typically α= 5%

- Decide if you are using z or t-distribution and

x̄−μ0

calculate z/t-statistic using formula:

SE

- Use R to calculate p-value as:

- If using z-statistic, the p-value is: p <- 2 * mosaic::xpnorm(-abs(z_stat))

- If using t-statistic, the p-value is: p <- 2 * pt(-abs(t_stat), n-1)

- Make a decision:

- If p-value < 0.05 reject the null hypothesis, the result is significant.

- If p-value > 0.05 cannot reject the null

hypothesis.

What you see What you believe How different they are

<small>Source Page 30 of 56</small>

01 | Hypothesis -------: Confidence Interval Approach 02 | Hypothesis -------: z/t-statistic Approach 03 | Hypothesis -------: p-value Approach 04 | Automating Hypothesis ------- 05 | ------- for Differences 06 | Statistical Errors

Hypothesis -------
07 | What α to pick?

<small>Source Page 31 of 56</small>

### Automating Hypothesis -------

One Sample t-----:

Use a function from the stats package to produce the results from all three approaches in a single table (i.e. the CI approach, z/t-stat approach, pvalue approach)

```r
# set 5 decimal places or results will be rounded options(digits = 5) stats::t.----(x, mu =
mu0, data = data)
```

where: x is column of numeric sample data mu hypothesized mean data variable name containing your dataset

Example for CVR dataset:

```r
options(digits = 5) stats::t.----(cvr$conversion, mu=0.3, data=cvr)
```

Values agree with the three manual calculations.

Note, p-value was calculated using the function pt() for t-stat, not xpnorm() for z-stat.

Open session3.Rmd

<small>Source Page 32 of 56</small>

### Hypothesis ------- Recipe

- Set up the hypothesis

```r
Claim (null hypothesis): H0: CVR = 0.3 Alternative hypothesis:  Ha: CVR  0.3 (two tail
hypothesis)
```

What you believe

- Take a sample

Sample Mean (Evidence) = 0.2 SE = 0.04

What you see

- Choose significance level, typically 5%

Corresponds to 95% confidence (approximately ± 2*SE)

- Use one of three possible methods to decide whether to reject or not reject the null

hypothesis
CVR Example, Three Methods Results:

- Confidence Intervals: claim, 0.3, was outside of CI [0.12,0.28] thus we reject H0

- z-statistic: z-stat was found to be -2.49. Since

| −2.49| > 2 we reject H0

- p-value: p-value was 0.0128, since 0.0128 < 0.05 (i.e. 1.28% < 5%) we reject H0

How different they are

<small>Source Page 33 of 56</small>

### Decision Rule Summary

We have 3 equivalent ways of ------- hypothesis. The decision taken based on one approach will agree with the rest, therefore you only need to use a single approach (recommended approach: p-value).

Approach Decision Rule Calculation

```r
Approach (1) Confidence Interval (CI built around x̄) Confidence Interval (CI built around
μ0)
```

Reject H0 if claim (μ0) is outside CI Reject H0 if evidence ( x̄) is outside CI

s

x̄ ± z

```r
n (use z, or t)*
```

s

μ0 ± z

```r
n (use z, or t)*
Approach (2) t-statistic z-statistic
```

Reject H0 if |t-stat| > critical level t Reject H0 if |z-stat| > critical level z

For α= 5% use t = qt(0.975, n-1) For α= 5% use z = qnorm(0.975)

```r
Approach (3) p-value (find probability for t-stat) Reject H0 if p< α Typical α:
```

0.01 1% , 0.05 5% , 0.10(10%)

For α= 5% use p=2*pt(-abs(tstat),n-1)
For ----: use t if n< 30, population distribution is Normal, and σ is unknown. Otherwise, use z.

But! in practice we always use t since the t-distribution converges to Standard Normal as sample size increases. For ----: for 95% confidence level (i.e. 5% critical level) use z= 1.96 or round up to z= 2.

<small>Source Page 34 of 56</small>

### Comprehension Questions

With your classmate next to you, discuss the following:

- Explain the meaning of the null hypothesis?

- Verbalize the steps involved in performing a hypothesis ----.

- In which case do we reject the null hypothesis when basing the ---- on Confidence In‐

tervals?

- In the z/t-statistic approach to hypothesis -------, what is the difference between the

terms “z-critical value” and the “z-statistic”? How is each obtained?

- In the p-value approach to hypothesis -------, how is the p-value obtained? Specify the

function which you’d need to use when working with z-statistic and the t-statistic.

<small>Source Page 35 of 56</small>

01 | Hypothesis -------: Confidence Interval Approach 02 | Hypothesis -------: z/t-statistic Approach 03 | Hypothesis -------: p-value Approach 04 | Automating Hypothesis ------- 05 | ------- for Differences 06 | Statistical Errors

Hypothesis -------

07 | What α to pick?

<small>Source Page 36 of 56</small>

### Motivation

Examples of ------- for Differences

- Difference between true mean of two stocks

- Difference in true mean sales volume of two agents

- Difference in true mean salaries between different

groups of employees
The difference between two sample means can be due to a real difference between true mean parameters of the groups (significant difference) or due to the inherent randomness in the sampling process (sampling error).

When can we conclude there is a difference in true means?

Start with the theory there is no difference, then try to disprove it by finding significant evidence from data.

For 2 groups:

Group 1 Group 2

μ1, σ1 μ2, σ2

Formulate the hypothesis as:

H0: μ1 −μ2 = 0 H1: μ1 −μ2 ≠0

<small>Source Page 37 of 56</small>

### ------- for Differences: CI Approach

Build a joint confidence interval Take a random sample from each population of size n1 and n2, respectively (unequal sample sizes is ok).

Calculate sample means x̄1 and x̄2 and obtain their difference x̄1 −x̄2.

Null hypothesis: no difference between population means (μ1 = μ2) i.e. samples are drawn from 2 populations with the same mean.

Establish sampling distribution of differences in means approx. Normally distributed by CLT if n> 30 or tdistributed if group populations are Normal, standard deviations are unknown and n< 30

Joint CI Calculation Assume n is large, then by CLT we can use z-value.

The standard error is:

Replace with σ1 and σ2 if they are known.

SE x̄1 −x̄2 = s12

+ s22

n1

n2

The 95% Confidence Interval for the difference between means is:

Use z= 2 as approxim ation

( x̄1−x̄2) ± zs12

+ s22
n1

n2

Decision rule: if the joint CI does not contain 0, then reject the null, H0.

<small>Source Page 38 of 56</small>

### Hypothesis ------- Recipe

Hypothesis Setup:

Equivalent ways of writing the hypothesis, where δ= μ1 −μ2

H0: μ1 −μ2 = 0 H1: μ1 −μ2 ≠0

H0: δ= 0 H1: δ≠0

From a sample of data calculate:

- Sample statistic: δ∗ (i.e., δ∗= x̄1 −x̄2)

- Standard error: SE = s12

n1 + s22

n2

Choose a significance level, typically use = 5%

Hypothesis ----:

You can start by building two separate CI around each x̄ . If CI don’t overlap, reject H0.

If they overlap use any of the 3 methods below to run an official statistical ----:

- Joint Confidence Interval

- t-stat

- p-value

<small>Source Page 39 of 56</small>

### Equivalent Approaches

Joint Confidence Interval:

Build a joint CI as:

( x̄1−x̄2) ± zs12

+ s22

n1
n2 Decision: If CI doesn't contain 0, reject H0.

Calculate t-stat:

Obtain t-stat as:

( x̄1−x̄2) −0

t−stat =

s12

n1 +s22

n2

Decision: If |t−stat| > 2 reject H0.

p-value:

Calculate p-value as:

2*pt(-abs(t_stat), m) where

Decision: If p<0.05 reject H0.

R Software:

Obtain all three above results in a single function call:

stats::t.----()

<small>Source Page 40 of 56</small>

### ------- for Differences Mean Movie Ratings

Do movies from different genre have different population mean ratings?

Consider Biography vs. Horror movie rating CI. Difference of the 95% CI is so pronounced, that we don’t need to run a ----.

What about: Crime vs. Drama? or Action vs. Comedy? We can see an overlap of individual Confidence Intervals, therefore need to run an official t-----.

<small>Source Page 41 of 56</small>

### ------- for Differences Mean Movie Ratings

When comparing means we do not care about differences in individual values. For example, in Biography vs. Horror, there can be an individual horror movie that has a higher rating than a Bio movie. We care whether the population mean rating between groups is the same or not.
<small>Source Page 42 of 56</small>

### Action vs. Comedy

Let’s use the following information to compare mean rating of Action vs Comedy genre.

First consideration: will we work with z or t distribution?

<small>Source Page 43 of 56</small>

### Action vs. Comedy, CI Approach

Individual CI:

Is there a difference in true population mean between Action and Comedy genres? Build two CIs for mean rating using formula and check whether they overlap.

Action CI = 6.23 ± 1.96 ∗ 1.03

≈[6.16, 6.31]

Comedy CI = 6.11 ± 1.96 ∗ 1.02

≈[6.04, 6.18]

Decision: ?

Joint CI:

Build a single CI for mean difference in ratings using formula and check whether CI contains zero.

x̄1 −x̄2 ± 1.96 s1

+ s2

n1

n2

= 6.23 −6.11 ± 1.96 1.032

738 + 1.022

= 0.02, 0.22

Decision: ?

<small>Source Page 44 of 56</small>

### Action vs. Comedy, CI Approach

Individual CI:
Is there a difference in true population mean between Action and Comedy genres? Build two CIs for mean rating using formula and check whether they overlap.

Action CI = 6.23 ± 1.96 ∗ 1.03

≈[6.16, 6.31]

Comedy CI = 6.11 ± 1.96 ∗ 1.02

≈[6.04, 6.18]

Decision:

CI overlap therefore we need to build joint CI and perform an official statistical ---- for difference.

Joint CI:

Build a single CI for mean difference in ratings using formula and check whether CI contains zero.

x̄1 −x̄2 ± 1.96 s1

+ s2

n1

n2

= 6.23 −6.11 ± 1.96 1.032

738 + 1.022

= 0.02, 0.22

Decision:

CI does not contain 0, therefore we reject the null hypothesis that the two population means are the same.

<small>Source Page 45 of 56</small>

### Automating Hypothesis -------

Welch Two Sample t-----:

Use Two Sample Assuming Unequal Variances t----- (Welch Two Sample t-----) to produce the results of the three different approaches. Use the function based on if your data is in long or wide format.

Data in wide format:

options(digits = 5) stats::t.----(data$x1, data$x2, data=data) where: data$x1 group1 sample data (numeric) data$x2 group2 sample data (numeric) data variable name containing your dataset
Data in long format:

```r
options(digits = 5) stats::t.----(x ~ c, data = data) where: x  column of sample data
(numeric) c  categorical column (as factor) data  variable name containing your dataset
```

Our movies data is in the long format:

```r
action_comedy <- movies %>% filter(genre %in% c("Action", "Comedy")) %>% select(genre,
rating)
```

<small>Source Page 46 of 56</small>

### Automating Hypothesis -------

Compare Action vs Comedy using stats::t.----(): options(digits = 5) t.----(rating ~ genre, data = action_comedy)

numeric binary (factor)

Base Decision on either:

C.I. does not include 0

p-value < 0.05

t-stat > 1.96

Decision: reject H0

Open session3.Rmd

<small>Source Page 47 of 56</small>

### Pen and Paper Exercise

With your classmate next to you, discuss the following:

Two Business Schools decided to compare the average scores that their -------- achieved in the math ----. Establish if there is truly a difference in population means between the math -------- in the two different schools. Use a significance level of α= 5%. Build a joint CI. What is the conclusion?

The following sample statistics have been found:

school school_1 school_2
<small>Source Page 48 of 56</small>

01 | Hypothesis -------: Confidence Interval Approach 02 | Hypothesis -------: z/t-statistic Approach 03 | Hypothesis -------: p-value Approach 04 | Automating Hypothesis ------- 05 | ------- for Differences 06 | Statistical Errors

Hypothesis -------

07 | What α to pick?

<small>Source Page 49 of 56</small>

### Types of Statistical Errors

Because of the potential for extreme sampling error, two possible errors can occur when a hypothesis is ------: Type I and Type II errors. These errors show the relationship between what actually exists (a state of nature) and the decision made based on the sample information.

<small>Source Page 50 of 56</small>

### Type I vs Type II Errors

Type I Error:

α = P(reject a true null ℎypotℎesis)

α is the probability of making a Type I Error!

H0: not pregnant H1: pregnant

False Positive: concluding something exists when it doesn’t

Type II Error:

β = P(fail to reject a false null ℎypotℎesis)

H0: not pregnant H1: pregnant

False Negative: concluding there is no effect when there is; i.e. missing a true positive

<small>Source Page 51 of 56</small>

### Significance Level: Hypothesis -------

What is the effect of the significance level on hypothesis -------?

95% Confidence: (α= 5%) z-critical value 1.96

Say you had a t-statistic = 1.876
90% Confidence: (α= 10%) z-critical value 1.64

t-stat = 1.876 t-stat = 1.876

95%

2.5% 2.5% 5% 5%

-1. 96 +1. 96 -1. 64 +1. 64

|1.876| < 1.96, therefore we would not reject H0.

|1.876| > 1.64, therefore we would reject H0.

A smaller Confidence Level (larger α) leads to a more precise but less confident result (higher risk, 10%, of rejecting a true null hypothesis).

90%

<small>Source Page 52 of 56</small>

### Significance Level: Confidence Interval

What is the effect of the significance level on Confidence Interval formation?

95% CI:

x̄ ± 1. 96∗s

n= 18.4 ± 1.96 ∗4.2

50 = [17.236, 19.564]

90% CI:

s

4.2

x̄ ± 1. 64∗

n= 18.4 ± 1.64 ∗

50 = [17.426, 19.374]

Smaller α (e.g. 5%) Wider CI (less precise)

Larger α (e.g. 10%) Narrower CI (more precise)

17.2 19.6

17.4 19.3

Less likely to make Type I error (more confident)

More likely to make Type II error

More likely to make Type I error (less confident)
Less likely to make Type II error

<small>Source Page 53 of 56</small>

### Industry Conventions for α

Conventions in Your Industry:

Psychology / education α= 0.05 Good balance of avoiding false positives and detecting genuine effects.

Physics / chemistry α= 0.001 Stricter threshold ensures extremely robust findings, i.e. assume your idea is not correct and let the evidence reject this null.

Marketing / finance α= 0.1 Typically, data has inherent noise. Larger α means we will reject the null hypothesis more often thus giving us a greater chance of detecting potential trends among noise. Missing a true positive (Type II error) could mean missing an important business opportunity.

Examples:

H0: μnew teacℎing metℎod−μold teacℎing metℎod= 0 H1: μnew teacℎing metℎod−μold teacℎing metℎod≠0

H0: μ= μtℎere is no life on tℎe moon H1: μ≠μtℎere is life on tℎe moon

H0: μsales after advertising−μsales before advertising= 0 H1: μsales after advertising−μsales before advertising≠0

<small>Source Page 54 of 56</small>

### False Positives vs False Negatives

https://www.theguardian.com/society/article/2024/jun/23/dwp-algorithm-wronglyflags-200000-people-possible-fraud-error https://www.nytimes.com/interactive/2024/07/18/ technology/spain-domestic-violence-viogen-algorithm.html

<small>Source Page 55 of 56</small>

### What α Shall I Pick?

General Convention:

Factors that influence choice of significance level:

Significance Level (α) is the probability of rejecting a null hypothesis when it is true.

Sample Size and Variance
- More Stable Results happen when: you have large sample size and low variance Use a

lower significance level to α= 0.01 to increase the confidence in your results, i.e. setting stricter threshold for declaring significance (reject less often)

Standard choice of alpha is 5% (α = 0.05) is commonly used across many fields.

There are some factors that may influence your choice of the significance level.

- More Unstable Results happen when: you have small sample size and high variance

Use a higher significance level to 10% (α= 0.1) i.e. more willing to detect significance (reject more often)

<small>Source Page 56 of 56</small>

### Session Summary

We covered:

Hypothesis ------- ------- for Difference

Readings:

Modern Dives chapter 9

Optional/ Extra practice: workshop3.Rmd

Workshop Questions:

Look at the workshop questions in advance.

Attend optional workshop to go over the solutions.


[↑ Back to the source list](#source-documents)

---

<a name="source-2"></a>

## session3_slides_post_class.pdf

<small>File type: PDF · Reader pages 190–219 · [View source PDF](PDF%20Slides.pdf#page=190)</small>

<small>Source Page 1 of 62</small>

### Lecture 3

Dr Helen Wang |

<small>Source Page 2 of 62</small>

### New $7 Cup of Coffee at Starbucks

Source: Kimmy Kimmel Live

<small>Source Page 3 of 62</small>

### Weeks 1-5 Outline

Week 01 | Exploratory Data Analysis

Week 02 | Statistics Foundation

Week 03 | Hypothesis -------

Week 04 | Regression, Part I

Week 05 | Regression, Part II

<small>Source Page 4 of 62</small>

01 | Hypothesis -------: Confidence Interval Approach 02 | Hypothesis -------: z/t-statistic Approach 03 | Hypothesis -------: p-value Approach 04 | Automating Hypothesis ------- 05 | ------- for Differences 06 | Statistical Errors

Hypothesis -------

07 | What α to pick?
<small>Source Page 5 of 62</small>

### Nomenclature

Null Hypothesis: H0 belief about true population parameter value Sample mean: H1 alternative

Significance Level: α α= 5% (corresponds to confidence level 1 − α = 95%) is the probability of rejecting the null hypothesis when it is true

Critical value / Cutoff point: z−critical value or t−critical value ±z/t-value which act as cutoff points beyond which the null hypothesis should be rejected

Statistic: z−stat or t−stat standardized value of the sample statistic obtained from the sample

p-value: p probability of obtaining a value of the ---- statistic as extreme as, or more extreme than, the actual value obtained, when the null hypothesis is true

<small>Source Page 6 of 62</small>

01 | Hypothesis -------: Confidence Interval Approach 02 | Hypothesis -------: z/t-statistic Approach 03 | Hypothesis -------: p-value Approach 04 | Automating Hypothesis ------- 05 | ------- for Differences 06 | Statistical Errors

Hypothesis -------

07 | What α to pick?

<small>Source Page 7 of 62</small>

### What is the null hypothesis in these contexts?

Court

H0: The defendant is not guilty

The defendant is assumed to be not guilty until proven guilty beyond a

reasonable doubt.

Production Line

H0: The machine is in normal condition

The machine is assumed to be in normal condition until proven abnormal beyond a reasonable doubt.

Drug Approval

H0: The drug is unsafe

The drug is assumed to be unsafe until proven to be safe beyond a reasonable doubt.
<small>Source Page 8 of 62</small>

### Statistical Hypothesis -------

Hypothesis: is a statement of assertion about the true value of an unknown population parameter (e.g. μ= 100).

Every hypothesis implies its contradiction or an alternative, (e.g. μ≠100).

The validity of a hypothesis is ------ based on sample data and you may “reject it” or “fail to reject it”

How to report results:

“we accept the null hypothesis as truth” “we cannot reject the null hypothesis”

Formulating Hypothesis

- The null hypothesis, H0, is assumed to hold unless we obtain significant evidence

from sample data that suggests otherwise.

- The alternative hypothesis, H1, specifies the range of values that excludes the values

specified by the null.

- Hypothesis notation:

H0: μ= μ0 H1: μ≠μ0

<small>Source Page 9 of 62</small>

### Formulating Hypothesis

Null Hypothesis is typically:

Represents the status quo situation or an existing belief. It is typically a:

- Value that happened in the past (thus you

expect it to reoccur)

- Value claimed (by a company about their

product or service)

- Value meant to occur e.g. based on regulation (a manufactured item with an

expectation of a true mean)

Examples:

- Mutual fund was observed to have average annual return of 5%. Null hypothesis could

state that 5% will continue to be delivered to customers in the future.

- Arla Protein Yogurt is claimed to contain an average of 20g of protein per pot. Null

hypothesis would ---- that claim (i.e. H0: μ= 20).

- A blue-chip company makes a forward-looking statement that a $2 dividend is meant

to occur.
Perform a hypothesis ---- based on past values.

<small>Source Page 10 of 62</small>

### Example

Portfolio Manager’s Decision:

You are a portfolio manager for an investment fund, and your goal is to maintain an average annual return of 8% for your clients.

Use hypothesis ------- at monthly or quarterly interval to examine if your strategy is on track to meet the target average, or if adjustments are needed.

H0: μ= 0.08 H1: μ≠0.08

Steps Needed:

- Data Collection: at the end of each quarter collect monthly return data for the last 12

months.

What you see

- Hypothesis ----: Calculate annualized sample mean return and std dev, then perform

the ----.

What you believe

- Decision: if the sample statistic is significantly different from the hypothesized value,

investment strategy will need to be adjusted.

How different they are

<small>Source Page 11 of 62</small>

### Example: Web Conversion Rate

Default Belief:

```r
CVR (1 for conversion)
```

… …

Customer

Management believes that the mean Conversion Rate (CVR) for Robinhood online brokerage website is 30%, i.e. from all the customers that visited the website 30% performed a desired action (e.g. signed up).

ID

We can write down this hypothesis as:
H0: μ= 0.3 (claim) H1: μ≠0.3 (alternative)

We have a sample of n= 100 observations.

The sample mean is 0.2, i.e. x̄= 0.2.

<small>Source Page 12 of 62</small>

### Example: CVR Hypothesis ----

Setup the Hypothesis ----:

Claim, null hypothesis: H0: μ= 0.3

- A default belief that holds unless we obtain sufficient statistical

95% 2.5% 2.5%

evidence to reject it

- Statistical evidence is to be based on a sample of data

0.3 – 1.96 × SE 0.3 0.3 + 1.96 × SE

Alternative hypothesis: H1: μ≠0.3 We choose significance level of 5% and build a confidence interval around the hypothesized mean.

Hint: Form a confidence interval around the hypothesized mean using formula CI= μ0 ± z s

n.

Open the CVR.csv data in RStudio and find the values you need.

Open session3.Rmd

<small>Source Page 13 of 62</small>

### Example: CVR Hypothesis ----

Perform Hypothesis ----:

Claim, null hypothesis: H0: μ= 0.3

- A default belief that holds unless we obtain sufficient statistical evidence to reject it

- Statistical evidence is to be based on a sample of data Alternative hypothesis: H1:

μ≠0.3

We choose significance level of 5% and build a confidence interval around the hypothesized mean. x̄= 0.2 is NOT within the CI, so we have sufficient evidence to reject the null hypothesis beyond a reasonable doubt.

Conclusion:

Confidence Interval:
CI= μ0 ± z s

n = 0.3 ± 0.0788 = [0.221, 0.378]

95% 2.5% 2.5%

0.3 – 1.96 × 0.402 0.3 0.3 + 1.96 × 0.402

<small>Source Page 14 of 62</small>

### Hypothesis -------: CI Approach

Null hypothesis: H0: μ= μ0

- Claims a value for population mean Alternative hypothesis: H1: μ≠μ0

- Population mean does not equal the claim

Hypothesis ------- Idea:

- Assume hypothesized mean μ0 is true

- Form CI around μ0 (i.e. obtain cutoff points: upper and lower CI bounds)

- Examine whether the sample mean falls within the formed CI

- If it does, do not reject the null hypothesis

Most likely values of x̄, given null hypothesis is correct

μ0 − z s

n μ0 + z s

n

<small>Source Page 15 of 62</small>

### Build CI Around the Claim

Construct CI around μ0

- Form a 95% CI around the claim μ0. For CVR example, n> 30 therefore CLT holds, and

we use the z-value:

C.I.= μ0 ± 1.96 s

n = 0.3 ± 0.0788 = [0.22, 0.38]

- Obtain the sample mean x̄ (i.e., the evidence)

- Check if sample mean is contained inside the CI

Decision:
- Reject the null hypothesis since the sample mean (evidence) is outside of the con‐

structed CI (cutoff points). We reject the null, H0, in favour of the alternative, H1.

- If distance was less than 1.96 × SE, we would not be

able to reject the null hypothesis

95% 2.5% 2.5%

0.22 0.3 0.38

x̄= 0.2

Sample mean is outside!

<small>Source Page 16 of 62</small>

### Build CI Around the Evidence

Construct CI around x̄

- Obtain the sample mean x̄ (i.e., the evidence)

- Form a 95% CI around the evidence, x̄. For CVR example, n> 30 therefore CLT holds,

and we use the z-value:

s

C.I.= x̄± 1.96

n= 0.2 ± 0.0788 = [0.12, 0.28]

- Check if claimed mean is contained inside the CI

Decision:

- Reject the null hypothesis since the claimed mean is outside of the constructed CI

(cutoff points). We reject the null, H0, in favour of the alternative, H1.

- If distance was less than 1.96 × SE, we would not be

able to reject the null hypothesis

95% 2.5% 2.5%

0.12 0.2 0.28

μ0 = 0.3

Claimed value outside!
<small>Source Page 17 of 62</small>

### Hypothesis ------- Cookbook: CI Approach

Step 1 Step 2 Step 2 Step 3

Form a hypothesis H0: μ= μ0

Pick a confidence level

Build CI around the hypothesized mean μ0.

Reject H0 if the sample mean x̄ is outside of the CI.

Build CI around the sample mean

Reject H0 if the hypothesized mean μ0 is outside of the CI.

x̄.

<small>Source Page 18 of 62</small>

### CI Approach: Illustration

Null Hypothesis: true mean is exactly equal to asserted value μ0. If x̄ falls above upper cutoff point or below lower cutoff point, we reject the H0.

Calculating CI Cutoff Points Use t-dist when n< 30 and σ is unknown, otherwise use z. In practice, we can use t for all cases.

- Standard Normal Distribution:

z

α

σ

μ0 ± qnorm 1 −

2 ×

n

- t-Distribution:

t

α

s

μ0 ± qt 1 −

2 , n−1 ×

n
Most likely values of x̄, given null hypothesis is correct

Example CI for 95% (significance level α= 5%)

- z= 1.96 obtained from qnorm(0.975) i.e. 2.5% in each tail

- t obtained from qt(0.975, n-1) i.e. 2.5% in each tail (reminder: t-value depends on the

number of obs, n)

<small>Source Page 19 of 62</small>

### Pen and Paper Exercise

With your classmate next to you, calculate and discuss the following:

Assume the population of interest is approximately Normally distributed, with the population mean unknown. You would like to make an inference about the population mean which you expect takes on the value of 20.9.

---- your above hypothesis using confidence interval approach, assuming a significance level of 10% and the following sample statistics:

x̄= 18.4 s= 4.2 n= 13

Suggested Steps To Consider:

- Write down the hypothesis

- Will you use z or t distribution?

- Build a confidence interval

- Make a decision based on CI

What you see What you believe How different they are

<small>Source Page 20 of 62</small>

### Answer

The hypothesis is:

H0: μ0 = 20.9 H1: μ0 ≠20.9

- Since n< 30 and σ is unknown use the t-distribution with n−1 = 12 degrees of

freedom. The t-value is

t = qt(0.95, 12), t = 1.7823

- Calculate the Standard Error: SE = s 13 = 1.1649

- Create the confidence interval either around the evidence or the claim. CI around the

evidence is:

x̄ ± t∗SE = 18.4 ± 1.7823 ∗1.1649 = 18.4 ± 2.0762 = [16.324, 20.476]
- Reject the null hypothesis since the confidence interval does not contain the claim.

<small>Source Page 21 of 62</small>

01 | Hypothesis -------: Confidence Interval Approach 02 | Hypothesis -------: z/t-statistic Approach 03 | Hypothesis -------: p-value Approach 04 | Automating Hypothesis ------- 05 | ------- for Differences 06 | Statistical Errors

Hypothesis -------

07 | What α to pick?

<small>Source Page 22 of 62</small>

**z/t-stat Approach**

The ---- is performed using a ---- statistic, which is the standardized value derived from sample data, e.g. the standardized value of the sample mean.

x̄−μ0

~N(0,1) use when n≥30 and σ (un)known

z-stat

s n

x̄−μ0

~ T(ν) use when n< 30 and σ unknown

t-stat

s n

If the ---- statistic lands in the rejection region, then the null hypothesis is rejected in favour of the alternative.

Example:

Large sample size with unknown σ, i.e. use a Normal Distribution. Examine how far away is the sample evidence from the claim in terms of standard errors?

Most likely values of z−stat given null hypothesis is correct

−z critical value

+z critical value

= -1.96

= +1.96
<small>Source Page 23 of 62</small>

### CVR Hypothesis -------

- Cutoff points:

Calculate the cutoff points by finding the critical value for significance level of α = 5%. Since n= 100 we use the z-critical value of 1.96, obtained as

0.05

z = qnorm 1−

= qnorm(0.975) = 1.96

If you were using the t-dist you’d obtain the t-critical value as

t = qt 1−0.05

2, 100−1= qt 0. 975, 99= 1.98

- z-stat:

Calculate the z-stat using sample mean and

x̄−μ0

= 0.2−0.3

claim: z−stat=

0.04 = −2.5

s n

see slide 13, where SE = 0.0402

Decision:

Reject the null hypothesis since the absolute value of the statistic exceeds the critical value, i.e. |t-stat| > critical value since we have: |-2.5| > 1.96

Explanation:

The calculated z-stat falls outside the 95% body of the Normal distribution, therefore it’s an unlikely value for the sample mean if the null hypothesis was true.

<small>Source Page 24 of 62</small>

### Example: CVR ---- Illustration

Most likely values of z−stat given null hypothesis is correct

z-stat = -2.5

−z critical value
+z critical value

= -1.96

= +1.96

Decision: Reject H0: μ= 0.3 since |-2.5| > 1.96

<small>Source Page 25 of 62</small>

### Pen and Paper Exercise

With your classmate next to you, calculate and discuss the following:

Assume the population of interest is approximately Normally distributed, with the population mean unknown. You would like to make an inference about the population mean which you expect takes on the value of 20.9.

---- your above hypothesis using z/t-stat approach, assuming a significance level of 5% and the following sample statistics:

x̄= 18.4 s= 4.2 n= 13

Suggested Steps To Consider:

- Write down the hypothesis

- Will you use z or t critical value?

- Calculate z/t-stat

- Make a decision based on how the statistic compares to the critical level

What you see What you believe How different they are

<small>Source Page 26 of 62</small>

### Answer

The hypothesis is:

H0: μ0 = 20.9 Ha: μ0 ≠20.9

- Since n< 30 and σ is unknown use the t-critical value with n−1 = 12 degrees of

freedom. The t-

value is

t−critical value = qt(0.975, 12), t = 2.1788

- Calculate the t−stat: 18.4−20.9

= −2.146

4.2
- Compare t-critical level with the t-statistic: |t−stat| < critical value since −2.14 < 2.18

- We cannot reject the null hypothesis at 5% significance level since the the observed t-

statistic does

not fall into the rejection region.

<small>Source Page 27 of 62</small>

01 | Hypothesis -------: Confidence Interval Approach 02 | Hypothesis -------: z/t-statistic Approach 03 | Hypothesis -------: p-value Approach 04 | Automating Hypothesis ------- 05 | ------- for Differences 06 | Statistical Errors

Hypothesis -------

07 | What α to pick?

<small>Source Page 28 of 62</small>

**p-value Approach**

p-value Definition:

- p-value is the probability of obtaining a value of the ---- statistic (z/t-stat) as extreme

as, or more extreme than, the actual value obtained from the sample, when the null hypothesis is true

- p-value gives the probability of observing the ---- statistic (z/t-stat) if the hypothesis

was true.

Significance level is the minimum p-value that we allow if the hypothesis was true (e.g. α= 5%)

Example:

- If we found z-stat = -2.5, we can mark this on the Normal distribution as before, and

find the probability P(Z < −2.5) + P(Z> 2.5) which in total equals to the p-value.

Standard Normal distribution if using z-statistic

(t-distribution if using t-statistic)

more extreme than -2.5

more extreme than 2.5

<small>Source Page 29 of 62</small>

### Hypothesis ------- with p-value

p-value Calculation Steps:
Step1: Calculate the z/t-stat using the formula (use σ if

x̄−μ0

it is known):

s n

Step 2: Calculate the total probability in the tails to the left and right of the z/t-stat using a function in R

Step 3: Compare the total probability (also known as the p-value, e.g. p= 1.2%) with the significance level (e.g. α = 5%)

Step 4: Decision, reject H0 if the p-value < α

Surprising:

p< 0.05

2.5% 2.5%

Not surprising:

p> 0.05

95%

<small>Source Page 30 of 62</small>

**p-value Calculation**

Using R obtain the tail probability to the left of the negative statistic and multiply it by 2, since this probability is equal in both tails by symmetry.

We formulate a general syntax, that always uses notation –abs() to avoid mistakes:

p-value Calculation for z-stat: p <- 2 * mosaic::xpnorm(abs(z_statistic))

p-value Calculation for t-stat: p <- 2 * pt(-abs(t_statistic), n-1)

p-value CVR Example:

We use z-stat since n=100 is >30. Hence:

z −stat= x̄−μ0

SE = 0.2 −0.3

0.0402 = −2.49

```r
p <- 2 * mosaic::xpnorm(-abs(-2.49))
```

p-value = 2 × 0.00639 = 1.28%, i.e.

2 x
<small>Source Page 31 of 62</small>

**p-value Approach: Overall Steps**

- Write down the hypothesis

H0: μ= μ0 H1: μ≠μ0

- Choose significance level, typically α= 5%

- Decide if you are using z or t-distribution and

x̄−μ0

calculate z/t-statistic using formula:

SE

- Use R to calculate p-value as:

- If using z-statistic, the p-value is: p <- 2 * mosaic::xpnorm(-abs(z_stat))

- If using t-statistic, the p-value is: p <- 2 * pt(-abs(t_stat), n-1)

- Make a decision:

- If p-value < 0.05 reject the null hypothesis, the result is significant.

- If p-value > 0.05 cannot reject the null

hypothesis.

What you see What you believe How different they are

<small>Source Page 32 of 62</small>

### In-class Quiz 3 (2.5% of grade)

With your classmate next to you, compute the following:

You are a financial analyst interested in ------- whether the average monthly return of your mutual fund adheres to the expected target return value of 1%. Formulate and ---- this hypothesis using the p-value approach.

You collect a sample of monthly returns over the past 12 months:

x̄= 1.3% s= 0.8% n= 12

Work with significance level of 5%.

Compute the p-value and state your decision regarding the null hypothesis.
<small>Source Page 33 of 62</small>

### Answer

- Write down the hypothesis

H0: μ= 1% H1: μ≠1%

- Significance level α= 5%

- Since n<30 and population standard deviation is unknown, we use the t-distribution.

Find the t-stat:

x̄−μ0

SE= 1.3−1

= 0.3 0.231 = 1.298

t-stat =

0.8

- Calculate p-value using the t-stat, with R software as p = 2 * pt(-abs(1.298), 11) p-

value = 0.221

- Since the p-value is bigger than the significance level (0.221 > 0.05), we cannot reject

the null hypothesis.

<small>Source Page 34 of 62</small>

01 | Hypothesis -------: Confidence Interval Approach 02 | Hypothesis -------: z/t-statistic Approach 03 | Hypothesis -------: p-value Approach 04 | Automating Hypothesis ------- 05 | ------- for Differences 06 | Statistical Errors

Hypothesis -------

07 | What α to pick?

<small>Source Page 35 of 62</small>

### Automating Hypothesis -------

One Sample t-----:

Use a function from the stats package to produce the results from all three approaches in a single table (i.e. the CI approach, z/t-stat approach, pvalue approach)

```r
# set 5 decimal places or results will be rounded options(digits = 5) stats::t.----(x, mu =
mu0, data = data)
```
where: x is column of numeric sample data mu hypothesized mean data variable name containing your dataset

Example for CVR dataset:

```r
options(digits = 5) stats::t.----(cvr$conversion, mu=0.3, data=cvr)
```

Values agree with the three manual calculations.

Note, p-value was calculated using the function pt() for t-stat, not xpnorm() for z-stat.

Open session3.Rmd

<small>Source Page 36 of 62</small>

### Hypothesis ------- Recipe

- Set up the hypothesis

```r
Claim (null hypothesis): H0: CVR = 0.3 Alternative hypothesis:  Ha: CVR  0.3 (two tail
hypothesis)
```

What you believe

- Take a sample

Sample Mean (Evidence) = 0.2 SE = 0.04

What you see

- Choose significance level, typically 5%

Corresponds to 95% confidence (approximately ± 2*SE)

- Use one of three possible methods to decide whether to reject or not reject the null

hypothesis

CVR Example, Three Methods Results:

- Confidence Intervals: claim, 0.3, was outside of CI [0.12,0.28] thus we reject H0

- z-statistic: z-stat was found to be -2.49. Since

| −2.49| > 2 we reject H0

- p-value: p-value was 0.0128, since 0.0128 < 0.05 (i.e. 1.28% < 5%) we reject H0

How different they are
<small>Source Page 37 of 62</small>

### Decision Rule Summary

We have 3 equivalent ways of ------- hypothesis. The decision taken based on one approach will agree with the rest, therefore you only need to use a single approach (recommended approach: p-value).

Approach Decision Rule Calculation

```r
Approach (1) Confidence Interval (CI built around x̄) Confidence Interval (CI built around
μ0)
```

Reject H0 if claim (μ0) is outside CI Reject H0 if evidence ( x̄) is outside CI

s

x̄ ± z

```r
n (use z, or t)*
```

s

μ0 ± z

```r
n (use z, or t)*
Approach (2) t-statistic z-statistic
```

Reject H0 if |t-stat| > critical level t Reject H0 if |z-stat| > critical level z

For α= 5% use t = qt(0.975, n-1) For α= 5% use z = qnorm(0.975)

```r
Approach (3) p-value (find probability for t-stat) Reject H0 if p< α Typical α:
```

0.01 1% , 0.05 5% , 0.10(10%)

For α= 5% use p=2*pt(-abs(tstat),n-1)

For ----: use t if n< 30, population distribution is Normal, and σ is unknown. Otherwise, use z.

But! in practice we always use t since the t-distribution converges to Standard Normal as sample size increases. For ----: for 95% confidence level (i.e. 5% critical level) use z= 1.96 or round up to z= 2.

<small>Source Page 38 of 62</small>

### Comprehension Questions

With your classmate next to you, discuss the following:
- Explain the meaning of the null hypothesis?

- Verbalize the steps involved in performing a hypothesis ----.

- In which case do we reject the null hypothesis when basing the ---- on Confidence In‐

tervals?

- In the z/t-statistic approach to hypothesis -------, what is the difference between the

terms “z-critical value” and the “z-statistic”? How is each obtained?

- In the p-value approach to hypothesis -------, how is the p-value obtained? Specify the

function which you’d need to use when working with z-statistic and the t-statistic.

<small>Source Page 39 of 62</small>

### Answers

- We hypothesize that the true population mean equals some particular value.

- Steps involved in performing a hypothesis ----:

a. State the null and alternative hypothesis.

b. Establish the significance level at which the ---- should be carried out.

c. Obtain the sample and calculate the sample mean.

d. Either: build confidence interval, obtain the z/t-statistic or calculate the p-value.

e. Make a decision on whether to reject or not reject the null hypothesis.

- When building CI around the sample mean, reject the null hypothesis if the claim is

outside the confidence interval.

- Critical z or t-value corresponding to a particular significance level, e.g. 5%, which

forms the cutoff points. Z or t-statistic is obtained from the sample.

- Obtain p-value by calculating the total probability in the tails to the left/right of the z/

t-statistic found

z-critical value: 2 * mosaic::xpnorm(-abs(z_statistic)) t-critical value: 2 * pt(-abs(t_statistic), n-1)

<small>Source Page 40 of 62</small>

01 | Hypothesis -------: Confidence Interval Approach 02 | Hypothesis -------: z/t-statistic Approach 03 | Hypothesis -------: p-value Approach 04 | Automating Hypothesis ------- 05 | ------- for Differences 06 | Statistical Errors

Hypothesis -------

07 | What α to pick?
<small>Source Page 41 of 62</small>

### Motivation

Examples of ------- for Differences

- Difference between true mean of two stocks

- Difference in true mean sales volume of two agents

- Difference in true mean salaries between different

groups of employees

The difference between two sample means can be due to a real difference between true mean parameters of the groups (significant difference) or due to the inherent randomness in the sampling process (sampling error).

When can we conclude there is a difference in true means?

Start with the theory there is no difference, then try to disprove it by finding significant evidence from data.

For 2 groups:

Group 1 Group 2

μ1, σ1 μ2, σ2

Formulate the hypothesis as:

H0: μ1 −μ2 = 0 H1: μ1 −μ2 ≠0

<small>Source Page 42 of 62</small>

### ------- for Differences: CI Approach

Build a joint confidence interval Take a random sample from each population of size n1 and n2, respectively (unequal sample sizes is ok).

Calculate sample means x̄1 and x̄2 and obtain their difference x̄1 −x̄2.

Null hypothesis: no difference between population means (μ1 = μ2) i.e. samples are drawn from 2 populations with the same mean.

Establish sampling distribution of differences in means approx. Normally distributed by CLT if n> 30 or tdistributed if group populations are Normal, standard deviations are unknown and n< 30

Joint CI Calculation Assume n is large, then by CLT we can use z-value.

The standard error is:

Replace with σ1 and σ2 if they are known.

SE x̄1 −x̄2 = s12
+ s22

n1

n2

The 95% Confidence Interval for the difference between means is:

Use z = 2 as approxim ation

( x̄1−x̄2) ± zs12

+ s22

n1

n2

Decision rule: if the joint CI does not contain 0, then reject the null, H0.

<small>Source Page 43 of 62</small>

### Hypothesis ------- Recipe

Hypothesis Setup:

Equivalent ways of writing the hypothesis, where δ= μ1 −μ2

H0: μ1 −μ2 = 0 H1: μ1 −μ2 ≠0

H0: δ= 0 H1: δ≠0

From a sample of data calculate:

- Sample statistic: δ∗ (i.e., δ∗= x̄1 −x̄2)

- Standard error: SE = s12

n1 + s22

n2

Choose a significance level, typically use = 5%

Hypothesis ----:

You can start by building two separate CI around each x̄ . If CI don’t overlap, reject H0.

If they overlap use any of the 3 methods below to run an official statistical ----:

- Joint Confidence Interval

- t-stat

- p-value
<small>Source Page 44 of 62</small>

### Equivalent Approaches

Joint Confidence Interval:

Build a joint CI as:

( x̄1−x̄2) ± zs12

+ s22

n1

n2 Decision: If CI doesn't contain 0, reject H0.

Calculate t-stat:

Obtain t-stat as:

( x̄1−x̄2) −0

t−stat =

s12

n1 +s22

n2

Decision: If |t−stat| > 2 reject H0.

p-value:

Calculate p-value as:

2*pt(-abs(t_stat), m) where

Decision: If p<0.05 reject H0.

R Software:

Obtain all three above results in a single function call:

stats::t.----()

<small>Source Page 45 of 62</small>

### ------- for Differences Mean Movie Ratings

Do movies from different genre have different population mean ratings?

Consider Biography vs. Horror movie rating CI. Difference of the 95% CI is so pronounced, that we don’t need to run a ----.

What about: Crime vs. Drama? or Action vs. Comedy? We can see an overlap of individual Confidence Intervals, therefore need to run an official t-----.
<small>Source Page 46 of 62</small>

### ------- for Differences Mean Movie Ratings

When comparing means we do not care about differences in individual values. For example, in Biography vs. Horror, there can be an individual horror movie that has a higher rating than a Bio movie. We care whether the population mean rating between groups is the same or not.

<small>Source Page 47 of 62</small>

### Action vs. Comedy

Let’s use the following information to compare mean rating of Action vs Comedy genre.

First consideration: will we work with z or t distribution?

<small>Source Page 48 of 62</small>

### Action vs. Comedy, CI Approach

Individual CI:

Is there a difference in true population mean between Action and Comedy genres? Build two CIs for mean rating using formula and check whether they overlap.

Action CI = 6.23 ± 1.96 ∗ 1.03

≈[6.16, 6.31]

Comedy CI = 6.11 ± 1.96 ∗ 1.02

≈[6.04, 6.18]

Decision: ?

Joint CI:

Build a single CI for mean difference in ratings using formula and check whether CI contains zero.

x̄1 −x̄2 ± 1.96 s1

+ s2

n1

n2

= 6.23 −6.11 ± 1.96 1.032

738 + 1.022
= 0.02, 0.22

Decision: ?

<small>Source Page 49 of 62</small>

### Action vs. Comedy, CI Approach

Individual CI:

Is there a difference in true population mean between Action and Comedy genres? Build two CIs for mean rating using formula and check whether they overlap.

Action CI = 6.23 ± 1.96 ∗ 1.03

≈[6.16, 6.31]

Comedy CI = 6.11 ± 1.96 ∗ 1.02

≈[6.04, 6.18]

Decision:

CI overlap therefore we need to build joint CI and perform an official statistical ---- for difference.

Joint CI:

Build a single CI for mean difference in ratings using formula and check whether CI contains zero.

x̄1 −x̄2 ± 1.96 s1

+ s2

n1

n2

= 6.23 −6.11 ± 1.96 1.032

738 + 1.022

= 0.02, 0.22

Decision:

CI does not contain 0, therefore we reject the null hypothesis that the two population means are the same.
<small>Source Page 50 of 62</small>

### Automating Hypothesis -------

Welch Two Sample t-----:

Use Two Sample Assuming Unequal Variances t----- (Welch Two Sample t-----) to produce the results of the three different approaches. Use the function based on if your data is in long or wide format.

Data in wide format:

options(digits = 5) stats::t.----(data$x1, data$x2, data=data) where: data$x1 group1 sample data (numeric) data$x2 group2 sample data (numeric) data variable name containing your dataset

Data in long format:

```r
options(digits = 5) stats::t.----(x ~ c, data = data) where: x  column of sample data
(numeric) c  categorical column (as factor) data  variable name containing your dataset
```

Our movies data is in the long format:

```r
action_comedy <- movies %>% filter(genre %in% c("Action", "Comedy")) %>% select(genre,
rating)
```

<small>Source Page 51 of 62</small>

### Automating Hypothesis -------

Compare Action vs Comedy using stats::t.----(): options(digits = 5) t.----(rating ~ genre, data = action_comedy)

numeric binary (factor)

Base Decision on either:

C.I. does not include 0

p-value < 0.05

t-stat > 1.96

Decision: reject H0

Open session3.Rmd
<small>Source Page 52 of 62</small>

### Pen and Paper Exercise

With your classmate next to you, discuss the following:

Two Business Schools decided to compare the average scores that their -------- achieved in the math ----. Establish if there is truly a difference in population means between the math -------- in the two different schools. Use a significance level of α= 5%. Build a joint CI. What is the conclusion?

The following sample statistics have been found:

school school_1 school_2

<small>Source Page 53 of 62</small>

### Answer

Hypothesis:

H0: μ1 −μ2 = 0 Ha: μ1 −μ2 ≠0 Assumption:

The distribution of the difference of sample means is Normally distributed by CLT.

Joint CI:

x̄1 −x̄2 ± 1.96 s1

+ s2

=

n1

n2

Since n around 500 is large, we can use z.

For = 5% we know z= 1.96.

−4.3 ± 1.96 0.1365 + 0.1313 =

−4.3 ± 1.96 ∗0.5175

= −4.3 ± 1.014 = −5.3, −3.28 Conclusion:

We reject the null hypothesis that there is no difference between the population mean performance of -------- in math between school 1 and school 2, since the CI does not contain 0.
<small>Source Page 54 of 62</small>

01 | Hypothesis -------: Confidence Interval Approach 02 | Hypothesis -------: z/t-statistic Approach 03 | Hypothesis -------: p-value Approach 04 | Automating Hypothesis ------- 05 | ------- for Differences 06 | Statistical Errors

Hypothesis -------

07 | What α to pick?

<small>Source Page 55 of 62</small>

### Types of Statistical Errors

Because of the potential for extreme sampling error, two possible errors can occur when a hypothesis is ------: Type I and Type II errors. These errors show the relationship between what actually exists (a state of nature) and the decision made based on the sample information.

<small>Source Page 56 of 62</small>

### Type I vs Type II Errors

Type I Error:

α = P(reject a true null ℎypotℎesis)

α is the probability of making a Type I Error!

H0: not pregnant H1: pregnant

False Positive: concluding something exists when it doesn’t

Type II Error:

β = P(fail to reject a false null ℎypotℎesis)

H0: not pregnant H1: pregnant

False Negative: concluding there is no effect when there is; i.e. missing a true positive

<small>Source Page 57 of 62</small>

### Significance Level: Hypothesis -------

What is the effect of the significance level on hypothesis -------?

95% Confidence: (α= 5%) z-critical value 1.96

Say you had a t-statistic = 1.876
90% Confidence: (α= 10%) z-critical value 1.64

t-stat = 1.876 t-stat = 1.876

95%

2.5% 2.5% 5% 5%

-1. 96 +1. 96 -1. 64 +1. 64

|1.876| < 1.96, therefore we would not reject H0.

|1.876| > 1.64, therefore we would reject H0.

A smaller Confidence Level (larger α) leads to a more precise but less confident result (higher risk, 10%, of rejecting a true null hypothesis).

90%

<small>Source Page 58 of 62</small>

### Significance Level: Confidence Interval

What is the effect of the significance level on Confidence Interval formation?

95% CI:

x̄ ± 1. 96∗s

n= 18.4 ± 1.96 ∗4.2

50 = [17.236, 19.564]

90% CI:

s

4.2

x̄ ± 1. 64∗

n= 18.4 ± 1.64 ∗

50 = [17.426, 19.374]

Smaller α (e.g. 5%) Wider CI (less precise)

Larger α (e.g. 10%) Narrower CI (more precise)

17.2 19.6

17.4 19.3

Less likely to make Type I error (more confident)

More likely to make Type II error

More likely to make Type I error (less confident)
Less likely to make Type II error

<small>Source Page 59 of 62</small>

### Industry Conventions for α

Conventions in Your Industry:

Psychology / education α= 0.05 Good balance of avoiding false positives and detecting genuine effects.

Physics / chemistry α= 0.001 Stricter threshold ensures extremely robust findings, i.e. assume your idea is not correct and let the evidence reject this null.

Marketing / finance α= 0.1 Typically, data has inherent noise. Larger α means we will reject the null hypothesis more often thus giving us a greater chance of detecting potential trends among noise. Missing a true positive (Type II error) could mean missing an important business opportunity.

Examples:

H0: μnew teacℎing metℎod−μold teacℎing metℎod= 0 H1: μnew teacℎing metℎod−μold teacℎing metℎod≠0

H0: μ= μtℎere is no life on tℎe moon H1: μ≠μtℎere is life on tℎe moon

H0: μsales after advertising−μsales before advertising= 0 H1: μsales after advertising−μsales before advertising≠0

<small>Source Page 60 of 62</small>

### False Positives vs False Negatives

https://www.theguardian.com/society/article/2024/jun/23/dwp-algorithm-wronglyflags-200000-people-possible-fraud-error https://www.nytimes.com/interactive/2024/07/18/ technology/spain-domestic-violence-viogen-algorithm.html

<small>Source Page 61 of 62</small>

### What α Shall I Pick?

General Convention:

Factors that influence choice of significance level:

Significance Level (α) is the probability of rejecting a null hypothesis when it is true.

Sample Size and Variance
- More Stable Results happen when: you have large sample size and low variance Use a

lower significance level to α= 0.01 to increase the confidence in your results, i.e. setting stricter threshold for declaring significance (reject less often)

Standard choice of alpha is 5% (α = 0.05) is commonly used across many fields.

There are some factors that may influence your choice of the significance level.

- More Unstable Results happen when: you have small sample size and high variance

Use a higher significance level to 10% (α= 0.1) i.e. more willing to detect significance (reject more often)

<small>Source Page 62 of 62</small>

### Session Summary

We covered:

Hypothesis ------- ------- for Difference

Readings:

Modern Dives chapter 9

Optional/ Extra practice: workshop3.Rmd

Workshop Questions:

Look at the workshop questions in advance.

Attend optional workshop to go over the solutions.


[↑ Back to the source list](#source-documents)

---

<a name="source-3"></a>

## session3.Rmd

<small>File type: RMD · Reader pages 220–223 · [View source PDF](PDF%20Slides.pdf#page=220)</small>

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
library(tidyverse)
library(tidyquant)
library(dplyr)
library(ggplot2)
```

### Hypothesis -------

Conversion Rate Exercise

```r
cvr <- read_csv('CVR.csv')
mu0 <- 0.3 # this is the null hypothesis
stats <- cvr %>%
summarise(mu0 = 0.3,
xbar = mean(conversion),
s = sd(conversion),
n = n(),
# get z-critical value
z_critical = qnorm(0.975), # 95% confidence level
SE = s / sqrt(n), # Standard Error
margin_of_error = z_critical * SE,
CI_low = mu0 - margin_of_error,
CI_high = mu0 + margin_of_error)
print(stats)
```

Hypothesis ------- CVR, three approaches:

### CONFIDENCE INTERVAL APPROACH (A)

Building confidence interval around sample mean.

```r
upper_CI <- stats$xbar + stats$z_critical * (stats$s/sqrt(stats$n)) # 0.28
lower_CI <- stats$xbar - stats$z_critical * (stats$s/sqrt(stats$n)) # 0.12
# Since mu0 = 0.30 is outside the interval we reject the null hypothesis
```
### CONFIDENCE INTERVAL APPROACH (B)

Building confidence interval around claimed mean.

```r
upper_CI <- mu0 + stats$z_critical * (stats$s/sqrt(stats$n)) # 0.38
lower_CI <- mu0 - stats$z_critical * (stats$s/sqrt(stats$n)) # 0.22
# Since xbar = 0.20 is outside the interval we reject the null hypothesis
```

### Z-STAT APPROACH

```r
z_stat <- (stats$xbar - mu0) / stats$SE  # -2.487 (approx -2.5)
reject_t <- abs(z_stat) > stats$z_critical # TRUE
# Since z-stat in abs value is greater than critical level, we reject the null hypothesis
```

### P-VALUE APPROACH

```r
p_value <- 2 * pnorm(-abs(z_stat)) # 0.013
reject_p <- p_value < 0.05  # TRUE
# Since p-value is less than 0.05 we reject the null hypothesis
```

### AUTOMATE HYPOTHESIS ------- WITH T.----()

In practice we use the t-distribution.

```r
options(digits = 5)
t.----(cvr$conversion, mu = 0.3, data = cvr)
```

### Reproducing Plots from the Slides

Plot with coloured 95% of the density.

```r
# Generate a sequence of x values for the standard normal distribution
data <- data.frame(x = seq(-4, 4, by = 0.01))
# Calculate the density of the standard normal distribution
data <- data %>%
mutate(y = dnorm(x),
# Identify whether each point falls within the 95% interval
in_interval = ifelse(x >= -1.96 & x <= 1.96, TRUE, FALSE))
# Plot the standard normal distribution
ggplot(data, aes(x = x, y = y)) +
geom_line(color = "black") +  # Plot the normal distribution line
geom_ribbon(aes(ymin = 0, ymax = ifelse(in_interval, y, NA)), fill = "green", alpha = 0.5) +
# Shade the 95% interval
labs(title = "Standard Normal Distribution with 95% Confidence Interval",
x = "Z-score",
y = "Density") +
theme_minimal() +
theme(
axis.text.x = element_text(size = 16),  # Set x-axis tick font size
axis.text.y = element_text(size = 16),  # Set y-axis tick font size
axis.title.x = element_text(size = 18), # Set x-axis label font size
axis.title.y = element_text(size = 18), # Set y-axis label font size
```
```r
plot.title = element_text(size = 20)  # Set plot title font size
)
```

Plot with colored 5% of the density, using 2.5% in each tail.

```r
# Generate a sequence of x values for the standard normal distribution
data <- data.frame(x = seq(-4, 4, by = 0.01))
# Calculate the density of the standard normal distribution
data <- data %>%
mutate(y = dnorm(x),
# Identify whether each point falls within the lower and upper 2.5% tails
in_tail = ifelse(x <= -1.96 | x >= 1.96, TRUE, FALSE))
# Plot the standard normal distribution
ggplot(data, aes(x = x, y = y)) +
geom_line(color = "black") +  # Plot the normal distribution line
geom_ribbon(aes(ymin = 0, ymax = ifelse(in_tail, y, NA)), fill = "red", alpha = 0.5) + #
Shade the 2.5% tails in red
labs(title = "Standard Normal Distribution with 2.5% Tails Shaded in Red",
x = "Z-score",
y = "Density") +
theme_minimal() +
theme(
axis.text.x = element_text(size = 16),  # Set x-axis tick font size
axis.text.y = element_text(size = 16),  # Set y-axis tick font size
axis.title.x = element_text(size = 18), # Set x-axis label font size
axis.title.y = element_text(size = 18), # Set y-axis label font size
plot.title = element_text(size = 20)  # Set plot title font size
)
```

### Movie Ratings, ------- For Differences

```r
movies <- read_csv('movies.csv')
glimpse(movies)
# Choose Crime vs Drama; Action vs Comedy; and Bio vs Horror genres
movies <- movies %>%
filter (genre %in% c("Crime", "Drama", "Action", "Comedy", "Biography", "Horror")) %>%
mutate( comparison =
case_when(
genre == "Action" ~ 1,
genre == "Comedy" ~ 1,
genre == "Drama" ~ 2,
genre == "Crime" ~ 2,
genre == "Biography" ~ 3,
genre == "Horror" ~ 3),
comparison_name =
case_when(
comparison == 1 ~ "Action vs. Comedy",
comparison == 2 ~ "Crime vs. Drama",
comparison == 3 ~ "Biography vs. Horror")
)
movies %>%
ggplot(aes(x = rating)) +
```
```r
geom_density(aes(fill=genre), alpha = 0.25) +
facet_grid(rows = vars(comparison_name)) +
theme_bw()+
# theme(legend.position = "none") +
labs(title = "Differences of IMDB ratings among genres",
x = "IMDB Rating",
y = " ") +
NULL
# Confidence Interval (CI) using the formula mean +- t_critical * SE
genre_formula_ci <- movies %>%
filter (genre %in% c("Crime", "Drama", "Action", "Comedy")) %>%
group_by(genre) %>%
summarise(mean_rating = mean(rating),
sd_rating = sd(rating),
count = n(),
# get t-critical value with (n-1) degrees of freedom
t_critical = qt(0.975, count-1),
se_rating = sd(rating) / sqrt(count),
margin_of_error = t_critical * se_rating,
rating_low = mean_rating - margin_of_error,
rating_high = mean_rating + margin_of_error) %>%
arrange(desc(mean_rating))
print(genre_formula_ci)
# Visualise CIs for 4 genres.
ggplot(genre_formula_ci, aes(x = reorder(genre, mean_rating), y = mean_rating, colour =
genre)) +
geom_point() +
geom_errorbar(width = 0.2, aes(ymin = rating_low, ymax = rating_high)) +
labs(x =" ",
y = "Mean IMDB Rating",
title = "Which film genres have the highest mean IMDB ratings?") +
theme_bw() +
coord_flip() +
theme(legend.position = "none") +
NULL
```

### Hypothesis ------- using t.----()

Let's ---- the hypothesis that Action and Comedy films have different mean ratings, based on the null hypothesis that there's no difference between the genres

```r
# Choose Action and Comedy genres
action_comedy <- movies %>%
filter(genre %in% c("Action", "Comedy")) %>% # filter rows
select(genre, rating)  # select columns (we do not need all other variables)
# ------------------ t-stat approach
options(digits=5)
t.----(rating ~ genre, data = action_comedy)
```


[↑ Back to the source list](#source-documents)

---

<a name="source-4"></a>

## CVR.csv

<small>File type: CSV · Reader pages 224–224 · [View source PDF](PDF%20Slides.pdf#page=224)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

> Data preview (up to six records and twelve columns); the full CSV remains in the original files.

customer_ID

conversion

1

0

2

0

3

1

4

0

5

0

6

0

</details>


[↑ Back to the source list](#source-documents)

---

<a name="source-5"></a>

## movies.csv

<small>File type: CSV · Reader pages 225–226 · [View source PDF](PDF%20Slides.pdf#page=225)</small>

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

