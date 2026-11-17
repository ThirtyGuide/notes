# Lecture 1

**Exploratory data analysis and tidy data**

[← All chapters](README.md) · [Original PDF](PDF%20Slides.pdf#page=13)

## Overview

- Types and structures of data; atomic types, tibbles, vectors, matrices and feature matrices.
- Data cleaning: missing values, duplicates, types and variable names.
- Tidy data and manipulation with dplyr verbs, joins, pipes and visualisation with ggplot2.

## Source documents

1. [session1_slides_pre_class.pdf](#source-1) — PDF, reader page 14
2. [session1_slides_post_class.pdf](#source-2) — PDF, reader page 36
3. [session1.Rmd](#source-3) — RMD, reader page 60
4. [session1_solutions.Rmd](#source-4) — RMD, reader page 75
5. [dji_index.csv](#source-5) — CSV, reader page 79
6. [dji_index_1.csv](#source-6) — CSV, reader page 81
7. [dji_index_2.csv](#source-7) — CSV, reader page 82
8. [dji_index_3.csv](#source-8) — CSV, reader page 83
9. [dji_index_missing_and_duplicates.csv](#source-9) — CSV, reader page 84
10. [dji_stocks.csv](#source-10) — CSV, reader page 86
11. [dji_stocks_unclean.csv](#source-11) — CSV, reader page 88
12. [snp_index.csv](#source-12) — CSV, reader page 90
13. [sse_index.csv](#source-13) — CSV, reader page 91

---

<a name="source-1"></a>

## session1_slides_pre_class.pdf

<small>File type: PDF · Reader pages 14–35 · [View source PDF](PDF%20Slides.pdf#page=14)</small>

<small>Source Page 1 of 63</small>

### Lecture 1

Dr Helen Wang |

<small>Source Page 2 of 63</small>

### How do we predict the winner?

<small>Source Page 3 of 63</small>

### Magic power…

<small>Source Page 4 of 63</small>

### Crowdsourced wisdom…

<small>Source Page 5 of 63</small>

### Data-driven prediction…

Opta Power Rankings, Historical results, Recent results, Strength of opposition, Betting-market odds, World Cup fixtures/draw, …

<small>Source Page 6 of 63</small>

### What You’ll Learn

What do we mean by data?

o Uncertainty in data: Noise vs Signal o Types of data: Survey vs. Experimental vs. Observational

How do we use data?
o Quant Framework 1: Hypothesis -------

How do businesses like Uber/Google/Facebook conduct data-driven experiments?

o Quant Framework 2: Linear regression

How do businesses design and evaluate predictive tools?

How do we drive business impact?

o “Tough questions”, caveats, best practices

<small>Source Page 7 of 63</small>

### • About Myself

- Academic Background BA: Finance (FDU) PhD: Business Economics (UM)

Research casual inference, business analytics, NLP, ML, GenAI…

- Industry Experience Economic Consulting Blockchain (Stable Coin) Quantitative Re‐

searcher

EdTech

<small>Source Page 8 of 63</small>

### Weeks 1-5 Outline

Week 01 | Exploratory Data Analysis

Week 02 | Statistics Foundation

Week 03 | Hypothesis -------

Week 04 | Regression, Part I

Week 05 | Regression, Part II

<small>Source Page 9 of 63</small>

### Course Logistics

- Lecture slides, data, and code files are on Canvas.

- Textbook ModernDive - https://moderndive.com/v2/

- No use of smart phones in class, only use Laptops for course purposes.

- Use of GenAI is allowed for assignments but NOT for the final ----. Late submission will

NOT be accepted.
- ----------: two group projects (20% *2), final ---- (50%), In-class quizzes (2.5% * 4, the

highest four grades are counted).

<small>Source Page 10 of 63</small>

### Support Available To You

Teaching Assistant Lead (Optional) Workshops

- Led by dedicated teaching assistants

- Attendance not required but highly recommended

- Pen & paper, as well as R programming-based practice questions on the topics

covered that week

- Similar questions may appear in assignments and final ----.

Office Hours

- There will be open Q&A time during each workshop

- Open office hours format – email our dedicated list of teaching assistants and

--------- at any time

- My email:

<small>Source Page 11 of 63</small>

### Weeks 1-5 Learning Outcomes

Programming

in R

Use R and RStudio effectively for data analysis

Communicate quantitative analysis and recommendations using RMarkdown

Learn to extract, clean and manipulate data using R

Use simple unified R framework, called Tidyverse

Data Analytics

Stats

Learn to explore datasets to gain insights prior to analysis

Faced with samples of different sizes, be able to quantify accuracy of sample evidence

---- hypothesis about population parameters

Build regression models to predict future outcomes
<small>Source Page 12 of 63</small>

### Reason Coding Excel

Visualization Far better graphics than Excel (e.g., ggplot2 library) Basic tools

Price Free £59.99 / year

Ease of Use Easy to learn

Reusable: import existing code and apply it to new tasks

Transparent: code analysis is performed step by step and is contained in a single file

Statistical Analysis

Designed for data analysis, statistics and econometrics.

Contains ~17000 statistical libraries.

Reporting Produce HTML / pdf reports by knitting the Rmd file (markdown text, latex formulas, imbedded videos, code and its resulting outputs -> all contained in one final file)

Is point and click (+ VBA)

Need to pay for additional plugins No facility

<small>Source Page 13 of 63</small>

### Descriptive vs Inferential Statistics

Descriptive Statistics

- Collect

- Organize

- Summarize

- Display

- Analyze

Typical Questions:

- What is the average return per year of a stock?

- Are stock returns Normally

distributed?

Inferential Statistics

- Predict and forecast values of population parameters

- ---- hypothesis and draw conclusions about values of population parameters
- Make decisions

Typical Questions:

- Is restaurant revenue significant lower during tube strike compared to usual?

- Do companies with female CEOs provide better family-friendly benefits?

<small>Source Page 14 of 63</small>

### Why ----- Data Analytics?

Data empowers decision-making in uncertain situations – financial analysts who harness the power of data in the face of uncertainty make better decisions.

outcomei= modeli+ errori

yi

xi Systematic

ei Unsystematic

Part

Part

Statistics helps understand variability and make an inference – decisions should be grounded in statistical evidence. “Can trading signal extracted from a dataset be attributed to chance or is there a pattern?”

Model: explains how much of the overall variance in the data can be explained by the model vs. the noise i.e., systematic (model variance) vs. unsystematic (random variance).

<small>Source Page 15 of 63</small>

### Analytics in the era of GenAI

<small>Source Page 16 of 63</small>

<small>Source Page 17 of 63</small>

### ChatGPT Analysis
<small>Source Page 18 of 63</small>

01 | Understanding Data Structure 02 | Data Cleaning 03 | Data Wrangling: Tidy Data 04 | Data Wrangling: Manipulate Data 05 | Visualization

Exploratory Data Analysis

<small>Source Page 19 of 63</small>

01 | Understanding Data Structure 02 | Data Cleaning 03 | Data Wrangling: Tidy Data 04 | Data Wrangling: Manipulate Data 05 | Visualization

Exploratory Data Analysis

<small>Source Page 20 of 63</small>

### Reading in Data

To read in csv data use the tidyverse package’s function called read_csv()

```r
library(tidyverse) dji_index_original <- read_csv(‘dji_index.csv')
```

If you see an error message:

- Ensure that your .R or .Rmd programming file (where you write your code) and your

csv data are located in the same folder

- Ensure to point the RStudio’s current working directory to the locaton of the file

Set Current Working Directory

To set the cwd to the location of your .R or .Rmd file:

- Open the file in RStudio

- Right click on its name at the top

- Click on ‘Set Working

Directory’

Open session1.Rmd

<small>Source Page 21 of 63</small>

### Understanding Data Structure

Answer Three Questions
- Data Type: numerical, categorical, date etc. This is essential for selecting suitable

analytical techniques.

- Data Dimensionality: how many different variables (features) are available for analys‐

is?

- Data Summary: find the basic statistical information, what are the min, max, mean

values?

We will work with the Dow Jones 30 Index

```r
library(tidyverse) dji_index_original <- read_csv(‘dji_index.csv')
```

Open session1.Rmd

<small>Source Page 22 of 63</small>

### Basic Data Types in R

Every programming language comes with fundamental, pre-built objects that the programmer manipulates on a day-to-day basis.

Atomic Class Example Definition

Character "abc" 'abc' Data type used to store sequences of characters (we call it a ‘string’)

Double 2.321

Inf NaN

Real number (double precision) In R, all numbers are converted to double by default. So, 3 in R is treated as 3.0 Inf – infinity (i.e., result of 1/0) NaN – not a number (i.e., result of 0/0); can also be thought of as a missing value

Numeric

Integer 3L as.integer(3)

To create an integer, use L suffix (stands for Long integer, single precision)

Logical TRUE FALSE NA

Boolean logic, a variable denoting truth value: TRUE FALSE 1 is treated as TRUE, 0 is treated as FALSE NA – not available; is a filler for missing values

<small>Source Page 23 of 63</small>

### Data Dimensionality in R

In R (and most other coding languages), dimensionality is the number of indices needed to locate a data point.
Vector – 1-D (one row of an excel data)

Matrix – 2-D (an excel sheet)

Array – 3-D (stacked excel sheets)

DataFrame – 2-D array that can hold different data types down each column

Tibble – 2-D array with less functionality than a dataframe to limit user mistakes. Tibble is the unifying feature of tidyverse.

rows columns depth

row rows columns

Vector Matrix Array

"a" True

Tibble with 2 rows and 3 columns

"d"

False

<small>Source Page 24 of 63</small>

### Data Dimensionality in Stats

Indpendent variables data is usually structured as rows (observations) and columns (features / variables), overall called a Feature Matrix.

A feature matrix X∈ℝN×D means there are N observations and D features, with elements xi,j referenced by i for rows and j for columns:

D columns, j changes x1,1 x1,2 x1,3 … x2,1 x2,2 x2,3 … x3,1 x3,2 x3,3 … ⋮ ⋮ ⋮

N rows, i changes

Example: assume a feature matrix X∈ℝ1000×3, with 3 features (columns) x1, x2, x3.

3 columns

x1,1 x1,2 x1,3 x2,1 x2,2 x2,3 ⋮ x1000,1

1000

⋮ x1000,2

⋮ x1000,3

rows

A single observation forms a row of the data.

So, the first observation is a data point x1 = x1,1, x1,2, x1,3
T that resides in a multidimensional space.

dimensionality of any data point in feature matrix X, such as x1, is D= 3.

<small>Source Page 25 of 63</small>

01 | Understanding Data Structure 02 | Data Cleaning 03 | Data Wrangling: Tidy Data 04 | Data Wrangling: Manipulate Data 05 | Visualization

Exploratory Data Analysis

<small>Source Page 26 of 63</small>

### “80% of data analysis is spent on the process of cleaning and preparing

**the data.”**

<small>Source Page 27 of 63</small>

### Pipe Operator %>%

3 equivalent ways to code the same thing:

Why use the pipe operator?

```r
z <- 15.99 %>% round() %>% sqrt() %>% print()
```

- Enhanced Workflow: the pipe connects multiple dplyr functions (‘verb’ / actions)

together into a sequence of operations (‘pipeline’)

- Consistency Across the Tidyverse: consistent syntax

```r
x <- round(15.99) y <- sqrt(x) z <- print(y)
```

across dplyr, tidyr and ggplot2 libraries

- Readability: the pipe takes output of one function and feeds it as input to the next

function, making it easier to understand code

```r
z <- print(sqrt(round(15.99)))
```
<small>Source Page 28 of 63</small>

### Cleaning Data

Stages of cleaning data:

- Clean Column Headers: convert all names to lower case letters and separate spaces

with an underscore

- Convert Date from String to Date Format:

timeseries data should be in a ‘Date’ format

- Convert Categorical Variables to Factor / Numeric Format: instead of using strings for

categorical variables it is best to store them as numbers in R’s memory

- Remove Duplicate Rows: drop

duplicates

- Fill in Missing Data: either delete rows if they are missing any data, or forward fill the

data from the last available data until the next

Open session1.Rmd

<small>Source Page 29 of 63</small>

01 | Understanding Data Structure 02 | Data Cleaning 03 | Data Wrangling: Tidy Data 04 | Data Wrangling: Manipulate Data 05 | Visualization

Exploratory Data Analysis

<small>Source Page 30 of 63</small>

### “Happy families are all alike; every unhappy family is unhappy in its

**own way.”**

― Leo Tolstoy

<small>Source Page 31 of 63</small>

### Tidy Data Standard

Untidy

Tidy Data is a standardized way to structure datasets to facilitate analysis. Tidy tools and datasets help make data analysis easier, allowing you to focus on the problem, not on logistics of cleaning data. Four rules to Tidy Data:

Tidy
1.

Each variable forms a column 2.

Each observation forms a row 3.

Each type of observational unit forms a table.

4.

Each value has its own cell

More about Tidy Data: https://vita.had.co.nz/papers/tidy-data.pdf

More about Tidy Data: https://vita.had.co.nz/papers/tidy-data.pdf

<small>Source Page 32 of 63</small>

### From Untidy to Tidy: Wide -> Long

```r
library(tidyr)  # note tidyr is already loaded as part of library(tidyverse)
dji_index_tidy <- dji_index %>%
pivot_longer(cols = open:ret, names_to = "measurement", values_to = "value")
```

Wide format: column headers are values

Long format: each variable has its own column

<small>Source Page 33 of 63</small>

### Make Impact with Data Analytics

<small>Source Page 34 of 63</small>

<small>Source Page 35 of 63</small>
<small>Source Page 36 of 63</small>

### In May 2024, Canvas released an update, allowing graders to randomize

### -------- at one click.

<small>Source Page 37 of 63</small>

### Pen and Paper Exercise

Is the ------- data in a tidy format? Together with your neighbour sketch out on a piece of paper how this data should look like in a tidy format. What line of code is needed to tidy the data?

-------_id final_---- midterm group_project

2457625

1758293

1622247

<small>Source Page 38 of 63</small>

### From Untidy to Tidy: Separate

```r
dji_split <- dji_table3 %>%
separate(`high/low`, into = c("high", "low") , sep = '/', convert=TRUE) # do the same for
open/adj_close
dji_split_tidy <- dji_split %>% pivot_longer(cols = volume:adj_close, names_to =
"measurement", values_to = "value")
```

Wide format: untidy format and columns are ratios

Long format: each variable has its own column

<small>Source Page 39 of 63</small>

### Untidy vs. Tidy Data

Main ways in which data can be untidy:

- Column headers are values and not variable names

- A single observation unit is stored in multiple tables

- Multiple values are stored in one column
- Variables are stored in both rows and columns

- Multiple types of observational units are stored in

one table

Data is tidy when:

- Data set is in ONE table

- Each column is a variable

- Each observation has its own row

- Each value has its own cell

For programming examples see “R For Data Science” book, Chapter 12 ‘Tidy Data’.

Open session1.Rmd

<small>Source Page 40 of 63</small>

### Practice Question 1

You now have the DJI Constituent Stock data which is untidy. Your task is to convert it to a tidy format.

LAB 1 QUESTION 1

<small>Source Page 41 of 63</small>

01 | Understanding Data Structure 02 | Data Cleaning 03 | Data Wrangling: Tidy Data 04 | Data Wrangling: Manipulate Data 05 | Visualization

Exploratory Data Analysis

<small>Source Page 42 of 63</small>

### “If you want to have a better performance than the crowd, you must do

**things differently from the crowd.”**

― John Templeton

<small>Source Page 43 of 63</small>

### Grammar Manipulation

DPLYR Package:
- Provides grammar manipulation which is a consistent set of verbs used to solve

common data manipulation tasks

- Verbs are highly optimised through execution in C++ making them fast

- Used for problems with extracting rows and columns of interest as well as re-ordering

and collapsing tibbles

Key Features:

- Requirement: data typically should be in a

tidy format

- Data Storage: data input and data output to and from dplyr functions is always a

tibble

- Operator: %>% pipe

- Key Verbs: select, filter, arrange, rename, mutate, summarise, group_by

<small>Source Page 44 of 63</small>

### Verbs

Verbs Meaning

Atomic Class

Purpose

```r
select() Select columns of interest filter() Select rows of interest arrange() Reorder rows
in ascending/descending order based on a column
rename() Raname columns mutate() Compute transforms on columns
```

Perform exploratory analysis

```r
summarise( )
group_by() Group data by categories within a variable of interest
```

How Verbs Work All verbs work similarly:

- First argument is a dataset

- Rest describe what to do with the tibble

- Result is a new tibble

Example with piping operator:
```r
r_mu_pipe <- dji_index_original %>% mutate(ret = ( `Adj Close` / lag(`Adj Close`) - 1 ) *
100) %>% filter(!is.na(ret)) %>% filter(ret > 0) %>% summarise(r_mu = mean(ret))
```

Example without piping operator:

Open session1.Rmd

<small>Source Page 45 of 63</small>

### Verb: Select

```r
select() pick columns (variables) directly by the names
```

Key Features:

- No need for `` (use adj_close not "adj_close")

- If the name is not standard such as containing a space, use `` (e.g. instead of Adj

Close use `Adj Close`)

Example, select two columns:

```r
dji_ex1 <- dji_index %>% select(date, day_of_week)
```

Example, select all columns between given columns:

```r
dji_ex2 <- dji_index %>% select(open:low)
```

Example, select all but one columns:

```r
dji_ex3 <- dji_index %>% select(-ret)
```

<small>Source Page 46 of 63</small>

### Verb: Filter

```r
filter() pick rows (observations) by their values using logical conditions
```

Key Features:

- Logical condition (e.g. ret > 0) used to pick rows of interest

- Only rows where condition is TRUE are picked

Example, filter positive returns
```r
dji_ex4 <- dji_index %>% filter(ret > 0)
```

Example, filter positive returns for large volume:

```r
dji_ex6 <- dji_index %>% filter(ret > 0, volume > 4e8)
```

Example, filter Tuesdays for 2015 onwards:

```r
dji_ex8 <- dji_index %>% filter(day_of_week == 2,
```

date >= as.Date("2015-01-06"))

Open session1.Rmd

<small>Source Page 47 of 63</small>

### Verb: Arrange

```r
arrange() reorders rows according to one of variable names while preserving order of
columns.
```

Key Features:

- Specify the column by which the data should be rearranged

- Result is always in ascending order by default

- Use desc() for descending order

Example, rearrange by column returns, to see smallest returns first:

```r
dji_ex9 <- dji_index %>% arrange(ret)
```

Example, rearrange by column returns, to see largest returns first:

```r
dji_ex10 <- dji_index %>% arrange(desc(ret))
```

<small>Source Page 48 of 63</small>

### Verb: Rename

```r
rename() rename columns.
```

Example, rename `Day Of Week` to day_of_week:
```r
dji_ex11 <- dji_index_original %>% rename(day_of_week = `Day Of Week`)
```

Example, rename `Day Of Week` to day_of_week and `Adj Close` to adj_close

Key Features:

- Can rename one or more columns

- New name is to be on the left

- Old name on the right

```r
dji_ex12 <- dji_index_original %>% rename(day_of_week = `Day Of Week`,
```

adj_close = `Adj Close`)

<small>Source Page 49 of 63</small>

### Verb: Mutate

```r
mutate() compute transformations on columns: create new columns using existing columns.
```

Key Features:

- Automatically adds new column to existing tibble

- To drop all non-transformed variables use

```r
transmute()
```

Example, perform feature engineering i.e. create a new feature (variable) using information from an existing feature. For example, create a 50-day moving average:

```r
dji_ex13 <- dji_index %>% mutate(ma50 = rollmean(adj_close, k = 50, fill = NA, align =
"right"))
```

- fill = NA fills the first 49 rows with missing values

- align = "right" aligns rolling mean with the last day of the window (i.e. records the MA

result into last day of the window)

<small>Source Page 50 of 63</small>

### Verb: Summarise

```r
summarise() generate summary statistics for variables of interest.
```
Key Features:

- Collapses each column to a single value

- Most useful together with verb group_by() as this allows to observe summary statistic

per each group

Example, find mean return of DJI:

```r
dji_ex14 <- dji_index %>% summarise(r_mu = mean(ret)) >>> 0.04246185
```

If we group the data by year first, we can obtain the mean each year (see next verb).

Open session1.Rmd Run through line 367 to 514

<small>Source Page 51 of 63</small>

### Practice Question 2

You are working with the DJI Constituent Stock data which is now tidy.

LAB 1 QUESTION 2

<small>Source Page 52 of 63</small>

### Verb: Group By

```r
group_by() group data into categories within a given variable.
```

Key Features:

- Does not change how data looks

- Grouping changes how data acts with other verbs

- Application of verbs on the resulting object will

be performed by group

Example, group by ’a’ and find mean of ‘b’:

```r
ex15 <- data %>% group_by(a) %>% summarise(mu_b = mean(b))
```

Example, find mean return of DJI per year:

```r
ex16 <- dji_index %>% mutate(year = year(date)) %>% group_by(year) %>% summarise(mu_r =
mean(ret))
```
<small>Source Page 53 of 63</small>

### Verb: Join

```r
xxx_join() join tibbles based on matching columns.
```

tb1 tb2

tb1 tb2 tb1 tb2

tb1 tb2

full join

inner join

left join

right join

Key Features:

- First 2 arguments are tibbles to be joined

- Results is always a new tibble

- Argument by specifies which column should be used to match the observations in 2

tables

Full join keeps all data from both tables (i.e. all rows)

```r
dji_joined_full <- full_join(dji_table1, dji_table2, by = 'date')
```

Inner join keeps only data for those dates that match (i.e. only matching rows).

Left join keeps all rows from table 1 and only matching rows from table 2.

Right join keeps all rows from table 2 and only matching rows from table 2.

<small>Source Page 54 of 63</small>

### In-class Quiz 1

Dataframe A Dataframe B

------- ID Name

Alice

Bob

Carol

Which join operation would generate the displayed output?
A.

Inner join B.

Full join

C. Left join

D. Right join

------- ID Age

Output:

ID Name Age

Bob

Carol

NA

<small>Source Page 55 of 63</small>

### Practice Question 3

You are working with the DJI Constituent Stock data which is now tidy.

LAB 1 QUESTION 3

<small>Source Page 56 of 63</small>

01 | Understanding Data Structure 02 | Data Cleaning 03 | Data Wrangling: Tidy Data 04 | Data Wrangling: Manipulate Data 05 | Visualization

Exploratory Data Analysis

<small>Source Page 57 of 63</small>

### “The world cannot be understood without numbers. But the world

**cannot be understood with numbers alone.”**

A person touching a graph with numbers AI-generated content may be incorrect.

― Hans Rosling
<small>Source Page 58 of 63</small>

### Always Plot Your Data

Anscombe’s quartet is a dataframe with 4 datasets, each with n = 11 datapoints, and all datasets have the same mean and standard deviation for both x and y.

Would you expect to have any differences among the data in the 4 datasets? After all, they all have the same mean, sd, and cor(x, y).

<small>Source Page 59 of 63</small>

### Always Plot Your Data

Even though descriptive statistics are identical, data has different distributions and are very different when plotted.

<small>Source Page 60 of 63</small>

### Data Visualization: Density

Example: Density of standardized DJI returns

Example: Density of standardized DJI returns faceted by year

<small>Source Page 61 of 63</small>

### Data Visualization: Box Plot

Example: Box Plot of DJI returns

<small>Source Page 62 of 63</small>

### Data Visualization with ggplot2

ggplot2 produces statistical graphs using grammar of graphics: components that can be put together.

All plots are composed of:

- Data – data stored in a tibble in a tidy format

- Aesthetic mapping – specify x and y variables

- Layers – made of ▪geoms (geometric objects) – represent objects visible on the plot

(points / lines) ▪stats (statistical transformations) – summarise data by creating a linear model, histogram binning etc
- Faceting – break data into subsets

- Theme – font size, background colour

- Scales – colour, size, shape, legend, axes

Typical Commands

- aes() map a variable to x, map a variable to y

- labs() label axes and title

- geom_point() data as dots

- geom_line() data as line

- geom_historgram() data as histogram

- geom_density() data as density

Open session1.Rmd

<small>Source Page 63 of 63</small>

### Session Summary

We covered:

Exploratory Data Analysis using R

Readings:

Modern Dives chapters 1-4

Optional/ Extra practice: workshop1.Rmd

Workshop 1:

Try the practice questions in session1.Rmd.

Look at the workshop questions in advance.

Attend optional workshop to go over the solutions and extra exercises.


[↑ Back to the source list](#source-documents)

---

<a name="source-2"></a>

## session1_slides_post_class.pdf

<small>File type: PDF · Reader pages 36–59 · [View source PDF](PDF%20Slides.pdf#page=36)</small>

<small>Source Page 1 of 65</small>

### Lecture 1

Dr Helen Wang |

<small>Source Page 2 of 65</small>

### How do we predict the winner?

<small>Source Page 3 of 65</small>

### Magic power…

<small>Source Page 4 of 65</small>

### Crowdsourced wisdom…

<small>Source Page 5 of 65</small>

### Data-driven prediction…

Opta Power Rankings, Historical results, Recent results, Strength of opposition, Betting-market odds, World Cup fixtures/draw, …

<small>Source Page 6 of 65</small>

### What You’ll Learn

What do we mean by data?

o Uncertainty in data: Noise vs Signal o Types of data: Survey vs. Experimental vs. Observational

How do we use data?
o Quant Framework 1: Hypothesis -------

How do businesses like Uber/Google/Facebook conduct data-driven experiments?

o Quant Framework 2: Linear regression

How do businesses design and evaluate predictive tools?

How do we drive business impact?

o “Tough questions”, caveats, best practices

<small>Source Page 7 of 65</small>

### • About Myself

- Academic Background BA: Finance (FDU) PhD: Business Economics (UM)

Research casual inference, business analytics, NLP, ML, GenAI…

- Industry Experience Economic Consulting Blockchain (Stable Coin) Quantitative Re‐

searcher

EdTech

<small>Source Page 8 of 65</small>

### Weeks 1-5 Outline

Week 01 | Exploratory Data Analysis

Week 02 | Statistics Foundation

Week 03 | Hypothesis -------

Week 04 | Regression, Part I

Week 05 | Regression, Part II

<small>Source Page 9 of 65</small>

### Course Logistics

- Lecture slides, data, and code files are on Canvas.

- Textbook ModernDive - https://moderndive.com/v2/

- No use of smart phones in class, only use Laptops for course purposes.

- Use of GenAI is allowed for assignments but NOT for the final ----. Late submission will

NOT be accepted.
- ----------: two group projects (20% *2), final ---- (50%), In-class quizzes (2.5% * 4, the

highest four grades are counted).

<small>Source Page 10 of 65</small>

### Support Available To You

Teaching Assistant Lead (Optional) Workshops

- Led by dedicated teaching assistants

- Attendance not required but highly recommended

- Pen & paper, as well as R programming-based practice questions on the topics

covered that week

- Similar questions may appear in assignments and final ----.

Office Hours

- There will be open Q&A time during each workshop

- Open office hours format – email our dedicated list of teaching assistants and

--------- at any time

- My email:

<small>Source Page 11 of 65</small>

### Weeks 1-5 Learning Outcomes

Programming

in R

Use R and RStudio effectively for data analysis

Communicate quantitative analysis and recommendations using RMarkdown

Learn to extract, clean and manipulate data using R

Use simple unified R framework, called Tidyverse

Data Analytics

Stats

Learn to explore datasets to gain insights prior to analysis

Faced with samples of different sizes, be able to quantify accuracy of sample evidence

---- hypothesis about population parameters

Build regression models to predict future outcomes
<small>Source Page 12 of 65</small>

### Reason Coding Excel

Visualization Far better graphics than Excel (e.g., ggplot2 library) Basic tools

Price Free £59.99 / year

Ease of Use Easy to learn

Reusable: import existing code and apply it to new tasks

Transparent: code analysis is performed step by step and is contained in a single file

Statistical Analysis

Designed for data analysis, statistics and econometrics.

Contains ~17000 statistical libraries.

Reporting Produce HTML / pdf reports by knitting the Rmd file (markdown text, latex formulas, imbedded videos, code and its resulting outputs -> all contained in one final file)

Is point and click (+ VBA)

Need to pay for additional plugins No facility

<small>Source Page 13 of 65</small>

### Descriptive vs Inferential Statistics

Descriptive Statistics

- Collect

- Organize

- Summarize

- Display

- Analyze

Typical Questions:

- What is the average return per year of a stock?

- Are stock returns Normally

distributed?

Inferential Statistics

- Predict and forecast values of population parameters

- ---- hypothesis and draw conclusions about values of population parameters
- Make decisions

Typical Questions:

- Is restaurant revenue significant lower during tube strike compared to usual?

- Do companies with female CEOs provide better family-friendly benefits?

<small>Source Page 14 of 65</small>

### Why ----- Data Analytics?

Data empowers decision-making in uncertain situations – financial analysts who harness the power of data in the face of uncertainty make better decisions.

outcomei= modeli+ errori

yi

xi Systematic

ei Unsystematic

Part

Part

Statistics helps understand variability and make an inference – decisions should be grounded in statistical evidence. “Can trading signal extracted from a dataset be attributed to chance or is there a pattern?”

Model: explains how much of the overall variance in the data can be explained by the model vs. the noise i.e., systematic (model variance) vs. unsystematic (random variance).

<small>Source Page 15 of 65</small>

### Analytics in the era of GenAI

<small>Source Page 16 of 65</small>

<small>Source Page 17 of 65</small>

### ChatGPT Analysis
<small>Source Page 18 of 65</small>

01 | Understanding Data Structure 02 | Data Cleaning 03 | Data Wrangling: Tidy Data 04 | Data Wrangling: Manipulate Data 05 | Visualization

Exploratory Data Analysis

<small>Source Page 19 of 65</small>

01 | Understanding Data Structure 02 | Data Cleaning 03 | Data Wrangling: Tidy Data 04 | Data Wrangling: Manipulate Data 05 | Visualization

Exploratory Data Analysis

<small>Source Page 20 of 65</small>

### Reading in Data

To read in csv data use the tidyverse package’s function called read_csv()

```r
library(tidyverse) dji_index_original <- read_csv(‘dji_index.csv')
```

If you see an error message:

- Ensure that your .R or .Rmd programming file (where you write your code) and your

csv data are located in the same folder

- Ensure to point the RStudio’s current working directory to the locaton of the file

Set Current Working Directory

To set the cwd to the location of your .R or .Rmd file:

- Open the file in RStudio

- Right click on its name at the top

- Click on ‘Set Working

Directory’

Open session1.Rmd

<small>Source Page 21 of 65</small>

### Understanding Data Structure

Answer Three Questions
- Data Type: numerical, categorical, date etc. This is essential for selecting suitable

analytical techniques.

- Data Dimensionality: how many different variables (features) are available for analys‐

is?

- Data Summary: find the basic statistical information, what are the min, max, mean

values?

We will work with the Dow Jones 30 Index

```r
library(tidyverse) dji_index_original <- read_csv(‘dji_index.csv')
```

Open session1.Rmd

<small>Source Page 22 of 65</small>

### Basic Data Types in R

Every programming language comes with fundamental, pre-built objects that the programmer manipulates on a day-to-day basis.

Atomic Class Example Definition

Character "abc" 'abc' Data type used to store sequences of characters (we call it a ‘string’)

Double 2.321

Inf NaN

Real number (double precision) In R, all numbers are converted to double by default. So, 3 in R is treated as 3.0 Inf – infinity (i.e., result of 1/0) NaN – not a number (i.e., result of 0/0); can also be thought of as a missing value

Numeric

Integer 3L as.integer(3)

To create an integer, use L suffix (stands for Long integer, single precision)

Logical TRUE FALSE NA

Boolean logic, a variable denoting truth value: TRUE FALSE 1 is treated as TRUE, 0 is treated as FALSE NA – not available; is a filler for missing values

<small>Source Page 23 of 65</small>

### Data Dimensionality in R

In R (and most other coding languages), dimensionality is the number of indices needed to locate a data point.
Vector – 1-D (one row of an excel data)

Matrix – 2-D (an excel sheet)

Array – 3-D (stacked excel sheets)

DataFrame – 2-D array that can hold different data types down each column

Tibble – 2-D array with less functionality than a dataframe to limit user mistakes. Tibble is the unifying feature of tidyverse.

rows columns depth

row rows columns

Vector Matrix Array

"a" True

Tibble with 2 rows and 3 columns

"d"

False

<small>Source Page 24 of 65</small>

### Data Dimensionality in Stats

Indpendent variables data is usually structured as rows (observations) and columns (features / variables), overall called a Feature Matrix.

A feature matrix X∈ℝN×D means there are N observations and D features, with elements xi,j referenced by i for rows and j for columns:

D columns, j changes x1,1 x1,2 x1,3 … x2,1 x2,2 x2,3 … x3,1 x3,2 x3,3 … ⋮ ⋮ ⋮

N rows, i changes

Example: assume a feature matrix X∈ℝ1000×3, with 3 features (columns) x1, x2, x3.

3 columns

x1,1 x1,2 x1,3 x2,1 x2,2 x2,3 ⋮ x1000,1

1000

⋮ x1000,2

⋮ x1000,3

rows

A single observation forms a row of the data.

So, the first observation is a data point x1 = x1,1, x1,2, x1,3
T that resides in a multidimensional space.

dimensionality of any data point in feature matrix X, such as x1, is D= 3.

<small>Source Page 25 of 65</small>

01 | Understanding Data Structure 02 | Data Cleaning 03 | Data Wrangling: Tidy Data 04 | Data Wrangling: Manipulate Data 05 | Visualization

Exploratory Data Analysis

<small>Source Page 26 of 65</small>

### “80% of data analysis is spent on the process of cleaning and preparing

**the data.”**

<small>Source Page 27 of 65</small>

### Pipe Operator %>%

3 equivalent ways to code the same thing:

Why use the pipe operator?

```r
z <- 15.99 %>% round() %>% sqrt() %>% print()
```

- Enhanced Workflow: the pipe connects multiple dplyr functions (‘verb’ / actions)

together into a sequence of operations (‘pipeline’)

- Consistency Across the Tidyverse: consistent syntax

```r
x <- round(15.99) y <- sqrt(x) z <- print(y)
```

across dplyr, tidyr and ggplot2 libraries

- Readability: the pipe takes output of one function and feeds it as input to the next

function, making it easier to understand code

```r
z <- print(sqrt(round(15.99)))
```
<small>Source Page 28 of 65</small>

### Cleaning Data

Stages of cleaning data:

- Clean Column Headers: convert all names to lower case letters and separate spaces

with an underscore

- Convert Date from String to Date Format:

timeseries data should be in a ‘Date’ format

- Convert Categorical Variables to Factor / Numeric Format: instead of using strings for

categorical variables it is best to store them as numbers in R’s memory

- Remove Duplicate Rows: drop

duplicates

- Fill in Missing Data: either delete rows if they are missing any data, or forward fill the

data from the last available data until the next

Open session1.Rmd

<small>Source Page 29 of 65</small>

01 | Understanding Data Structure 02 | Data Cleaning 03 | Data Wrangling: Tidy Data 04 | Data Wrangling: Manipulate Data 05 | Visualization

Exploratory Data Analysis

<small>Source Page 30 of 65</small>

### “Happy families are all alike; every unhappy family is unhappy in its

**own way.”**

― Leo Tolstoy

<small>Source Page 31 of 65</small>

### Tidy Data Standard

Untidy

Tidy Data is a standardized way to structure datasets to facilitate analysis. Tidy tools and datasets help make data analysis easier, allowing you to focus on the problem, not on logistics of cleaning data. Four rules to Tidy Data:

Tidy
1.

Each variable forms a column 2.

Each observation forms a row 3.

Each type of observational unit forms a table.

4.

Each value has its own cell

More about Tidy Data: https://vita.had.co.nz/papers/tidy-data.pdf

More about Tidy Data: https://vita.had.co.nz/papers/tidy-data.pdf

<small>Source Page 32 of 65</small>

### From Untidy to Tidy: Wide -> Long

```r
library(tidyr)  # note tidyr is already loaded as part of library(tidyverse)
dji_index_tidy <- dji_index %>%
pivot_longer(cols = open:ret, names_to = "measurement", values_to = "value")
```

Wide format: column headers are values

Long format: each variable has its own column

<small>Source Page 33 of 65</small>

### Make Impact with Data Analytics

<small>Source Page 34 of 65</small>

<small>Source Page 35 of 65</small>
<small>Source Page 36 of 65</small>

### In May 2024, Canvas released an update, allowing graders to randomize

### -------- at one click.

<small>Source Page 37 of 65</small>

### Pen and Paper Exercise

Is the ------- data in a tidy format? Together with your neighbour sketch out on a piece of paper how this data should look like in a tidy format. What line of code is needed to tidy the data?

-------_id final_---- midterm group_project

2457625

1758293

1622247

<small>Source Page 38 of 65</small>

### Answer

Data was not in a tidy format since column names are values instead of variables. Instead, we should have columns: -------_id, assignment, score.

```r
-------_data_long <- -------_data %>% pivot_longer(cols = --------_id, names_to =
"assignment", values_to = "score")
```

-------_id assignment score 2457625 final_----

2457625 midterm

2457625 group_project

1758293 final_----

1758293 midterm

1758293 group_project

1622247 final_----

1622247 midterm

1622247 group_project
<small>Source Page 39 of 65</small>

### From Untidy to Tidy: Separate

```r
dji_split <- dji_table3 %>%
separate(`high/low`, into = c("high", "low") , sep = '/', convert=TRUE) # do the same for
open/adj_close
dji_split_tidy <- dji_split %>% pivot_longer(cols = volume:adj_close, names_to =
"measurement", values_to = "value")
```

Wide format: untidy format and columns are ratios

Long format: each variable has its own column

<small>Source Page 40 of 65</small>

### Untidy vs. Tidy Data

Main ways in which data can be untidy:

- Column headers are values and not variable names

- A single observation unit is stored in multiple tables

- Multiple values are stored in one column

- Variables are stored in both rows and columns

- Multiple types of observational units are stored in

one table

Data is tidy when:

- Data set is in ONE table

- Each column is a variable

- Each observation has its own row

- Each value has its own cell

For programming examples see “R For Data Science” book, Chapter 12 ‘Tidy Data’.

Open session1.Rmd
<small>Source Page 41 of 65</small>

### Practice Question 1

You now have the DJI Constituent Stock data which is untidy. Your task is to convert it to a tidy format.

LAB 1 QUESTION 1

<small>Source Page 42 of 65</small>

01 | Understanding Data Structure 02 | Data Cleaning 03 | Data Wrangling: Tidy Data 04 | Data Wrangling: Manipulate Data 05 | Visualization

Exploratory Data Analysis

<small>Source Page 43 of 65</small>

### “If you want to have a better performance than the crowd, you must do

**things differently from the crowd.”**

― John Templeton

<small>Source Page 44 of 65</small>

### Grammar Manipulation

DPLYR Package:

- Provides grammar manipulation which is a consistent set of verbs used to solve

common data manipulation tasks

- Verbs are highly optimised through execution in C++ making them fast

- Used for problems with extracting rows and columns of interest as well as re-ordering

and collapsing tibbles

Key Features:

- Requirement: data typically should be in a

tidy format

- Data Storage: data input and data output to and from dplyr functions is always a

tibble

- Operator: %>% pipe

- Key Verbs: select, filter, arrange, rename, mutate, summarise, group_by
<small>Source Page 45 of 65</small>

### Verbs

Verbs Meaning

Atomic Class

Purpose

```r
select() Select columns of interest filter() Select rows of interest arrange() Reorder rows
in ascending/descending order based on a column
rename() Raname columns mutate() Compute transforms on columns
```

Perform exploratory analysis

```r
summarise( )
group_by() Group data by categories within a variable of interest
```

How Verbs Work All verbs work similarly:

- First argument is a dataset

- Rest describe what to do with the tibble

- Result is a new tibble

Example with piping operator:

```r
r_mu_pipe <- dji_index_original %>% mutate(ret = ( `Adj Close` / lag(`Adj Close`) - 1 ) *
100) %>% filter(!is.na(ret)) %>% filter(ret > 0) %>% summarise(r_mu = mean(ret))
```

Example without piping operator:

Open session1.Rmd

<small>Source Page 46 of 65</small>

### Verb: Select

```r
select() pick columns (variables) directly by the names
```

Key Features:

- No need for `` (use adj_close not "adj_close")
- If the name is not standard such as containing a space, use `` (e.g. instead of Adj

Close use `Adj Close`)

Example, select two columns:

```r
dji_ex1 <- dji_index %>% select(date, day_of_week)
```

Example, select all columns between given columns:

```r
dji_ex2 <- dji_index %>% select(open:low)
```

Example, select all but one columns:

```r
dji_ex3 <- dji_index %>% select(-ret)
```

<small>Source Page 47 of 65</small>

### Verb: Filter

```r
filter() pick rows (observations) by their values using logical conditions
```

Key Features:

- Logical condition (e.g. ret > 0) used to pick rows of interest

- Only rows where condition is TRUE are picked

Example, filter positive returns

```r
dji_ex4 <- dji_index %>% filter(ret > 0)
```

Example, filter positive returns for large volume:

```r
dji_ex6 <- dji_index %>% filter(ret > 0, volume > 4e8)
```

Example, filter Tuesdays for 2015 onwards:

```r
dji_ex8 <- dji_index %>% filter(day_of_week == 2,
```

date >= as.Date("2015-01-06"))

Open session1.Rmd
<small>Source Page 48 of 65</small>

### Verb: Arrange

```r
arrange() reorders rows according to one of variable names while preserving order of
columns.
```

Key Features:

- Specify the column by which the data should be rearranged

- Result is always in ascending order by default

- Use desc() for descending order

Example, rearrange by column returns, to see smallest returns first:

```r
dji_ex9 <- dji_index %>% arrange(ret)
```

Example, rearrange by column returns, to see largest returns first:

```r
dji_ex10 <- dji_index %>% arrange(desc(ret))
```

<small>Source Page 49 of 65</small>

### Verb: Rename

```r
rename() rename columns.
```

Example, rename `Day Of Week` to day_of_week:

```r
dji_ex11 <- dji_index_original %>% rename(day_of_week = `Day Of Week`)
```

Example, rename `Day Of Week` to day_of_week and `Adj Close` to adj_close

Key Features:

- Can rename one or more columns

- New name is to be on the left

- Old name on the right

```r
dji_ex12 <- dji_index_original %>% rename(day_of_week = `Day Of Week`,
```

adj_close = `Adj Close`)
<small>Source Page 50 of 65</small>

### Verb: Mutate

```r
mutate() compute transformations on columns: create new columns using existing columns.
```

Key Features:

- Automatically adds new column to existing tibble

- To drop all non-transformed variables use

```r
transmute()
```

Example, perform feature engineering i.e. create a new feature (variable) using information from an existing feature. For example, create a 50-day moving average:

```r
dji_ex13 <- dji_index %>% mutate(ma50 = rollmean(adj_close, k = 50, fill = NA, align =
"right"))
```

- fill = NA fills the first 49 rows with missing values

- align = "right" aligns rolling mean with the last day of the window (i.e. records the MA

result into last day of the window)

<small>Source Page 51 of 65</small>

### Verb: Summarise

```r
summarise() generate summary statistics for variables of interest.
```

Key Features:

- Collapses each column to a single value

- Most useful together with verb group_by() as this allows to observe summary statistic

per each group

Example, find mean return of DJI:

```r
dji_ex14 <- dji_index %>% summarise(r_mu = mean(ret)) >>> 0.04246185
```

If we group the data by year first, we can obtain the mean each year (see next verb).

Open session1.Rmd Run through line 367 to 514
<small>Source Page 52 of 65</small>

### Practice Question 2

You are working with the DJI Constituent Stock data which is now tidy.

LAB 1 QUESTION 2

<small>Source Page 53 of 65</small>

### Verb: Group By

```r
group_by() group data into categories within a given variable.
```

Key Features:

- Does not change how data looks

- Grouping changes how data acts with other verbs

- Application of verbs on the resulting object will

be performed by group

Example, group by ’a’ and find mean of ‘b’:

```r
ex15 <- data %>% group_by(a) %>% summarise(mu_b = mean(b))
```

Example, find mean return of DJI per year:

```r
ex16 <- dji_index %>% mutate(year = year(date)) %>% group_by(year) %>% summarise(mu_r =
mean(ret))
```

<small>Source Page 54 of 65</small>

### Verb: Join

```r
xxx_join() join tibbles based on matching columns.
```

tb1 tb2

tb1 tb2 tb1 tb2

tb1 tb2

full join

inner join
left join

right join

Key Features:

- First 2 arguments are tibbles to be joined

- Results is always a new tibble

- Argument by specifies which column should be used to match the observations in 2

tables

Full join keeps all data from both tables (i.e. all rows)

```r
dji_joined_full <- full_join(dji_table1, dji_table2, by = 'date')
```

Inner join keeps only data for those dates that match (i.e. only matching rows).

Left join keeps all rows from table 1 and only matching rows from table 2.

Right join keeps all rows from table 2 and only matching rows from table 2.

<small>Source Page 55 of 65</small>

### In-class Quiz 1 (2.5% of Grade)

Dataframe A Dataframe B

------- ID Name

Alice

Bob

Carol

Which join operation would generate the displayed output?

A.

Inner join B.

Full join

C. Left join

D. Right join

------- ID Age

Output:

ID Name Age

Bob
Carol

NA

<small>Source Page 56 of 65</small>

### Answers

Inner join

ID Name Age

Bob

Carol

Left join

ID Name Age

Alice NA

Bob

Carol

Right join

ID Name Age

Bob

Carol

NA

Full join

ID Name Age

Alice NA

Bob

Carol

NA

Open session1.Rmd

<small>Source Page 57 of 65</small>

### Practice Question 3

You are working with the DJI Constituent Stock data which is now tidy.
LAB 1 QUESTION 3

<small>Source Page 58 of 65</small>

01 | Understanding Data Structure 02 | Data Cleaning 03 | Data Wrangling: Tidy Data 04 | Data Wrangling: Manipulate Data 05 | Visualization

Exploratory Data Analysis

<small>Source Page 59 of 65</small>

### “The world cannot be understood without numbers. But the world

**cannot be understood with numbers alone.”**

A person touching a graph with numbers AI-generated content may be incorrect.

― Hans Rosling

<small>Source Page 60 of 65</small>

### Always Plot Your Data

Anscombe’s quartet is a dataframe with 4 datasets, each with n = 11 datapoints, and all datasets have the same mean and standard deviation for both x and y.

Would you expect to have any differences among the data in the 4 datasets? After all, they all have the same mean, sd, and cor(x, y).

<small>Source Page 61 of 65</small>

### Always Plot Your Data

Even though descriptive statistics are identical, data has different distributions and are very different when plotted.

<small>Source Page 62 of 65</small>

### Data Visualization: Density

Example: Density of standardized DJI returns

Example: Density of standardized DJI returns faceted by year
<small>Source Page 63 of 65</small>

### Data Visualization: Box Plot

Example: Box Plot of DJI returns

<small>Source Page 64 of 65</small>

### Data Visualization with ggplot2

ggplot2 produces statistical graphs using grammar of graphics: components that can be put together.

All plots are composed of:

- Data – data stored in a tibble in a tidy format

- Aesthetic mapping – specify x and y variables

- Layers – made of ▪geoms (geometric objects) – represent objects visible on the plot

(points / lines) ▪stats (statistical transformations) – summarise data by creating a linear model, histogram binning etc

- Faceting – break data into subsets

- Theme – font size, background colour

- Scales – colour, size, shape, legend, axes

Typical Commands

- aes() map a variable to x, map a variable to y

- labs() label axes and title

- geom_point() data as dots

- geom_line() data as line

- geom_historgram() data as histogram

- geom_density() data as density

Open session1.Rmd

<small>Source Page 65 of 65</small>

### Session Summary

We covered:

Exploratory Data Analysis using R

Readings:
Modern Dives chapters 1-4

Optional/ Extra practice: workshop1.Rmd

Workshop 1:

Try the practice questions in session1.Rmd.

Look at the workshop questions in advance.

Attend optional workshop to go over the solutions and extra exercises.


[↑ Back to the source list](#source-documents)

---

<a name="source-3"></a>

## session1.Rmd

<small>File type: RMD · Reader pages 60–74 · [View source PDF](PDF%20Slides.pdf#page=60)</small>

```r
# include=FALSE means that the this particular code chunk and its output will not be included
in the knitted document
# echo = TRUE means code used in this document will be displayed along the output in the final
rendered document
knitr::opts_chunk$set(echo = TRUE)
```

Library / package – is a collection of code aimed to solve a particular task. Load a collection of libraries called 'tidyverse', designed for speed and efficiency when dealing with data and working with data analytics. Note: ignore red text in the Console (bottom left pane) when the packages are loading, unless you see the word 'error'.

- MOSAIC - is a package for statistics and calculus

- JANITOR - is a package to clean dirty data

- TIDYVERSE is a collection of packages designed to work in a Tidy framework

- ZOO - is a package that allows to find rolling mean

```r
# include=TRUE means that the code and its output will be included in the knitted document
# message=FALSE means that messages produced during the execution of the code chunk will not
be displayed in the output
# warning=FALSE means that any warnings produced by the code chunk will be suppressed and not
shown in the document
library(mosaic)
library(janitor)
library(zoo)
library(tidyverse)
```

### Exploratory Data Analysis for Dow Jones 30

We will use Dow Jones Index data, as well as Dow Jones individual constituents data, from 2010 to 2024 to demonstrate the steps that you should take when preparing data for analysis i.e. when performing Exploratory Data Analysis.

We are working with R Markdown file type, which allows us to combine text, code, and output in a single document, making it a powerful tool for data analysis, reporting, and reproducible research. You can knit this file to an HTML or pdf formats in order to share it with colleagues / management.

Let's first load the data. Place the data and the .Rmd file in the same folder. Point RStudio to the location of your files (go to Tools -\> Global Options -\> General -\> Default Working Directory -\> Navigate to your directory -\> Apply -\> OK)

```r
dji_index_original <- read_csv('dji_index.csv')
```
### Understanding Data Structure

Let's examine three things: \* Data types down each column of the data \* Dimensionality of your data\ \* Observe statistical data summary down each column

Data Types

We would like to know what kind of data is stored in each column. We see that we have data

types:

- <chr> character (i.e. data read in as text)

- <dbl> double (i.e. data read in as numbers)

```r
glimpse(dji_index_original)
```

Dimensionality of Data

"Dimensionality of Data" means "how many columns (how many features / variables) do we have that can be used as inputs into our model for data analysis"? When we make predicts we will typically make models where $x$ variables (independent variables) are used to make a prediction of a $y$ variable:

$y = \beta_0 + \beta_1 * x_1 + ... + \beta_m * x_m + error$

When we talk about 'dimensionality' we typically mean 'how many independent variables do I have for analysis'?

In the DJI data's case, we can think of our data in the following way:

- Date column: we can think of it as an observation number given by each date.

- Assume that the data prediction task involves predicting the Adjusted Close of the DJI

(usually we would try to predict if the DJI return was positive or negative rather than working with Adj Close directly). Therefore this column will form the y-label (the variable we are trying to predict).\

- Therefore we can use 'High, Open, Low, Volume and Day Of Week' as the independent

variables which can be input into our model to make predictions. Therefore the dimensionality of our data is 5.

Data Summary

Let's first create returns for the DJI Adjusted Closing prices.

```r
# create simple returns
dji_index <- dji_index_original %>%
mutate(ret = ( `Adj Close` / lag(`Adj Close`) - 1 ) * 100) %>%
filter(!is.na(ret))
# keep columns: date, returns and day of the week and store into a new variable
dji_returns <- dji_index %>%
select(Date, ret, `Day Of Week`)
```

We can use the Mosaic library function favstats() to find the min, max, std dev of the return data i.e. to observe the basic statistics of the return feature / variable. Note the syntax of the favstats() function: here you have a single numerical variable, hence use \~ x.
```r
# Single numerical variable, use ~ x
favstats(~ret, data=dji_returns)
```

We can also 'facet' analysis of the returns by day of the week to see if can suspect any significant difference in the returns obtained on different days.

```r
# Single numerical variable and single categorical variable syntax: x ~ y
favstats(ret ~ `Day Of Week`, data=dji_returns)
```

We can see that the mean return on Tuesdays seems higher than on the other days. This could be due to outliers or potentially a signal we could investigate.

### Cleaning Data

### Clean Column Headers

Convert column headers to a conventional format: all lower case letters, any spaces to be replaced with an underscore. To do this quickly, we use a package called JANITOR (already loaded at the top of the file).

```r
dji_index <- dji_index %>%
clean_names()
```

### Convert String to Date

Change the strings in the column 'date' into a timestamp Date format.

```r
dji_index <- dji_index %>%
mutate(date = dmy(date)) # Lubridate package of the Tidyverse, uses a function dmy() which
stands for Date Month Year format
```

### Convert String to Numeric Format

Change `day_of_week` variable to a numeric format (since it is harder to work with strings). We will do this in two steps.

Convert string to factor first, i.e. provide both character and numeric representation to the categorical data. Factor is a special data type (like string, numeric etc) which is used with categorical data, where categories are called 'levels'. Internally, factors are stored as integers, where each unique category is assigned a unique integer value, however if you look at the data it will display strings. Therefore it is a flexible data type.

```r
dji_index <- dji_index %>%
mutate(day_of_week = factor(day_of_week,
levels = c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday"),
ordered = TRUE))
```

Now obtain just the integer values of the factor and drop the string content, thereby converting factor to numeric format.
```r
dji_index <- dji_index %>%
mutate(day_of_week = as.numeric(day_of_week))
```

When cleaning data we may encounter situations where the data we read in has missing values or may have duplicate values. Let's assume we read in the data in such a format using a dataset with missing values and duplicates, called 'dji_index_missing_and_duplicates.csv'.

```r
dji_index_unclean <- read_csv('dji_index_missing_and_duplicates.csv')
```

### Remove Duplicates

Sometimes data may erroneously contain duplicated rows, let's check how many duplicates we

have:

```r
num_duplicated_rows <- dji_index_unclean %>%
filter(duplicated(.)) %>%  # Filter only duplicated rows
summarise(n = n())  # Count the number of duplicated rows
print(num_duplicated_rows)
```

Duplicated rows should be removed:

```r
dji_index_unclean <- dji_index_unclean %>%
distinct()
```

### Fill in Missing Values

Sometimes data may be missing in some columns, lets examine how many missing values we have in each column.

```r
missing_values_per_column <- dji_index_unclean %>%
summarise(across(everything(), ~ sum(is.na(.)))) # summarize works down columns
print(missing_values_per_column)
```

We need to make a decision whether to delete rows with missing values, or since this is a time series of stock Index data, forward fill the missing values so that not to introduce a forward looking bias. This means use the last available data and fill in the missing values using this data until the next available data.

```r
dji_index_unclean <- dji_index_unclean %>%
fill(everything(), .direction = "down")
```

We note that we still have 1 missing value in the first row since there was nothing to forward fill it with. We can now drop the data with missing rows (i.e. the first row):

```r
dji_index_unclean <- dji_index_unclean %>%
filter(complete.cases(.))
```
### Data Wrangling: Tidy Data

When preparing data for analysis and working with the Tidyverse packages, it is important to place the data into a format compatible with the Tidyverse framework.

Tidyverse is a collection of packages such as READR package (to read in data using read_csv()), TIDYR package (to tidy data into a standard format), DPLYR package (to calculate statistics and manipulate data),\ GGPLOT2 package (to visualize data), LUBRIDATE package (to work the dates if using time series data) and more.

The key unifying feature of Tidyverse is that all data inputs and outputs from any functions operate with data stored in a Tibble data structure.

### Convert Data from Untidy to Tidy Format

As part of the Tidyverse framework, the data needs to be in a particular format we call 'tidy'.

Let's examine ways in which data can be untidy and convert it to a tidy format.

Column headers are values and not variable names

Current Dow Jones Index data is in the 'wide' (untidy) format i.e. values of the variable 'measurement' (High, Low, Open, Close etc) is spread across the columns. Instead they all should be grouped into a single column called 'measurement'. Let's tidy up the data into a format Tidyverse expects using a function pivot_longer() of the TIDYR package.

```r
dji_index_tidy <- dji_index %>%
pivot_longer(cols = open:ret,
names_to = "measurement",
values_to = "value")
```

A single observation unit is stored in multiple tables

If the DJI data was stored as two tables (where a single unit called 'date' is present in both tables), and one table contained 'high, open, low, adj_close', while the other contained 'volume' measurements, then this is not considered a tidy format as the data set is meant to be in a single table.

Hence these tables should be combined into a single table and converted to a tidy format.

You can combine the two tables using a full_join(x,y) function, and then convert the single resulting table to a tidy format using pivot_longer() function.

```r
dji_table1 <- read_csv('dji_index_1.csv')
dji_table2 <- read_csv('dji_index_2.csv')
dji_joined <- full_join(dji_table1, dji_table2, by = 'date')
dji_joined_tidy <- dji_joined %>%
pivot_longer(cols = open:volume,
names_to = "measurement",
values_to = "value")
```
Multiple varaibles are stored in one column

If the DJI data was stored as ratios of High/Low and Open/Adj_Close, then this is not considered a tidy format as each value is expected to have its own cell.

```r
dji_table3 <- read_csv('dji_index_3.csv')
glimpse(dji_table3)
```

We need to separate the data and then pivot_longer() to convert the data into a tidy format. Let's separate the ratios into single columns first.

Note: convert=TRUE is needed in order to let R automatically recognize the data type of the new columns. Here they will be recognized as numeric data type. If you do not do this, they will be kept as characters.

```r
dji_split <- dji_table3 %>%
separate(`high/low`, into = c("high", "low"), convert=TRUE) %>%
separate(`open/adj_close`, into = c("open", "adj_close"), convert=TRUE)
glimpse(dji_split)
```

Now pivot the data to obtain the long format.

```r
dji_split_tidy <- dji_split %>%
pivot_longer(cols = volume:adj_close,
names_to = "measurement",
values_to = "value")
glimpse(dji_split_tidy)
```

For further programming examples of untidy data see “R For Data Science” book, Chapter 12 ‘Tidy Data’.

### Pivot Back From Long (Tidy) to Wide (Untidy) If Needed

In case you would like to convert back to a wide format for some reason, you can do so with the pivot_wider() function, which spreads the data across columns.

```r
dji_index_untidy <- dji_index_tidy %>%
pivot_wider(names_from = measurement,
values_from = value)
glimpse(dji_index_untidy)
```

### LAB 1 QUESTION 1

You are now faced with a different dataset which contains the DJI constituent stocks instead of the DJI itself.

```r
dji_stocks <- read_csv('dji_stocks_unclean.csv')
glimpse(dji_stocks)
```

- Split the columns containing high/low and open/close ratios.
- First tidy up column names.

- Convert string 'Date' column to Date format.

- Create a tidy dataset called dji_stocks_tidy.

### Data Wrangling: Manipulating Data

The DPLYR library allows us to manipulate data in a variety of ways. This library expects data to be in a tidy format (i.e. long format), however for certain verbs it is easier to work with the wide format, for example:

### DPLYR vs. R Base

DPLYR allows you to manipulate the data through a series of verbs connected with pipe operators, which makes your code tidy and easy to read. The example below shows you how to compute the mean of all positive returns through DPLYR vs. R base.

DPLYR:

```r
r_mu_pipe <- dji_index_original %>%
mutate(ret = ( `Adj Close` / lag(`Adj Close`) - 1 ) * 100) %>%
filter(!is.na(ret)) %>%
filter(ret > 0) %>%
summarise(r_mu = mean(ret))
```

R Base:

```r
r_mu_base <- data.frame(r_mu = mean(((dji_index_original$`Adj Close` / c(NA,
head(dji_index_original$`Adj Close`, -1)) - 1) * 100)[((dji_index_original$`Adj Close` / c(NA,
head(dji_index_original$`Adj Close`, -1)) - 1) * 100) > 0], na.rm = TRUE))
```

### Verb Select

Select columns of interest:

```r
dji_ex1 <- dji_index %>%
select(date, day_of_week)
dji_ex2 <- dji_index %>%
select(open:low)
dji_ex3 <- dji_index %>%
select(-ret)
```

### Verb Filter

Filter rows of interest, such as those observations with positive returns only.

Explanation of boolean indexing (i.e. filtering data based on a condition):
```r
dji_ex4a <- dji_index %>%
mutate(ret_pos = ret > 0)
```

Example when working with data in a *wide* format data:

```r
dji_ex4b <- dji_index %>%
filter(ret > 0)
```

Example when working with data in a *long* format data:

```r
dji_ex5 <- dji_index_tidy %>%
filter(measurement == "ret" & value > 0)
```

Filter rows of interest, such as those observations for positive returns and large volume days.

Example when working with data in a *wide* format data:

```r
dji_ex6 <- dji_index %>%
filter(ret > 0, volume > 4e8)
```

[Advanced / Extra] Example when working with data in a *long* format data. Since now all data is in a long format, each measurement is stored in separate rows, so you cannot directly filter for two conditions. First we need to group data by date, so that the conditions are checked across the rows for the same date.

```r
dji_ex7 <- dji_index_tidy %>%
group_by(date) %>%
filter(any(measurement == "ret" & value > 0) &
any(measurement == "volume" & value > 4e8)) %>%
ungroup()
```

Filter only Tuesdays for year 2015 onwards.

```r
dji_ex8 <- dji_index %>%
filter(day_of_week == 2,
date >= as.Date("2015-01-06"))
```

### Verb Arrange

We may wish to examine the date on which the lowest returns occurred. To do so arrange the data by column returns in ascending order.

```r
dji_ex9 <- dji_index %>%
arrange(ret)
```

To see highest returns first use function desc() which stands for descending order.

```r
dji_ex10 <- dji_index %>%
arrange(desc(ret))
```
Missing values, NA, are always sorted in the end, both when using default and for desc().

### Verb Rename

Rename a column.

```r
dji_ex11 <- dji_index_original %>%
rename(day_of_week = `Day Of Week`)
```

To rename several columns use comma separation.

```r
dji_ex12 <- dji_index_original %>%
rename(day_of_week = `Day Of Week`,
adj_close = `Adj Close`)
```

### Verb Mutate

Sometimes we may wish to create new variables from existing ones. For example we may be interested in the 50-day moving average. Creating new columns from existing ones is called 'feature engineering'.

```r
dji_ex13 <- dji_index %>%
mutate(ma50 = rollmean(adj_close,
k = 50,
fill = NA,
align = "right"))
```

### Verb Summarise

Find mean daily return of the DJI.

```r
dji_ex14 <- dji_index %>%
summarise(r_mu = mean(ret))
```

Let's practice our understanding of data types. Note that the data type of the resulting variable dji_ex13 is a tibble. If we print the contents we see it is contained in a 1x1 tibble i.e. tibble with a single row and a single column.

```r
print(class(dji_ex14)) # class() reveals the data type of the variable
print(dji_ex14) # observe contents of the variable by printing it
```

To obtain the number itself, i.e. the mean value, store the result by accessing the value out of the tibble using square brackets, like this:

```r
r_mu <- dji_ex14[[1]]
print(r_mu)
print(class(r_mu)) # now the variable is of numeric data type (not tibble), i.e. variable r_mu
stores a number, not a number inside a tibble
```
### LAB 1 QUESTION 2

You are working with the DJI Constituent Stock data which is now tidy (run code below). Your task is to perform the following grammar manipulation of the data:

```r
dji_stocks <- read_csv('dji_stocks_unclean.csv')
dji_stocks <- dji_stocks %>%
separate(`High/Low`, into = c("high", "low"), sep = '/', convert=TRUE) %>%
separate(`Open/adj_close`, into = c("open", "adj_close"), sep = '/', convert=TRUE) %>%
clean_names() %>%
mutate(date = dmy(date))
dji_stocks_tidy <- dji_stocks %>%
pivot_longer(cols = c(volume, day:adj_close), # c() concatenates items together
names_to = "measurement",
values_to = "value")
```

- Extract all data that you have for Apple stock.

- Select only the volume data for Apple stock and arrange this data in descending order.

- Select only the volume data for Apple stock again and calculate the cumulative volume

over time (hint: you can use the cumsum() function). Ensure that your resulting data only keeps the new cumulative sum volume data and not other columns.

- [EXTRA] Find the average traded volume of Apple stock data for the year 2020 and store

it into a variable called av_apple_vol_2020 as a number.

```r
# aapl <- dji_stocks_tidy %>%
```

### Verb Group By

Group By with Summarise

Grouping the data by year first, before finding the mean return, would allow us to obtain more information i.e. to obtain mean return per year.

Let's create a new column called 'year' using Lubridate package first.

```r
dji_index <- dji_index %>%
mutate(year = year(date),
month = month(date)) # can also create month for example
print(dji_index)
```

Let's observe if grouping this tibble by year creates any visual change to the data. Observe that visually there is no change. We only see at the top that we have grouped the data by year and that there are 15 groups (i.e. 15 years).

```r
dji_ex15 <- dji_index %>%
group_by(year) # group by year so that subsequent operations are applied per group
```
```r
print(dji_ex15)
```

Let's now find mean return of the DJI per each year.

```r
dji_ex16 <- dji_index %>%
group_by(year) %>%
summarise(mu_r = mean(ret))
print(dji_ex16)
```

We can also count the number of observations within each group (in this case it will be the number of days in each working year). There are typically 252 trading days in a year, but we can see some small variation.

```r
dji_ex17 <- dji_index %>%
group_by(year) %>%
summarise(count = n())
print(dji_ex17)
```

We can also use group_by with mutate and arrange verbs to allow us to examine information by group.

Group By with Mutate

Let's see an example of grouping followed by mutate. Let's find the z-value of the returns per year. Reminder the z-value is found using the formula:

$z_i = \frac{x_i - \bar{x}}{s}$, where $\bar{x}$ is the sample mean and $s$ is the sample standard deviation.

Let's assume we would like to find the z-value of our data pear year, i.e. we will use the sample mean and sample standard deviation per year to adjust our returns into z-values.

```r
dji_ex18 <- dji_index %>%
group_by(year) %>%
mutate(ret_z = (ret - mean(ret) / sd(ret)))
```

Q: if we don't use the grouping by year first, how will ret_r be different?

Group By with Arrange

We can re-order data based on a column of interest, for example year again. Let's order our returns data in *descending* order by year. Note: that in order to arrange using groups, we need to specify .by_group = TRUE

```r
dji_ex19 <- dji_index %>%
group_by(year) %>%
arrange(desc(ret), .by_group = TRUE)
```

Q. If we wanted to arrange returns by year in *ascending* order, what do we need to change in the code?
### Verb Join

Full Join

Keep all data from both tables regardless if dates match, i.e. keep all dates data from table 1 and all dates data from table 2. Remember we have already done this above, when we had to tidy a dataset stored across 2 tables. In that case all the dates matched anyway.

```r
dji_joined <- full_join(dji_table1, dji_table2, by = 'date')
```

Let's say we have a Shanghai Stock Exchange Composite Index (sse.csv) that we would like to combine with the S&P500 Index data. Both data sets contain data from 14/05/2010 to 15/05/2020. Sometimes these trade on different dates due to holidays, therefore the different ways of joining data will be demonstrated better. Note that we have 2517 observations for S&P500 and 2427 observations for SSE.

Read in both indices data:

```r
sse_index <- read_csv('sse_index.csv')
snp_index <- read_csv('snp_index.csv')
# convert first column to Date datatype (rather than string)
sse_index <- sse_index %>%
mutate(date = dmy(date))
snp_index <- snp_index %>%
mutate(date = dmy(date))
```

Inner Join

Only keep data for matching dates. We note that there are 2346 matching dates.

```r
indices_join_inner <- inner_join(sse_index, snp_index, by = 'date')
```

Left Join

Keep all of the dates for SSE, but only matching S&P. We note that all 2427 rows of SSE were kept, but missing values of S&P are present on dates when it did not trade.

```r
indices_join_left <- left_join(sse_index, snp_index, by = 'date') %>%
arrange(date)
```

Right Join

Keep all of the dates for S&P, but only matching SSE. We note that all 2517 rows of S&P were kept, but missing values of SSE are present on dates when it did not trade.

```r
indices_join_right <- right_join(sse_index, snp_index, by = 'date') %>%
arrange(date)
```
### LAB 1 QUESTION 3

In this task you will need to combine your learnt skills for the previous sections. For example you will need to find the returns data yourself (hint provided).

- Find the average S&P500 daily returns per year, using the snp_index variable that we

loaded earlier.

- Find the same information for the SSE and join the two resulting average daily returns

tables into one.

```r
# hint to create returns use:
# mutate(ret = ( col / lag(col) - 1 ) * 100) %>%
```

### Visualizing Data

### Scatter Plot

```r
ggplot(data = dji_index, aes(x = date, y = ret)) +
geom_point() +
labs(x = "Date", y = "DJI Simple Return", title = "Scatter plot of Date vs. DJI Returns") +
theme_bw()
```

Line Plot

```r
ggplot(data = dji_index, aes(x = date, y = ret)) +
geom_point() +
geom_line() +
labs(x = "Date", y = "DJI Simple Return", title = "Scatter plot of Date vs. DJI Returns") +
theme_bw()
```

Line Of Best Fit (Simple Regression Line)

Let's see if we can fit a line to the Volume data across the last 15 years by using a smoothing method called 'lm' which stands for Linear Model.

```r
ggplot(data = dji_index, aes(x = date, y = volume)) +
geom_point() +
geom_line() +
geom_smooth(method = "lm", color = "red", linewidth = 1.5) +
labs(x = "Date", y = "Volume", title = "Regression line")
```

Nonlinear Fit (Polynomial Regression Curve)

Let's see if non-linear fit is better using a smoothing method called 'loess', which stands for Locally Estimated Scatterplot Smoothing.

```r
ggplot(data = dji_index, aes(x = date, y = volume)) +
geom_point() +
geom_line() +
geom_smooth(method = "loess", color = "red", linewidth = 1.5) +
labs(x = "Date", y = "Volume", title = "Regression line")
```
Histogram Plot

Histogram of DJI volume

We can see that the volume is bimodal and skewed to the right.

```r
ggplot(dji_index, aes(x = volume)) +
geom_histogram() +
theme_bw() + # classic dark-on-light ggplot2 theme
NULL
```

Histogram of standardized returns by year

Let's examine the z-values we obtained previously (which were calculated by year), and plot them for each of the years. Let's look at the last 6 years as an example to see if there is any visual difference in the standardized returns. We can see that the distribution of standardized returns look different for different years.

```r
dji_z_values <- dji_ex18 %>%
select(year, ret_z) %>%
filter(year >= 2018, year < 2024) # look at last 6 full years worth of data
ggplot(dji_z_values, aes(x = ret_z)) +
geom_histogram() +
facet_wrap(~ year, nrow = 2) + # arrange in 2 rows
theme_light() +
NULL
```

Density Plots

Density of standardized returns

```r
ggplot(dji_z_values, aes(x = ret_z)) +
geom_density() +
NULL
```

Density of standardized returns by year

```r
ggplot(dji_z_values, aes(x = ret_z)) +
geom_density(aes(fill = as.factor(year),
alpha = 0.3)) + # alpha refers to opacity of geom.
NULL
```

Box Plot

Box plot of returns by year for the DJI. Let's make this plot as pretty as possible.

```r
ggplot(dji_index, aes(x = as.factor(year), y = ret)) +
geom_boxplot(aes(fill = as.factor(year))) +
labs(x = "",
y = "Return",
title = "Box Plot of DJI Returns",
fill = "Year") + # legend title
theme(axis.text.x  = element_text(angle = 45, hjust = 1, vjust = 0.5),
axis.text  = element_text(size = 15),
axis.title  = element_text(size = 15, face = "bold", colour = "red"),
```
```r
plot.title  = element_text(size = 15, colour = "blue"),
legend.text  = element_text(size = 10),
# legend.position = "none" # omit legend
# legend.title = element_blank() # omit title from legend
# legend.title.x = element_blank() # omit x-axis title
legend.title = element_text(size = 15, colour = "green")) +
geom_hline(yintercept = -2.5, colour = "blue", linewidth = 0.5) +
NULL
```


[↑ Back to the source list](#source-documents)

---

<a name="source-4"></a>

## session1_solutions.Rmd

<small>File type: RMD · Reader pages 75–78 · [View source PDF](PDF%20Slides.pdf#page=75)</small>

```r
knitr::opts_chunk$set(echo = TRUE)
library(mosaic)
library(janitor)
library(tidyverse)
```

### Solution to L1_LAB_Q1

*QUESTION*: You are now faced with a different dataset which contains the DJI constituent stocks instead of the DJI itself.

```r
dji_stocks <- read_csv('dji_stocks_unclean.csv')
glimpse(dji_stocks)
```

- Split the columns containing high/low and open/close ratios.

- First tidy up column names.

- Convert string 'Date' column to Date format.

- Create a tidy dataset called dji_stocks_tidy.

Read in the DJI individual stocks data. Note that the Day of the week is already a number.

### Clean the data into a tidy format.

### Split ratios into individual columns

```r
dji_stocks <- dji_stocks %>%
separate(`High/Low`, into = c("high", "low"), sep = '/', convert=TRUE) %>%
separate(`Open/adj_close`, into = c("open", "adj_close"), sep = '/', convert=TRUE)
glimpse(dji_stocks)
```

### Clean Column Headers

```r
dji_stocks <- dji_stocks %>%
clean_names()
glimpse(dji_stocks)
```

### Convert String to Date

```r
dji_stocks <- dji_stocks %>%
mutate(date = dmy(date))
```
```r
glimpse(dji_stocks)
```

### Convert Data to Tidy Format

Leave out the date and tic columns as we will treat them as labels, and pivot all the other columns. Note: column 'day_of_week' now is called 'day'.

```r
dji_stocks_tidy <- dji_stocks %>%
pivot_longer(cols = c(volume, day:adj_close), # c() concatenates items together
names_to = "measurement",
values_to = "value")
glimpse(dji_stocks_tidy)
```

### Solution to L1_LAB_Q2

*QUESTION* You working with the DJI Constituent Stock data which is now tidy, dji_stocks_tidy. Your task is to perform the following grammar manipulation of the data:

- Extract all data that you have for Apple stock.

- Select only the volume data for Apple stock and arrange this data in descending order.

- Select only the volume data for Apple stock again and calculate the cumulative volume

over time (hint: you can use the cumsum() function). Ensure that your resulting data only keeps the new cumulative sum volume data and not other columns.

- [EXTRA] Find the average traded volume of Apple stock data for the year 2020 and store

it into a variable called av_apple_vol_2020 as a number.

To obtain all data for apple, we need to subset rows of the tidy data.

```r
aapl <- dji_stocks_tidy %>%
filter(tic == 'AAPL')
glimpse(aapl)
```

Select only the volume data from apple stock and arrange it in descending order:

```r
vol_desc <- aapl %>%
filter(measurement == 'volume') %>%
arrange(desc(value))
glimpse(vol_desc)
```

Cumulative volume over time for apple stock. Use transmute() to only keep the resulting cumulative volume data.

```r
vol_cumsum <- aapl %>%
filter(measurement == 'volume') %>%
transmute(vol_cum_sum = cumsum(value))
glimpse(vol_cumsum)
```
Average traded volume of Apple stock data for the year 2020

```r
av_apple_vol_2020 <- aapl %>%
filter(measurement == 'volume') %>%
filter(date >= as.Date("2020-01-01")) %>%
filter(date < as.Date("2021-01-01")) %>%
summarise(av_vol = mean(value))
av_apple_vol_2020 <- av_apple_vol_2020[[1]]
```

### Solution to L1_LAB_Q3

*QUESTION* In this task you will need to combine your learnt skills for the previous sections. For example you will need to find the returns data yourself (hint provided).

```r
# hint to create returns use:
# mutate(ret = ( col / lag(col) - 1 ) * 100) %>%
```

- Find the average S&P500 daily returns per year, using the snp_index variable that we

loaded earlier.

- Find the same information for the SSE and join the two resulting average daily returns

tables into one.

```r
sse_index <- read_csv('sse_index.csv')
snp_index <- read_csv('snp_index.csv')
```

Find the average daily S&P500 returns per each year.

```r
av_snp_daily_ret <- snp_index %>%
mutate(ret = (snp_adj_close / lag(snp_adj_close) - 1 ) * 100) %>%
filter(!is.na(ret)) %>%
mutate(year = year(dmy(date))) %>%
group_by(year) %>%
summarise(mu_r_snp = mean(ret))
print(av_snp_daily_ret)
av_sse_daily_ret <- sse_index %>%
mutate(ret = (sse_adj_close / lag(sse_adj_close) - 1 ) * 100) %>%
filter(!is.na(ret)) %>%
mutate(year = year(dmy(date))) %>%
group_by(year) %>%
summarise(mu_r_sse = mean(ret))
print(av_sse_daily_ret)
```

Joining two tables: both contain the same dates so we can either do full join or inner join on year and we will get the same information.
```r
av_ret_per_year <- inner_join(av_snp_daily_ret, av_sse_daily_ret, by = 'year')
print(av_ret_per_year)
```


[↑ Back to the source list](#source-documents)

---

<a name="source-5"></a>

## dji_index.csv

<small>File type: CSV · Reader pages 79–80 · [View source PDF](PDF%20Slides.pdf#page=79)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

> Data preview (up to six records and twelve columns); the full CSV remains in the original files.

Table displayed as labelled records for readability (6 rows, 7 columns).

04/01/2010

Open 10430.69043

High 10604.96973

Low 10430.69043

Adj Close 10583.95996

Volume 179780000

Day Of Week Monday

05/01/2010

Open 10584.55957

High 10584.55957

Low 10522.51953

Adj Close 10572.01953

Volume 188540000

Day Of Week Tuesday

06/01/2010

Open 10564.71973

High 10594.99023

Low 10546.5498

Adj Close 10573.67969

Volume 186040000

Day Of Week Wednesday

07/01/2010

Open 10571.11035

High 10612.37012

Low 10505.20996

Adj Close 10606.86035

Volume 217390000

Day Of Week Thursday
08/01/2010

Open 10606.40039

High 10619.40039

Low 10554.33008

Adj Close 10618.19043

Volume 172710000

Day Of Week Friday

11/01/2010

Open 10620.30957

High 10676.23047

Low 10591.58984

Adj Close 10663.99023

Volume 182050000

Day Of Week Monday

</details>


[↑ Back to the source list](#source-documents)

---

<a name="source-6"></a>

## dji_index_1.csv

<small>File type: CSV · Reader pages 81–81 · [View source PDF](PDF%20Slides.pdf#page=81)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

> Data preview (up to six records and twelve columns); the full CSV remains in the original files.

date

open

high

low

adj_close

04/01/2010

10430.69043

10604.96973

10430.69043

10583.95996

05/01/2010

10584.55957

10584.55957

10522.51953

10572.01953

06/01/2010

10564.71973

10594.99023

10546.5498

10573.67969

07/01/2010

10571.11035

10612.37012

10505.20996

10606.86035

08/01/2010

10606.40039

10619.40039

10554.33008

10618.19043

11/01/2010

10620.30957

10676.23047

10591.58984

10663.99023

</details>


[↑ Back to the source list](#source-documents)

---

<a name="source-7"></a>

## dji_index_2.csv

<small>File type: CSV · Reader pages 82–82 · [View source PDF](PDF%20Slides.pdf#page=82)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

> Data preview (up to six records and twelve columns); the full CSV remains in the original files.

date

volume

04/01/2010

179780000

05/01/2010

188540000

06/01/2010

186040000

07/01/2010

217390000

08/01/2010

172710000

11/01/2010

182050000

</details>


[↑ Back to the source list](#source-documents)

---

<a name="source-8"></a>

## dji_index_3.csv

<small>File type: CSV · Reader pages 83–83 · [View source PDF](PDF%20Slides.pdf#page=83)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

> Data preview (up to six records and twelve columns); the full CSV remains in the original files.

date

volume

high/low

open/adj_close

04/01/2010

179780000

10605/10431

10431/10584

05/01/2010

188540000

10585/10523

10585/10572

06/01/2010

186040000

10595/10547

10565/10574

07/01/2010

217390000

10612/10505

10571/10607

08/01/2010

172710000

10619/10554

10606/10618

11/01/2010

182050000

10676/10592

10620/10664

</details>


[↑ Back to the source list](#source-documents)

---

<a name="source-9"></a>

## dji_index_missing_and_duplicates.csv

<small>File type: CSV · Reader pages 84–85 · [View source PDF](PDF%20Slides.pdf#page=84)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

> Data preview (up to six records and twelve columns); the full CSV remains in the original files.

Table displayed as labelled records for readability (6 rows, 7 columns).

04/01/2010

open 10430.69043

high NA

low 10430.69043

adj_close 10583.95996

volume 179780000

day_of_week Monday

05/01/2010

open 10584.55957

high 10584.55957

low 10522.51953

adj_close 10572.01953

volume 188540000

day_of_week Tuesday

06/01/2010

open 10564.71973

high 10594.99023

low 10546.5498

adj_close 10573.67969

volume 186040000

day_of_week Wednesday

07/01/2010

open NA

high 10612.37012

low 10505.20996

adj_close 10606.86035

volume 217390000

day_of_week Thursday
08/01/2010

open 10606.40039

high 10619.40039

low 10554.33008

adj_close 10618.19043

volume 172710000

day_of_week Friday

11/01/2010

open 10620.30957

high NA

low 10591.58984

adj_close 10663.99023

volume 182050000

day_of_week Monday

</details>


[↑ Back to the source list](#source-documents)

---

<a name="source-10"></a>

## dji_stocks.csv

<small>File type: CSV · Reader pages 86–87 · [View source PDF](PDF%20Slides.pdf#page=86)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

> Data preview (up to six records and twelve columns); the full CSV remains in the original files.

Table displayed as labelled records for readability (6 rows, 8 columns).

04/01/2010

Open 7.622499943

High 7.660714149

Low 7.585000038

Adj Close 6.454505444

Volume 493729600

TIC AAPL

Day 1

04/01/2010

Open 56.63000107

High 57.86999893

Low 56.56000137

Adj Close 40.91589737

Volume 5277400

TIC AMGN

Day 1

04/01/2010

Open 40.81000137

High 41.09999847

Low 40.38999939

Adj Close 32.99215698

Volume 6894300

TIC AXP

Day 1
04/01/2010

Open 55.72000122

High 56.38999939

Low 54.79999924

Adj Close 43.77754593

Volume 6186700

TIC BA

Day 1

04/01/2010

Open 57.65000153

High 59.18999863

Low 57.50999832

Adj Close 40.02720261

Volume 7325600

TIC CAT

Day 1

04/01/2010

Open 18.65250015

High 18.88249969

Low 18.54750061

Adj Close 18.65156364

Volume 7906000

TIC CRM

Day 1

</details>


[↑ Back to the source list](#source-documents)

---

<a name="source-11"></a>

## dji_stocks_unclean.csv

<small>File type: CSV · Reader pages 88–89 · [View source PDF](PDF%20Slides.pdf#page=88)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

> Data preview (up to six records and twelve columns); the full CSV remains in the original files.

Table displayed as labelled records for readability (6 rows, 6 columns).

04/01/2010

Volume 493729600

TIC AAPL

Day 1

High/Low 7.6607/7.5850

Open/adj_close 7.6225/6.4545

04/01/2010

Volume 5277400

TIC AMGN

Day 1

High/Low 57.8700/56.5600

Open/adj_close 56.6300/40.9159

04/01/2010

Volume 6894300

TIC AXP

Day 1

High/Low 41.1000/40.3900

Open/adj_close 40.8100/32.9922

04/01/2010

Volume 6186700

TIC BA

Day 1

High/Low 56.3900/54.8000

Open/adj_close 55.7200/43.7775
04/01/2010

Volume 7325600

TIC CAT

Day 1

High/Low 59.1900/57.5100

Open/adj_close 57.6500/40.0272

04/01/2010

Volume 7906000

TIC CRM

Day 1

High/Low 18.8825/18.5475

Open/adj_close 18.6525/18.6516

</details>


[↑ Back to the source list](#source-documents)

---

<a name="source-12"></a>

## snp_index.csv

<small>File type: CSV · Reader pages 90–90 · [View source PDF](PDF%20Slides.pdf#page=90)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

> Data preview (up to six records and twelve columns); the full CSV remains in the original files.

date

snp_adj_close

snp_volume

14/05/2010

1135.680054

6126400000

17/05/2010

1136.939941

5922920000

18/05/2010

1120.800049

6170840000

19/05/2010

1115.050049

6765800000

20/05/2010

1071.589966

8328570000

21/05/2010

1087.689941

5452130000

</details>


[↑ Back to the source list](#source-documents)

---

<a name="source-13"></a>

## sse_index.csv

<small>File type: CSV · Reader pages 91–91 · [View source PDF](PDF%20Slides.pdf#page=91)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

> Data preview (up to six records and twelve columns); the full CSV remains in the original files.

date

sse_adj_close

sse_volume

14/05/2010

2696.628906

73400

17/05/2010

2559.930908

82600

18/05/2010

2594.782959

82800

19/05/2010

2587.806885

71400

20/05/2010

2555.939941

66400

21/05/2010

2583.521973

83800

</details>


[↑ Back to the source list](#source-documents)

---

