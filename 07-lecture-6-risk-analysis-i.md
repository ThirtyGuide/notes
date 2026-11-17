# Lecture 6 - Risk Analysis I

**Spreadsheet-based risk analysis**

[← All chapters](README.md) · [Original PDF](PDF%20Slides.pdf#page=384)

## Overview

- Base cases, scenarios, sensitivity analysis and tornado diagrams.
- Monte Carlo simulation, uncertain inputs, correlations and interpretation of simulated outcomes.
- Eagle Airlines and Nova examples, including Excel and @RISK previews.

## Source documents

1. [Eagle Airlines.pdf](#source-1) — PDF, reader page 385
2. [Session Slides.pdf](#source-2) — PDF, reader page 388
3. [Workshop_Novaduct.pdf](#source-3) — PDF, reader page 403
4. [Eagle Airlines Template.xlsx](#source-4) — XLSX, reader page 411
5. [Eagle Airlines- Simulation.xlsx](#source-5) — XLSX, reader page 413
6. [Nova_Template.xlsx](#source-6) — XLSX, reader page 425
7. [Tornado_Diagram_Tutorial.xlsx](#source-7) — XLSX, reader page 428

---

<a name="source-1"></a>

## Eagle Airlines.pdf

<small>File type: PDF · Reader pages 385–387 · [View source PDF](PDF%20Slides.pdf#page=385)</small>

<small>Source Page 1 of 2</small>

### Eagle Airlines

Keith Russell, president of Eagle Airlines, a small airline operating in south-eastern Australia, had been considering expanding his operation and now the opportunity was available. An acquaintance had put him in contact with the president of a small airline in the west that was selling an aeroplane. Many aspects of the situation needed to be considered however, and Keith was having a

hard time sorting them out. The Company Eagle Airlines (“Eagle”) owned and operated three twin-engine aircraft. With this equipment, Eagle provided both charter flights and scheduled commuter service between several cities in eastern Australia (Melbourne, Sydney, Canberra, Adelaide, Hobart, Launceston and smaller communities in the area). Scheduled flights constituted approximately 60%

of Eagle’s flights, averaging about 2 hours of flying time and a distance of some 700 kilometres. The remaining 40% of flights were chartered. The mixture of charter flights and short scheduled flights had proved profitable, and Keith felt that he had found a niche for his company. However, he was aching to increase the level of service, especially in the area of charter flights, but

this was impossible without more aircraft. The Opportunity A Piper Chieftain was for sale at a price of $600,000 (Australian Dollar). This twin-engine aeroplane (see Exhibit 1) had been maintained according to the regulations and safety standards of the Civil Aviation Safety Authority (CASA), and the engines were in a good condition. One would easily get five years of normal use out of

the aeroplane. Furthermore, having been used by another small commercial charter service, the Piper Chieftain contained all the navigation and communication equipment that Eagle required. In the aeroplane, there are seats for 10 passengers and the pilot, plus room for baggage. Typical cruise speed is 200 nautical miles per hour, or 360 km/h. Operating cost were approximately $1,200 per

hour, including fuel, maintenance, and pilot salary. Annual fixed costs, including insurance, were estimated at $160,000. Based on his experience at Eagle, Keith knew that he could arrange charters for around $1,900 per hour, or charge a rate of approximately $240 per person per hour on scheduled flights. He expected on average that the scheduled flights would be 60% full. He hoped to be

able to fly the aeroplane for up to 1,000 hours per year.

Exhibit 1. The Piper Chieftain

This case is based on Clemen and Reilly, Making Hard Decisions, Duxbury.
spreadsheet, or transmitted in any form or by any means – electronic, mechanical, photocopying, recording, or otherwise– without the permission of .

<small>Source Page 2 of 2</small>

Keith would fund the purchase out of the cash surplus of Eagle Airlines, and tax relief is available for the depreciation of the aeroplane over 5 years. Profits resulting from the operation of the aeroplane would be taxed at the normal corporate tax rate of 33%. The after-tax discount rate employed by Eagle Airlines to evaluate projects is 15%. The Analysis As Keith pondered this

information, he realised that many of the numbers that he was using were estimates. Actually, there seemed to be a lot of uncertainty in most of the assumptions he made about his business, and he realised that these uncertainties may have a significant impact on the decision whether or not to purchase the new aeroplane. He therefore decided to investigate this a little further. Although

the new aeroplane will certainly be operational for 5 more years, there is a chance that it can be used for one or two years more. However, given his experience in the past, Keith was not willing to take this risk, and only considered buying the Piper Chieftain if it could be profitable in 5 years. In the past, scheduled flights accounted for 60% of Eagle’s flights. Keith believed that

this might very well change however. Although 60% was still his best estimate of the future situation, the proportion may decrease to 40% or increase to 70%. Operating costs were fairly easy to predict, although they may vary a little. Keith estimated that his best guess of $1,200 could be wrong by $50 in either direction, mainly depending on fuel prices. Ticket and charter prices were

partly under Keith’s control, but were highly influenced by competitors’ moves. Especially the charter prices were under high competitive pressures, resulting in Keith more or less matching the prices set by his major competitors. This resulted in a charter price in the range between $1,600 to $2,200 per hour. Keith had slightly more control over the ticket price per hour for scheduled

flights, which would probably have to be around $240 per person, but could range up to extremes of $200 or $300, depending on market conditions. According to Keith, a delicate point was the utilisation of the scheduled flights, which was currently around 60%, and Keith saw no reason why that would change. However, he had experienced some variability in utilisation rates in the past,

which he also expected to be there in the future. He therefore took into account that utilisation rates may turn out to be different, and range from lows of 50% to highs of 70%. However, the aeroplane utilisation rate will in part depend on the actual ticket price. A related issue was the total number of flight hours, driving the revenues. Keith hoped to be able to fly the aeroplane for
up to 1,000 hours per year, but realised that 800 might be more realistic. The total number of flight hours depends mainly on the state of the economy. If things get really bad, 700 hours per year was a possibility, although remote, according to Keith. Keith was wondering how he should he assess the profits resulting from the purchase of the aeroplane, and incorporate all of the

uncertainties involved in the decision. Two questions keep playing up in his mind: Is the Piper Chieftain worth buying? and What are the major risks involved? Questions

- Do you think Keith Russell should buy the Piper Chieftain?

- Think about the uncertainties involved when buying the aeroplane, what the major

factors are

that may have a severe impact on profitability, and how these factors influence profitability and the decision whether or not to buy the aeroplane.

- Optional: Try to build a spreadsheet with a model to analyse the profitability of the in‐

vestment.

A template “Eagle.xls” is available on Canvas.


[↑ Back to the source list](#source-documents)

---

<a name="source-2"></a>

## Session Slides.pdf

<small>File type: PDF · Reader pages 388–402 · [View source PDF](PDF%20Slides.pdf#page=388)</small>

<small>Source Page 1 of 54</small>

### Risk Analysis I

CA09

Session 6

Rohit Mattu

<small>Source Page 2 of 54</small>

Historical data and forecasting tools help us predict future outcomes.

Our decision must also account for what happens if those estimates are imprecise.

<small>Source Page 3 of 54</small>

### About me

- Postdoctoral Research Fellow at (September 2026–present).

- PhD in Management Information Systems, IIM Calcutta (2021–2026).

Research

- How digital technologies contribute to sustainable development in emerging contexts.

- Digital infrastructure investments, public-sector digital reforms, and AI-enabled solu‐

tions.

Industry collaborations

Beyond research, I love playing squash, am passionate about cars. Also learning to play tennis.

<small>Source Page 4 of 54</small>
<small>Source Page 5 of 54</small>

How much to invest in the compute infrastructure?

Watch Dario (Anthropic’s CEO) discussing this challenge.

<small>Source Page 6 of 54</small>

What are the key characteristics of this decision that makes it distinct from other decisions?

What information would you need to make this important decision for Anthropic?

Think of yourself in Dario’s shoes.

<small>Source Page 7 of 54</small>

### Inputs to the decision

- Future demand / Prices and revenue

- Computing and other costs

- Timing of payments and receipts

Which of these are uncertain?

What if our forecasts are wrong?

<small>Source Page 8 of 54</small>

BBC AI Decoded Video

<small>Source Page 9 of 54</small>

### The flaw of averages

An average can hide important risks

<small>Source Page 10 of 54</small>

### Russian Roulette
<small>Source Page 11 of 54</small>

Three consecutive loaded chambers

Scan to vote etc.ch/qEPD

Open live results

Spin once or before every shot

<small>Source Page 12 of 54</small>

### Analysis

- Imagine that the bullets are in cylinders 1, 2, and 3.

- Option 1: Spin once

- Shot 1: 3/6 (or 1/2) probability of surviving

- Shot 2: If after the first shot you are not killed, you hit cylinders 4, 5, or 6 in your first

shot. That means the second shot will be at cylinders 5, 6, or 1. The three possibilities are equally likely, and exactly one of them (cylinder 1) has a bullet, so your chance of survival is 2/3.

- Shot 3: If after the first two shots you are not killed, you got cylinders 4-5, or 5-6. That

means that if you don’t spin, the third shot will be at cylinders 6 or 1. This means your chance of survival is ½.

- Putting it all together, the probability of survival is 1/2 * 2/3 * 1/2 = 1/6 or about 16.7%

- Option 2: Spin revolver every time

- In each case, you have 3/6, or 1/2 probability of surviving

- Putting it all together, the probability of survival is 1/2 * 1/2 * 1/2 = 1/8 or about 12.5%

<small>Source Page 13 of 54</small>

Why do people choose one over the other?

If I randomize and take a chance, I will always have half of the chance that there will be bullet.

<small>Source Page 14 of 54</small>

### Why do we need Risk Analysis?

- Naïve decision making ignores uncertainties and based on a single view of the future

- Single point forecasts are dangerous

- Risk analysis: process to help you take calculated risks
- Derive bounds for the range of possible outcomes

- Better perception of risks and their interaction

- Overall reduction of risk exposure through hedging

<small>Source Page 15 of 54</small>

### Process of Decision Making

- Structuring a problem allows dealing with it systematically

- Objectives

- Alternatives

- Consequences

- What is the likelihood and impact of risks associated with your decision?

Objectives, alternatives and consequences

<small>Source Page 16 of 54</small>

### Eagle Airlines

<small>Source Page 17 of 54</small>

- Small regional airline in south-eastern Australia: scheduled & chartered flights

- Opportunity for Expansion - Piper Chieftain for sale @ $600,000

- 5 years

- 10 passengers

- operating costs $1,200/hour

- annual fixed costs: $160,000

- Financial Data

- Charters: $1,900/hour, 40% of Eagle’s flights

- Scheduled flights: $240/hour, 60% load factor (utilization)

- 800 flight hours/year

- corporate tax rate: 33%

- Cost of capital: 15%

Piper Chieftain
<small>Source Page 18 of 54</small>

### Base Case Model

- Open “Eagle AirlinesSimulation.xlsx”, go to “Template” Tab.

- Fill out the Profit & Loss table and Cash Flow table using formulas.

- Use Base Value for computation.

Eagle Airlines base-case spreadsheet

<small>Source Page 19 of 54</small>

### Scenario Analysis

<small>Source Page 20 of 54</small>

### Scenario Analysis

- “Scenarios are discrete internally consistent views of how the world will look in the fu‐

ture, which can be selected to bound the possible range of outcomes that might occur.”

- Michael Porter in Competitive Strategy

Alternative future scenarios

- “Shell flavour” of scenarios

- Scenarios should present ------- conditions for the business. The future will of course be

different from all of these views/scenarios, but if the company is prepared to cope with any of them, it will be able to cope with the real world.

<small>Source Page 21 of 54</small>

### Eagle Airlines - Scenario Analysis

- Three NPV Scenarios

- Pessimistic : -653,668

- Base: -64,782

- Optimistic: 1,374,419

Eagle Airlines scenario spreadsheet
<small>Source Page 22 of 54</small>

<small>Source Page 23 of 54</small>

“What will our economic future look like?”

“We don’t know yet how AI will reshape the economy.”

anthropic.com/institute/econ-scenarios

<small>Source Page 24 of 54</small>

### Sensitivity Analysis

<small>Source Page 25 of 54</small>

### Sensitivity Analysis

- Explore robustness of results to variations in model parameters

- Identify variables to which results are particularly sensitive and those to which they

are relatively insensitive

- Gain an indication into range over which results might vary, thus assessing the risks

- One- and two-way sensitivity analysis

- Tornado diagrams

<small>Source Page 26 of 54</small>

### What-if Analysis: One Way Sensitivity

- What-if load factor (or capacity utilisation) of scheduled flights is, e.g., 65%

- Sensitivity Analysis using Data Table (Data. . . What-If Analysis. . . Data Table)

- Break-Even Analysis using Solver or Goal Seek, utilisation = 62.5%

Excel What-If Analysis menu

NPV versus load factor
<small>Source Page 27 of 54</small>

### What-if Analysis: Two Way Sensitivity

- What-if capacity = 65% and ticket price = 220

<small>Source Page 28 of 54</small>

### Tornado Diagrams

- Help us identify the impact of each uncertain parameter.

- Change one parameter at a time from its optimistic to its pessimistic value while

keeping the remaining parameters at their base value.

NPV ranges for individual risk factors

<small>Source Page 29 of 54</small>

### Tornado Diagrams

- Helps us determine visually the main uncertainty drivers.

Sensitivity of NPV to uncertain inputs

<small>Source Page 30 of 54</small>

### Let’s Reflect

What are we trying to achieve? Why will be not able to achieve using existing methods?

<small>Source Page 31 of 54</small>

### Simulations

<small>Source Page 32 of 54</small>
<small>Source Page 33 of 54</small>

### Introduction to Simulation

- A simulation model is a computer model that explicitly incorporates uncertainty in one

or more input variables.

- When you run a simulation, you allow these random input variables to take on various

values, and you keep track of any resulting output variables of interest.

- The fundamental advantage of a simulation model is that it provides an entire

distribution of results, not simply a single bottom-line result.

- Each different set of values for the uncertain quantities can be considered a scenario.

<small>Source Page 34 of 54</small>

### Monte-Carlo Simulation: Steps

- Step 1: Build a base case cash-flow model for the investment you are evaluating,

usually in a spreadsheet.

- Step 2: Model the uncertainty about the main inputs of the model using probability dis‐

tributions.

- Step 3: Specify the relationships between input variables through regression or

correlation coefficients.

- Step 4: Run the simulation. The software package repetitively draws samples of all

random input parameters from their distributions and calculate the outputs.

- Step 5: The simulated outputs are analyzed and presented in a probability distribution

form.

<small>Source Page 35 of 54</small>

### Software Installation - Palisade Decision Tools

- 1. Windows users

Downloads

- Follow installation instructions for Palisade Decision Tools

- 2. Apporto Virtual Desktop

- Canvas course page. . . click on Apporto Virtual Desktop on the left-hand side

- You will be taken to a new tab; this load screen may take up to 10 minutes when

accessing for the 1st time

- You may also be asked to reconnect several times

Apporto in Canvas
<small>Source Page 36 of 54</small>

### Apporto Virtual Desktop

- Once loading is complete, you get a virtual desktop with many applications, including

@RISK

- Upload any files to the virtual desktop by clicking here

Apporto virtual desktop

<small>Source Page 37 of 54</small>

### @RISK: A Widely Used Excel Add-in for Risk Analysis

- Open @RISK, sign in using your email when prompted.

Examples of @RISK users

- And many others. . .

@RISK in Excel
<small>Source Page 38 of 54</small>

### Using @RISK for Excel

- @RISK supports many probability distributions, e.g.,

- RiskNormal(mean,SD)

- RiskTriang(minimum, most likely, maximum)

- RiskUniform(minimum, maximum)

- RiskDUniform({value 1, value 2,. . . , value n})

- RiskDiscrete({Event A, event B. . . event K},{ProbA, ProbB,. . . , ProbK})

- RiskCumul(min,max,{value list},{probability list})

- Select Output Cell(s), e.g. NPV on Eagle Airlines

- Run the simulation

- View Results

- Summary statistics

- Graphs

- Sensitivity Analysis

- Tutorial videos at http://www.palisade.com/videos/

<small>Source Page 39 of 54</small>

### @RISK for Excel toolbar

@RISK toolbar

- Define distributions for random variables

- Define the output or objective you want to keep track of, NPV in Eagle Airlines

- Set the number of iterations for the simulation

- Start simulation

- Go to summary window to explore the results

<small>Source Page 40 of 54</small>

### Define Distributions of Random Variables

- Specify values of distribution parameters

- Or, input manually, by typing =@RiskNormal(1200,20)

Defining a normal input distribution
<small>Source Page 41 of 54</small>

### Model Window

@RISK toolbar

@RISK model inputs

<small>Source Page 42 of 54</small>

### Modeling uncertainty in Eagle Airlines (1/3)

- “Keith hoped to be able to fly 1,000 hours per year but realized that 800 might be

more realistic. If things get really hard, 700 hours was a possibility, although remote”

- =RISKTRIANG(Min,MostLikely,Max)

- =RISKTRIANG(700, 800, 1000)

- Charter price per hour: competitive pressures resulted in a charter price in the range

between $1,600 and $2,200 per hour

Annual flight hours

- =RISKUNIFORM(Min, Max)

- =RISKUNIFORM(1600, 2200)

Charter price per hour

<small>Source Page 43 of 54</small>

### Modeling uncertainty in Eagle Airlines (2/3)

- Ticket price per hour for scheduled flights, which would probably have to be around

$240 per person, but could range up to extremes of $200 or $300, depending on market conditions.

- =RiskTriang(200,240,300)

- Utilisation of the scheduled flights, which was currently around 60%, may turn out to

be different, and range from lows of 50% to highs of 70%.

Scheduled ticket price

- =RiskTriang(0.5,0.60,0.7)

- However, the aeroplane utilisation rate will in part depend on the actual ticket price.

Scheduled-flight utilisation
<small>Source Page 44 of 54</small>

### Modeling uncertainty in Eagle Airlines (3/3)

- Although 60% was still Keith’s best estimate for the proportion of scheduled flights, the

proportion may decrease to 40% or increase to 70%

- =RiskTriang(0.4,0.6,0.7)

- “Keith’s best estimate for operating costs was $1200; however, this could be wrong by

$50 in either direction, mainly depending on fuel prices”

- =RISKNORMAL(Mean,SD)

- =RISKNORMAL(1200, 20)

Operating cost per hour

<small>Source Page 45 of 54</small>

### Correlated Input Variables

- Until now, all random numbers generated with @RISK functions have been

probabilistically independent.

- Sometimes, however, independence is unrealistic. In such cases, the random numbers

should be correlated in some way.

- As an example, you might expect load factor (utilisation) of an airplane to be

negatively correlated with ticket prices.

- @RISK enables you to build in this correlation between variables with the RISKCOR‐

RMAT function, or you can define correlations through the Model Window

- Alternatively, you could estimate a regression line between the two variables. You

sample for one of the variables and use the equation with random errors to generate the other one.

<small>Source Page 46 of 54</small>

### Specifying Correlation Matrices in @RISK

- Select ticket price and utilisation

- Right click and select “Correlate -> Edit Correlation Matrix”

- Enter correlation coefficient

Inputs linked to a correlation matrix

Ticket-price and utilisation correlation
<small>Source Page 47 of 54</small>

### Model Correlated Input Variables through Regression

Load-factor regression output

Ticket price and load factor

<small>Source Page 48 of 54</small>

### Model Correlated Input Variables through Regression

- The aeroplane utilisation rate will in part depend on the actual ticket price.

- Use Regression Model: Load Factor (Y) on ticket price (X)

- Load Factor = 1.094 – 0.002 * (ticket price) + error

- R^2 = 83%

- RSE = 0.02276 (2.28%) (zero mean, normally distributed)

- Load Factor = 1.094 – 0.002 * (ticket price) + RiskNormal(0, 0.02276)

- Use Correlations through @RISK

- Load factor and ticket price are negatively correlated

- Correlation coefficient = -0.911

Load-factor regression output

<small>Source Page 49 of 54</small>

### Browse Simulation Results - Summary

- 90% chance NPV will be between: [-226K, 336K]

Results controls

- Slide vertical lines to compute probabilities; by default you get the mid 90% interval

Central 90% of simulated NPVs

<small>Source Page 50 of 54</small>

### Simulation Results

- Expected NPV (mean) = $31.1K, SD = $178.6K

- May differ from result using expected values of parameters

- Range = [$-397K, $662K]
- Compare with scenario results [-654K, 1,374K]

- Central 90% of simulated NPVs: [-226K, 336K]

- Probability (NPV<0) = 47%

- Project’s VaR (5th percentile) = -226K

NPV distribution and summary statistics

- Q: Should we base the decision on the average NPV?

<small>Source Page 51 of 54</small>

What is the maximum amount you are willing to lose on this project?

<small>Source Page 52 of 54</small>

### Key takeaways

- A decision model describes a real situation by extracting the salient features that

affect decision-making.

- Risk consists of two parts: likelihood (chance of occurring) and impact. Risk analysis

constitutes of constructing and analyzing the likelihood and impact of a situation.

- You learned about the “flaw of averages”: that using average values to base decisions

on can be dangerous.

<small>Source Page 53 of 54</small>

### Key takeaways (continued)

- To avoid making dangerous decisions, you can do three things:

- Scenario Analysis: Optimistic/Most Likely/Pessimistic scenarios to get a sense of the

range of possible outcomes.

- Sensitivity Analysis: Sensitivity to outcomes (e.g. NPV) when we make small changes

to inputs.

- What if analysis refers to changing the value of an input one at a time

- One- and Two-way Sensitivity analysis allows you to obtain the full range of

sensitivities for one or two risk factors

- Tornado diagram identifies main uncertainty drivers.

- Simulation Analysis: Comprehensive picture of uncertain outcomes, with all uncertain‐

ties playing a role. Provide uncertainties as input distributions, and generate a distribution for output variable of interest (NPV/profit/cost). Can incorporate correlations of risk factors.
<small>Source Page 54 of 54</small>

### Thank you

Rohit Mattu


[↑ Back to the source list](#source-documents)

---

<a name="source-3"></a>

## Workshop_Novaduct.pdf

<small>File type: PDF · Reader pages 403–410 · [View source PDF](PDF%20Slides.pdf#page=403)</small>

<small>Source Page 1 of 14</small>

### Allowing for Risk in Spreadsheet Models A Tutorial on Risk Analysis with

### @Risk

- Novaduct New Product Appraisal A simple example of launching a new product is em‐

ployed to illustrate how risk analysis is undertaken with @Risk. The objective in Novaduct is to examine the robustness of decisions based on Net Present Value (NPV) analysis, when some of the assumptions change. First, the cash flows and resultant NPV are calculated in a small spreadsheet model, ‘Nova’.

Next, the uncertainty about certain key assumptions is modelled explicitly by deciding on suitable probability distributions. To start, the relevant details of the new product launch and the associated spreadsheet model are set out in the next paragraphs. 1.1 Details of Novaduct’s New Product Novaduct’s management is trying to decide whether or not to launch a new novelty product, which

is expected to have a market for the next five years. The following information about the product has been gathered:

- The expected market size is 8,000,000 units in the first year with 2% growth per

annum thereafter;

- A 15% market share is anticipated in the first year, growing by 0.3% per year after‐

wards;

- In the first year, the price is likely to be £7, growing by 6% annually thereafter;

- The expected variable cost per unit is £5 increasing by 3% per annum;

- Fixed costs are expected to start at £2,000,000 and to grow annually at 3% as well;

- An initial investment of £2,500,000 is planned. A discount rate of 15% is usually taken

in calculating the Net Present Value for projects of this kind.

in any form or by any means electronic, mechanical, photocopying, recording, or otherwise without the permission of .
<small>Source Page 2 of 14</small>

These figures represent the best (single figure) estimates for the product's future prospects in a growing market. This combination of estimates is referred to as the base case. Novaduct’s management requires two measures of profitability for the venture, the Present Value of the cash flows and the Rate of Return. A simple spreadsheet model can be built, (see ‘Nova’ in Figure 1 with the

cash flow modelled in £000s). As can be seen, the base case for Novaduct has an NPV of £1,312,000 and an Internal Rate of Return (IRR) of 30%. 1.2 Optimistic, Pessimistic & Base Case Estimates The estimates for the initial market size and market share are quite firm according to management, but there is uncertainty about the market share increase (currently 0.3%, in cell B17) and the

market growth (currently 102%, in cell B18). Optimistic, pessimistic and base case (most likely values) values for these parameters are set out in cells E17..G18 (see Figure 1). These can be used to determine the worst and best values for the NPV of the proposal (see cells E19..G19). However, it is extremely unlikely that all the worse (or best) circumstances will occur together.

Figure 1. ‘Nova’ spreadsheet model

<small>Source Page 3 of 14</small>

1.3 Uncertainty about Market Growth & Market Share Increase Further discussion about some of the assumptions in the estimates persuades management that more explicit modelling of uncertainty is required for the market growth and the market share increase. A more detailed analysis of the risks’ results in the following: Market growth is most likely to be a 2% increase but could range

from a 10% decrease to an 8% increase. Actually, a 10% decrease or an 8% increase are quite unlikely, but represent the extremes. It is decided that this situation can be modelled using a triangular distribution (a distribution for which the probability density function takes a triangular shape, the lowest and highest values determine the base of the triangle, the mode or most likely

value determines the highest point of the triangle). This form of distribution is quite plausible: the most likely values are around 2% but values as extreme as -10% and +8% are possible but not so likely to occur. The increase in the market share is more difficult to estimate. Management believes that basically, the market share increase can vary between –0.2% (a decrease) and 0.8%.

However, we have no idea which outcome is more likely. This situation can be modelled using a uniform distribution between -0.2% and 0.8%. This means that growth is equally likely to take any value in the range -0.2% to 0.8%. Armed with these assessed distributions, namely:

- Market Share Increase: Uniform on -0.2%, 0.8%

- Market Growth: Triangular on 90%, 102%, 108%, the entries in the cells B17 and B18

in the spreadsheet are amended using @Risk.
- Using @Risk on Novaduct’s Model 2.1 Getting Started Download the “Nova.xls” from

the forum to your personal H-drive (ensure that you have ample free capacity on your Hdrive). Then, from the Start menu choose Programs, Palisade Decision Tools, @Risk 5.5. This option starts Excel and then loads the @Risk spreadsheet add-in. The effect is that an @Risk menu is added to Excel.

Figure 2. The @Risk menu (the icons are explained in the appendix)

<small>Source Page 4 of 14</small>

the correct drive).

- Change the entries in B17 and B18 to hold distributions instead of values. Market

2.2 Adding Probabilistic Values with @Risk Next, the entries in the cells containing Market Share Increase and Market Growth information are changed into probability distributions. The steps are:

- Open the spreadsheet ‘Nova’ using File\Open (make sure that you are looking in

Share Increase is to be modelled as a uniform distribution; Market Share as a triangular distribution: - in B17, change MS Increase to =RiskUniform(E17,G17), or =RiskUniform(-0.002,0.008) - in B18, change MktGrowth to =RiskTriang(E18,F18,G18), or =RiskTriang(0.9,1.02,1.08) The default settings make that these @Risk distribution functions are displayed in the spreadsheet using their expected values (mean values, 0.3% and 100%).

- Save the file (using File\Save As) under the name ‘Novarisk’

4.

Choose the Simulation Settings button shown as under Simulation tab in @Risk menu to display a dialog box with the current simulation settings. Notice some of the current defaults, e.g. Number of Iterations equal to 100, Number of Simulations equal to 1. At the bottom of the window, different options are available for displaying values in cells with probability distributions. Static

Values means that the cell displays the mean of the distribution. This is the default display form. Try choosing Random Values (Monte Carlo) and press OK. Now instead of the mean values, actual sampling values are displayed in the distribution cells. Press the recalculation key [F9] a few times to see how the model simulates the model. Note that in order to choose the Random Values

(Monte Carlo) option you can also

simply click on the button under Simulation tab of @Risk Menu.

Alternatively, you can set the number of iterations from the shortcut button:

which is located on the same place.
<small>Source Page 5 of 14</small>

Figure 3. The Simulation Setting window

- Running your first Simulation The steps in a simulation run are:

- to select the output cells (for which results will be collected);

- to specify the simulation settings (how many iterations);

- to run the simulation;

- to view the results.

Most of these steps are initiated via the @Risk menu.

3.1 Selecting Output Cells

- Select the NPV in cell F13 and click the Add Output button under Model tab in

@Risk menu.

Add Output button

Similarly, select the IRR in cell F14, click the Add Output button again. Finally select the cell range C9..G9, which hold the cash flow values, and click the Add Output button. You will be asked to specify a name for this range: specify “Cash Flow”.

- To view the outputs selected, click on Model Window under Model tab in

@Risk menu.

<small>Source Page 6 of 14</small>

Model Window button

Clicking this button gives the @Risk’s Model Window, which displays Inputs and Outputs (see Figure 4). To see the input and output cells, click on their corresponding tabs, which are located on the top left side of the window. The outputs are the cells for which simulation results will be collected. The Inputs show cells that contain @Risk distribution functions. In addition, if each of the input rows is double-clicked, a new window is opened, which displays the detailed graph of the defined distribution for the respective input cell (see Figure 5).

Figure 4. The Model Window

Figure 4. The detailed graph of a cell’s input distribution

<small>Source Page 7 of 14</small>

3.2 Setting Simulation Settings
Click the Simulation Settings button shown as under Simulation tab in @Risk menu to display a dialog box with the current simulation settings. We have already looked at the current defaults, e.g. Number of Iterations equal to 100, Number of Simulations equal to 1. Leave the settings unchanged. We will experiment with different settings later. 3.3 Running the Simulation Click the Start Simulation button under Simulation tab in @Risk menu.

Start Simulation Button In each iteration, @Risk draws a new sample from each distribution and recalculates the spreadsheet contents. Values are collected for each selected output cell or range. When the simulation is complete (after 100 iterations), the summary results can be seen in the @Risk Results window. 3.4 Viewing the Results Graphically At the end of a simulation run, click the Summary button under Results tab in @Risk menu.

Summary button

At the left-hand side of the top of the window the tabs for input and output cells are displayed. Each tab contains the list of respective cells for inputs and outputs. In addition, the row of each cell (for both inputs and outputs) shows other helpful statistical information for the considered cell such as the distribution graph, minimum, mean and maximum values as well as the 90% range calculated for each of the considered input and output cells (see Figure 5). Now, we first explore the results by considering their generated distribution graphs.

<small>Source Page 8 of 14</small>

Figure 5. The @Risk Results Summary Window

- Right-click on the “NPV” output name as shown in the Results Window and from the

menu select Graph\Ascending Cumulative – Line. The graph window shown below is then displayed. The cumulative NPV distribution shows the probability of the NPV being less than or equal to any given value. For instance, you can see that the probability of negative NPV is roughly 16%. The graph also displays the expected NPV (mean), which in this case is approximately $912K. The pane on the right side of the graph displays important statistics about the results such as the mean and the standard deviation.

Figure 6. An output cell’s window As can be seen in Figure 6, the red band at the top of the graph displays (by default) a range including 90% of the observations, excluding the top and bottom 5%. You can change the range by dragging the vertical lines across the

<small>Source Page 9 of 14</small>

chart. You can also double-click on each of the left and right top white bands to enter your own values instead of the default values 5%. The default value on the left white band (i.e. 5%) indicates that the probability that the NPV is less than or equal to -389 is 5%. Similarly, the value on the top right white band (i.e. 5%) indicates that the probability of the NPV to be more than or equal to 2177 is 5%. 2. Right-click on the “IRR” output name in the right pane of the Results Window and select Graph\Probability Density. The following graph window is then displayed.
Figure 6. The Probability Density (histogram) of The IRR Outcomes: Determine the probability of the IRR being less than 15% (by dragging the lines across the chart or by using the Left X entry, it should be about 20%). 3.5 The Summary Graph @Risk can also display a summary graph for the results of a range of cells. The procedure is as follows: 1. Select the output cells C9-G9 and then

right click one of the selected outputs. Then select Summary Graph\Summary Trend. This will result in a graph similar to that shown below. This graph aggregates the main features of the probability densities (i.e., histograms) for each of the five cells C9-G9. The central line joins up the mean cash flow values. The inner band joins up the means plus/minus one standard deviation; the

outer band joins up the 5% and 95% percentiles for each of the five cells.

<small>Source Page 10 of 14</small>

Figure 7. The Summary Trend Graph Graphs can be exported to Excel by right-clicking on them and selecting the appropriate options. Similarly, simulation statistics can be copied into Excel. 3.6 Saving Simulation Statistics If you wish to save simulation results, select File\Save or File\Save As. The simulation results are saved together with the excel spreadsheet. 3.7 The number of

iterations Determining the required number of iterations (simulation runs) is quite difficult. However, the main principle is “The more, the better”. However, running many iterations often takes a lot of time. One way of determining the minimum number required is to successively increase the number of iterations until the results appear to be almost unchanged from one simulation to the

next. @Risk has a feature by which it monitors the convergence of results and automatically stops when a user defined convergence criterion is met. This feature can be activated from the Simulation Settings dialog box. In the Number of Iterations section, instead of typing the number of iterations, select Automatic from the drop-down list as in the figure below. Then rerun the

simulation and explore the results.

<small>Source Page 11 of 14</small>

Figure 8. Selecting ‘Automatic’ option for the number of iterations 3.8 Advanced Features This concludes the tutorial on @Risk. This elementary introduction does not cover some of the more advanced @Risk features. Mention should be made of @Risk's ability to handle relationships between inputs in which correlation plays a significant part, such as demand and price data and their

relationship. @Risk also allows for sensitivity analysis (determining which sources of uncertainty have the most severe impact on the outcome) and scenario analysis (identifying which situations contribute to or ensure a particular outcome).
<small>Source Page 12 of 14</small>

### Appendix: The @Risk Menu

Icon

Function Performed and Command Equivalent

Displays the Define Distribution pop-up window. Using this window, probability distributions can be assigned to values contained in the formula of the selected cell.

Adds the currently selected range of worksheet cells as a simulation output. A distribution of possible outcomes is generated for every output cell selected.

Provides a variety of custom functions that can be used in Excel formulas for defining probability distributions, returning simulation statistics to Excel and performing other modeling tasks.

Allows the samples of input probability distributions to be correlated. When the Define Correlations icon is clicked, a matrix is displayed, which includes a row and column for each probability distribution in the currently selected cells in Excel.

Specifies the input data to be fitted, its type, domain, and any filtering to be applied to the data.

Displays the Distribution Artist window where a curve to be used as a probability distribution can be drawn. This is useful for graphically assessing probabilities and then creating probability distributions from the graph. Distributions may be drawn as Probability Density (General) curves, histograms, cumulative curves or discrete distributions.

Displays current input and output cells along with all distribution functions entered in the worksheet in the Outputs and Inputs list.

Allows entry of the number of iterations and simulations, which will be executed, and specifies the type of values returned by @RISK distributions in normal Excel recalculations.

<small>Source Page 13 of 14</small>

Sets the types of values (Random or Static) by @Risk distribution function. In addition, each type it is clicked it runs the simulation once.

Automatically shows output graphs.

Automatically shows results summary windows.

Turns Demo mode on or off.

Turns updating of the open @Risk windows on or off.

Runs the simulation for the number of iterations specified.

Provides some advanced features for @Risk.

Shows the output distribution graph for the selected output cell.

Opens Summary Results window.
Filters values from simulation statistics calculations and graphs.

<small>Source Page 14 of 14</small>

Displays detailed statistics on simulation results, for output cells and inputs.

Displays data values, calculated for output cells and sampled input distributions.

Displays sensitivity analysis results for output cells. These results show the sensitivity of each output variable to its input variables.

Displays scenario analysis results for output cells.

Generates Excel reports.

Swaps @RISK functions in and out of cell formulas making it easy to give models to others who do not have @RISK.

Shows @Risk’s library.

Provides extra utilities for @Risk users.

Opens Help window.


[↑ Back to the source list](#source-documents)

---

<a name="source-4"></a>

## Eagle Airlines Template.xlsx

<small>File type: XLSX · Reader pages 411–412 · [View source PDF](PDF%20Slides.pdf#page=411)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

### Worksheet: Template

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (16 rows, 9 columns).

Number of Seats

Column 3 10

Uncertain Parameters Hours Flown

Base Value 800

Pessimistic 700

Optimistic 1000

Tax Rate

Column 3 0.33

Uncertain Parameters Charter Price/Hour

Base Value 1900

Pessimistic 1600

Optimistic 2200

Purchase Price

Column 3 600000

Uncertain Parameters Ticket Price/Hour

Base Value 240

Pessimistic 200

Optimistic 300

After tax discount rate

Column 3 0.15

Uncertain Parameters Utilisation of Scheduled flights

Base Value 0.6

Pessimistic 0.5

Optimistic 0.7
Fixed Cost

Column 3 160000

Uncertain Parameters Ratio of scheduled flights

Base Value 0.6

Pessimistic 0.4

Optimistic 0.7

Remaining life

Column 3 5

Uncertain Parameters Operating Cost/hour

Base Value 1200

Pessimistic 1250

Optimistic 1150

Profit & Loss

Income from Scheduled

Income from Chartered

Operating costs

Fixed Costs

Profit before tax

Capital allowance

Column 3 =+C4/C7

Taxable Profit

Tax

Profit after tax

</details>


[↑ Back to the source list](#source-documents)

---

<a name="source-5"></a>

## Eagle Airlines- Simulation.xlsx

<small>File type: XLSX · Reader pages 413–424 · [View source PDF](PDF%20Slides.pdf#page=413)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

### Worksheet: Template

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (16 rows, 9 columns).

Number of Seats

Column 3 10

Uncertain Parameters Hours Flown

Base Value 800

Tax Rate

Column 3 0.33

Uncertain Parameters Charter Price/Hour

Base Value 1900

Purchase Price

Column 3 600000

Uncertain Parameters Ticket Price/Hour

Base Value 240

After tax discount rate

Column 3 0.15

Uncertain Parameters Capacity of Sch. flights

Base Value 0.6

Fixed Cost

Column 3 160000

Uncertain Parameters Ratio of charter flights

Base Value 0.4
Remaining life

Column 3 5

Uncertain Parameters Operating Cost/hour

Base Value 1200

Profit & Loss

Income from Scheduled

Column 3 =C2*G2*G4*G5*(1-G6)

Income from Chartered

Column 3 =G3*G6*G2

Operating costs

Column 3 =G2*G7

Fixed Costs

Column 3 =C6

Profit before tax

Column 3 =C10+C11-C12-C13

Capital allowance

Column 3 =C4/C7

Taxable Profit

Column 3 =C14-C15

Tax

Column 3 =C16*C3
Profit after tax

Column 3 =C14-C17

### Worksheet: Solution

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (16 rows, 9 columns).

Number of Seats

Column 3 10

Uncertain Parameters Hours Flown

Base Value 800

Pessimistic 700

Optimistic 1000

Tax Rate

Column 3 0.33

Uncertain Parameters Charter Price/Hour

Base Value 1900

Pessimistic 1600

Optimistic 2200

Purchase Price

Column 3 600000

Uncertain Parameters Ticket Price/Hour

Base Value 240

Pessimistic 200

Optimistic 300

After tax discount rate

Column 3 0.15

Uncertain Parameters Utilisation of Scheduled flights

Base Value 0.6

Pessimistic 0.5

Optimistic 0.7
Fixed Cost

Column 3 160000

Uncertain Parameters Ratio of scheduled flights

Base Value 0.6

Pessimistic 0.4

Optimistic 0.7

Remaining life

Column 3 5

Uncertain Parameters Operating Cost/hour

Base Value 1200

Pessimistic 1250

Optimistic 1150

Profit & Loss

Uncertain Parameters Profit & Loss

Income from Scheduled

Column 3 =+G2*(G6)*G4*$C$2*G5

Uncertain Parameters Income from Scheduled

Base Value =C10

Pessimistic =+H2*(H6)*H4*$C$2*H5

Optimistic =+I2*(I6)*I4*$C$2*I5

Income from Chartered

Column 3 =+G2*(1-G6)*G3

Uncertain Parameters Income from Chartered

Base Value =C11

Pessimistic =+H2*(1-H6)*H3

Optimistic =+I2*(1-I6)*I3

Operating costs

Column 3 =-G2*G7

Uncertain Parameters Operating costs

Base Value =C12

Pessimistic =-H2*H7

Optimistic =-I2*I7
Fixed Costs

Column 3 =-$C$6

Uncertain Parameters Fixed Costs

Base Value =C13

Pessimistic =-$C$6

Optimistic =-$C$6

Profit before tax

Column 3 =+C10+C11+C12+C13

Uncertain Parameters Profit before tax

Base Value =C14

Pessimistic =+H10+H11+H12+H13

Optimistic =+I10+I11+I12+I13

Capital allowance

Column 3 =$C$4/$C$7

Uncertain Parameters Capital allowance

Base Value =C15

Pessimistic =$C$4/$C$7

Optimistic =$C$4/$C$7

Taxable Profit

Column 3 =+C14-C15

Uncertain Parameters Taxable Profit

Base Value =C16

Pessimistic =+H14-H15

Optimistic =+I14-I15

Tax

Column 3 =+C16*$C$3

Uncertain Parameters Tax

Base Value =C17

Pessimistic =+H16*$C$3

Optimistic =+I16*$C$3
Profit after tax

Column 3 =+C14-C17

Uncertain Parameters Profit after tax

Base Value =C18

Pessimistic =+H14-H17

Optimistic =+I14-I17

### Worksheet: SensitivityAnalysis

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (13 rows, 9 columns).

Number of Seats

Column 3 10

Tax Rate

Column 3 0.33

Column 7 Cash Flows

Purchase Price

Column 3 600000

Column 7 Year

Column 8 0

Column 9 1

After tax discount rate

Column 3 0.15

Column 7 CF

Column 8 -600000

Column 9 =C29

Fixed Cost

Column 3 160000

Column 7 NPV

Column 8 =NPV(rate,I5:M5)+H5
Remaining life

Column 3 5

Column 7 IRR

Column 8 =IRR(H5:M5)

Uncertain Parameters

Column 3 Base Value

Column 4 Pessimistic

Column 5 Optimistic

Column 8 =H6

Hours Flown

Column 3 800

Column 4 700

Column 5 1000

Column 7 0.5

Column 8 <openpyxl.worksheet.formula.DataTableFormula object at 0x7f475e80efd0>

Charter Price/Hour

Column 3 1900

Column 4 1600

Column 5 2200

Column 7 0.55

Column 8 -194147.87797356345

Ticket Price/Hour

Column 3 240

Column 4 200

Column 5 300

Column 7 0.6

Column 8 -64781.50843110739

Capacity of Sch. flights

Column 3 0.6

Column 4 0.5

Column 5 0.7

Column 7 0.65

Column 8 64584.86111134861
Ratio of Scheduled flights

Column 3 0.6

Column 4 0.4

Column 5 0.7

Column 7 0.7

Column 8 193951.23065380473

Operating Cost/hour

Column 3 1200

Column 4 1250

Column 5 1150

472d66193a4c1a68a4c963b3c21 23dd70|1|61679| fd1ce9d370bd35c40dcb25e1eb1 cfc90

d3eaeb2bd5d52be4a5e1f255652 cc070_x0004__x0005_ÐÏ_x0011_à ¡±_x001A_á_x0004__x0004__x000 4__x0004__x0004__x0004__x0004 __x0004__x0004__x0004__x0004__ x0004__x0004__x0004__x0004__x 0004_>_

67f8c93a246242bb28fd171724c d5cc4_x0001__x0004_îà>ÊuÎà? _x000E_mò¹÷à?9l;^xÃå? Ùß_x000F_\cbâ?¸ª¯hã?«±mXGeâ? Çm0ç-ä?_x001A_Ö_x0012_ÀÃ±å? _x000B_!V³ã?n°1ÂMá?_x0013_ ´q(tá?`$Ï_x0018_

Table displayed as labelled records for readability (7 rows, 9 columns).

Serialization Major Version

8.14.0 4

Serialization Minor Version

8.14.0 0

Browse Record

8.14.0 Display Mode

Column 3 Sens Graph Type

Column 4 Cond Sens Settings

Column 5 Scenario Settings

Column 6 Selected Scenario

=ModelRef('Monte Carlo'!$K$7,2,0,0)

8.14.0 0

Column 3 3

Column 6
=ModelRef('Monte Carlo'!$K$19,1,0,0)

8.14.0 0

Column 3 3

Column 6 0

Distribution Record

Column 3 Reserved

Column 4 Record Count

Column 5 Inputs

='Monte Carlo'!$K$7

Column 4 1

Column 5 2_x0001_19_x0001_0_x0001_RiskNormal(1200,20)

Column 6 0

Column 7 GF1_rK0qDwEAEwDUAAwjACcAPABkAHgAeQCHAJUArg DQAMoAKwD// wAAAAAAAAEEAAAAAAdHZW5lcmFsAAAAASJPcGVyY XRpbmcgQ29zdC9ob3VyIC8gRGlzdHJpYnV0aW9uAQA BARAAAgABClN0YXRpc3RpY3MDAQEA/ wEBAQEBAAEBAQAE

Column 8 Reserved

Column 9 0

### Worksheet: Monte Carlo

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (16 rows, 9 columns).

Number of Seats

Column 3 10

Uncertain Parameters Hours Flown

Base Value 800

Pessimistic 700

Optimistic 1000

Tax Rate

Column 3 0.33

Uncertain Parameters Charter Price/Hour

Base Value 1900

Pessimistic 1600

Optimistic
Purchase Price

Column 3 600000

Uncertain Parameters Ticket Price/Hour

Base Value 240

Pessimistic 200

Optimistic 300

After tax discount rate

Column 3 0.15

Uncertain Parameters Utilisation of Scheduled flights

Base Value 0.6

Pessimistic 0.5

Optimistic 0.7

Fixed Cost

Column 3 160000

Uncertain Parameters Ratio of scheduled flights

Base Value 0.6

Pessimistic 0.4

Optimistic 0.7

Remaining life

Column 3 5

Uncertain Parameters Operating Cost/hour

Base Value 1200

Pessimistic 1250

Optimistic 1150

Profit & Loss

Uncertain Parameters Profit & Loss

Income from Scheduled

Column 3 =+G2*(G6)*G4*$C$2*G5

Uncertain Parameters Income from Scheduled

Base Value =C10

Pessimistic =+H2*(H6)*H4*$C$2*H5

Optimistic =+I2*(I6)*I4*$C$2*I5
Income from Chartered

Column 3 =+G2*(1-G6)*G3

Uncertain Parameters Income from Chartered

Base Value =C11

Pessimistic =+H2*(1-H6)*H3

Optimistic =+I2*(1-I6)*I3

Operating costs

Column 3 =-G2*G7

Uncertain Parameters Operating costs

Base Value =C12

Pessimistic =-H2*H7

Optimistic =-I2*I7

Fixed Costs

Column 3 =-$C$6

Uncertain Parameters Fixed Costs

Base Value =C13

Pessimistic =-$C$6

Optimistic =-$C$6

Profit before tax

Column 3 =+C10+C11+C12+C13

Uncertain Parameters Profit before tax

Base Value =C14

Pessimistic =+H10+H11+H12+H13

Optimistic =+I10+I11+I12+I13

Capital allowance

Column 3 =$C$4/$C$7

Uncertain Parameters Capital allowance

Base Value =C15

Pessimistic =$C$4/$C$7

Optimistic =$C$4/$C$7
Taxable Profit

Column 3 =+C14-C15

Uncertain Parameters Taxable Profit

Base Value =C16

Pessimistic =+H14-H15

Optimistic =+I14-I15

Tax

Column 3 =+C16*$C$3

Uncertain Parameters Tax

Base Value =C17

Pessimistic =+H16*$C$3

Optimistic =+I16*$C$3

Profit after tax

Column 3 =+C14-C17

Uncertain Parameters Profit after tax

Base Value =C18

Pessimistic =+H14-H17

Optimistic =+I14-I17

</details>


[↑ Back to the source list](#source-documents)

---

<a name="source-6"></a>

## Nova_Template.xlsx

<small>File type: XLSX · Reader pages 425–427 · [View source PDF](PDF%20Slides.pdf#page=425)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

### Worksheet: NOVA1

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (15 rows, 9 columns).

Row 1

Column 2 YEAR

Column 3 1

Column 4 2

Column 5 3

Column 6 4

Column 7 5

MARKET

Column 3 8000

Column 4 =C3*$B$18

Column 5 =D3*$B$18

Column 6 =E3*$B$18

Column 7 =F3*$B$18

PRICE

Column 3 7

Column 4 =C4*$C$15

Column 5 =D4*$C$15

Column 6 =E4*$C$15

Column 7 =F4*$C$15

V COST

Column 3 5

Column 4 =C5*$C$14

Column 5 =D5*$C$14

Column 6 =E5*$C$14

Column 7 =F5*$C$14
SALES (MS)

Column 3 =C3*B16

Column 4 =D3*($B$16+$B$17)

Column 5 =E3*($B$16+2*$B$17)

Column 6 =F3*($B$16+3*$B$17)

Column 7 =G3*($B$16+4*$B$17)

NET REVENUE

Column 3 =C6*(C4-C5)

Column 4 =D6*(D4-D5)

Column 5 =E6*(E4-E5)

Column 6 =F6*(F4-F5)

Column 7 =G6*(G4-G5)

FIXED COSTS

Column 3 -2000

Column 4 =C8*$C$14

Column 5 =D8*$C$14

Column 6 =E8*$C$14

Column 7 =F8*$C$14

CASHFLOW

Column 2 -2500

Column 3 =C7+C8

Column 4 =D7+D8

Column 5 =E7+E8

Column 6 =F7+F8

Column 7 =G7+G8

ASSUMPTIONS

Column 5 RESULTS

Discount Rate

Column 2 0.15

Column 5 NPV

Column 6 =B9+NPV(B13,C9:G9)
Prod Cost

Column 2 5

Column 3 1.03

Column 5 IRR

Column 6 =IRR(B9:G9,0.15)

Price

Column 2 7

Column 3 1.06

Market Share

Column 2 0.15

Column 4 BaseCase

Column 5 Pess

Column 6 ML

Column 7 Opt

MS Incr

Column 2 0.003

Column 4 MS Incr

Column 5 -0.002

Column 6 0.003

Column 7 0.008

MktGrowth

Column 2 1.02

Column 4 MktGrowth

Column 5 0.9

Column 6 1.02

Column 7 1.08

</details>


[↑ Back to the source list](#source-documents)

---

<a name="source-7"></a>

## Tornado_Diagram_Tutorial.xlsx

<small>File type: XLSX · Reader pages 428–429 · [View source PDF](PDF%20Slides.pdf#page=428)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

### Worksheet: Tornado

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (11 rows, 9 columns).

Purpose:

Column 2 To display visually the sensitivity of a given model result to changes in the model parameters

Step 1:

Column 2 Construct assumptions table, by assessing optimistic and pessimistic values for all uncertain parametes

Row 3

Column 2 Uncertain Parameters

Column 4 Base Value

Column 5 Pessimistic

Column 6 Optimistic

Row 4

Column 2 Hours Flown

Column 4 800

Column 5 700

Column 6 1000

Row 5

Column 2 Charter Price/Hour

Column 4 1900

Column 5 1600

Column 6 2200

Row 6

Column 2 Ticket Price/Hour

Column 4 240

Column 5

Column 6
Row 7

Column 2 Capacity of Sch. flights

Column 4 0.6

Column 5 0.5

Column 6 0.7

Row 8

Column 2 Ratio of charter flights

Column 4 0.4

Column 5 0.3

Column 6 0.6

Row 9

Column 2 Operating Cost/hour

Column 4 1200

Column 5 1150

Column 6 1250

Step 2:

Column 2 For each parameter in the assumptions table find the optimistic & pessimistic result values

Row 11

Column 2 This step is laborious. It can be carried out using what-ifs or better using data tables

</details>


[↑ Back to the source list](#source-documents)

---

