# Readable Course Notes

> A guided overview of the 19 sections in the uploaded files. These are organised notes based on the source material, not a replacement for the full source text or original diagrams.

[← Repository homepage](README.md) · [Original PDF](PDF%20Slides.pdf)

## Jump to a section

- [01. Pre-course Assignments](#part-1)
- [02. Lecture 1](#part-2)
- [03. Lecture 2](#part-3)
- [04. Lecture 3](#part-4)
- [05. Lecture 4](#part-5)
- [06. Lecture 5](#part-6)
- [07. Lecture 6 - Risk Analysis I](#part-7)
- [08. Lecture 7 - Risk Analysis II](#part-8)
- [09. Lecture 8 - Group Assignment on Risk Analysis](#part-9)
- [10. Lecture 9 - Intro Optimisation](#part-10)
- [11. Lecture 10](#part-11)
- [12. Workshop 1](#part-12)
- [13. Workshop 2](#part-13)
- [14. Workshop 3](#part-14)
- [15. Workshop 4](#part-15)
- [16. Workshop 5](#part-16)
- [17. Group Assignment 1](#part-17)
- [18. Sample Final ----](#part-18)
- [19. ---- Practice Questions (Part II)](#part-19)

---

<a name="part-1"></a>
## 01. Pre-course Assignments

The introductory materials distinguish **R** (the language used for statistical computing) from **RStudio** (the interface used to edit and run R code). The installation guide covers the RStudio console, script, environment and display panels, and explains the role of the CRAN software repository. It introduces R scripts, R Markdown and the idea of “knitting” code, output and narrative into a single report.

- **Working pattern:** Install R, then RStudio; install packages once, then load them when needed. The materials focus on the `tidyverse` collection for data manipulation and graphics.
- **Console versus script:** The console executes individual commands; script files save a reproducible sequence of commands; an R Markdown document can combine explanations, code and rendered output.
- **Typical first steps:** Open a script, load `tidyverse`, inspect data objects and use built-in help to explore functions.
- **Caution:** Version numbers and product interfaces in these particular source materials may change after publication. The attached files are the basis for this reader.

**Full material:** [Pre-course Assignments](01-pre-course-assignments.md)

---

<a name="part-2"></a>
## 02. Lecture 1

This section introduces **exploratory data analysis**: understanding the structure and quality of a dataset before drawing conclusions from it. It contrasts descriptive summaries with inference about a wider population, and uses the Dow Jones datasets for hands-on R examples.

- **Data structure:** Character, numeric, integer and logical values; vectors, matrices, arrays, data frames and tibbles; observations as rows and features as columns.
- **Before modelling:** Inspect variable types and dimensions, check missing values, remove duplicates, standardise names and correct dates or numbers imported as strings.
- **Tidy data:** Use a consistent one-variable-per-column and one-observation-per-row structure. Source exercises show the transition between wide and long formats.
- **Manipulation:** The source explains pipes and core dplyr verbs for choosing columns, filtering rows, sorting, creating variables, grouping, aggregating and joining.
- **Visual inspection:** Histograms, density charts, box plots and `ggplot2` graphics can reveal patterns a single summary number hides.
- **Worked context:** Dow Jones index values and constituent stocks, including examples of unclean files and R Markdown solutions.

**Full material:** [Lecture 1](02-lecture-1.md)

---

<a name="part-3"></a>
## 03. Lecture 2

The emphasis is on **uncertainty in samples and distributions**. The slides move from describing a probability distribution to estimating an unknown population quantity using a sample.

- **Distribution shape:** Compare central tendency, spread, skewness and tail behaviour. The material includes normal, standard normal and t-distributions.
- **Standardisation:** A z-score expresses an observation relative to a mean in units of standard deviation; the slides also discuss values in the tails and cumulative probabilities.
- **Sampling uncertainty:** A sample statistic changes from one random sample to another. The material distinguishes raw data standard deviation from the standard error of a sample statistic.
- **Central limit theorem:** The course illustrates why a sample mean can have an approximately normal sampling distribution under relevant conditions, even when raw observations are not normal.
- **Confidence intervals:** A point estimate is presented together with uncertainty around it. The source compares large- and smaller-sample approaches, interval width and the role of sample size.
- **Applications:** The materials include yield-curve data, z-score visualisations and R code for intervals and distribution calculations.

**Full material:** [Lecture 2](03-lecture-2.md)

---

<a name="part-4"></a>
## 04. Lecture 3

The material develops a structured way to evaluate a **claim about a population** using sample data. It covers equivalent perspectives based on confidence intervals, a standardised statistic and a p-value.

- **Start with the claim:** State a null hypothesis and an alternative clearly, including whether the direction matters.
- **Three decision perspectives:** Compare a claim with an interval, calculate a z- or t-statistic, or use a p-value against a chosen significance threshold.
- **Differences between groups:** The materials include comparisons of conversion rates and movie ratings, not only single-mean examples.
- **Errors:** Distinguish false positives (Type I) and false negatives (Type II), and recognise that changing the significance level changes the decision trade-off.
- **R calculations:** Worked examples illustrate manual reasoning as well as automated R functions, although some function names were already obscured in the supplied files.
- **Practical note:** Always match the approach to the question, the sample size, the quantity being compared and the source assumptions.

**Full material:** [Lecture 3](04-lecture-3.md)

---

<a name="part-5"></a>
## 05. Lecture 4

This section connects **correlation and simple linear regression**, emphasising that association alone does not establish causation. The slides use historical and business examples to illustrate the distinction.

- **Correlation:** Summarises the direction and strength of a linear association but can conceal curved relationships or outliers. The source references Anscombe’s quartet.
- **Causation:** The John Snow cholera example is used in discussing observational evidence, experiments and alternative explanations.
- **Simple regression:** Fit a line relating an outcome to one predictor using ordinary least squares; understand intercepts, slopes, fitted values and residuals.
- **Model evaluation:** Interpret R² and adjusted R², the residual standard error, estimated coefficient uncertainty and prediction intervals.
- **Diagnostics:** Check nonlinear residual patterns, unequal variance, serial dependence, atypical observations and Q–Q plots.
- **Worked examples:** Pub/crime patterns and used Prius prices support regression interpretation and diagnostics.

**Full material:** [Lecture 4](05-lecture-4.md)

---

<a name="part-6"></a>
## 06. Lecture 5

The source extends simple regression into **multiple-predictor and more flexible models**. It examines how specification choices can improve the usefulness of an estimated relationship.

- **Multiple regression:** Add predictors to account for more than one factor affecting the outcome; compare fitted models, not just individual coefficients.
- **Transformations:** A curved relationship may be represented by changing a variable, such as a squared or logarithmic term; the source provides toy datasets for this idea.
- **Interactions:** Permit the estimated effect of one predictor to vary with another predictor; car-price examples show the interpretation.
- **Qualitative inputs:** Use indicator variables for categories, seasons or other group membership, respecting the reference group.
- **Other extensions:** The lecture covers multicollinearity, lagged terms, event-oriented comparisons and a model selection checklist.
- **Practical coding:** The `.Rmd` source is generally a clearer reference for executable R than the accompanying HTML export, whose formatting has been fragmented.

**Full material:** [Lecture 5](06-lecture-5.md)

---

<a name="part-7"></a>
## 07. Lecture 6 - Risk Analysis I

This section shows how a spreadsheet model can move from **one assumed outcome** to a range of plausible outcomes. The Eagle Airlines case is central.

- **Base case:** Build a coherent spreadsheet around selected inputs before introducing uncertainty.
- **Scenario analysis:** Change several assumptions together to describe alternative futures.
- **Sensitivity analysis:** Change one input at a time, or two inputs together, to see which assumptions matter most. Tornado diagrams summarise relative influence.
- **Simulation:** Define uncertain input distributions and generate many possible model outcomes using Monte Carlo methods.
- **Dependence matters:** Inputs may be correlated; treating them as unrelated can produce misleading output distributions.
- **Tools and cases:** The materials walk through Excel and @RISK, Eagle Airlines, Nova and spreadsheet templates. Workbook previews do not carry every formula.

**Full material:** [Lecture 6 - Risk Analysis I](07-lecture-6-risk-analysis-i.md)

---

<a name="part-8"></a>
## 08. Lecture 7 - Risk Analysis II

The second risk-analysis section focuses on **building distributions and interpreting simulation results** for decisions about inventory, investment and cash.

- **Historical resampling:** Use observed outcomes to construct simulated inputs, and compare that technique with fitting parametric probability distributions.
- **Investment examples:** The source shows simulation work with market and short-term government-security series.
- **Demand uncertainty:** The retail production case illustrates how an operating decision may have several possible profits depending on demand.
- **Cash management:** The source develops minimal cash-balance decisions under uncertain inflows and outflows.
- **Dynatron:** This case compares a base model, sensitivity analysis and simulated outcomes to evaluate a business decision.
- **Interpretation:** Focus on the distribution of outcomes and decision consequences, not merely an average projection.

**Full material:** [Lecture 7 - Risk Analysis II](08-lecture-7-risk-analysis-ii.md)

---

<a name="part-9"></a>
## 09. Lecture 8 - Group Assignment on Risk Analysis

The airline case applies **simulation and sensitivity reasoning to seat overbooking**.

- **Decision:** The carrier must weigh the consequences of spare seats against the consequences of more ticket-holders turning up than available places.
- **Uncertain quantity:** The no-show proportion affects realised occupancy and the economics of a booking policy.
- **Requested work:** Consider the existing policy, propose alternatives, vary the no-show assumptions and use simulation to compare results.
- **Source limitation:** The accompanying spreadsheet preview is not the full operating model. The original workbook is needed to inspect its formulas.

**Full material:** [Lecture 8 - Group Assignment on Risk Analysis](09-lecture-8-group-assignment-on-risk-analysis.md)

---

<a name="part-10"></a>
## 10. Lecture 9 - Intro Optimisation

The central question is **how to choose the best feasible combination of decisions when resources are constrained**. Red Brand Canners and product-mix models illustrate the ideas.

- **Formulate the decision:** Identify decision variables, an objective to maximise or minimise, and the conditions that must be satisfied.
- **Linear programming:** Explore feasible combinations graphically and algebraically. The slides introduce slack variables and the simplex method.
- **Solver:** Translate the decision variables, objective cell and constraints into an Excel model, then review the output and any limits of the formulation.
- **Sensitivity:** Understand how the best solution responds to a change in a resource level or an input coefficient; shadow prices communicate the local value of relaxing a binding resource constraint.
- **Red Brand Canners:** The case compares different product uses for tomato grades and discusses resource values, contributions and sunk costs.
- **Practical caveat:** Financial results and Solver layouts often depend on figures embedded in the original visual pages; verify all numbers against the PDF.

**Full material:** [Lecture 9 - Intro Optimisation](10-lecture-9-intro-optimisation.md)

---

<a name="part-11"></a>
## 11. Lecture 10

This material covers **decision trees for classification**, using a subscriber-renewal example to show how repeated splits produce decision rules.

- **Features and outcome:** The teaching example uses region, plan type and viewing pattern to predict renewal or cancellation.
- **Build a tree:** Select a split, repeat within each subgroup and stop when a useful stopping rule is reached.
- **Split quality:** The slides calculate Gini impurity, and later compare entropy and information gain. A more useful split creates relatively purer child groups.
- **Generalisation:** A tree can fit its training observations well but perform poorly on new cases. Depth restrictions and other controls address overfitting.
- **Classification performance:** Confusion matrices organise correct and incorrect classifications; precision and recall highlight different error priorities.
- **Continuous features:** The source discusses choosing thresholds when a variable is numerical rather than categorical.

**Full material:** [Lecture 10](11-lecture-10.md)

---

<a name="part-12"></a>
## 12. Workshop 1

The exercises combine **R data preparation and graphical communication**.

- Reorganise drinks data into a tidy layout and create faceted histograms and density plots.
- Work with temperature-anomaly series and compare changes over time.
- Summarise aviation crash and fatality data with charts and group calculations.
- Compare the question files with the answer `.Rmd` files for the intended code and plotted outputs.
- The attached `Image1.png` reference is only represented as an inventory in the uploaded text PDF.

**Full material:** [Workshop 1](12-workshop-1.md)

---

<a name="part-13"></a>
## 13. Workshop 2

These worked materials reinforce **interval estimation** across different settings.

- Build and interpret confidence intervals for weather anomalies.
- Apply the same reasoning to stock-return examples.
- Compare intervals thoughtfully: they communicate uncertainty, not a guarantee about any single observation.
- The source includes pen-and-paper prompts, worked solutions and R Markdown code.
- A ticker-data preview is included but is not the complete CSV.

**Full material:** [Workshop 2](13-workshop-2.md)

---

<a name="part-14"></a>
## 14. Workshop 3

The focus is on **inference when comparing groups**, together with return calculations.

- Determine which quantities are being compared and what the relevant uncertainty measure represents.
- Follow both hand calculations and automated R approaches for differences between samples.
- Read the supplied solution documents beside the corresponding questions.
- Calculate and visualise stock risk/return profiles from market data.
- Some source function names are intentionally hyphenated and are not directly runnable.

**Full material:** [Workshop 3](14-workshop-3.md)

---

<a name="part-15"></a>
## 15. Workshop 4

This section puts **data manipulation and regression** into applied coding tasks.

- The carseats exercises focus on exploring and modelling a sales-related dataset.
- NHANES/BMI tasks practise transformations and model construction.
- SAT/GPA examples provide another relationship to explore and interpret.
- The question/answer files contain R code and regression discussion; use the `.Rmd` files for the clearer code layout.
- Results depend on the exact supplied dataset and the specification used.

**Full material:** [Workshop 4](15-workshop-4.md)

---

<a name="part-16"></a>
## 16. Workshop 5

The final workshop grouping contains **additional coding and regression problem sets**.

- Read the numbered question PDF alongside its answer file.
- Continue practising regression model interpretation and calculation.
- Check any visual graphs, equations or layouts in the original PDF if the transcribed text is incomplete.
- The source files are preserved as separate subsections in the full chapter.

**Full material:** [Workshop 5](16-workshop-5.md)

---

<a name="part-17"></a>
## 17. Group Assignment 1

The group project asks for **data analysis and communication using New York City rat-sighting reports**.

- **Prepare:** Load the city service-request data, clean variable names and handle missing-value markers.
- **Explore:** Produce informative descriptive charts and maps that highlight geographic or time-based patterns.
- **Model:** Use regression and comment on diagnostics, collinearity and whether the results support the conclusions.
- **Reproducibility:** The source emphasises understandable code, clear graphs and organised outputs.
- **Data caveat:** The uploaded files contain an inventory of the nested dataset, not the complete original archive.

**Full material:** [Group Assignment 1](17-group-assignment-1.md)

---

<a name="part-18"></a>
## 18. Sample Final ----

The supplied text edition identifies a multi-page question document and a solution file, but much of the source is **visual-only**.

- The rendered text here is not sufficient to reconstruct each problem or its diagrams accurately.
- Open the original PDF at the linked reader pages to inspect the question layouts.
- Do not infer missing numerical inputs or silently complete partially extracted problems.

**Full material:** [Sample Final ----](18-sample-final-questions.md)

---

<a name="part-19"></a>
## 19. ---- Practice Questions (Part II)

The final materials focus on **optimisation calculations and the interpretation of solutions**.

- The exercises involve resource constraints and a choice of decision-variable quantities.
- The solution files discuss optimisation and sensitivity concepts.
- A ferry example includes passenger, vehicle, demand, capacity and loading-time restrictions; it asks for an economically attractive mix.
- Where Solver figures or tables are supplied only as images, the full visual PDF is needed to check values and conclusions.

**Full material:** [---- Practice Questions (Part II)](19-questions-practice-questions-part-ii.md)

---

