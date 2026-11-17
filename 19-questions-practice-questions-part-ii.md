# ---- Practice Questions (Part II)

**Optimisation problem sets**

[← All chapters](README.md) · [Original PDF](PDF%20Slides.pdf#page=824)

## Overview

- Optimisation questions and worked solutions.
- Constraints, shadow prices and sensitivity-analysis considerations.
- A ferry-loading allocation example and its numeric restrictions.

## Source documents

1. [---- AUT23 optimisation- solution.pdf](#source-1) — PDF, reader page 825
2. [Optimisation Exercises Solutions.pdf](#source-2) — PDF, reader page 829
3. [Optimisation Exercises.pdf](#source-3) — PDF, reader page 831
4. [---- AUT23 optimisation.docx](#source-4) — DOCX, reader page 835

---

<a name="source-1"></a>

## ---- AUT23 optimisation- solution.pdf

<small>File type: PDF · Reader pages 825–828 · [View source PDF](PDF%20Slides.pdf#page=825)</small>

<small>Source Page 1 of 5</small>

### Optimization Exercise Solution

Type

Profit Margin (£)

Loading time (minutes)

A ferry service between Liverpool and Belfast can carry various categories of passengers. These together with their respective profit margin per trip and loading time, where appropriate, are listed below:

Foot Passengers

Car with driver and 3 passengers

0.25

Coach with driver and 49 passengers

Lorry with driver

The ferry can be loaded subject to the following conditions:

Total Passengers (plus driver) capacity should not exceed 1500 due to safety regulations.

Maximum number of coaches plus lorries is 25.

Maximum number of cars is 150 plus four for every lorry or coach space that is not used.

Vehicle loading time should be 1 hour maximum.

Market research indicates that maximum demand for foot passengers is 600.

The profit margins apply whether or not cars and coaches carry the full complement of passengers, but for safety purposes it must be assumed that they are always full.

Jean Farell, the marketing manager of the company and a graduate, has tried to use optimisation to find the optimal mix of passengers, cars, couches and lorries that the ferry can carry. She has developed the spreadsheet shown in Figure 2.1 and used Solver to find the mix that maximises the contribution to profit. Figure 2.3 shows the Solver specification and Figure 2.1 shows the Solver solution obtained. Figure 2.2 shows the formulas of the same model and Figure 2.4 shows the Solver sensitivity analysis.
<small>Source Page 2 of 5</small>

Figure 2.1: The ferry service model showing the optimal solution.

Figure 2.2: The ferry service model showing the formulas

<small>Source Page 3 of 5</small>

Figure2.3: The Solver Specification

Figure 3.4: The Solver sensitivity analysis.

!"#$"%F'()'FF*

!"#$% F'()*'( +H-'*."I' 0%%12$H%' 0%%12$H%' 3'%% 4$5' 6$%)' 317.

31'88"*"'#.

9#*:'$7' ;'*:'$7' +H+.II01233

789:5 -;< +H+: )2=3 --<;6

:6 L;:?6 -;7 +H+< )I2)@83

A-4;6 :55 -4;6 789:5 +H+6 BI==C83 7;L

-55 <6;4 ?6

)DN*F#"$NF*

!"#$% <=$(12 31#7.:$"#.

0%%12$H%' 0%%12$H%' 3'%% 4$5' 6$%)' >:"*' F?@?A<"(' 9#*:'$7' ;'*:'$7' +G+75 0DF"F(H"**'NI'#* 7655 -;4 7655

?76 +G+77 )D"JO'*("NL(FD##$'* 7;L

-6 789:5 -:;7 +G+7- MNO%'#(DP(J"#* 7:-;:

789:5 7?;? +G+7: !'O$JF'(FD"L$NI(F$O'

LQ;?

L;:;?6 +G+7< .DDF(H"**'NI'#*

-;<

?76

<small>Source Page 4 of 5</small>

a) What is the solution that maximises the profit contribution (objective function and optimal values of the variables) and which constraints are binding? [2 points]
The optimal loading mix results in a contribution to profit of £11,245. This is achieved by loading 600 passengers, 224.5 cars and 1.9 lorries. Clearly the fractional values for cars and lorries do not make sense. (See next question).

The binding constraints are the Total passenger, the Vehicle loading time and the Foot passengers constraints.

b) Jean understands that the fractional values in the solution do not make sense. Find a feasible integer solution by rounding the fractional values. You need to check that the solution you found satisfies all constrains. [3 points]

By rounding the results for cars and lorries you can produce the following solution. 600 passengers, 224 cars and 2 lorries. The rounded solution satisfies all constraints and therefore is feasible, but note that in general it may not be optimal.

c) How would you use Excel Solver to find the best integer solution? [5 points]

We need to add a constraint specifying that our decision variables are integer and resolve.

By default the Excel Solver will find a solution which is not guaranteed to be optimal, but will be within a tolerance from the optimal solution. This is controlled by a Solver option called “Integer optimality (%). By setting this option to zero, we can force the Solver to search for the true optimal solution, but this may increase the solving time. In that case we will no longer get the sensitivity analysis results.

<small>Source Page 5 of 5</small>

Answer the remaining questions based on the solution with fractional values shown in Figure 2.1 and using the Solver sensitivity analysis in Figure 2.4.

d) Interpret the reduced cost for the “Coach” variable. [5 points]

Adding one coach to the optimal ferry loading plan, at the expense of a number of cars and lorries, would reduce profits by £26.5. Another interpretation is that the profit margin of coaches would need to improve by £26.5 before it becomes optimal to include coaches in the optimal loading plan.

e) Evaluate the impact of increasing the limit on Foot Passengers from 600 to 700. [5 points]

The shadow price of the last constraint is 2.4. This means that for every extra foot passenger we allow on the ferry, profits go up by £2.4. The allowable increase is 715, so the increase from 600 to 700 is within the allowable range, for which the shadow price stays constant. So the impact on the profit contribution is an increase of (700-600)*2.4 = £240.

f) Discuss the effect of increasing the allowable loading time to:

i) 65 minutes

ii) 75 minutes.

[5 points]
From the dual price of the 4th constraint we see that for every extra minute of loading time we can increase profits by £98.7. This dual price holds for increases of up to 9.17 minutes (sensitivity analysis results). So increasing the allowed loading time to 65 minutes would add 5 * £98.7 = £493.5 to the profit contribution. The impact of an increase of 15 minutes cannot be assessed

using the solution of the base formulation. You would need to reformulate the problem changing the righthand side of the 4th constraint and resolving the problem. One thing you know is that the increase in profit will be at least 9.17 * £98.7.


[↑ Back to the source list](#source-documents)

---

<a name="source-2"></a>

## Optimisation Exercises Solutions.pdf

<small>File type: PDF · Reader pages 829–830 · [View source PDF](PDF%20Slides.pdf#page=829)</small>

<small>Source Page 1 of 2</small>

### Business Optimisation Exercises— Solutions

Exercise 1

(a) At which time segments there are more drivers than the minimum required numbers?

12:00-16:00, 16:00-20:00 (b) What would the impact be of having 3 more drivers available?

The shadow price for the constraint on the total number of drivers is €75 and the allowable increase infinity. So an extra 3 drivers with increase profit by 75 * 3 = €225. (c) Suppose that two drivers are sick and unavailable for work on a given day. What is the financial impact? The allowable decrease on the total number of drivers is 4, which greater than

- So the shadow price holds for a reduction of 2. Therefore, the decrease in profits is 2 *

75 = €150. (d) One of the 15 drivers who is available for the shift from 8pm to 4am, has been advised by his doctor not to work at nights. What is the effect on the profit contribution? There is no impact since the corresponding constraint (Shift20to04) is not binding and the shadow price is

- (e) Suppose that Euripides finds that the service is slipping during the period from

8pm to 8am. One approach would be to raise the minimum number of drivers on duty between 8pm and midnight. How would this affect profit? Profits will be reduced by €30, since the shadow price of the corresponding constraint is -30. (f) Alternatively, the minimum number on duty between midnight and

4am could be raised from 14 to 15. Which alternative is cheaper? In this case the drop in profits is €35, so this is more expensive. (g) Another alternative is to ensure that at least one driver starts work at 4am. (Currently no one starts at 4am). How would this affect profit?

The variable “04:00-08:00 Number of drivers”, which corresponds to the number of drivers that start work at 4am has currently a value of 0 (i.e. is not optimal), but (unusually) has a reduced cost of 0. This means that the penalty for introducing that variable to the optimal solution is zero, i.e. we can ensure that at least one driver starts work at 4am without reducing our profit.

<small>Source Page 2 of 2</small>

Exercise 2

(a) What is the optimal loan combination and the resulting revenue?

The optimal loan combination in €(000)s is Unsecured Loans
Furniture Loans

Automobile Loans

First Home Mortgages

(b) What is the average return on the amount lent? What is the marginal return (% return on an additional £1,000 of loan)? The return on the €1500,000 is 142,500 (from figure 3.1). Therefore the average return is 142.5/1500 = 0.095 or 9.5%. The marginal return can be obtained by the shadow price of the constraint on Total Investment. This shadow price (0.099) tells us that an extra

unit of investment (€1,000) would give us an increase in return of 0.099 (€000s) which corresponds to a 9.9% marginal return. (c) Would the optimal solution change if the return on Second Home Mortgages improves by 0.5%? Explain.

Currently the Annual return of Second hand Mortgages is 8%. At this rate it is not optimal to invest in these financial instruments. The reduced cost of this variable in figure 3.3 (-0.01) tells us that in order for this variable to become economic to invest the contribution (i.e. the annual return) needs to improve by 1%. An improvement of 0.5% is not enough and would have no impact.

(d) What would be the impact of increasing the limit on unsecured loans from 10% to 20%? Currently we are limiting the investment on Unsecured Loans to 150 (€000s) which is 10% of the overall investment. The shadow price of this constraint (0.03), shows that for every €1000 of increase in this limit the overall return of the portfolio increases by 0.03 (€000s) i.e. €30. The allowable

increase is 150 (€000s). So the shadow price holds for the increase of the limit from 10% to 20% of the overall investment which is €150,000. and the impact is 0.03 * 150 = 4.5 (€000s). (e) What would be the impact of reducing the minimum requirement of First Home Mortgages from €300,000 to €200,000?

The First Home Mortgages have an annual return of 7% which is the lowest of all available investments. Nevertheless, for policy reasons we are forcing the allocation of at least €300,000 to this kind of investment. The shadow price of this constraint (-0.02) shows that if we increase the limit by €1,000 the overall return drops by 0.02 (€000). Accordingly for every €1,000 we decrease

the limit profits go up by 0.02 (€000). The allowable decrease is 300 (€000s), so the reduction of €100,000 we are considering (from €300,000 to €200,000) is within the range that the shadow prices hold. The impact of such a change would be an increase in profits of 100 * 0.02 = 20 (€000s).


[↑ Back to the source list](#source-documents)

---

<a name="source-3"></a>

## Optimisation Exercises.pdf

<small>File type: PDF · Reader pages 831–834 · [View source PDF](PDF%20Slides.pdf#page=831)</small>

<small>Source Page 1 of 5</small>

### Optimisation Exercises

Exercise 1 Vienna Taxi Services (VTS) is a local cab company with operations centred around the area of Vienna. They employ 70 drives who work on 8 hour shifts. Demand for cabs in the area varies dramatically according to the time of day. The slowest period is between midnight and 4am when very few people are going to the airport or taking other long distance trips. Euripides, an author and VTS’s manager is has estimated that on average a driver will pick up €45 in fares during that period. The average fares per driver for each of the subsequent 4 hour period are shown in Table 1.

Table 1: Fares, Pay & Minimum Numbers of drivers for VTS Time Segment Average Fares Pay Minimum number 00:00-04:00 € 45 € 40

04:00-08:00 € 50 € 40

08:00-12:00 € 55 € 25

12:00-16:00 € 60 € 25

16:00-20:00 € 65 € 25

20:00-24:00 € 45 € 40

Even though demand is low in some periods Euripides feels that he must have drivers on duty at all times to retain customers and acquire new ones. In order to do this Euripides has determined the minimum number of drivers he needs working during each 4 hour time segment and these are also shown in table 1 together with the pay that applies in each segment. Thus each driver who works

from 8am to 4pm will be paid €50 and earns fares of €115 on average. However a complication is that only 15 of her drivers will work from 8pm to 4am. Figure 1.1 provides a spreadsheet model that Euripides has built to optimise the allocation of drivers to shifts (showing the optimal solution). The decision variables are the cells B14 to B19 containing the number of drivers starting

their shift in each time segment. Using these cells the range B26 to B31 calculate the number of drivers working in each shift. There three types of constraints. The first relates to the total number of available drivers, the second to the constraint on the number of drivers starting their shift at 8pm (15) and the last one relates to the minimum number of drivers in each time
segment. The solver settings are given in figure 1.2. (nonnegativity constraints are assumed) and the sensitivity analysis results in figure 1.3. Please answer the following questions: (a) At which time segments there are more drivers than the minimum required numbers? (b) What would the impact be of having 3 more drivers available? (c) Suppose that two drivers are sick and unavailable

for work on a given day. What is the financial impact? (d) One of the 15 drivers who is available for the shift from 8pm to 4am, has been advised by his doctor not to work at nights. What is the effect on the profit contribution? (e) Suppose that Euripides finds that the service is slipping during the period from 8pm to 8am. One approach would be to raise the minimum number of drivers

on duty between 8pm and midnight. How would this affect profit? (f) Alternatively, the minimum number on duty between midnight and 4am could be raised from 14 to 15. Which alternative is cheaper? (g) Another alternative is to ensure that at least one driver starts work at 4am. (Currently no one starts at 4am). How would this affect profit?

<small>Source Page 2 of 5</small>

Figure 1.1: An Excel model for Vienna Taxi Services

Figure 2.2: Solver settings

<small>Source Page 3 of 5</small>

Figure 1.3: Sensitivity Analysis !"#ABCDE)*+,*))B

!"#A% CD(F*D( HI-D*."/D 0%%NOAI%D 0%%NOAI%D PD%% 4ARD SA%FD PN7.

PND88"*"D#.

V#*:DA7D ;D*:DA7D -.-/0 NNONN3N0ONN+4A5E*S+78+"S9:*SB /;

N /< ;< N -.-/< N0ONN3N=ONN+4A5E*S+78+"S9:*SB N N 0N N />?@N -.-/A N=ONN3/;ONN+4A5E*S+78+"S9:*SB ;N N A< /N N -.-/B /;ONN3/ AONN+4A5E*S+78+"S9:*SB ;A N B< N /N -.-/= /AONN3;NONN+4A5E*S+78+"S9:*SB /N N 0< ;< N -.-/C ab98C;NC7N0 ; N /N N ;<

,7FBCSD9FCB

!"#A% <=A(NO PN#7.:A"#.

0%%NOAI%D 0%%NOAI%D PD%% 4ARD SA%FD >:"*D C?@?A<"(D V#*:DA7D ;D*:DA7D -.-;N 4A5E*Sd8eS9:*SB BN B< BN />?@N

-.-/C ab98C;NC70N ;

N /< />?@N /@ -.-;A NNONN3N0ONN+4A5E*S+78+"S9:*SB /0 3@< /0

; -.-;B N0ONN3N=ONN+4A5E*S+78+"S9:*SB /;
3;< /; ; /N -.-;= N=ONN3/;ONN+4A5E*S+78+"S9:*SB ;N 3/N ;N

;N -.-;C /;ONN3/AONN+4A5E*S+78+"S9:*SB 0A N ;< ;/ />?@N -.-@N / AONN3;NONN+4A5E*S+78+"S9:*SB @A N @;

/>?@N -.-@/ ;NONN3;0ONN+4A5E*S+78+"S9:*SB /;

3@N /; ;/ /N

<small>Source Page 4 of 5</small>

Exercise 2

The Beta Bank Loan Company is planning its operations for the next year. The company makes five types of loans, listed below, together with the annual return (in percent) to the company Type of Loan Annual Return (%) Unsecured Loans

Furniture Loans

Automobile Loans

First Home Mortgages

Second Home Mortgages

Legal requirements and company policy place the following limits upon the amounts of the various types of loans.

Unsecured loans cannot exceed 10% of the total amount of loans.

The amount of unsecured and furniture loans together cannot exceed 20 % of the total.

Automobile loans should represent at least 30% of the total amount of loans.

The firm can lend a maximum of €1.5 million, of which at least €300,000 should be invested in first home mortgages and no more than €375,000 in second home mortgages. The company wishes to maximise the revenue from loan interest, subject to the above restrictions. A spreadsheet model has been developed to determine the optimal mix of loans. (Figure 2.1, showing the optimal solution).

The Solver settings and the sensitivity analysis are provided in Figures 2.2 and 2.3 respectively. (a) What is the optimal loan combination and the resulting revenue? (b) What is the average return on the amount lent? What is the marginal return (% return on an additional €1,000 of loan)? (c) Would the optimal solution change if the return on Second Home Mortgages improves by 0.5%?

Explain. (d) What would be the impact of increasing the limit on unsecured loans from 10% to 20%? (e) What would be the impact of reducing the minimum requirement of First Home Mortgages from €300,000 to €200,000?
<small>Source Page 5 of 5</small>

Figure 2.1: The spreadsheet model with the optimal solution displayed

Figure 2.2: Solver settings Figure 2.3: Sensitivity analysis results

!"#ABC'EF*HI*FFB

!"#A% CD(F*D( HI-D*."/D 0%%NOAI%D 0%%NOAI%D PD%% 4ARD SA%FD PN7.

PND88"*"D#.

V#*:DA7D ;D*:DA7D -I-.

LMB*1A2*"H34'MBH5MS*BCT*MCB U9:

:;U9 U<=>: :;:> -I-9 ?A2M@CA2*H34'MBH5MS*BCT*MCB U9:

:;UA :;:> :;:> -I-B !AC4T4E@F*H34'MBH5MS*BCT*MCB C::

:;:C :;:> :;:U -I-a ?@2BCHb4T*Hc42Cd'd*BH5MS*BCT*MCB >::

:;:a :;:A U<=>: -I-e I*14M"Hb4T*Hc42Cd'd*BH5MS*BCT*MCB

g:;:U :;:e :;:U U<=>:

I4MBC2'@MCB

!"#A% <=A(NO PN#7.:A"#.

0%%NOAI%D 0%%NOAI%D PD%% 4ARD SA%FD >:"*D C?@?A<"(D V#*:DA7D ;D*:DA7D -K-UB LMB*1A2*"H34'MBH5MS*BCT*MCB U9: :;:>

U9:

U9: -K-Ua LM1*1A2*"H=H?A2M@CA2*H34'MBH5MS*BCT*MCB >:: :;:>

.9:

U9: -K-Ue !AC4T4E@F*H34'MBH5MS*BCT*MCB C::

.9:

U<=>: -K-UC ?@2BCHb4T*Hc42Cd'd*BH5MS*BCT*MCB >:: g:;:A >:: .9: >:: -K-A: I*14M"Hb4T*Hc42Cd'd*BH5MS*BCT*MCB

>a9 U<=>: >a9 -I-C i4C'F5MS*BCT*MC U9:: :;:CC U9::

U<=>:

C::


[↑ Back to the source list](#source-documents)

---

<a name="source-4"></a>

## ---- AUT23 optimisation.docx

<small>File type: DOCX · Reader pages 835–836 · [View source PDF](PDF%20Slides.pdf#page=835)</small>

Question 2 (25 points)

A ferry service between Liverpool and Belfast can carry various categories of passengers. These together with their respective profit margin per trip and loading time, where appropriate, are listed below:

The ferry can be loaded subject to the following conditions:

Total Passengers (plus driver) capacity should not exceed 1500 due to safety regulations.

Maximum number of coaches plus lorries is 25.

Maximum number of cars is 150 plus four for every lorry or coach space that is not used.

Vehicle loading time should be 1 hour maximum.

Market research indicates that maximum demand for foot passengers is 600.

The profit margins apply whether or not cars and coaches carry the full complement of passengers, but for safety purposes it must be assumed that they are always full.

Jean Farell, the marketing manager of the company and a graduate, has tried to use optimisation to find the optimal mix of passengers, cars, couches and lorries that the ferry can carry. She has developed the spreadsheet shown in Figure 2.1 and used Solver to find the mix that maximises the contribution to profit. Figure 2.3 shows the Solver specification and Figure 2.1 shows the Solver solution obtained. Figure 2.2 shows the formulas of the same model and Figure 2.4 shows the Solver sensitivity analysis.

Figure 2.1: The ferry service model showing the optimal solution.

Figure 2.2: The ferry service model showing the formulas

Figure2.3: The Solver Specification

Figure 3.4: The Solver sensitivity analysis.

a) What is the solution that maximises the profit contribution (objective function and optimal values of the variables) and which constraints are binding? [2 points]

b) Jean understands that the fractional values in the solution do not make sense. Find a feasible integer solution by rounding the fractional values. You need to check that the solution you found satisfies all constrains. [3 points]

c) How would you use Excel Solver to find the best integer solution? [5 points]

Answer the remaining questions based on the solution with fractional values shown in Figure 2.1 and using the Solver sensitivity analysis in Figure 2.4.

d) Interpret the reduced cost for the “Coach” variable. [5 points]

e) Evaluate the impact of increasing the limit on Foot Passengers from 600 to 700. [5 points]
f) [5 points] Discuss the effect of increasing the allowable loading time to:

i) 65 minutes

ii) 75 minutes.

/ Type

/ Profit Margin (£)

/ Loading time (minutes)

/ Foot Passengers

/ 5

/ -

/ Car with driver and 3 passengers

/ 35

/ 0.25

/ Coach with driver and 49 passengers

/ 300

/ 2

/ Lorry with driver

/ 200

/ 2


[↑ Back to the source list](#source-documents)

---

