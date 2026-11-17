# Lecture 8 - Group Assignment on Risk Analysis

**Airline overbooking decisions**

[← All chapters](README.md) · [Original PDF](PDF%20Slides.pdf#page=495)

## Overview

- An airline overbooking model with no-show uncertainty.
- Comparison of policies using sensitivity analysis and simulation.
- Related workbook preview and assignment prompts.

## Source documents

1. [Eagle LHR-JFK.pdf](#source-1) — PDF, reader page 496
2. [Eagle LHR-JFK.xlsx](#source-2) — XLSX, reader page 503

---

<a name="source-1"></a>

## Eagle LHR-JFK.pdf

<small>File type: PDF · Reader pages 496–502 · [View source PDF](PDF%20Slides.pdf#page=496)</small>

<small>Source Page 1 of 8</small>

### Eagle Airlines

Eagle Airlines, after its successful purchases and operation of small aircraft in Australia, decided to enter the low-cost market offering flights on one of the busiest routes in the world, between London and New York. Judy looks at the figures on the sheet that lies in front of her. Mike, her supervisor who is in charge of yield management at Eagle Airlines has just called her into his office, and told her that the booking policy which Eagle has been using for a couple of years now,

is urgently in need of --------.

Eagle Airlines

From its humble origins in Australia, Eagle now operates flights on several routes, especially on the route between London Heathrow and New York JFK. The sheet contains data on the route Heathrow – New York JFK, a successful business route that is generating more revenues than any other route in Eagle’s portfolio. Each day, there are 4 flights from London Heathrow to New York JFK using a

Boeing 777-300, which can carry up to 500 passengers, 400 in economy class and 100 in business class. The ticket price is £450 in economy class and £1450 in business class. In contrast with other airlines who use different economy fares with different types of restrictions (e.g. advance purchase, maximum stay, Saturday/Sunday night included, etc..), Eagle has always chosen for a

transparent pricing policy,

meaning one single business class fare and one single economy fare.

A problem with this route, and also with the other routes, is that often, people who have made a reservation, do not show up for their flight. Eagle’s policy is that both economy and business class

passengers can do so without incurring a penalty.

This case is intended to be used as a basis for class discussion, rather than to illustrate either effective or ineffective handling of an administrative situation. All names of individuals and companies are fictitious.
<small>Source Page 2 of 8</small>

In order to cope with no-shows, Eagle uses an overbooking policy in order to make sure that the plane does not fly with too many empty seats. Since the incremental cost of carrying an extra passenger on a plane is negligible, an empty seat represents a loss, which is approximately equal to the ticket price.

However, this overbooking policy sometimes leads to more passengers showing up than can actually get on the plane, resulting in ‘bumped’ passengers, who are scheduled on the next flight. Bumped customers are compensated by being offered a discount on a next flight, a meal allowance and a hotel room if the next flight leaves the next day. Moreover, bumping customers to a next flight

creates a loss of goodwill, in the sense that some customers will switch to a competing airline for their future flights. Although this cost is difficult to estimate, Eagle estimates the cost of bumping a passenger to be £150 for an economy class passenger, and £300 for a business class passenger (including meal and

lodging costs, and goodwill loss).

The London Heathrow – New York JFK route

Judy looks at the figures at the bottom of the sheet. The current policy of Eagle Airlines is to accept reservations up to 420 for economy class (i.e. 5% overbooking) and up to 120 for business class (i.e.

20% overbooking). The reason why overbooking in business class is much higher is because the noshow phenomenon is much more pronounced in business class, although the number of no-shows is

highly variable from flight to flight.

Judy is not sure why Mike chose exactly this route, perhaps because it is the most important route for Eagle, perhaps because it is one of the routes that are plagued by a high number of no-shows.

Whatever the reason, Mike wants her to come up with a revised booking policy for this route, and if things work out well, he would revise the booking policies for the other routes in a similar way.

On the sheet it also says that Eagle has not kept detailed records about the number of noshows on the Heathrow-JFK flight. However, there is a consensus that the number of no-shows in economy class is somewhere between 3% and 8%. For business class passengers, the noshow percentage is expected to be between 15% and 30%. Most people at Eagle estimate the economy no-shows to be 5%, and business no-shows to be 20%. Well, Judy thinks, the booking policy seems to make sense then?
<small>Source Page 3 of 8</small>

Judy looks at the back of the sheet. It contains what seems like a sheet out of spreadsheet package, with some calculations. She thinks it is probably the sheet that her predecessor used a couple of years

ago to come up with the booking policy that is currently operational.

Table 1. Spreadsheet

Background Information

Airlines were pioneers in the use of Risk Analysis and Monte Carlo Simulation and still make intensive use of these tools, with American Airlines generally considered to be the leader. An important problem that airlines are facing is no-shows, passengers who made a reservation for but who do not show up for their flights. This results in empty seats and (huge) losses for the airline,

considering that whether a passenger actually boards a plane or not, hardly makes any difference in the operating costs. This has led to the practice of flight overbooking, which means that more reservations are accepted on a flight than the actual capacity of the flight itself. This results in higher plane utilisation rates, at the expense of customers sometimes being ‘bumped’ to the

next flight if more passengers show up than can actually board the plane, which calls for some kind of compensation. American Airlines has estimated that the practice of overbooking flights alone adds $200 million per year to its bottom line!

<small>Source Page 4 of 8</small>

### Assignment You are asked to carry out an analysis in order to

**investigate whether the current overbooking**

policy can be improved upon You need to produce a three-page (excluding appendices) managerial report summarising your results, your interpretation of the results, conclusions and recommendations. For top marks, you need to address all questions. You can include graphs and outputs in a separate appendix, but note that any outputs that are not referred to in the main body of the report will not be read. Also note that an appendix is not necessary to gain full marks.

Please make sure to submit your assignments on Canvas.

- The Model Save the file Eagle LHR-JFK.xlsx from Canvas (Files… Course materials…

Session 8) to your own

computer. Start Excel, but first make sure that @Risk is not running. Using the template, build a model for the problem Eagle is faced with. Given the current overbooking policy, calculate the total costs resulting from empty seats and bumped customers. Assume that the flights are fully booked up to the accepted number of reservations (booking level), and use the most likely scenario for each of the parameters in the model (i.e. develop a base case model).

TIPS
– Save your model regularly, and save a backup version of your report once in a while!

– Make sure that only @Risk and Word (for your report) are open, close any other applications, because they will reduce your PC’s available memory and slow it down. Also use only one Excel workbook at a

time.

– Interpret your results, do not just report them.

– The spreadsheet model “Eagle.xls” has been pre-formatted. For instance, the cells where fares are entered are defined as currency cells (£). You can change the format of cells using Format\Cells.

– Think about what are the decisions in your model (variables under your control), the uncertainties (outside your control) and the objectives. I suggest using appropriate colours (green, red, blue) to highlight

them.

– The Max(value 1, value 2) function might be helpful. It returns the maximum of the two values. The

```r
Round(value, 0) rounds the value to the nearest integer number.
```

<small>Source Page 5 of 8</small>

### 2. Improving the overbooking policy

Based on the base-case model you developed, would you advocate a new overbooking policy to Eagle?

– Don’t use a simulation analysis just yet. Just use the base-case model to determine a new

As mentioned in the case, Eagle has not kept detailed records about the number of no-shows on the Heathrow-JFK flight. However, there is a consensus that the number of no-shows in economy class is somewhere between 3% and 8%. For business class passengers, the no-show percentage is expected

Using your own suggested overbooking policy, evaluate a pessimistic and optimistic scenario, and

– Sometimes, it is not easy to determine what constitutes a pessimistic and optimistic scenario.

Think about this carefully, and think about why a particular case constitutes a pessimistic or

BEFORE CONTINUING, CHECK WITH ROHIT OR THE TUTORS THAT YOUR MODEL IS CORRECT

What can you conclude from the results?

booking policy based on the most likely scenario.

– Do not use Data Tables. Try to find the best booking level by trial-and-error.
- Scenario Analysis

to be between 15% and 30%.

examine the impact on the total costs incurred. What can you conclude?

optimistic view.

TIPS

TIPS

<small>Source Page 6 of 8</small>

### 4. Sensitivity Analysis Again using your own suggested overbooking

**policy, examine the impact of a variation in the no-show**

TIPS

percentage on the costs for both economy and business class more closely. You can do this using data

tables and graphs. What can you conclude?

– You can construct a one-way data table using the Data\Table command. Suppose you want to examine different values for the Economy no-show percentage. First, in an empty part of the spreadsheet, make a list with different values for the no-show percentage (in a column). In the cell above and to the right of that column, enter “=B22” (or enter “=”, click on cell B22 and press [enter]).

Then, select the range consisting of the values and the column to the right of that, including the cells above. Select Data\Table. In Column input cell, refer to the cell where the data table values need to be substituted into the model. Press [OK], and the data table will be

completed.

– Based on a data table, a graph can be constructed as follows: Select Insert\Chart\Line. Press [Next] and specify the data range by selecting, with your mouse, the column of the data table containing the results (except the first value). Select Series in Columns. Select the Series tab on top of the window, enter “Costs” in Name, and in Category (X) axis labels, select (using your

mouse), the first column of values (without the label on top).

– You can also construct a two-way data table using the Data\Table command. Suppose you want to examine different values for Economy and Business no-show percentages simultaneously.

First, in an empty part of the spreadsheet, make a column with a list of different values of Economy no-show percentage; for instance, in cells G11:G15. Then, in the cell above and to the right of that column, make a row with a list with different values for Business no-show percentage; for instance, from H10:M10. Then, in cell G10 enter “=B22” (or enter “=”, click on cell B22 and press
[enter]). Then, select the whole range of cells (G10:M15) and select Data\Table. In Column input cell, refer to the cell where the Economy no-show percentages need to be substituted into the model. Finally, in Row input cell, refer to the cell where the Business no-show percentages need to be substituted into the model. Press [OK], and the data

table will be completed.

<small>Source Page 7 of 8</small>

### 5. Simulation

Evaluate the overbooking policy of Eagle (not your own) using a simulation analysis, taking into account the uncertainty in the percentage of no-shows in economy and business class. Recall that the number of no-shows in economy class is somewhere between 3% and 8%, although most people at Eagle estimate it to be at 5%, and that for business class passengers, the no-show percentage is

expected to be between 15% and 30%, and is thought to be 20%.

What is the average (total) cost of this overbooking policy? What does this mean?

In what range is the (total) cost probably going to be (90% confidence)?

What is the probability that the (total) cost will exceed £10,000?

Now evaluate the overbooking policy you recommended in Section 2 (using the same criteria).

Also evaluate the (total) costs of a policy of not overbooking at all, a practice that is employed by some

airlines to guarantee a seat to a customer who has reserved in advance.

Is the policy you recommended better than the other policies? Why?

Will your policy be the best on every individual flight? On most flights?

TIPS

– Before using the automated @Risk simulation tool, simulate the model set-by-step by pressing the [F9]-key. To do this, clock on the Recalculation icon shown below. This will enable simulating

one iteration at a time by pressing the [F9]-key.

– If the simulation is very slow, decrease the number of iterations in ‘Simulation Settings\Iterations\#Iterations’, or ask Rohit or the tutors to come and have a look.

– You can copy the model (the two columns with the economy and business model), making it possible to perform a simulation with different overbooking policies at the same time.

Alternatively, you can use the Risksimtable function (see next page).
<small>Source Page 8 of 8</small>

### 6. Further improving the overbooking policy

TIPS

Try to further improve your recommended overbooking policy, by simulating different alternatives

and selecting the policy with the best results.

– The RiskSimtable function enables you to compare different policies without having to run a separate simulation for each policy. Suppose you want to run multiple simulations with different economy class booking levels, contained in cells X1 through X10. In the cell containing the Economy class booking level, enter “=Risksimtable(X1:X10)”, and in Simulation Settings, set

the number of Simulations equal to 10.

– If you now run a simulation, @Risk will simulate the model 10 times, each time with a different level of the Economy class booking level. The results can easily be compared in the @Risk results window. If you use several RiskSimtable functions simultaneously, @Risk will take the first values of each RiskSimtable function first, then the second values etc.

- Improving the model

If economy class is overbooked, but there are still empty seats in business class, economy class passengers can be upgraded to business class, leading to fewer bumped customers. Try to enhance your model to take this into account. Would you advise a different overbooking policy?

TIPS

– Using the [F9]-key, try to simulate a situation in which economy class passengers are bumped, while there is still some space in business class. Then think about how to enhance the model.

– Insert a new row called ‘Transferred Passengers’ below row ‘Bumped Passengers’.

– “Downgrading” overbooked business class passengers to economy class is usually not a viable

option.

– Think carefully about what the effect is of upgrading an economy passenger on the costs.


[↑ Back to the source list](#source-documents)

---

<a name="source-2"></a>

## Eagle LHR-JFK.xlsx

<small>File type: XLSX · Reader pages 503–503 · [View source PDF](PDF%20Slides.pdf#page=503)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

### Worksheet: Sheet1

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Eagle Airlines

Economy

Business

Capacity and Cost Data

Boeing 777-300 capacity

400

100

Fare

450

1450

Cost of bumping passenger

150

300

No-show %

0.05

0.2

Overbooking Policy

Booking Level (accepted reservations)

420

120

Passenger Data

Actual passengers showing up

Empty Seats

Bumped Passengers

Cost and Revenues

Lost Revenues

=(B14*B5)

=C14*C5

</details>


[↑ Back to the source list](#source-documents)

---

