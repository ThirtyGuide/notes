# Lecture 9 - Intro Optimisation

**Linear optimisation and Solver**

[← All chapters](README.md) · [Original PDF](PDF%20Slides.pdf#page=504)

## Overview

- Decision variables, objective functions, constraints and the feasible region.
- Linear programming, simplex reasoning, slack variables and sensitivity analysis.
- Excel Solver, shadow prices and Red Brand Canners / product-mix models.

## Source documents

1. [RBC Lab.pdf](#source-1) — PDF, reader page 505
2. [RBC Seminar Doc 2026.pdf](#source-2) — PDF, reader page 512
3. [RBC Slides.pdf](#source-3) — PDF, reader page 519
4. [Red Brand Canners.pdf](#source-4) — PDF, reader page 527
5. [session09.pdf](#source-5) — PDF, reader page 531
6. [Bobs Muffler.xlsx](#source-6) — XLSX, reader page 596
7. [ProductMix2.xlsx](#source-7) — XLSX, reader page 598
8. [RBC1.xlsx](#source-8) — XLSX, reader page 606
9. [RBC2.xlsx](#source-9) — XLSX, reader page 618
10. [RBC3.xlsx](#source-10) — XLSX, reader page 630
11. [RBC6.xlsx](#source-11) — XLSX, reader page 642
12. [RBCTemplate.xlsx](#source-12) — XLSX, reader page 649
13. [RBCTemplate.xlsx](#source-13) — XLSX, reader page 652
14. [Red Brand Canners - Solution.xlsx](#source-14) — XLSX, reader page 655

---

<a name="source-1"></a>

## RBC Lab.pdf

<small>File type: PDF · Reader pages 505–511 · [View source PDF](PDF%20Slides.pdf#page=505)</small>

<small>Source Page 1 of 6</small>

### Red Brand Canners Lab

Red Brand Canners is an interesting case that captures several points that are important in realworld model formulation. It highlights the importance of distinguishing between information and facts that are relevant for decision making, and data that is not. Distinguishing between the two may be especially difficult because on occasion, confused or incorrect concepts will be strongly

held by members of the management team. The Red Brand Canners case illustrates such a situation, where different decision makers have different opinions about the relevance of the data, and how it should be employed for making the decision at hand. Also, the case highlights the dangers of using intuitive reasoning when making business decisions. Moreover, in situations where we are faced

with a “What’s Best?” question, we often require a software tool to help us analysing the problem and making recommendations. In this workshop, we will use Excel’s Solver. We have dealt with the Red Brand Canners case in class. However, there are still several interesting issues that we have not yet discussed. In this workshop, you will be asked to go again through the entire process

from building the model to making recommendations, and extending the model to incorporate new information and new options. This lab assignment consists of 6 parts; you are required to work through them in your ----- group. Please write a report of no more than 4 pages answering Parts 3-6 and submit it on Canvas by the deadline. No appendix is allowed, and no Excel files should be

submitted. Check with the --------- or one of the tutors for your answers to Parts 1 and 2 before proceeding with the other parts. Red Brand Canners was a medium-size company that was specialised in canning and distributing a variety of fruit and vegetable products under private brand names in the western states of the US. On Monday, September 13th, Mitchell Gordon, Vice-President of

Operations, asked the Controller, the Sales Manager, and the Production Manager of Red Brand Canners to meet with him to discuss the amount of tomato products to pack that season. The tomato crop, which had been purchased at planting, was beginning to arrive at the cannery. Packing operations would have to start by the following Monday because, after this time, the fruit would begin to

deteriorate. In effect this ruled out the possibility of reselling any part of the crop which, if it remained unpacked, would be worthless. This case is intended to be used as a basis for class discussion, rather than to illustrate either effective or ineffective handling of an administrative situation. All names of individuals and companies are fictitious.
form or by any means electronic, mechanical, photocopying, recording, or otherwise without the permission of .

<small>Source Page 2 of 6</small>

William Cooper, Controller, and Charles Myers, Sales Manager, were the first to arrive in Mr.

Gordon's office. Dan Tucker, Production Manager, came in a few minutes later and said that he had picked up Produce Inspection's latest estimate of the quality of the incoming tomatoes. According to the report, about 20% of the 3,000,000 pound crop was Grade “A” and the remaining portion Grade “B”. Mr. Gordon asked Mr. Myers about the demand for tomato products for the coming year. Mr.

Myers replied that they could sell all of the whole canned tomatoes they could produce. The expected demand for tomato juice and tomato paste, however, was limited. The Sales Manager then passed around the latest demand forecast (Exhibit 1) reminding the group that selling prices had been set in light of long-term marketing strategy of the company, and that potential sales had been

forecast at these prices. After looking at Mr. Myers’ estimates of demand, Mr. Cooper said that it looked as though the company, "should do quite well on the tomato crop this year". With the new accounting system that had been set up, he had been able to compute the contribution for each product, and according to his analysis the incremental profit on whole tomatoes was greater than for

any other tomato product. In May, after Red Brand had signed contracts agreeing to purchase the grower's production at an average delivered price of 18 cents per pound, Mr. Cooper had computed the tomato products' contributions (Exhibit 2).

24-2½ whole tomatoes $ 12.00 800,000

24-2½ choice peach halves $ 16.20 10,000

24-2½ peach nectar $ 13.80 5,000

24-2½ tomato juice $ 13.50 50,000

24-2¼ cooking apples $ 14.70 15,000

24-2½ tomato paste $ 11.40 80,000

($) Selling Price 12.00 16.20 13.80 13.50 14.70 11.40 Direct labour 3.54 4.20 3.81 3.96 2.10 1.62 Variable overhead 0.72 0.96 0.69 1.08 0.66 0.78 Variable selling 1.20 0.90 1.20 2.55 0.84 1.14 Packaging material 2.10 1.68 1.80 1.95 2.10 2.31 Fruit 3.24 5.40 5.10 3.60 2.70 4.50 Total Variable Costs 10.80 13.14 12.60 13.14 8.40 10.35 Contribution 1.20 3.06 1.20 0.36 6.30 1.05 Allocated Overhead 0.84 2.10 1.56 0.63 2.25 0.69 Net Profit 0.36 0.96 (0.36) (0.27) 4.05 0.36

Mr. Tucker called Mr. Cooper's attention to the fact that, although production capacity was ample, it was impossible to produce all whole tomatoes because too small a portion of the crop was “A” quality. Red Brand used a numerical scale to record the quality of both raw pro‐
duce and prepared products. This scale ran from zero to ten, the higher number representing better quality. “A” tomatoes averaged nine points per pound and “B” tomatoes five points per pound. Mr. Tucker

Exhibit 1. Demand Forecasts

Product Selling Price per

Case

Exhibit 2. Product Item Profitability (per case)

Product 24-2½ Whole Tomatoes

24-2½ Choice Peach Halves ($)

($)

Demand Forecast

Pounds per Case

(Cases)

24-2½ Peach Nectar

24-2½ Tomato

24-2½ Cooking

24-2½ Tomato

Juice

Apples

Paste

($)

($)

($)

<small>Source Page 3 of 6</small>

noted that the minimum average input quality for canned whole tomatoes was eight and for juice six points per pound.1 Paste could be made entirely from “B” grade tomatoes. This meant that whole tomato production was limited to 800,000 pounds. Mr. Gordon stated that this was not a real limitation. Recently solicited to purchase 80,000 pounds of Grade “A” tomatoes at 25½ cents per pound,
he had turned down the offer. He thought, however, that the tomatoes were still available. Mr. Myers, who had been doing some calculations, said that although he agreed that the Company "should do quite well this year", it would not be by canning whole tomatoes. It seemed to him that tomato costs should be allocated on the basis of quality and quantity rather than by quantity only, as

Mr. Cooper had done. Therefore, he had recomputed the marginal profit on this basis and from his results (see Exhibit 3), believed that Red Brand should use 2,000,000 pounds of the “B” tomatoes for paste, and the remaining 400,000 pounds of “B” tomatoes and all of the “A” tomatoes for juice. If demand expectations were realised, a profit contribution of $144,000 would be made in this

year's tomato crop.

Exhibit 3. Myers’ Analysis of Tomato Costs

In calculating the cost of the tomatoes used in the different products, we should distinguish based on the quality of the tomatoes (“A” or “B”). Although average price paid for the tomatoes, namely 18 cents per pound, is for the entire crop, I suggest using different costs for the different qualities. Below is a suggestion on how to compute these costs. Assume that

x = cost per pound of “A” tomatoes used in a product (in cents)

y = cost per pound of “B” tomatoes used in a product (in cents) Then:

(600.000 lbs. * x) + (2,400,000 lbs. * y) should equal (3,000,000 lbs. * 18), and

x/9 should equal y/5 The first condition ensures that the total price paid for the tomato crop is correct, the second condition ensures that the tomato cost is directly related to its quality, measured by its point value. The resulting prices are:

x = 27.9 cents per pound

y = 15.5 cents per pound This gives rise to the marginal profit analysis given in Exhibit 4.

1 This meant, for example, that for every pound of “B” tomatoes used in a batch of tomato juice, one-third pound of “A” tomatoes would have to be used to maintain an average quality level of six points per pound for the batch.

<small>Source Page 4 of 6</small>

- The Model without the option of additional A tomatoes

Exhibit 4. Myers’ Marginal Profit Analysis of Tomato Products

Product Canned Whole Tomatoes ($) Tomato Juice ($) Tomato Paste ($) Selling Price 12.00 13.50 11.40 Variable Costs (excluding tomato cost)

7.56 9.54 5.85

```r
Contribution (excluding tomato cost)
```

4.44 3.96 5.55
Tomato Cost 4.47 3.72 3.90 Marginal Contribution (0.03) 0.24 1.65

Copy the file RBC Template.xlsx that can be found on Canvas. Using the template, build a model for the problem Red Brand Canners is faced with, disregarding the availability of the additional A tomatoes.

Make a recommendation about which products to produce in what quantities.

How can you be sure that your recommendation is the best possible one?

- Additional supply of grade A tomatoes

Save the model as RBC2.

Modify the model to incorporate the option of buying the additional 80,000 pounds of A tomatoes at 25.5 cents/pound as suggested by Mitchell Gordon.

Should Gordon buy the additional A tomatoes?

If yes, how should he allocate the additional A tomatoes to the different products?

Is there only one optimal allocation?

Suppose the additional A tomatoes cost more than 25.5 cents/pound.

Up to what price should Gordon be willing to pay?

Check your solutions to Parts 1 and 2 with one of the tutors before proceeding.

<small>Source Page 5 of 6</small>

- Advertising (2 points)

Save the model as RBC3. Continue with the same model, namely with the option to buy the additional A tomatoes included. Suppose that the marketing department of Red Brand Canners feels that it could increase the demand for any of the three tomato products by 5,000 cases, by means of advertising.

How much should RBC be willing to pay for such a campaign?

At which product(s) should the advertising be directed?

Show how you can use the Sensitivity Analysis report for making this decision.

- Additional supply of B tomatoes (2 points)

Continue with the same model, with additional A tomatoes and increased demand because of advertising – disregard the advertising cost.

Mitchell Gordon receives a call from Ed Dawkins, the Vice President of Operations at Tomaco, a company in the same business as Red Brand Canners, active in the Midwest. Dawkins tells Gordon that they are stuck with some B tomatoes that they cannot put to good use. Dawkins offers Gordon some of these tomatoes at 18 cents per pound, generally agreed as the “nor‐
mal” tomato price. Mitchell Gordon refuses to buy the tomatoes, claiming that the 18 cents per pound is based on the fact that the incoming crop normally contains a mix of grade A and grade B tomatoes.

What do you think about his reasoning?

Would you buy additional B tomatoes at 18 cents per pound? Why or why not?

Use the sensitivity analysis report from your model in Part 3 to answer this question.

Do NOT extend your model with additional decisions.

- Closing down production lines? (3 points)

Start with the original RBC.xls, and save it as RBC5.xls (no additional tomatoes, no advertising).

Starting up the production line for each of the products entails a substantial set-up cost. Dan Tucker estimates that the set-up costs are $50,000 per line. This means that if RBC decides not to start up a particular line, they would save $50,000, but they would not be able to produce that particular product.

If we decide not to start up the Paste line, will this increase or decrease our total profit?

Which production lines would you advise RBC to start up?

You can solve this part in two different ways:

- You can try all possible combinations of production lines open and choose the one that

gives the best objective, or…

- Your model can use “binary” decision variables, which only take the values 0 or 1:

In the Solver dialog box, ensure the “Changing Variable Cells” include your new binary variables. Then add a constraint to define them as binary, via the middle drop-down menu of Add. Also, via the Options, uncheck “Ignore Integer Constraints”. Solver will try all possible 0/1 combinations for your binary decision variables and choose the combination that gives the best objective

<small>Source Page 6 of 6</small>

- One year later (8 points)

Start with the original RBC.xls, and save it as RBC6.xls (no additional tomatoes, no advertising, no setup decisions). In April the year after, Red Brand Canners is preparing for the annual negotiations with the tomato farmers. Although the quality of the crop varies from year to year, the price and quantity are negotiated in advance. At a meeting, Dan Tucker, William Cooper, Charles

Myers and Mitchell Gordon agree that this year, an acceptable price would be 20 cents per pound, and they are debating how many pounds of tomatoes to contract for. Dan Tucker says that initial discussions revealed that they could order up to 13 million pounds of tomatoes. Charles Myers says that demand is pretty much the same as last year, i.e. they would be able to sell as many whole
canned tomatoes as they can make, and demand for juice and paste is again limited to 50,000 and 80,000 cases, respectively. Also prices and production costs are stable and would be the same as last year. The only uncertainty is the quality of the crop. Looking at historical data, Tucker observes that in the past there were basically three types of years:

- In “wet” years, like last year, the crop was quite poor, and contained only about 20%

grade A.

- In “sunny” years, the percentage of A tomatoes was around 60%, and

- In “normal” years, the crop contained approximately 50% grade A tomatoes.

Tucker also observed that about 25% of the years were “sunny”, 50% “normal” years and 25% “poor”.

Assume you know that next year is going to be a sunny year, how many pounds of tomatoes would you advise RBC to buy? Call this S. How about for a normal (N) and a poor (P) year? Remember that RBC can order at most 13 million pounds.

Suppose you order S pounds of tomatoes. What would be the possible outcomes, given that the year could be sunny, normal or poor? Perform a scenario analysis. Do the same for ordering N and P tomatoes.

Given the probabilities of sunny, poor and normal years, what is the average result of ordering S, P and N tomatoes?

How many pounds of tomatoes would you advise RBC to buy?

TIPS – Use Solver for this question. There is no need to use @Risk or PrecisionTree. – Don’t forget to change the price of the tomatoes to 20 cents per lb. ($200 per 1,000 lbs.) – RBC has to pay for the tomatoes it orders, not for the ones actually used. Leftovers cannot be returned nor sold.


[↑ Back to the source list](#source-documents)

---

<a name="source-2"></a>

## RBC Seminar Doc 2026.pdf

<small>File type: PDF · Reader pages 512–518 · [View source PDF](PDF%20Slides.pdf#page=512)</small>

<small>Source Page 1 of 6</small>

### Red Brand Canners Lab

Red Brand Canners is an interesting case that captures several points that are important in realworld model formulation. It highlights the importance of distinguishing between information and facts that are relevant for decision making, and data that is not. Distinguishing between the two may be especially difficult because on occasion, confused or incorrect concepts will be strongly

held by members of the management team. The Red Brand Canners case illustrates such a situation, where different decision makers have different opinions about the relevance of the data, and how it should be employed for making the decision at hand. Also, the case highlights the dangers of using intuitive reasoning when making business decisions. Moreover, in situations where we are faced

with a “What’s Best?” question, we often require a software tool to help us analysing the problem and making recommendations. In this workshop, we will use Excel’s Solver. We have dealt with the Red Brand Canners case in class. However, there are still several interesting issues that we have not yet discussed. In this workshop, you will be asked to go again through the entire process

from building the model to making recommendations, and extending the model to incorporate new information and new options. This lab assignment consists of 6 parts; you are required to work through them in your ----- group. Please write a report of no more than 4 pages answering Parts 3-6 and submit it on Canvas by the deadline. No appendix is allowed, and no Excel files should be

submitted. Check with the --------- or one of the tutors for your answers to Parts 1 and 2 before proceeding with the other parts. Red Brand Canners was a medium-size company that was specialised in canning and distributing a variety of fruit and vegetable products under private brand names in the western states of the US. On Monday, September 13th, Mitchell Gordon, Vice-President of

Operations, asked the Controller, the Sales Manager, and the Production Manager of Red Brand Canners to meet with him to discuss the amount of tomato products to pack that season. The tomato crop, which had been purchased at planting, was beginning to arrive at the cannery. Packing operations would have to start by the following Monday because, after this time, the fruit would begin to

deteriorate. In effect this ruled out the possibility of reselling any part of the crop which, if it remained unpacked, would be worthless. This case is intended to be used as a basis for class discussion, rather than to illustrate either effective or ineffective handling of an administrative situation. All names of individuals and companies are fictitious.
form or by any means electronic, mechanical, photocopying, recording, or otherwise without the permission of .

<small>Source Page 2 of 6</small>

William Cooper, Controller, and Charles Myers, Sales Manager, were the first to arrive in Mr.

Gordon's office. Dan Tucker, Production Manager, came in a few minutes later and said that he had picked up Produce Inspection's latest estimate of the quality of the incoming tomatoes. According to the report, about 20% of the 3,000,000 pound crop was Grade “A” and the remaining portion Grade “B”. Mr. Gordon asked Mr. Myers about the demand for tomato products for the coming year. Mr.

Myers replied that they could sell all of the whole canned tomatoes they could produce. The expected demand for tomato juice and tomato paste, however, was limited. The Sales Manager then passed around the latest demand forecast (Exhibit 1) reminding the group that selling prices had been set in light of long-term marketing strategy of the company, and that potential sales had been

forecast at these prices. After looking at Mr. Myers’ estimates of demand, Mr. Cooper said that it looked as though the company, "should do quite well on the tomato crop this year". With the new accounting system that had been set up, he had been able to compute the contribution for each product, and according to his analysis the incremental profit on whole tomatoes was greater than for

any other tomato product. In May, after Red Brand had signed contracts agreeing to purchase the grower's production at an average delivered price of 18 cents per pound, Mr. Cooper had computed the tomato products' contributions (Exhibit 2).

24-2½ whole tomatoes $ 12.00 800,000

24-2½ choice peach halves $ 16.20 10,000

24-2½ peach nectar $ 13.80 5,000

24-2½ tomato juice $ 13.50 50,000

24-2¼ cooking apples $ 14.70 15,000

24-2½ tomato paste $ 11.40 80,000

($) Selling Price 12.00 16.20 13.80 13.50 14.70 11.40 Direct labour 3.54 4.20 3.81 3.96 2.10 1.62 Variable overhead 0.72 0.96 0.69 1.08 0.66 0.78 Variable selling 1.20 0.90 1.20 2.55 0.84 1.14 Packaging material 2.10 1.68 1.80 1.95 2.10 2.31 Fruit 3.24 5.40 5.10 3.60 2.70 4.50 Total Variable Costs 10.80 13.14 12.60 13.14 8.40 10.35 Contribution 1.20 3.06 1.20 0.36 6.30 1.05 Allocated Overhead 0.84 2.10 1.56 0.63 2.25 0.69 Net Profit 0.36 0.96 (0.36) (0.27) 4.05 0.36

Mr. Tucker called Mr. Cooper's attention to the fact that, although production capacity was ample, it was impossible to produce all whole tomatoes because too small a portion of the crop was “A” quality. Red Brand used a numerical scale to record the quality of both raw pro‐
duce and prepared products. This scale ran from zero to ten, the higher number representing better quality. “A” tomatoes averaged nine points per pound and “B” tomatoes five points per pound. Mr. Tucker

Exhibit 1. Demand Forecasts

Product Selling Price per

Case

Exhibit 2. Product Item Profitability (per case)

Product 24-2½ Whole Tomatoes

24-2½ Choice Peach Halves ($)

($)

Demand Forecast

Pounds per Case

(Cases)

24-2½ Peach Nectar

24-2½ Tomato

24-2½ Cooking

24-2½ Tomato

Juice

Apples

Paste

($)

($)

($)

<small>Source Page 3 of 6</small>

noted that the minimum average input quality for canned whole tomatoes was eight and for juice six points per pound.1 Paste could be made entirely from “B” grade tomatoes. This meant that whole tomato production was limited to 800,000 pounds. Mr. Gordon stated that this was not a real limitation. Recently solicited to purchase 80,000 pounds of Grade “A” tomatoes at 25½ cents per pound,
he had turned down the offer. He thought, however, that the tomatoes were still available. Mr. Myers, who had been doing some calculations, said that although he agreed that the Company "should do quite well this year", it would not be by canning whole tomatoes. It seemed to him that tomato costs should be allocated on the basis of quality and quantity rather than by quantity only, as

Mr. Cooper had done. Therefore, he had recomputed the marginal profit on this basis and from his results (see Exhibit 3), believed that Red Brand should use 2,000,000 pounds of the “B” tomatoes for paste, and the remaining 400,000 pounds of “B” tomatoes and all of the “A” tomatoes for juice. If demand expectations were realised, a profit contribution of $144,000 would be made in this

year's tomato crop.

Exhibit 3. Myers’ Analysis of Tomato Costs

In calculating the cost of the tomatoes used in the different products, we should distinguish based on the quality of the tomatoes (“A” or “B”). Although average price paid for the tomatoes, namely 18 cents per pound, is for the entire crop, I suggest using different costs for the different qualities. Below is a suggestion on how to compute these costs. Assume that

x = cost per pound of “A” tomatoes used in a product (in cents)

y = cost per pound of “B” tomatoes used in a product (in cents) Then:

(600.000 lbs. * x) + (2,400,000 lbs. * y) should equal (3,000,000 lbs. * 18), and

x/9 should equal y/5 The first condition ensures that the total price paid for the tomato crop is correct, the second condition ensures that the tomato cost is directly related to its quality, measured by its point value. The resulting prices are:

x = 27.9 cents per pound

y = 15.5 cents per pound This gives rise to the marginal profit analysis given in Exhibit 4.

1 This meant, for example, that for every pound of “B” tomatoes used in a batch of tomato juice, one-third pound of “A” tomatoes would have to be used to maintain an average quality level of six points per pound for the batch.

<small>Source Page 4 of 6</small>

- The Model without the option of additional A tomatoes

Exhibit 4. Myers’ Marginal Profit Analysis of Tomato Products

Product Canned Whole Tomatoes ($) Tomato Juice ($) Tomato Paste ($) Selling Price 12.00 13.50 11.40 Variable Costs (excluding tomato cost)

7.56 9.54 5.85

```r
Contribution (excluding tomato cost)
```

4.44 3.96 5.55
Tomato Cost 4.47 3.72 3.90 Marginal Contribution (0.03) 0.24 1.65

Copy the file RBC Template.xlsx that can be found on Canvas. Using the template, build a model for the problem Red Brand Canners is faced with, disregarding the availability of the additional A tomatoes.

Make a recommendation about which products to produce in what quantities.

How can you be sure that your recommendation is the best possible one?

- Additional supply of grade A tomatoes

Save the model as RBC2.

Modify the model to incorporate the option of buying the additional 80,000 pounds of A tomatoes at 25.5 cents/pound as suggested by Mitchell Gordon.

Should Gordon buy the additional A tomatoes?

If yes, how should he allocate the additional A tomatoes to the different products?

Is there only one optimal allocation?

Suppose the additional A tomatoes cost more than 25.5 cents/pound.

Up to what price should Gordon be willing to pay?

Check your solutions to Parts 1 and 2 with one of the tutors before proceeding.

<small>Source Page 5 of 6</small>

- Advertising (2 points)

Save the model as RBC3. Continue with the same model, namely with the option to buy the additional A tomatoes included. Suppose that the marketing department of Red Brand Canners feels that it could increase the demand for any of the three tomato products by 5,000 cases, by means of advertising.

How much should RBC be willing to pay for such a campaign?

At which product(s) should the advertising be directed?

Show how you can use the Sensitivity Analysis report for making this decision.

- Additional supply of B tomatoes (2 points)

Continue with the same model, with additional A tomatoes and increased demand because of advertising – disregard the advertising cost.

Mitchell Gordon receives a call from Ed Dawkins, the Vice President of Operations at Tomaco, a company in the same business as Red Brand Canners, active in the Midwest. Dawkins tells Gordon that they are stuck with some B tomatoes that they cannot put to good use. Dawkins offers Gordon some of these tomatoes at 18 cents per pound, generally agreed as the “nor‐
mal” tomato price. Mitchell Gordon refuses to buy the tomatoes, claiming that the 18 cents per pound is based on the fact that the incoming crop normally contains a mix of grade A and grade B tomatoes.

What do you think about his reasoning?

Would you buy additional B tomatoes at 18 cents per pound? Why or why not?

Use the sensitivity analysis report from your model in Part 3 to answer this question.

Do NOT extend your model with additional decisions.

- Closing down production lines? (3 points)

Start with the original RBC.xls, and save it as RBC5.xls (no additional tomatoes, no advertising).

Starting up the production line for each of the products entails a substantial set-up cost. Dan Tucker estimates that the set-up costs are $50,000 per line. This means that if RBC decides not to start up a particular line, they would save $50,000, but they would not be able to produce that particular product.

If we decide not to start up the Paste line, will this increase or decrease our total profit?

Which production lines would you advise RBC to start up?

You can solve this part in two different ways:

- You can try all possible combinations of production lines open and choose the one that

gives the best objective, or…

- Your model can use “binary” decision variables, which only take the values 0 or 1:

In the Solver dialog box, ensure the “Changing Variable Cells” include your new binary variables. Then add a constraint to define them as binary, via the middle drop-down menu of Add. Also, via the Options, uncheck “Ignore Integer Constraints”. Solver will try all possible 0/1 combinations for your binary decision variables and choose the combination that gives the best objective

<small>Source Page 6 of 6</small>

- One Year Later (4 points)

Start with the original RBC.xls, and save it as RBC6.xls (no additional tomatoes, no advertising, no closing down decisions).

One of the reasons for the lower amount of grade A tomatoes was incidence of tomato blight (a fungal infection). For this reason, the following year the farmer will use a blight resistant variety of tomatoes in the hope of increasing the percentage of grade A tomatoes. This improved tomato variety and expected quality are reflected in a higher price: 20 cents per pound. He is also able to guarantee a higher production yield.

The farmer can provide us with up to 15 million pounds of tomato and expects that 80% of tomatoes will now be grade A.
If all other variables (demand constraints, production costs, market prices, quality constraints) remain fixed, how many pounds of tomato should RBC purchase? What would the profit be?

There is a small possibility of a strand of super-strong blight fungi affecting the crop. This would lower the percentage of grade A tomatoes to 10%. How much would you recommend RBC purchases then?

If the probability of blight is 5% what is the expected profit for RBC?


[↑ Back to the source list](#source-documents)

---

<a name="source-3"></a>

## RBC Slides.pdf

<small>File type: PDF · Reader pages 519–526 · [View source PDF](PDF%20Slides.pdf#page=519)</small>

<small>Source Page 1 of 29</small>

### CA09

Session 9

Examples and Red Brand Canners

Rohit Mattu

<small>Source Page 2 of 29</small>

### A larger product mix problem (1/2)

- Instead of two models, suppose we now produce have eight different PC models

- There are two lines for -------; first line is faster and with higher labour costs. A com‐

puter can be ------ in either line and we have a certain number of hours available per line.

- Objective: Maximize profit, subject to the available labor hours and maximum sales

<small>Source Page 3 of 29</small>

### A larger product mix problem (2/2)

<small>Source Page 4 of 29</small>

### Sensitivity Analysis on Product Mix (1/2)

A reduced cost for a product not in the optimal mix (yellow cells) indicates how much greater its margin would have to be before it would enter the optimal mix.

Number ------ on line 1 Model 2 has a reduced cost of -20 and a Final Value of 0, i.e., we are not producing any at all. We can think of the reduced cost of -20 in two ways: 1. Our profit would reduce by 20 if we are forced to produce a model 2 which is ------ on line 1 2. Currently, the objective coefficient of this model is 132, and we are not producing any as it is not optimal. Were the contribution to increase by 20 to 132 + 20 = 152, then it would be worthwhile
<small>Source Page 5 of 29</small>

### Sensitivity Analysis on Product Mix (2/2)

A nonzero shadow price (green cells) indicates how much profit would change for a one-unit increase in that resource. But this holds only for changes within the allowable increase and decrease.

Labor hours for assembly has a shadow price = 29.5. As long as the number of assembly hours is between 20,000-2,375 and 20,000+3,250, then any change in assembly hours will impact profit by 29.5.

A zero shadow price usually indicates that we have more of the resource than we need.

<small>Source Page 6 of 29</small>

### Red Brand Canners

<small>Source Page 7 of 29</small>

### Red Brand Canners

- Canner and distributor of fruits and vegetables in West USA

- Starring executives

- Mitchell Gordon, VP of operations

- William Cooper, Controller

- Charles Myers, Sales manager

- Dan Tucker, Production manager

- Meeting

- Tomato crop has already been paid for and was beginning to arrive

- Amount of tomato products to pack for the coming season ?

- Packing operations start Monday

<small>Source Page 8 of 29</small>

### Supply & Demand

- Supply (Tucker)

- quantity: 3,000,000 pounds (lbs)

- quality: 20% grade A, 80% grade B
- 18 cents / pound

- Demand forecasts (Myers)

- “Selling prices are set in light of the long-term marketing strategy of the company,

potential sales are forecast at these prices”

- “We can sell all the whole tomatoes we can produce.”

- “Demand for tomato juice and paste is limited”

Product Selling Price per Case Demand Forecast (Cases)

Whole Tomatoes $12.00 800,000 Tomato Juice $13.50 50,000 Tomato Paste $11.40 80,000

<small>Source Page 9 of 29</small>

### Management Accounting

- Profit contributions (Cooper)

- “Incremental profit is greatest for whole tomatoes”

<small>Source Page 10 of 29</small>

### Quality

- Quality requirements (Tucker)

- “Impossible to produce all whole tomatoes because too small portion of the

crop is grade A”

- RBC quality scale: 0 (low quality) - 10 (high quality)

- Raw Tomatoes

- Grade A 9 points

- Grade B 5 points

- Product quality requirements

- Whole canned tomatoes 8 points

- Tomato juice 6 points

- Tomato paste 5 points

- Conclusion: “Whole tomato production is limited to 800,000 pounds”

- Extra supply (Gordon)

- “Additional 80,000 pounds grade A tomatoes available at 25.50 cents per

pound”
<small>Source Page 11 of 29</small>

### Tomato Cost

- Myers does not agree with Coopers

- Whole canned tomatoes look attractive, but require more grade A tomatoes

(higher quality, fewer available) compared to other products

- “Tomato cost has to be allocated on the basis of quantity and quality” (different

tomato cost for different products)

- Computes cost of A and B tomatoes based on their quality

(quality 10 tomatoes should cost twice as much as quality 5 tomatoes)

<small>Source Page 12 of 29</small>

### Tomato Cost

Product Cost

- whole (8 points) = 8/9 * 27.96 = 24.85 cents/pound ($4.47/case)

- juice (6 points) = 6/9 * 27.96 = 18.64 cents/pound ($3.72/case)

- paste (5 points) = 5/9 * 27.96 = 15.53 cents/pound ($3.90/case)

<small>Source Page 13 of 29</small>

### Meyer’s Recommendation

- Tomato paste is the most profitable → make as much as you can sell

- “Use 2,000,000 pounds of grade B tomatoes to make 80,000 cases of tomato paste

(satisfy demand).

- Tomato juice is the second most profitable → make as much as your

resources allow

- “Use the remaining 400,000 pounds of B tomatoes and the 600,000

grade A tomatoes to make 50,000 cases of tomato juice (satisfy demand).

Total contribution of paste = $132,000 (80,000*$1.65) Total contribution of juice = $12,000 (50,000*$0.24) Total contribution = $144,000
<small>Source Page 14 of 29</small>

### Myer’s Solution

Grade A tomatoes implicitly cost the company more (27.96 cents) than grade B tomatoes (15.54 cents)

Does this have anything to do with the current task at hand which is to maximize the operating profit for the season given the resources (tomatoes) at hand?

<small>Source Page 15 of 29</small>

### Sunk cost fallacy

Tomatoes have already been purchased and, hence, their purchase price is a sunk cost.

It does not make sense to penalize the production of whole tomatoes because of the cost already incurred in purchasing grade A tomatoes.

<small>Source Page 16 of 29</small>

### Cost of tomatoes?

<small>Source Page 17 of 29</small>

### Contribution

Contribution = Revenue – Variable Costs

<small>Source Page 18 of 29</small>

### Contribution Calculations

<small>Source Page 19 of 29</small>

### Decision Variables

How many decision variables we have in this problem?
<small>Source Page 20 of 29</small>

### Decision Variables

<small>Source Page 21 of 29</small>

### Problem Formulation

Objective Function

Subject to Constraints

<small>Source Page 22 of 29</small>

### Problem Formulation

Objective Function Subject to Demand Constraints Supply Constraints Quality Constraints

Maximize 247AW + 198AJ + 222AP + 247BW + 198BJ + 222BP

Subject to AW + BW ≤ 14,400 (Demand) AJ + BJ ≤ 1,000 (Demand) AP + BP ≤ 2,000 (Demand)

AW + AJ + AP ≤ 600 (Supply) BW + BJ + BP ≤ 2,400 (Supply)

9AW + 5BW ≥ 8(AW+BW) (Quality) 9AJ + 5BJ ≥ 6(AJ+BJ) (Quality)

<small>Source Page 23 of 29</small>

### Model

<small>Source Page 24 of 29</small>

### RBC - Sensitivity Analysis

<small>Source Page 25 of 29</small>

### Should we buy extra 80,000 extra lbs of Grade A tomatoes at 25.5 c

### (0.255)/lb?
<small>Source Page 26 of 29</small>

### RBC - Sensitivity Analysis

The shadow price is the increase in the objective if we increase the right hand side constraint of the corresponding by 1 unit. Shadow price of “Tomato A Pounds Used” (grade A supply constraint): $271 (/1000 pounds)

We should be willing to pay up to $0.271/lb of grade A tomatoes for an allowable increase of 600,000 pounds.

We should buy the 80,000 extra pounds at a price of $255/1000 pounds: net benefit = $0.271- $0.255 = $0.016 per pound, $1,280 (=80*0.016*1000) in total

<small>Source Page 27 of 29</small>

### Comparison of different solutions

<small>Source Page 28 of 29</small>

### Summary

- Allocating scarce resources ⇒ Optimization

- Overhead and sunk costs are irrelevant for decision making

- Formulate model

- What do we want? ⇒ (goal, objective)

- What we have to decide/ What we have to do? ⇒ (decision variables)

- What are our constraints? ⇒ (constraints)

- Do not make decision solely on intuition (e.g. Cooper, Myers’ accounting data,

extra A tomatoes with negative contributions)

- Use Solver

- if problem is linear, select “Simplex LP” as the solver method; solver will compute

optimal solution

- if problem is not linear, Solver cannot always guarantee optimal solution

- if negative values do not make sense, “Assume Non-Negative”

- use sensitivity analysis to understand the value of relaxing constraints

- Applications (Finance, Operations, Marketing, Management Accounting, …)
<small>Source Page 29 of 29</small>

### Thank you

Rohit Mattu


[↑ Back to the source list](#source-documents)

---

<a name="source-4"></a>

## Red Brand Canners.pdf

<small>File type: PDF · Reader pages 527–530 · [View source PDF](PDF%20Slides.pdf#page=527)</small>

<small>Source Page 1 of 4</small>

### Red Brand Canners

Red Brand Canners was a medium-size company that was specialised in canning and distributing a variety of fruit and vegetable products under private brand names in the western states of the US. On Monday, September 13th, Mitchell Gordon, Vice-President of Operations, asked the Controller, the Sales Manager, and the Production Manager of Red Brand Canners to meet with him to discuss the

amount of tomato products to pack that season. The tomato crop, which had been purchased at planting, was beginning to arrive at the cannery. Packing operations would have to start by the following Monday because, after this time, the fruit would begin to deteriorate. In effect this ruled out the possibility of reselling any part of the crop which, if it remained unpacked, would be

worthless. William Cooper, Controller, and Charles Myers, Sales Manager, were the first to arrive in Mr. Gordon's office. Dan Tucker, Production Manager, came in a few minutes later and said that he had picked up Produce Inspection's latest estimate of the quality of the incoming tomatoes. According to the report, about 20% of the 3,000,000 pound crop was Grade “A” and the remaining

portion Grade “B”. Mr. Gordon asked Mr. Myers about the demand for tomato products for the coming year. Mr. Myers replied that they could sell all of the whole canned tomatoes they could produce. The expected demand for tomato juice and tomato paste, however, was limited. The Sales Manager then passed around the latest demand forecast (Exhibit 1) reminding the group that selling prices

had been set in light of long-term marketing strategy of the company, and that potential sales had been forecast at these prices. After looking at Mr. Myers’ estimates of demand, Mr. Cooper said that it looked as though the company, "should do quite well on the tomato crop this year". With the new accounting system that had been set up, he had been able to compute the contribution for

each product, and according to his analysis the incremental profit on whole tomatoes was greater than for any other tomato product. In May, after Red Brand had signed contracts agreeing to purchase the grower's production at an average delivered price of 18 cents per pound, Mr. Cooper had computed the tomato products' contributions (Exhibit 2). This case is intended to be used as a basis

for class discussion, rather than to illustrate either effective or ineffective handling of an administrative situation. All names of individuals and companies are fictitious.

form or by any means ⎯ electronic, mechanical, photocopying, recording, or otherwise ⎯ without the permission of .
<small>Source Page 2 of 4</small>

Exhibit 1. Demand Forecasts Product Selling Price per Case Demand Forecast (Cases) Pounds per Case 24-2½ whole tomatoes $ 12.00 800,000

24-2½ choice peach halves $ 16.20 10,000

24-2½ peach nectar $ 13.80 5,000

24-2½ tomato juice $ 13.50 50,000

24-2¼ cooking apples $ 14.70 15,000

24-2½ tomato paste $ 11.40 80,000

Exhibit 2. Product Item Profitability (per case) Product 24-2½ Whole Tomatoes

24-2½ Choice Peach Halves

24-2½ Peach Nectar

24-2½ Tomato

24-2½ Cooking

24-2½ Tomato

($)

Juice

Apples

Paste

($) Selling Price 12.00 16.20 13.80 13.50 14.70 11.40 Direct labour 3.54 4.20 3.81 3.96 2.10 1.62 Variable overhead 0.72 0.96 0.69 1.08 0.66 0.78 Variable selling 1.20 0.90 1.20 2.55 0.84 1.14 Packaging material 2.10 1.68 1.80 1.95 2.10 2.31 Fruit 3.24 5.40 5.10 3.60 2.70 4.50 Total Variable Costs 10.80 13.14 12.60 13.14 8.40 10.35 Contribution 1.20 3.06 1.20 0.36 6.30 1.05 Allocated Overhead 0.84 2.10 1.56 0.63 2.25 0.69 Net Profit 0.36 0.96 (0.36) (0.27) 4.05 0.36

($)

($)

($)

($)

Mr. Tucker called Mr. Cooper's attention to the fact that, although production capacity was ample, it was impossible to produce all whole tomatoes because too small a portion of the crop was “A” quality. Red Brand used a numerical scale to record the quality of both raw produce and prepared products. This scale ran from zero to ten, the higher number representing better quality. “A”
tomatoes averaged nine points per pound and “B” tomatoes five points per pound. Mr. Tucker noted that the minimum average input quality for canned whole tomatoes was eight and for juice six points per pound.1 Paste could be made entirely from “B” grade tomatoes. This meant that whole tomato production was limited to 800,000 pounds. Mr. Gordon stated that this was not a real limitation.

Recently solicited to purchase 80,000 pounds of Grade “A” tomatoes at 25½ cents per pound, he had turned down the offer. He thought, however, that the tomatoes were still available. Mr. Myers, who had been doing some calculations, said that although he agreed that the Company "should do quite well this year", it would not be by canning whole tomatoes. It seemed to him that tomato costs

should be allocated on the basis of quality and quantity rather than by quantity only, as Mr. Cooper had done. Therefore, he had recomputed the marginal profit on this basis and from his results (see Exhibit 3), believed that Red Brand should use 2,000,000 pounds of the “B” tomatoes for paste, and the remaining 400,000 pounds of “B” tomatoes and all of the “A” tomatoes for juice. If

demand expectations were realised, a profit contribution of $144,000 would be made in this year's tomato crop.

1 This meant, for example, that for every pound of “B” tomatoes used in a batch of tomato juice, one-third pound of “A” tomatoes would have to be used to maintain an average quality level of six points per pound for the batch.

<small>Source Page 3 of 4</small>

Exhibit 3. Myers’ Analysis of Tomato Costs In calculating the cost of the tomatoes used in the different products, we should distinguish based on the quality of the tomatoes (“A” or “B”). Although average price paid for the tomatoes, namely 18 cents per pound, is for the entire crop, I suggest using different costs for the different qualities. Below is a suggestion on how to compute

these costs. Assume that ▪ x = cost per pound of “A” tomatoes used in a product (in cents) ▪ y = cost per pound of “B” tomatoes used in a product (in cents) Then: ▪ (600.000 lbs. * x) + (2,400,000 lbs. * y) should equal (3,000,000 lbs. * 18), and ▪ x/9 should equal y/5 The first condition ensures that the total price paid for the tomato crop is correct, the second condition ensures that

the tomato cost is directly related to its quality, measured by its point value. The resulting prices are: ▪ x = 27.9 cents per pound ▪ y = 15.5 cents per pound This gives rise to the marginal profit analysis given in Exhibit 4.

Exhibit 4. Myers’ Marginal Profit Analysis of Tomato Products Product Canned Whole Tomatoes ($) Tomato Juice ($) Tomato Paste ($) Selling Price 12.00 13.50 11.40 Variable Costs (excluding tomato cost)

7.56 9.54 5.85

```r
Contribution (excluding tomato cost)
```
4.44 3.96 5.55

Tomato Cost 4.47 3.72 3.90 Marginal Contribution (0.03) 0.24 1.65

<small>Source Page 4 of 4</small>

### Questions 1. Both Mr. Cooper and Mr. Myers made ----------- of tomato

**product profitability and have**

drawn conclusions based on this to decide which products to produce. Mr. Cooper concluded that the incremental profit on whole tomatoes was greater than for any other tomato product, and therefore advised to produce whole tomatoes only. Is this reasoning correct?

- At some point, Mr. Tucker mentioned that it was impossible to produce all whole toma‐

toes because too small a portion of the crop was “A” quality, and claimed that the whole tomato production was limited to 800,000 pounds. How did he figure that out?

- What is the reasoning behind Mr. Myers’ analysis of tomato costs? Is his analysis cor‐

rect?

- Mr. Myers recommended using 2,000,000 pounds of the “B” tomatoes for paste, and

the remaining 400,000 pounds of “B” tomatoes and all of the “A” tomatoes for juice, resulting in a profit of $144,000. Is this figure correct? Do you agree with his recommendation?

- Mr. Gordon mentioned that he had received an offer for 80,000 pounds of Grade “A”

tomatoes

at 25½ cents per pound. Should he have accepted this offer?


[↑ Back to the source list](#source-documents)

---

<a name="source-5"></a>

## session09.pdf

<small>File type: PDF · Reader pages 531–595 · [View source PDF](PDF%20Slides.pdf#page=531)</small>

<small>Source Page 1 of 208</small>

### Resource Allocation

CA09

Session 9

Rohit Mattu

<small>Source Page 2 of 208</small>

### Decision Making Under Constraints

- In Risk Analysis, we asked how uncertainty affects our decisions.

- Today’s focus is resource allocation: how scarcity affects our decisions.

- What do we need to decide? What are we trying to achieve? What limits our choices?

<small>Source Page 3 of 208</small>

### LEGO Toy Problem

Large Block Small Block

- A chair needs 1 large and 2 small blocks, and earns a profit of 10.

- A table needs 2 large and 2 small blocks, and earns a profit of 16.

<small>Source Page 4 of 208</small>

### LEGO Toy Problem

Large Block Small Block

- A chair needs 1 large and 2 small blocks, and earns a profit of 10.

- A table needs 2 large and 2 small blocks, and earns a profit of 16.

- How many chairs and tables you should make to maximize profit?
<small>Source Page 5 of 208</small>

### LEGO Toy Problem

Large Block Small Block

- A chair needs 1 large and 2 small blocks, and earns a profit of 10.

- A table needs 2 large and 2 small blocks, and earns a profit of 16.

- How many chairs and tables you should make to maximize profit?

- You have 6 large blocks and 8 small blocks in total.

<small>Source Page 6 of 208</small>

### Linear Programming Formulation

<small>Source Page 7 of 208</small>

### Linear programming formulation

- Decision variables C chairs and T tables.

<small>Source Page 8 of 208</small>

### Linear programming formulation

- Decision variables C chairs and T tables.

- Objective function Maximize 10C + 16T.

<small>Source Page 9 of 208</small>

### Linear programming formulation

- Decision variables C chairs and T tables.

- Objective function Maximize 10C + 16T.

Product Large blocks per unit Small blocks per unit Profit per unit Chair
<small>Source Page 10 of 208</small>

### Linear programming formulation

- Decision variables C chairs and T tables.

- Objective function Maximize 10C + 16T.

Product Large blocks per unit Small blocks per unit Profit per unit Chair

Table

<small>Source Page 11 of 208</small>

### Linear programming formulation

- Decision variables C chairs and T tables.

- Objective function Maximize 10C + 16T.

Product Large blocks per unit Small blocks per unit Profit per unit Chair

Table

Available

<small>Source Page 12 of 208</small>

### Linear programming formulation

- Decision variables C chairs and T tables.

- Objective function Maximize 10C + 16T.

Product Large blocks per unit Small blocks per unit Profit per unit Chair

Table

Available

subject to C + 2T ≤6 (large blocks)

<small>Source Page 13 of 208</small>

### Linear programming formulation

- Decision variables C chairs and T tables.

- Objective function Maximize 10C + 16T.

Product Large blocks per unit Small blocks per unit Profit per unit Chair

Table
Available

subject to C + 2T ≤6 (large blocks)

2C + 2T ≤8 (small blocks)

<small>Source Page 14 of 208</small>

### Linear programming formulation

- Decision variables C chairs and T tables.

- Objective function Maximize 10C + 16T.

Product Large blocks per unit Small blocks per unit Profit per unit Chair

Table

Available

subject to C + 2T ≤6 (large blocks)

2C + 2T ≤8 (small blocks) C, T ≥0 (non-negativity constraints)

<small>Source Page 15 of 208</small>

### Linear programming formulation

Decision variables C chairs and T tables

Objective function Maximize 10C + 16T

Constraints C + 2T ≤6 (large blocks)

2C + 2T ≤8 (small blocks) C, T ≥0 (non-negativity)

<small>Source Page 16 of 208</small>

### Assumptions in Linear Programming problem

- Linearity: The objective function and constraints are linear. The profit from A and B is

the sum of the individual profits.

- Proportionality: If the profit of one item is A, the profit of two items is 2A.

- Deterministic: All parameters and coefficients are deterministic and are known with

certainty. They don’t change during or after the formulation
<small>Source Page 17 of 208</small>

### Graphical solution

<small>Source Page 18 of 208</small>

### Graphical solution

```r
Tables (T)
```

−1

−1

```r
Chairs (C) Each point (C, T) represents a production plan.
```

<small>Source Page 19 of 208</small>

### Graphical solution

C = 0

```r
Tables (T)
```

−1

−1

```r
Chairs (C) C ≥0 keeps the points on or to the right of C = 0.
```

<small>Source Page 20 of 208</small>

### Graphical solution

C = 0

```r
Tables (T)
```

T = 0

−1

−1
```r
Chairs (C)
```

T ≥0 keeps the points on or above T = 0. Together, the two restrictions give the first quadrant.

<small>Source Page 21 of 208</small>

### Graphical solution

C = 0

```r
Tables (T)
```

C + 2T = 6

T = 0

```r
Chairs (C)
```

The origin satisfies C + 2T ≤6. Keep the part of the first quadrant on its side of the line.

<small>Source Page 22 of 208</small>

### Graphical solution

C = 0 2C + 2T = 8

```r
Tables (T)
```

C + 2T = 6

Feasible region

T = 0

```r
Chairs (C)
```

Gold meets the small-block limit only. Grey meets the large-block limit only. Blue meets both.

<small>Source Page 23 of 208</small>

### Graphical solution

```r
At (1, 1), profit is 16 + 10 = 26. Shift this line in parallel to increase profit.
```
C = 0 2C + 2T = 8

```r
Tables (T)
```

(1, 1)

Feasible region

```r
Chairs (C)
```

10C + 16T = 26

C + 2T = 6

T = 0

<small>Source Page 24 of 208</small>

### Graphical solution

Each isoprofit line holds profit constant. Move to a parallel line farther out to increase profit.

C = 0 2C + 2T = 8

```r
Tables (T)
```

P = 46 P = 36 P = 26 Feasible region

```r
Chairs (C)
```

P = 10C + 16T

C + 2T = 6

T = 0

<small>Source Page 25 of 208</small>

### Graphical solution

The last point the line touches is (2, 2), giving a maximum profit of 52.

C = 0 2C + 2T = 8

```r
Tables (T)
```

(2, 2)
Feasible region

```r
Chairs (C)
```

10C + 16T = 52

C + 2T = 6

T = 0

<small>Source Page 26 of 208</small>

Why does the optimum lie on the boundary?

<small>Source Page 27 of 208</small>

### Non-Linearity

- A linear objective gives you a direction in which profit increases. The boundary is

where the constraints stop you from moving in that direction.

<small>Source Page 28 of 208</small>

Why does the optimum lie on the boundary?

Why does it lie at a corner?

<small>Source Page 29 of 208</small>

### Moving along the feasible edges

Trade one table for two chairs on the navy edge, or one chair for one table on the gold edge.

<small>Source Page 30 of 208</small>

### Moving along the feasible edges

10C + 16T = 46

Trade one table for two chairs on the navy edge, or one chair for one table on the gold edge.
<small>Source Page 31 of 208</small>

### Moving along the feasible edges

C = 0

2C + 2T = 8

```r
Tables (T)
```

(2, 2)

Feasible region

```r
Chairs (C) Slope −0.625 lies between −1 and −0.5. The optimum is (2, 2).
```

10C + 16T = 52

C + 2T = 6

T = 0

<small>Source Page 32 of 208</small>

### Algebraic solution

<small>Source Page 33 of 208</small>

### Linear programming formulation

Decision variables C chairs and T tables

Objective function Maximize 10C + 16T

Constraints C + 2T ≤6 (large blocks)

2C + 2T ≤8 (small blocks) C, T ≥0 (non-negativity)

<small>Source Page 34 of 208</small>

### Adding slack variables

Blocks used + blocks unused = blocks available.

S1 counts unused small blocks. S2 counts unused large blocks.
<small>Source Page 35 of 208</small>

### Adding slack variables

Blocks used + blocks unused = blocks available.

S1 counts unused small blocks. S2 counts unused large blocks.

Small blocks 2C + 2T ≤8 −→ 2C + 2T + S1 = 8

<small>Source Page 36 of 208</small>

### Adding slack variables

Blocks used + blocks unused = blocks available.

S1 counts unused small blocks. S2 counts unused large blocks.

Small blocks 2C + 2T ≤8 −→ 2C + 2T + S1 = 8 Large blocks C + 2T ≤6 −→ C + 2T + S2 = 6

<small>Source Page 37 of 208</small>

### Adding slack variables

Blocks used + blocks unused = blocks available.

S1 counts unused small blocks. S2 counts unused large blocks.

Small blocks 2C + 2T ≤8 −→ 2C + 2T + S1 = 8 Large blocks C + 2T ≤6 −→ C + 2T + S2 = 6 Objective function Maximize Z = 10C + 16T + 0S1 + 0S2

<small>Source Page 38 of 208</small>

### Adding slack variables

Blocks used + blocks unused = blocks available.

S1 counts unused small blocks. S2 counts unused large blocks.

Small blocks 2C + 2T ≤8 −→ 2C + 2T + S1 = 8 Large blocks C + 2T ≤6 −→ C + 2T + S2 = 6 Objective function Maximize Z = 10C + 16T + 0S1 + 0S2 Non-negativity C, T, S1, S2 ≥0

<small>Source Page 39 of 208</small>

### Six candidate solutions of the LEGO problem

- Use Z = 10C + 16T. Set two variables to zero non basic variables and solve for the

other two (basic variables).
Fixed at zero C T S1 S2 Z Feasible?

C = 0, T = 0

Yes

- S1: unused small blocks; S2: unused large blocks.

- Feasibility requires C, T, S1, S2 ≥0. A negative slack makes a plan infeasible.

<small>Source Page 40 of 208</small>

### Six candidate solutions of the LEGO problem

- Use Z = 10C + 16T. Set two variables to zero non basic variables and solve for the

other two (basic variables).

Fixed at zero C T S1 S2 Z Feasible?

C = 0, T = 0

Yes C = 0, S1 = 0

−2

No

- S1: unused small blocks; S2: unused large blocks.

- Feasibility requires C, T, S1, S2 ≥0. A negative slack makes a plan infeasible.

<small>Source Page 41 of 208</small>

### Six candidate solutions of the LEGO problem

- Use Z = 10C + 16T. Set two variables to zero non basic variables and solve for the

other two (basic variables).

Fixed at zero C T S1 S2 Z Feasible?

C = 0, T = 0

Yes C = 0, S1 = 0

−2

No C = 0, S2 = 0

Yes

- S1: unused small blocks; S2: unused large blocks.

- Feasibility requires C, T, S1, S2 ≥0. A negative slack makes a plan infeasible.
<small>Source Page 42 of 208</small>

### Six candidate solutions of the LEGO problem

- Use Z = 10C + 16T. Set two variables to zero non basic variables and solve for the

other two (basic variables).

Fixed at zero C T S1 S2 Z Feasible?

C = 0, T = 0

Yes C = 0, S1 = 0

−2

No C = 0, S2 = 0

Yes T = 0, S1 = 0

Yes

- S1: unused small blocks; S2: unused large blocks.

- Feasibility requires C, T, S1, S2 ≥0. A negative slack makes a plan infeasible.

<small>Source Page 43 of 208</small>

### Six candidate solutions of the LEGO problem

- Use Z = 10C + 16T. Set two variables to zero non basic variables and solve for the

other two (basic variables).

Fixed at zero C T S1 S2 Z Feasible?

C = 0, T = 0

Yes C = 0, S1 = 0

−2

No C = 0, S2 = 0

Yes T = 0, S1 = 0

Yes T = 0, S2 = 0

−4

No

- S1: unused small blocks; S2: unused large blocks.

- Feasibility requires C, T, S1, S2 ≥0. A negative slack makes a plan infeasible.
<small>Source Page 44 of 208</small>

### Six candidate solutions of the LEGO problem

- Use Z = 10C + 16T. Set two variables to zero non basic variables and solve for the

other two (basic variables).

Fixed at zero C T S1 S2 Z Feasible?

C = 0, T = 0

Yes C = 0, S1 = 0

−2

No C = 0, S2 = 0

Yes T = 0, S1 = 0

Yes T = 0, S2 = 0

−4

No S1 = 0, S2 = 0

```r
Yes (Optimal)
```

- S1: unused small blocks; S2: unused large blocks.

- Feasibility requires C, T, S1, S2 ≥0. A negative slack makes a plan infeasible.

<small>Source Page 45 of 208</small>

### Limitations of the algebraic solution

- It evaluates all solutions. The number of combinations grows rapidly with the number

of variables and constraints.

- It evaluates many infeasible solutions, which it may need not even consider.

- It is not systematic in the sense that it does not provide a clear path to the optimal

solution.

<small>Source Page 46 of 208</small>

### Simplex solution

<small>Source Page 47 of 208</small>

Initialization
<small>Source Page 48 of 208</small>

### Start with a feasible plan

- S1 counts unused small blocks. S2 counts unused large blocks.

2C + 2T + S1 = 8

C + 2T + S2 = 6

Z = 10C + 16T

<small>Source Page 49 of 208</small>

### Start with a feasible plan

- S1 counts unused small blocks. S2 counts unused large blocks.

2C + 2T + S1 = 8 =⇒ S1 = 8 −2C −2T C + 2T + S2 = 6 =⇒ S2 = 6 −C −2T

Z = 10C + 16T

<small>Source Page 50 of 208</small>

### Start with a feasible plan

- S1 counts unused small blocks. S2 counts unused large blocks.

2C + 2T + S1 = 8 =⇒ S1 = 8 −2C −2T C + 2T + S2 = 6 =⇒ S2 = 6 −C −2T

Z = 10C + 16T

- Set the nonbasic variables C and T to zero.

Solve for the basic variables S1 and S2.

<small>Source Page 51 of 208</small>

### Start with a feasible plan

- S1 counts unused small blocks. S2 counts unused large blocks.

2C + 2T + S1 = 8 =⇒ S1 = 8 −2C −2T

2C + 2T = 8

```r
Tables (T)
```

(2, 2) (0, 3)
C + 2T + S2 = 6 =⇒ S2 = 6 −C −2T

C + 2T = 6

Z = 10C + 16T

Feasible region

- Set the nonbasic variables C and T to zero.

Solve for the basic variables S1 and S2.

(0, 0) (4, 0)

```r
Chairs (C)
```

- We start with S1 = 8, S2 = 6, Z = 0. All quantities are nonnegative, so the starting

plan is feasible.

Starting corner (C, T ) = (0, 0).

<small>Source Page 52 of 208</small>

### Iterations

<small>Source Page 53 of 208</small>

### Iteration 1: Limits to Increase Tables

- From Z = 10C + 16T, a table adds 16 and a chair adds 10 at the starting corner.

Choose T and keep C = 0.

2C + 2T = 8

```r
Tables (T)
```

(2, 2) (0, 3)

C + 2T = 6

Feasible region (0, 0) (4, 0)

```r
Chairs (C)
```

Starting corner (C, T ) = (0, 0).
<small>Source Page 54 of 208</small>

### Iteration 1: Limits to Increase Tables

- From Z = 10C + 16T, a table adds 16 and a chair adds 10 at the starting corner.

Choose T and keep C = 0.

S1 = 8 −2T ≥0 =⇒ T ≤4 (small blocks)

2C + 2T = 8

```r
Tables (T)
```

(2, 2) (0, 3)

C + 2T = 6

Feasible region (0, 0) (4, 0)

```r
Chairs (C)
```

Starting corner (C, T ) = (0, 0).

<small>Source Page 55 of 208</small>

### Iteration 1: Limits to Increase Tables

- From Z = 10C + 16T, a table adds 16 and a chair adds 10 at the starting corner.

Choose T and keep C = 0.

S1 = 8 −2T ≥0 =⇒ T ≤4 (small blocks)

2C + 2T = 8

```r
Tables (T)
```

(2, 2) (0, 3)

C + 2T = 6

S2 = 6 −2T ≥0 =⇒ T ≤3 (large blocks)

Feasible region (0, 0) (4, 0)

```r
Chairs (C)
```

Starting corner (C, T ) = (0, 0).
<small>Source Page 56 of 208</small>

### Iteration 1: Limits to Increase Tables

- From Z = 10C + 16T, a table adds 16 and a chair adds 10 at the starting corner.

Choose T and keep C = 0.

S1 = 8 −2T ≥0 =⇒ T ≤4 (small blocks)

2C + 2T = 8

```r
Tables (T)
```

(2, 2) (0, 3)

C + 2T = 6

S2 = 6 −2T ≥0 =⇒ T ≤3 (large blocks)

Feasible region (0, 0) (4, 0)

- Large blocks run out first. Set T = 3, so S2 = 0. T enters the basis and S2 leaves.

```r
Chairs (C)
```

Starting corner (C, T ) = (0, 0).

<small>Source Page 57 of 208</small>

### Iteration 1: Limits to Increase Tables

- From Z = 10C + 16T, a table adds 16 and a chair adds 10 at the starting corner.

Choose T and keep C = 0.

S1 = 8 −2T ≥0 =⇒ T ≤4 (small blocks)

2C + 2T = 8

```r
Tables (T)
```

(2, 2) (0, 3)

C + 2T = 6

S2 = 6 −2T ≥0 =⇒ T ≤3 (large blocks)

Feasible region

- Large blocks run out first. Set T = 3, so S2 = 0. T enters the basis and S2 leaves.

(0, 0) (4, 0)
```r
Chairs (C)
```

- The plan moves from (C, T) = (0, 0) to (0, 3).

Profit rises to 48.

First move (0, 0) −→(0, 3).

<small>Source Page 58 of 208</small>

- Solve the large-block equation for the new basic variable T.

C + 2T + S2 = 6 =⇒ T = 3 −1

2C −1

2S2

<small>Source Page 59 of 208</small>

- Solve the large-block equation for the new basic variable T.

C + 2T + S2 = 6 =⇒ T = 3 −1

2C −1

2S2

S1 = 8 −2C −2

3 −1

2C −1

2S2

=⇒ S1 = 2 −C + S2

<small>Source Page 60 of 208</small>

- Solve the large-block equation for the new basic variable T.

C + 2T + S2 = 6 =⇒ T = 3 −1

2C −1

2S2

S1 = 8 −2C −2

3 −1
2C −1

2S2

=⇒ S1 = 2 −C + S2

Z = 10C + 16

3 −1

2C −1

2S2

=⇒ Z = 48 + 2C −8S2

<small>Source Page 61 of 208</small>

- Solve the large-block equation for the new basic variable T.

C + 2T + S2 = 6 =⇒ T = 3 −1

2C −1

2S2

S1 = 8 −2C −2

3 −1

2C −1

2S2

=⇒ S1 = 2 −C + S2

Z = 10C + 16

3 −1

2C −1

2S2

=⇒ Z = 48 + 2C −8S2

- The new nonbasic variables are C and S2. Setting both to zero gives T = 3, S1 = 2, Z =

48.

<small>Source Page 62 of 208</small>

### Iteration 2: Limits to Increase Chairs

- From Z = 48 + 2C −8S2, increasing C raises profit by 2 per chair. Keep S2 = 0.
2C + 2T = 8

```r
Tables (T)
```

(2, 2) (0, 3)

C + 2T = 6

Feasible region (0, 0) (4, 0)

```r
Chairs (C)
```

Current corner (C, T ) = (0, 3).

<small>Source Page 63 of 208</small>

### Iteration 2: Limits to Increase Chairs

- From Z = 48 + 2C −8S2, increasing C raises profit by 2 per chair. Keep S2 = 0.

S1 = 2 −C ≥0 =⇒ C ≤2 (unused small blocks)

2C + 2T = 8

```r
Tables (T)
```

(2, 2) (0, 3)

C + 2T = 6

Feasible region (0, 0) (4, 0)

```r
Chairs (C)
```

Current corner (C, T ) = (0, 3).

<small>Source Page 64 of 208</small>

### Iteration 2: Limits to Increase Chairs

- From Z = 48 + 2C −8S2, increasing C raises profit by 2 per chair. Keep S2 = 0.

S1 = 2 −C ≥0 =⇒ C ≤2 (unused small blocks)

2C + 2T = 8

```r
Tables (T)
```

(2, 2) (0, 3)
T = 3 −1

2C ≥0 =⇒ C ≤6 (tables)

C + 2T = 6

Feasible region (0, 0) (4, 0)

```r
Chairs (C)
```

Current corner (C, T ) = (0, 3).

<small>Source Page 65 of 208</small>

### Iteration 2: Limits to Increase Chairs

- From Z = 48 + 2C −8S2, increasing C raises profit by 2 per chair. Keep S2 = 0.

S1 = 2 −C ≥0 =⇒ C ≤2 (unused small blocks)

2C + 2T = 8

```r
Tables (T)
```

(2, 2) (0, 3)

T = 3 −1

2C ≥0 =⇒ C ≤6 (tables)

C + 2T = 6

Feasible region

- Small blocks run out before tables reach zero. Set C = 2, so S1 = 0. C enters the basis

and S1 leaves.

```r
Chairs (C)
```

(0, 0) (4, 0)

Current corner (C, T ) = (0, 3).

<small>Source Page 66 of 208</small>

### Iteration 2: Limits to Increase Chairs

- From Z = 48 + 2C −8S2, increasing C raises profit by 2 per chair. Keep S2 = 0.

S1 = 2 −C ≥0 =⇒ C ≤2 (unused small blocks)
2C + 2T = 8

```r
Tables (T)
```

(2, 2) (0, 3)

T = 3 −1

2C ≥0 =⇒ C ≤6 (tables)

C + 2T = 6

Feasible region

- Small blocks run out before tables reach zero. Set C = 2, so S1 = 0. C enters the basis

and S1 leaves.

(0, 0) (4, 0)

```r
Chairs (C)
```

- The plan moves from (0, 3) to (2, 2). Profit rises by 2(2) = 4, to 52.

Second move (0, 3) −→(2, 2).

<small>Source Page 67 of 208</small>

- Solve the small-block slack equation for the new basic variable C.

S1 = 2 −C + S2 =⇒ C = 2 −S1 + S2

<small>Source Page 68 of 208</small>

- Solve the small-block slack equation for the new basic variable C.

S1 = 2 −C + S2 =⇒ C = 2 −S1 + S2

T = 3 −1

```r
2(2 −S1 + S2) −1
```

2S2 =⇒ T = 2 + 1

2S1 −S2

<small>Source Page 69 of 208</small>

- Solve the small-block slack equation for the new basic variable C.
S1 = 2 −C + S2 =⇒ C = 2 −S1 + S2

T = 3 −1

```r
2(2 −S1 + S2) −1
```

2S2 =⇒ T = 2 + 1

2S1 −S2

Z = 48 + 2(2 −S1 + S2) −8S2 =⇒ Z = 52 −2S1 −6S2

<small>Source Page 70 of 208</small>

- Solve the small-block slack equation for the new basic variable C.

S1 = 2 −C + S2 =⇒ C = 2 −S1 + S2

T = 3 −1

```r
2(2 −S1 + S2) −1
```

2S2 =⇒ T = 2 + 1

2S1 −S2

Z = 48 + 2(2 −S1 + S2) −8S2 =⇒ Z = 52 −2S1 −6S2

- Both slacks are now nonbasic. Setting S1 = S2 = 0 gives C = 2, T = 2, Z = 52.

<small>Source Page 71 of 208</small>

Termination

<small>Source Page 72 of 208</small>

### Termination Condition

Z = 52 −2S1 −6S2

- Both slacks must be nonnegative. Increasing either slack lowers profit, so Z ≤52 for

every feasible plan.
<small>Source Page 73 of 208</small>

### Termination Condition

Z = 52 −2S1 −6S2

- Both slacks must be nonnegative. Increasing either slack lowers profit, so Z ≤52 for

every feasible plan.

- Two chairs and two tables use every block and attain 52.

<small>Source Page 74 of 208</small>

Tabular form of Simplex

<small>Source Page 75 of 208</small>

### Simplex Initialization

Unit profit Cj

Row CB Basic variable C T S1 S2 RHS

Enter the unit profits Cj. Each slack variable has a unit profit of zero.

<small>Source Page 76 of 208</small>

### Simplex Initialization

Unit profit Cj

Row CB Basic variable C T S1 S2 RHS R1

S1

Copy the small-block constraint into the S1 row.

<small>Source Page 77 of 208</small>

### Simplex Initialization

Basic S1 = 8, S2 = 6 Nonbasic C = T = 0 Profit Z = 0 Unit profit Cj

Row CB Basic variable C T S1 S2 RHS R1

S1

R2
S2

Copy the large-block constraint into the S2 row. Read the basic values from the RHS.

<small>Source Page 78 of 208</small>

### Simplex Initialization

Basic S1 = 8, S2 = 6 Nonbasic C = T = 0 Profit Z = 0 Unit profit Cj

Row CB Basic variable C T S1 S2 RHS R1

S1

R2

S2

Cj −Zj

Zj is the sum of the column entries weighted by CB. Here both basic profit coefficients are zero, so Cj −Zj = Cj.

<small>Source Page 79 of 208</small>

### Simplex Initialization

Basic S1 = 8, S2 = 6 Nonbasic C = T = 0 Profit Z = 0 Unit profit Cj

Row CB Basic variable C T S1 S2 RHS R1

S1

R2

S2

Cj −Zj

Entering T Choose T to enter. Its reduced cost of 16 is the largest positive value.

<small>Source Page 80 of 208</small>

### Simplex Initialization

Basic S1 = 8, S2 = 6 Nonbasic C = T = 0 Profit Z = 0 Unit profit Cj

Row CB Basic variable C T S1 S2 RHS Ratio θ R1

S1

8/2 = 4 R2
S2

Cj −Zj

Entering T For each positive entry in the entering column, divide the RHS by that entry to get θ.

<small>Source Page 81 of 208</small>

### Simplex Initialization

Basic S1 = 8, S2 = 6 Nonbasic C = T = 0 Profit Z = 0 Unit profit Cj

Row CB Basic variable C T S1 S2 RHS Ratio θ R1

S1

8/2 = 4 R2

S2

6/2 = 3 Cj −Zj

Entering T The large-block row allows 3 tables, compared with 4 in the small-block row.

<small>Source Page 82 of 208</small>

### Simplex Initialization

Basic S1 = 8, S2 = 6 Nonbasic C = T = 0 Profit Z = 0 Unit profit Cj

Row CB Basic variable C T S1 S2 RHS Ratio θ R1

S1

8/2 = 4 R2

S2

6/2 = 3 Cj −Zj

Entering T Leaving S2 Choose the smallest ratio. S2 reaches zero first and leaves the basis.

<small>Source Page 83 of 208</small>

### Simplex Initialization

Basic S1 = 8, S2 = 6 Nonbasic C = T = 0 Profit Z = 0 Unit profit Cj

Row CB Basic variable C T S1 S2 RHS Ratio θ R1

S1
8/2 = 4 R2

S2

6/2 = 3 Cj −Zj

Entering T Leaving S2 Pivot element 2 The pivot element is 2. Divide the pivot row by 2 to obtain the new T row.

<small>Source Page 84 of 208</small>

### Simplex starts at the origin

Starting corner (C, T) = (0, 0).

- Both decision variables are nonbasic. The first pivot increases T along C = 0.

Unit profit Cj 10 16

Row CB Basic C T S1 S2 RHS θ R1

S1

8/2 = 4 R2

S2

6/2 = 3 Cj −Zj 10 16

Nonbasic C = T = 0 Profit Z = 0 Next pivot T enters, S2 leaves.

2C + 2T = 8

```r
Tables (T)
```

(2, 2) (0, 3)

C + 2T = 6

Feasible region (0, 0) (4, 0)

```r
Chairs (C)
```

<small>Source Page 85 of 208</small>

### First iteration of Simplex

Unit profit Cj

Row CB Basic variable C T S1 S2 RHS

Carry forward the unit profits. The pivot changes the basis and the constraint rows.
<small>Source Page 86 of 208</small>

### First iteration of Simplex

Unit profit Cj

Row CB Basic variable C T S1 S2 RHS

R2

T

Row operations R2 −→R2/2

Divide the previous S2 row by 2. The new T row has a 1 in the T column.

<small>Source Page 87 of 208</small>

### First iteration of Simplex

Basic S1 = 2, T = 3 Nonbasic C = S2 = 0 Profit Z = 48 Unit profit Cj

Row CB Basic variable C T S1 S2 RHS R1

S1

−1

R2

T

Row operations R2 −→R2/2 R1 −→R1 −2R2

Use the updated R2 to eliminate T from R1.

<small>Source Page 88 of 208</small>

### First iteration of Simplex

Basic S1 = 2, T = 3 Nonbasic C = S2 = 0 Profit Z = 48 Unit profit Cj

Row CB Basic variable C T S1 S2 RHS R1

S1

−1

R2

T

Cj −Zj
−8

Row operations R2 −→R2/2 R1 −→R1 −2R2

For chairs, Cj −Zj = 10 −16( 1

- = 2.

<small>Source Page 89 of 208</small>

### First iteration of Simplex

Basic S1 = 2, T = 3 Nonbasic C = S2 = 0 Profit Z = 48 Unit profit Cj

Row CB Basic variable C T S1 S2 RHS R1

S1

−1

R2

T

Cj −Zj

−8

Row operations R2 −→R2/2 R1 −→R1 −2R2 Entering C Choose C to enter. Its reduced cost is positive.

<small>Source Page 90 of 208</small>

### First iteration of Simplex

Basic S1 = 2, T = 3 Nonbasic C = S2 = 0 Profit Z = 48 Unit profit Cj

Row CB Basic variable C T S1 S2 RHS Ratio θ R1

S1

−1

2/1 = 2 R2

T

Cj −Zj

−8

Row operations R2 −→R2/2 R1 −→R1 −2R2 Entering C In the S1 row, divide the RHS of 2 by the chair coefficient of 1.
<small>Source Page 91 of 208</small>

### First iteration of Simplex

Basic S1 = 2, T = 3 Nonbasic C = S2 = 0 Profit Z = 48 Unit profit Cj

Row CB Basic variable C T S1 S2 RHS Ratio θ R1

S1

−1

2/1 = 2 R2

T

3/( 1

- = 6

Cj −Zj

−8

Row operations R2 −→R2/2 R1 −→R1 −2R2 Entering C In the T row, divide the RHS of 3 by the chair coefficient of 1

2.

<small>Source Page 92 of 208</small>

### First iteration of Simplex

Basic S1 = 2, T = 3 Nonbasic C = S2 = 0 Profit Z = 48 Unit profit Cj

Row CB Basic variable C T S1 S2 RHS Ratio θ R1

S1

−1

2/1 = 2 R2

T

3/( 1

- = 6

Cj −Zj

−8

Row operations R2 −→R2/2 R1 −→R1 −2R2 Entering C Leaving S1 The smaller ratio is 2. S1 reaches zero first and leaves the basis.
<small>Source Page 93 of 208</small>

### First iteration of Simplex

Basic S1 = 2, T = 3 Nonbasic C = S2 = 0 Profit Z = 48 Unit profit Cj

Row CB Basic variable C T S1 S2 RHS Ratio θ R1

S1

−1

2/1 = 2 R2

T

3/( 1

- = 6

Cj −Zj

−8

Row operations R2 −→R2/2 R1 −→R1 −2R2 Entering C Leaving S1 Pivot element 1 The pivot element is already 1. The pivot row becomes the new C row.

<small>Source Page 94 of 208</small>

### End of first iteration of Simplex

First move (0, 0) −→(0, 3).

- With S2 = 0, the next pivot follows the large-block boundary C + 2T = 6.

Unit profit Cj 10 16

Row CB Basic C T S1 S2 RHS θ R1

S1

−1

2/1 = 2 R2

T

3/( 1

- = 6

Cj −Zj

−8

Nonbasic C = S2 = 0 Profit Z = 48 Next pivot C enters, S1 leaves.

2C + 2T = 8
```r
Tables (T)
```

(2, 2) (0, 3)

C + 2T = 6

Feasible region (0, 0) (4, 0)

```r
Chairs (C)
```

<small>Source Page 95 of 208</small>

### Second iteration of Simplex

Unit profit Cj

Row CB Basic variable C T S1 S2 RHS

Carry forward the unit profits after the second pivot.

<small>Source Page 96 of 208</small>

### Second iteration of Simplex

Unit profit Cj

Row CB Basic variable C T S1 S2 RHS R1

C

−1

Row operations R1 −→R1/1

The previous S1 row becomes the C row because the pivot element is 1.

<small>Source Page 97 of 208</small>

### Second iteration of Simplex

Basic C = 2, T = 2 Nonbasic S1 = S2 = 0 Profit Z = 52 Unit profit Cj

Row CB Basic variable C T S1 S2 RHS R1

C

−1

R2
T

−1

Row operations R1 −→R1/1 R2 −→R2 −R1/2

Use the updated R1 to eliminate C from R2.

<small>Source Page 98 of 208</small>

### Second iteration of Simplex

Basic C = 2, T = 2 Nonbasic S1 = S2 = 0 Profit Z = 52 Unit profit Cj

Row CB Basic variable C T S1 S2 RHS R1

C

−1

R2

T

−1 Cj −Zj

−2 −6

Row operations R1 −→R1/1 R2 −→R2 −R1/2

For small blocks, Cj −Zj = 0 −[10(1) + 16(−1

2)] = −2.

<small>Source Page 99 of 208</small>

### Second iteration of Simplex

Basic C = 2, T = 2 Nonbasic S1 = S2 = 0 Profit Z = 52 Unit profit Cj

Row CB Basic variable C T S1 S2 RHS R1

C

−1

R2

T

−1 Cj −Zj

−2 −6
Row operations R1 −→R1/1 R2 −→R2 −R1/2 Optimal basis Every reduced cost is nonpositive. The current plan is optimal.

<small>Source Page 100 of 208</small>

### End of second iteration of Simplex

Second move (0, 3) −→(2, 2).

- Both block limits bind at this corner. All reduced costs are nonpositive, so simplex

stops.

Unit profit Cj 10 16

Row CB Basic C T S1 S2 RHS R1

C

−1

R2

T

−1 Cj −Zj

−2 −6 Nonbasic S1 = S2 = 0

Profit Z = 52 Optimal basis

2C + 2T = 8

```r
Tables (T)
```

(2, 2) (0, 3)

C + 2T = 6

Feasible region (0, 0) (4, 0)

```r
Chairs (C)
```

<small>Source Page 101 of 208</small>

### Excel Solver
<small>Source Page 102 of 208</small>

### Enabling Solver

- Mac. Open Tools, choose Excel Add-ins, and select Solver Add-in.

- Windows. Open File, then Options and Add-ins. Select Excel Add-ins under Manage,

click Go, and select Solver Add-in.

- Open the Data tab and select Solver.

Solver setup in Excel for Windows.

<small>Source Page 103 of 208</small>

### LEGO spreadsheet model

<small>Source Page 104 of 208</small>

### LEGO spreadsheet model

- Yellow cells. Set starting quantities in B4 (chairs) and C4 (tables).

<small>Source Page 105 of 208</small>

### LEGO spreadsheet model

- Yellow cells. Set starting quantities in B4 (chairs) and C4 (tables).

- Profit. Unit profits are in B5:C5. The objective cell is D5.

<small>Source Page 106 of 208</small>

### LEGO spreadsheet model

- Yellow cells. Set starting quantities in B4 (chairs) and C4 (tables).

- Profit. Unit profits are in B5:C5. The objective cell is D5.

- Constraints. Column D shows blocks used. Column E shows blocks available.

<small>Source Page 107 of 208</small>

### LEGO spreadsheet model
<small>Source Page 108 of 208</small>

### Solver parameters for LEGO

- Objective. Maximise profit in $D$5.

- Changing cells. Select $B$4:$C$4.

- Constraints. Add $D$8:$D$9 ≤ $E$8:$E$9.

- Non-negativity. Tick Make Unconstrained Variables Non-Negative.

- Choose Simplex LP and click Solve.

<small>Source Page 109 of 208</small>

### Optimal production plan

- Make 2 chairs and 2 tables. The maximum profit is 10(2) + 16(2) = 52.

- The plan matches the optimal corner (C, T) = (2, 2) from the graph.

<small>Source Page 110 of 208</small>

### Answer Report

- Profit reaches 52 at C = T = 2.

<small>Source Page 111 of 208</small>

### Answer Report

- Profit reaches 52 at C = T = 2.

- All 6 large blocks and 8 small blocks are used.

<small>Source Page 112 of 208</small>

### Answer Report

- Profit reaches 52 at C = T = 2.

- All 6 large blocks and 8 small blocks are used.

- Both constraints bind.

Their slack is 0.
<small>Source Page 113 of 208</small>

- Two types of objective functions (Maximize and Minimize).

- Three types of constraints (≥type, equation and ≤type).

- Three types of variables (≥type, unrestricted and ≤type).

<small>Source Page 114 of 208</small>

### Sensitivity

<small>Source Page 115 of 208</small>

How does the optimal solution respond to changes in the model?

<small>Source Page 116 of 208</small>

### Linear programming formulation

Decision variables C chairs and T tables

Objective function Maximize 10C + 16T

Constraints C + 2T ≤6 (large blocks)

2C + 2T ≤8 (small blocks) C, T ≥0 (non-negativity)

<small>Source Page 117 of 208</small>

What if we relax a constraint by increasing its right-hand side?

<small>Source Page 118 of 208</small>

### Changing availability of large blocks

2C + 2T = 8

```r
Tables (T)
```

(2, 2) C + 2T = 6
```r
Chairs (C)
```

∆= 0 :

C = 2, T = 2, Z∗= 52.

Z * = 52 + 6Δ Maximum profit

Large blocks available

<small>Source Page 119 of 208</small>

### Changing availability of large blocks

2C + 2T = 8

(1, 3)

```r
Tables (T)
```

C + 2T = 7 C + 2T = 6

```r
Chairs (C)
```

∆= 1 :

C = 2 −1 = 1, T = 2 + 1 = 3, Z∗= 52 + 6 = 58.

Z * = 52 + 6Δ

Maximum profit

Large blocks available

<small>Source Page 120 of 208</small>

### Changing availability of large blocks

∆= 2 :

C = 0, T = 4, Z∗= 64.

Chairs reach zero: upper limit.

(0, 4)

2C + 2T = 8

```r
Tables (T)
```
C + 2T = 8

C + 2T = 6

```r
Chairs (C)
```

Z * = 52 + 6Δ Maximum profit

Large blocks available

<small>Source Page 121 of 208</small>

### Changing availability of large blocks

∆= −2 :

C = 4, T = 0, Z∗= 40.

Tables reach zero: lower limit.

2C + 2T = 8

```r
Tables (T)
```

C + 2T = 6

C + 2T = 4 (4, 0)

```r
Chairs (C)
```

Z * = 52 + 6Δ Maximum profit

Large blocks available

<small>Source Page 122 of 208</small>

### Changing availability of large blocks

4 ≤L ≤8: Shadow price: 6.; Allowable decrease: 2; Allowable increase: 2

(0, 4)

2C + 2T = 8

```r
Tables (T)
```

C + 2T = 8 (2, 2) C + 2T = 6

C + 2T = 4 (4, 0)
```r
Chairs (C)
```

Z * = 52 + 6Δ Maximum profit

4–8 large blocks

Large blocks available

<small>Source Page 123 of 208</small>

### Shadow price of the large block

- Vary the available large blocks, L. Keep 8 small blocks and unit profits 10 and 16 fixed.

<small>Source Page 124 of 208</small>

### Shadow price of the large block

- Vary the available large blocks, L. Keep 8 small blocks and unit profits 10 and 16 fixed.

C + 2T = L and 2C + 2T = 8.

<small>Source Page 125 of 208</small>

### Shadow price of the large block

- Vary the available large blocks, L. Keep 8 small blocks and unit profits 10 and 16 fixed.

C + 2T = L and 2C + 2T = 8.

=⇒ C = 8 −L, T = L −4.

<small>Source Page 126 of 208</small>

### Shadow price of the large block

- Vary the available large blocks, L. Keep 8 small blocks and unit profits 10 and 16 fixed.

C + 2T = L and 2C + 2T = 8.

=⇒ C = 8 −L, T = L −4.

Z∗(L) = 10(8 −L) + 16(L −4) = 16 + 6L .
<small>Source Page 127 of 208</small>

### Shadow price of the large block

- Vary the available large blocks, L. Keep 8 small blocks and unit profits 10 and 16 fixed.

C + 2T = L and 2C + 2T = 8.

=⇒ C = 8 −L, T = L −4.

Z∗(L) = 10(8 −L) + 16(L −4) = 16 + 6L .

- One extra large block increases optimal profit by 6.

<small>Source Page 128 of 208</small>

### Shadow price of the large block

- Vary the available large blocks, L. Keep 8 small blocks and unit profits 10 and 16 fixed.

C + 2T = L and 2C + 2T = 8.

=⇒ C = 8 −L, T = L −4.

Z∗(L) = 10(8 −L) + 16(L −4) = 16 + 6L .

- One extra large block increases optimal profit by 6.

- Valid for 4 ≤L ≤8.

<small>Source Page 129 of 208</small>

### Changing availability of small blocks

2C + 2T = 8 Tables (T)

(2, 2)

C + 2T = 6

```r
Chairs (C)
```

∆= 0 :

C = 2, T = 2, Z∗= 52.

Z * = 52 + 2Δ Maximum profit

Small blocks available
<small>Source Page 130 of 208</small>

### Changing availability of small blocks

2C + 2T = 8 Tables (T)

2C + 2T = 10

(4, 1) C + 2T = 6

```r
Chairs (C)
```

∆= 2 :

C = 2 + 2 = 4, T = 2 −1 = 1, Z∗= 52 + 4 = 56.

Z * = 52 + 2Δ

Maximum profit

Small blocks available

<small>Source Page 131 of 208</small>

### Changing availability of small blocks

∆= 4 :

C = 6, T = 0, Z∗= 60.

Tables reach zero: upper limit.

2C + 2T = 8 2C + 2T = 12 Tables (T)

C + 2T = 6

(6, 0)

```r
Chairs (C)
```

Z * = 52 + 2Δ

Maximum profit

Small blocks available

<small>Source Page 132 of 208</small>

### Changing availability of small blocks

∆= −2 :
C = 0, T = 3, Z∗= 48.

Chairs reach zero: lower limit.

2C + 2T = 8 (0, 3) Tables (T)

2C + 2T = 6

C + 2T = 6

```r
Chairs (C)
```

Z * = 52 + 2Δ Maximum profit

Small blocks available

<small>Source Page 133 of 208</small>

### Changing availability of small blocks

6 ≤S ≤12: shadow price 2; allowable decrease 2, allowable increase 4.

2C + 2T = 8 2C + 2T = 12 (0, 3) Tables (T)

2C + 2T = 6

(2, 2)

C + 2T = 6

(6, 0)

```r
Chairs (C)
```

Z * = 52 + 2Δ Maximum profit

6–12 small blocks

Small blocks available

<small>Source Page 134 of 208</small>

### Changing availability of small blocks

Shift

Change in maximum profit

- LP shadow price: 2. Allowable decrease: 2; increase: 4 (6–12 small blocks).
<small>Source Page 135 of 208</small>

### Shadow price

- The shadow price measures the contribution of a resource to the profit in the vicinity

of the optimal solution. It denotes the change in optimal profit per additional unit of a resource.

- How to calculate it: Change one right-hand side, keeping the other inputs fixed.

- Range: The shadow price remains valid only within the allowable range of a total re‐

source.

<small>Source Page 136 of 208</small>

### Shadow prices in the final simplex table

S1 = sS: unused small blocks S2 = sL: unused large blocks

Basic CB C T S1 S2 RHS C

−1

T

−1 Cj −Zj

−2 −6

<small>Source Page 137 of 208</small>

### Shadow prices in the final simplex table

S1 = sS: unused small blocks S2 = sL: unused large blocks

Basic CB C T S1 S2 RHS C

−1

T

−1 Cj −Zj

−2 −6

<small>Source Page 138 of 208</small>

### Shadow prices in the final simplex table

S1 = sS: unused small blocks S2 = sL: unused large blocks
Basic CB C T S1 S2 RHS C

−1

T

−1 Cj −Zj

−2 −6

<small>Source Page 139 of 208</small>

### Allowable range of large block constraint

- Change large blocks from 6 to 6 + ∆. Keep 8 small blocks.

Basic RHS S2 New RHS C

−1 T

<small>Source Page 140 of 208</small>

### Allowable range of large block constraint

- Change large blocks from 6 to 6 + ∆. Keep 8 small blocks.

Basic RHS S2 New RHS C

−1 2 −∆ T

C = 2 + (−1)∆

<small>Source Page 141 of 208</small>

### Allowable range of large block constraint

- Change large blocks from 6 to 6 + ∆. Keep 8 small blocks.

Basic RHS S2 New RHS C

−1 2 −∆ T

2 + ∆

C = 2 + (−1)∆ T = 2 + (1)∆
<small>Source Page 142 of 208</small>

### Allowable range of large block constraint

- Change large blocks from 6 to 6 + ∆. Keep 8 small blocks.

Keep every basic value nonnegative:

Basic RHS S2 New RHS

C = 2 −∆≥0 ⇒ ∆≤2,

C

−1 2 −∆ T

2 + ∆

C = 2 + (−1)∆ T = 2 + (1)∆

<small>Source Page 143 of 208</small>

### Allowable range of large block constraint

- Change large blocks from 6 to 6 + ∆. Keep 8 small blocks.

Keep every basic value nonnegative:

Basic RHS S2 New RHS

C = 2 −∆≥0 ⇒ ∆≤2,

C

−1 2 −∆

T = 2 + ∆≥0 ⇒ ∆≥−2.

T

2 + ∆

C = 2 + (−1)∆ T = 2 + (1)∆

<small>Source Page 144 of 208</small>

### Allowable range of large block constraint

- Change large blocks from 6 to 6 + ∆. Keep 8 small blocks.

Basic RHS S2 New RHS C

−1 2 −∆ T

2 + ∆
C = 2 + (−1)∆ T = 2 + (1)∆

Keep every basic value nonnegative:

C = 2 −∆≥0 ⇒ ∆≤2, T = 2 + ∆≥0 ⇒ ∆≥−2.

−2 ≤∆≤2 ⇒ 4 ≤6 + ∆≤8 .

<small>Source Page 145 of 208</small>

### Allowable range of large block constraint

- Change large blocks from 6 to 6 + ∆. Keep 8 small blocks.

- Allowable increase: 2, when chairs reach zero. Allowable decrease: 2, when tables

reach zero.

Basic RHS S2 New RHS C

−1 2 −∆ T

2 + ∆

C = 2 + (−1)∆ T = 2 + (1)∆

Keep every basic value nonnegative:

C = 2 −∆≥0 ⇒ ∆≤2, T = 2 + ∆≥0 ⇒ ∆≥−2.

−2 ≤∆≤2 ⇒ 4 ≤6 + ∆≤8 .

<small>Source Page 146 of 208</small>

### Allowable range of large block constraint

- Change large blocks from 6 to 6 + ∆. Keep 8 small blocks.

- Allowable increase: 2, when chairs reach zero. Allowable decrease: 2, when tables

reach zero.

- Within this range, Z∗= 10(2 −∆) + 16(2 + ∆) = 52 + 6∆.

Basic RHS S2 New RHS C

−1 2 −∆ T

2 + ∆

C = 2 + (−1)∆ T = 2 + (1)∆

Keep every basic value nonnegative:

C = 2 −∆≥0 ⇒ ∆≤2, T = 2 + ∆≥0 ⇒ ∆≥−2.

−2 ≤∆≤2 ⇒ 4 ≤6 + ∆≤8 .
<small>Source Page 147 of 208</small>

### Allowable range of small block constraint

- Change small blocks from 8 to 8 + ∆. Keep 6 large blocks.

Basic RHS S1 New RHS C

T

−1

<small>Source Page 148 of 208</small>

### Allowable range of small block constraint

- Change small blocks from 8 to 8 + ∆. Keep 6 large blocks.

Basic RHS S1 New RHS C

2 + ∆ T

−1 C = (8 + ∆) −6 = 2 + ∆

<small>Source Page 149 of 208</small>

### Allowable range of small block constraint

- Change small blocks from 8 to 8 + ∆. Keep 6 large blocks.

Basic RHS S1 New RHS C

2 + ∆ T

−1

2 −1

2∆

C = (8 + ∆) −6 = 2 + ∆ T = 6 −1

```r
2(8 + ∆) = 2 −1
```

2∆
<small>Source Page 150 of 208</small>

### Allowable range of small block constraint

- Change small blocks from 8 to 8 + ∆. Keep 6 large blocks.

Keep every basic value nonnegative:

Basic RHS S1 New RHS

C = 2 + ∆≥0 ⇒ ∆≥−2,

C

2 + ∆ T

−1

2 −1

2∆

C = (8 + ∆) −6 = 2 + ∆ T = 6 −1

```r
2(8 + ∆) = 2 −1
```

2∆

<small>Source Page 151 of 208</small>

### Allowable range of small block constraint

- Change small blocks from 8 to 8 + ∆. Keep 6 large blocks.

Keep every basic value nonnegative:

Basic RHS S1 New RHS

C = 2 + ∆≥0 ⇒ ∆≥−2,

C

2 + ∆

T = 2 −1

2∆≥0 ⇒ ∆≤4.

T

−1

2 −1

2∆
C = (8 + ∆) −6 = 2 + ∆ T = 6 −1

```r
2(8 + ∆) = 2 −1
```

2∆

<small>Source Page 152 of 208</small>

### Allowable range of small block constraint

- Change small blocks from 8 to 8 + ∆. Keep 6 large blocks.

Basic RHS S1 New RHS C

2 + ∆ T

−1

2 −1

2∆

C = (8 + ∆) −6 = 2 + ∆ T = 6 −1

```r
2(8 + ∆) = 2 −1
```

2∆

Keep every basic value nonnegative:

C = 2 + ∆≥0 ⇒ ∆≥−2, T = 2 −1

2∆≥0 ⇒ ∆≤4.

−2 ≤∆≤4 ⇒ 6 ≤8 + ∆≤12 .

<small>Source Page 153 of 208</small>

### Allowable range of small block constraint

- Change small blocks from 8 to 8 + ∆. Keep 6 large blocks.

- Allowable decrease: 2, when chairs reach zero. Allowable increase: 4, when tables

reach zero.

Basic RHS S1 New RHS C

2 + ∆ T

−1

2 −1
2∆

C = (8 + ∆) −6 = 2 + ∆ T = 6 −1

```r
2(8 + ∆) = 2 −1
```

2∆

Keep every basic value nonnegative:

C = 2 + ∆≥0 ⇒ ∆≥−2, T = 2 −1

2∆≥0 ⇒ ∆≤4.

−2 ≤∆≤4 ⇒ 6 ≤8 + ∆≤12 .

<small>Source Page 154 of 208</small>

### Allowable range of small block constraint

- Change small blocks from 8 to 8 + ∆. Keep 6 large blocks.

- Allowable decrease: 2, when chairs reach zero. Allowable increase: 4, when tables

reach zero.

- Within this range, Z∗= 10(2 + ∆) + 16(2 −1

Basic RHS S1 New RHS C

2 + ∆ T

−1

2 −1

2∆

C = (8 + ∆) −6 = 2 + ∆ T = 6 −1

```r
2(8 + ∆) = 2 −1
```

2∆

Keep every basic value nonnegative:

C = 2 + ∆≥0 ⇒ ∆≥−2, T = 2 −1

2∆≥0 ⇒ ∆≤4.

−2 ≤∆≤4 ⇒ 6 ≤8 + ∆≤12 .

2∆) = 52 + 2∆.
<small>Source Page 155 of 208</small>

### Solver Sensitivity Report

- Large blocks. Shadow price 6. Allowable decrease 2, Allowable increase 2, range 4–8.

- Small blocks. Shadow price 2. Allowable decrease 2, Allowable increase 4, range 6–12.

<small>Source Page 156 of 208</small>

What if the contribution per unit of an entity to the objective function changes? In our case, the profit per chair (or table).

<small>Source Page 157 of 208</small>

### From the horizontal line to the navy edge

C + 2T = 6

(0, 3)

2C + 2T = 8

Tables T

16T = 48

Feasible region

Chairs C

Chair profit 0, slope 0. The line is parallel to the C-axis and the unique optimum is (0, 3).

<small>Source Page 158 of 208</small>

### From the horizontal line to the navy edge

C + 2T = 6

(0, 3)

2C + 2T = 8

Tables T

8C + 16T = 48

(2, 2)

Feasible region
Chairs C

Chair profit 8, slope −0.5. Every point on the navy edge from (0, 3) to (2, 2) is optimal.

<small>Source Page 159 of 208</small>

### From the original optimum to the gold edge

C + 2T = 6 2C + 2T = 8

Tables T

10C + 16T = 52

(2, 2)

Feasible region

Chairs C

Chair profit 10, slope −0.625. The line touches the feasible region only at (2, 2).

<small>Source Page 160 of 208</small>

### From the original optimum to the gold edge

Chair profit 16, slope −1. Every point on the gold edge from (2, 2) to (4, 0) is optimal.

Tables T

(2, 2)

Feasible region

Chairs C

C + 2T = 6 2C + 2T = 8

16C + 16T = 64

(4, 0)

<small>Source Page 161 of 208</small>

### Isoprofit line steeper than the gold boundary

Chair profit 20, slope −1.25 < −1. The line touches the feasible region only at (4, 0).

Tables T

Feasible region
Chairs C

C + 2T = 6 2C + 2T = 8

20C + 16T = 80

(4, 0)

<small>Source Page 162 of 208</small>

### Solver Sensitivity Report

Variable cells from the saved Excel Sensitivity Report.

- Chairs. Unit profit is 10. The allowable decrease is 2 and the allowable increase is 6.

<small>Source Page 163 of 208</small>

### Solver Sensitivity Report

Variable cells from the saved Excel Sensitivity Report.

- Chairs. Unit profit is 10. The allowable decrease is 2 and the allowable increase is 6.

- Tables. Unit profit is 16. The allowable decrease is 6 and the allowable increase is 4.

<small>Source Page 164 of 208</small>

### Solver Sensitivity Report

Variable cells from the saved Excel Sensitivity Report.

- Chairs. Unit profit is 10. The allowable decrease is 2 and the allowable increase is 6.

- Tables. Unit profit is 16. The allowable decrease is 6 and the allowable increase is 4.

- Change one unit profit at a time. The plan (2, 2) remains optimal for chair profit 8–16

or table profit 10–20, with the other profit fixed.

<small>Source Page 165 of 208</small>

### Solver Sensitivity Report

Variable cells from the saved Excel Sensitivity Report.

- Chairs. Unit profit is 10. The allowable decrease is 2 and the allowable increase is 6.

- Tables. Unit profit is 16. The allowable decrease is 6 and the allowable increase is 4.
- Change one unit profit at a time. The plan (2, 2) remains optimal for chair profit 8–16

or table profit 10–20, with the other profit fixed.

- Both products have a reduced cost of 0 in this solution.

<small>Source Page 166 of 208</small>

Cj −Zj

{z } reduced cost = Cj |{z} unit profit − X

i aijyi

{z } value of the resources used

Here, aij is how much of resource i one unit of product j uses, and yi is that resource’s shadow price.

<small>Source Page 167 of 208</small>

What if we introduce a new product (a new decision variable)?

<small>Source Page 168 of 208</small>

### Linear programming formulation with stools

- Decision variables C chairs, T tables, and Q stools.

Product Large blocks per unit Small blocks per unit Profit per unit Chair

Table

Stool

<small>Source Page 169 of 208</small>

### Linear programming formulation with stools

- Decision variables C chairs, T tables, and Q stools.

Product Large blocks per unit Small blocks per unit Profit per unit Chair

Table

Stool

Maximize Z = 10C + 16T + 7Q
<small>Source Page 170 of 208</small>

### Linear programming formulation with stools

- Decision variables C chairs, T tables, and Q stools.

Product Large blocks per unit Small blocks per unit Profit per unit Chair

Table

Stool

Maximize Z = 10C + 16T + 7Q subject to C + 2T + Q ≤6 (large blocks)

<small>Source Page 171 of 208</small>

### Linear programming formulation with stools

- Decision variables C chairs, T tables, and Q stools.

Product Large blocks per unit Small blocks per unit Profit per unit Chair

Table

Stool

Maximize Z = 10C + 16T + 7Q subject to C + 2T + Q ≤6 (large blocks)

2C + 2T + Q ≤8 (small blocks)

<small>Source Page 172 of 208</small>

### Linear programming formulation with stools

- Decision variables C chairs, T tables, and Q stools.

Product Large blocks per unit Small blocks per unit Profit per unit Chair

Table

Stool

Maximize Z = 10C + 16T + 7Q subject to C + 2T + Q ≤6 (large blocks)

2C + 2T + Q ≤8 (small blocks) C, T, Q ≥0 (non-negativity)

<small>Source Page 173 of 208</small>

### Does the optimal plan change?

Unit profit Cj
Basic CB C T Q S1 S2 RHS C

−1

T

−1

<small>Source Page 174 of 208</small>

### Does the optimal plan change?

Unit profit Cj

Basic CB C T Q S1 S2 RHS C

−1

T

−1 Zj

<small>Source Page 175 of 208</small>

### Does the optimal plan change?

Unit profit Cj

Basic CB C T Q S1 S2 RHS C

−1

T

−1 Zj

Cj −Zj

−1 −2 −6

<small>Source Page 176 of 208</small>

### Reduced cost of the stool

- The best plan is still 2 chairs and 2 tables, with 0 stools.

- Replace one table with two stools. Both use two large and two small blocks.

- The table contributes 16, and the two stools contribute 14.

- Profit falls by 2, or 1 per stool. That’s the stool’s reduced cost of −1.
Reduced cost for an decision variable is the amount by which we need to improve the contribution of that variable before they could enter the optimal solution on their own merit.

<small>Source Page 177 of 208</small>

### The stool’s reduced cost in the simplex table

S1 counts unused small blocks and S2 counts unused large blocks.

Unit profit Cj

Basic CB C T Q S1 S2 RHS C

−1

T

−1

<small>Source Page 178 of 208</small>

### The stool’s reduced cost in the simplex table

S1 counts unused small blocks and S2 counts unused large blocks.

Unit profit Cj

Basic CB C T Q S1 S2 RHS C

−1

T

−1 Zj

ZQ = 8. The blocks for one stool are worth 6 + 2 = 8 at the current shadow prices.

<small>Source Page 179 of 208</small>

### The stool’s reduced cost in the simplex table

S1 counts unused small blocks and S2 counts unused large blocks.

Unit profit Cj

Basic CB C T Q S1 S2 RHS C

−1

T

−1 Zj
Cj −Zj

−1 −2 −6

CQ −ZQ = 7 −8 = −1. Each stool contributes 1 less than the value of its blocks.

<small>Source Page 180 of 208</small>

### The stool’s reduced cost in the simplex table

S1 counts unused small blocks and S2 counts unused large blocks.

Unit profit Cj

Basic CB C T Q S1 S2 RHS C

−1

T

−1 Zj

Cj −Zj

−1 −2 −6

At a contribution of 8 per stool, a plan with stools can tie the original optimum. Above 8, it can improve on it.

<small>Source Page 181 of 208</small>

What if we introduce a new constraint?

<small>Source Page 182 of 208</small>

### Adding a new constraint

- If the existing optimal plan satisfies the new constraint, it remains optimal and earns

the same profit. The new constraint only rules out feasible plans that violate it. Every remaining plan was already competing with the old optimum.

<small>Source Page 183 of 208</small>

### Adding a new constraint

- If the existing optimal plan satisfies the new constraint, it remains optimal and earns

the same profit. The new constraint only rules out feasible plans that violate it. Every remaining plan was already competing with the old optimum.
- If the old plan violates the new constraint, it must change. If feasible plans remain, the

best profit stays the same when another equally good plan survives, and falls when the constraint rules out all the old optima.

<small>Source Page 184 of 208</small>

What if we change the coefficient of X or Y in a constraint?

<small>Source Page 185 of 208</small>

Changing a constraint coefficient can change the feasible region.

Solve the model again, even if the old plan is still feasible.

<small>Source Page 186 of 208</small>

### Duality

<small>Source Page 187 of 208</small>

### Linear programming formulation

Decision variables C chairs and T tables

Objective function Maximize 10C + 16T

Constraints C + 2T ≤6 (large blocks)

2C + 2T ≤8 (small blocks) C, T ≥0 (non-negativity)

<small>Source Page 188 of 208</small>

Let’s say, a buyer walks into your LEGO workshop and offers a price for each large block and each small block.

You can make furniture, or sell the blocks directly, or make some furniture and sell the blocks you have left.

What would make you willing to sell all your blocks?

In other words, how much atleast should the buyer pay for each type of block so that you are indifferent between selling the blocks to the buyer directly and making furniture and then sell yourself?
<small>Source Page 189 of 208</small>

### Compare two uses of the same blocks

yL is the buyer’s price per large block; yS is the buyer’s price per small block.

- Chair. One large block and two small blocks can earn 10 as a chair. If those blocks sell

for less than 10, you’d make the chair and sell the remaining blocks.

<small>Source Page 190 of 208</small>

### Compare two uses of the same blocks

yL is the buyer’s price per large block; yS is the buyer’s price per small block.

- Chair. One large block and two small blocks can earn 10 as a chair. If those blocks sell

for less than 10, you’d make the chair and sell the remaining blocks.

yL + 2yS ≥10

<small>Source Page 191 of 208</small>

### Compare two uses of the same blocks

yL is the buyer’s price per large block; yS is the buyer’s price per small block.

- Chair. One large block and two small blocks can earn 10 as a chair. If those blocks sell

for less than 10, you’d make the chair and sell the remaining blocks.

yL + 2yS ≥10

- Table. Two large and two small blocks can earn 16 as a table. Selling those blocks has

to bring in at least 16.

<small>Source Page 192 of 208</small>

### Compare two uses of the same blocks

yL is the buyer’s price per large block; yS is the buyer’s price per small block.

- Chair. One large block and two small blocks can earn 10 as a chair. If those blocks sell

for less than 10, you’d make the chair and sell the remaining blocks.

yL + 2yS ≥10

- Table. Two large and two small blocks can earn 16 as a table. Selling those blocks has

to bring in at least 16.

2yL + 2yS ≥16
<small>Source Page 193 of 208</small>

### The dual problem

What is the cheapest price the buyer can quote for the whole stock?

<small>Source Page 194 of 208</small>

### The dual problem

What is the cheapest price the buyer can quote for the whole stock?

Minimise W = 6yL + 8yS (buy all six large and eight small blocks)

<small>Source Page 195 of 208</small>

### The dual problem

What is the cheapest price the buyer can quote for the whole stock?

Minimise W = 6yL + 8yS (buy all six large and eight small blocks) subject to yL + 2yS ≥10 (compensate for the profit of a chair)

<small>Source Page 196 of 208</small>

### The dual problem

What is the cheapest price the buyer can quote for the whole stock?

Minimise W = 6yL + 8yS (buy all six large and eight small blocks) subject to yL + 2yS ≥10 (compensate for the profit of a chair)

2yL + 2yS ≥16 (compensate for the profit of a table)

<small>Source Page 197 of 208</small>

### The dual problem

What is the cheapest price the buyer can quote for the whole stock?

Minimise W = 6yL + 8yS (buy all six large and eight small blocks) subject to yL + 2yS ≥10 (compensate for the profit of a chair)

2yL + 2yS ≥16 (compensate for the profit of a table) yL, yS ≥0 (non-negativity constraints)
<small>Source Page 198 of 208</small>

### What is the cheapest acceptable offer?

- Optimal: yL = 6 and yS = 2.

- The buyer would pay 6(6) + 8(2) = 52 for all the blocks.

- The workshop can also earn 2(10) + 2(16) = 52 by making two chairs and two tables.

The workshop is indifferent. Any lower offer loses to making furniture.

- The dual prices are the shadow prices. One large block is worth 6 at the margin, and

one small block is worth 2.

<small>Source Page 199 of 208</small>

### Thank you

Rohit Mattu

<small>Source Page 200 of 208</small>

### Bob Manufacturers

<small>Source Page 201 of 208</small>

### Simple Product Mix

- Bob manufactures 2 types of mufflers with the following

- $10 contribution margin, Family type

- $18 contribution margin, Sport type

- Objective?

- Profit function: $10f + $18s

- Decision variables?

- number of family (f) and sport (s) mufflers to manufacture each month

- Goal?

- Unconstrained world: sell how many sport as possible
<small>Source Page 202 of 208</small>

### Simple Product Mix

- Resources needed

- In any given month: he is limited to 150 Brackets, 40 Labor Hours and 50 Alloy

- Contract forces to manufacture 5 sports mufflers per month

- Demand for family mufflers in a given month will not exceed 35 These constraints can

be modeled as a system of linear equations:

2f + 6s ≤150 (brackets) f ≤35 (maximum demand) f + .8s ≤40 (labor) s ≥5 (contractual obligation) f + 1.5s ≤50 (alloy)

<small>Source Page 203 of 208</small>

### Graphical Solution

- How do we solve the problem?

The problem has a very specific geometrical structure!

- This situation can be represented graphically

- Constraint imposed by brackets:

2f + 6s ≤150

- How to:

- Find value corresponding to s=0

- Find value corresponding for f =0

- Connect the points

<small>Source Page 204 of 208</small>

### Feasible Region

- Points on the line

- scenarios in which all available brackets are used

- Feasible Region

- covers all product mixes that the constraint allows

- Why infeasible above the line?

- Not enough brackets
<small>Source Page 205 of 208</small>

### Feasible Region

- Add the rest of the constraints 2f + 6s≤150 (brackets) f + .8s≤40 (labour) f + 1.5s≤50

(alloy) f≤35 (maximum demand) s≥5 (contractual obligation)

<small>Source Page 206 of 208</small>

### Feasible Region

2f + 6s≤150 (brackets) f + .8s≤40 (labour) f + 1.5s≤50 (alloy) f≤35 (maximum demand) s≥5 (contractual obligation)

<small>Source Page 207 of 208</small>

### Isoprofit Lines

- Isoprofit lines: lines corresponding to equal level of profit

- How to

- Profit function: $10f + $18s

- Isoprofit line: line with slope of -5/9, ratio of the contribution margin of family mufflers

to sports mufflers

<small>Source Page 208 of 208</small>

### Optimal Solution

- By combining the profit lines with the feasible region, you can identify the highest

profit line that touches a feasible point

- The optimal point is a mix of 25 family mufflers and 16.67 sport mufflers. This

combination will net Bob $550.


[↑ Back to the source list](#source-documents)

---

<a name="source-6"></a>

## Bobs Muffler.xlsx

<small>File type: XLSX · Reader pages 596–597 · [View source PDF](PDF%20Slides.pdf#page=596)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

### Worksheet: Sheet1

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (12 rows, 6 columns).

Row 1

Column 2 Family

Column 3 Sports

Marginal Value

Column 2 10

Column 3 18

Decision Variables

Column 2 25

Column 3 16.666666666666668

Row 4

Column 4 Total

Profit

Column 2 10

Column 3 18

Column 4 =SUMPRODUCT(B9:C9,B7:C7)

Constraints

Row 7

Column 4 Constraints

Column 6 Resources available
Brackets

Column 2 2

Column 3 6

Column 4 =SUMPRODUCT($B$7:$C$7,B13:C13)

Column 5 ≤

Column 6 150

Labor Hours

Column 2 1

Column 3 0.8

Column 4 =SUMPRODUCT($B$7:$C$7,B14:C14)

Column 5 ≤

Column 6 40

Alloy

Column 2 1

Column 3 1.5

Column 4 =SUMPRODUCT($B$7:$C$7,B15:C15)

Column 5 ≤

Column 6 50

Max Family

Column 2 1

Column 4 =SUMPRODUCT($B$7:$C$7,B16:C16)

Column 5 ≤

Column 6 35

Min Sports

Column 3 1

Column 4 =SUMPRODUCT($B$7:$C$7,B17:C17)

Column 5 ≥

Column 6 5

</details>


[↑ Back to the source list](#source-documents)

---

<a name="source-7"></a>

## ProductMix2.xlsx

<small>File type: XLSX · Reader pages 598–605 · [View source PDF](PDF%20Slides.pdf#page=598)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

### Worksheet: Answer Report 1

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (13 rows, 7 columns).

Worksheet: [ProductMix2.xlsx]Model

Report Created: 11/8/26 9:49:33 PM

Row 3

Microsoft Excel 16.110 Answer Report Result: Solver found a solution. All constraints and optimality conditions are satisfied.

Solver Engine

Row 5

Column 2 Engine: Simplex LP

Row 6

Column 2 Solution Time: 353.291 Seconds.

Row 7

Column 2 Iterations: 12 Subproblems: 0

Solver Options

Row 9

Column 2 Max Time 100 sec, Iterations 100, Precision 0.000001
Row 10

Column 2 Max Subproblems Unlimited, Max Integer Sols Unlimited, Integer Tolerance 5%, Solve Without Integer Constraints, Assume NonNegative

Objective Cell (Max)

Row 12

Column 2 Cell

Column 3 Name

Column 4 Original Value

Column 5 Final Value

Row 13

Column 2 $J$34

Column 3 Total_profit

Column 4 615812.5

Column 5 615812.5

### Worksheet: Sensitivity Report 1

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (15 rows, 8 columns).

Worksheet: [ProductMix2.xlsx]Model

Report Created: 11/8/26 9:49:34 PM

Variable Cells

Row 4

Column 4 Final

Column 5 Reduced

Column 6 Objective

Column 7 Allowable

Column 8 Allowable
Row 5

Column 2 Cell

Column 3 Name

Column 4 Value

Column 5 Cost

Column 6 Coefficient

Column 7 Increase

Column 8 Decrease

Row 6

Column 2 $B$20

Column 3 Number ------ on line 1 Model 1

Column 4 1500

Column 5 0

Column 6 127.5

Column 7 1e+30

Column 8 2.1250000000000187

Row 7

Column 2 $C$20

Column 3 Number ------ on line 1 Model 2

Column 4 0

Column 5 -20

Column 6 132

Column 7 20

Column 8 1e+30

Row 8

Column 2 $D$20

Column 3 Number ------ on line 1 Model 3

Column 4 0

Column 5 -10

Column 6 142

Column 7 10

Column 8 1e+30
Row 9

Column 2 $E$20

Column 3 Number ------ on line 1 Model 4

Column 4 124.99999999999993

Column 5 0

Column 6 152

Column 7 2.833333333333358

Column 8 1.7000000000000042

Row 10

Column 2 $F$20

Column 3 Number ------ on line 1 Model 5

Column 4 0

Column 5 -25.874999999999986

Column 6 142

Column 7 25.874999999999986

Column 8 1e+30

Row 11

Column 2 $G$20

Column 3 Number ------ on line 1 Model 6

Column 4 0

Column 5 -2.1250000000000044

Column 6 167

Column 7 2.1250000000000044

Column 8 1e+30

Row 12

Column 2 $H$20

Column 3 Number ------ on line 1 Model 7

Column 4 1000

Column 5 0

Column 6 172

Column 7 1e+30

Column 8 4.1250000000000195
Row 13

Column 2 $I$20

Column 3 Number ------ on line 1 Model 8

Column 4 0

Column 5 -6.7499999999999725

Column 6 177

Column 7 6.7499999999999725

Column 8 1e+30

Row 14

Column 2 $B$21

Column 3 Number ------ on line 2 Model 1

Column 4 0

Column 5 -2.125000000000018

Column 6 122

Column 7 2.125000000000018

Column 8 1e+30

Row 15

Column 2 $C$21

Column 3 Number ------ on line 2 Model 2

Column 4 0

Column 5 -20

Column 6 127.5

Column 7 20

Column 8 1e+30

### Worksheet: Model

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (13 rows, 9 columns).

Cost per labor hour assembling

Column 2 11

Cost per labor hour -------, line 1

Column 2 19
Cost per labor hour -------, line 2

Column 2 17

Inputs for assembling and ------- a computer

Row 5

Column 2 Model 1

Column 3 Model 2

Column 4 Model 3

Column 5 Model 4

Column 6 Model 5

Column 7 Model 6

Column 8 Model 7

Column 9 Model 8

Selling price

Column 2 350

Column 3 450

Column 4 460

Column 5 470

Column 6 500

Column 7 525

Column 8 530

Column 9 600

Cost of component parts

Column 2 150

Column 3 225

Column 4 225

Column 5 225

Column 6 250

Column 7 250

Column 8 250

Column 9 300
Labor hours for assembly

Column 2 4

Column 3 5

Column 4 5

Column 5 5

Column 6 5.5

Column 7 5.5

Column 8 5.5

Column 9 6

Labor hours for -------, line 1

Column 2 1.5

Column 3 2

Column 4 2

Column 5 2

Column 6 2.5

Column 7 2.5

Column 8 2.5

Column 9 3

Labor hours for -------, line 2

Column 2 2

Column 3 2.5

Column 4 2.5

Column 5 2.5

Column 6 3

Column 7 3

Column 8 3.5

Column 9 3.5

Unit margin, ------ on line 1

Column 2 =B$9-B$10-$B$3*B$11-$B4*B12

Column 3 =C$9-$B$3*C$11-$B4*C12-C$10

Column 4 =D$9-$B$3*D$11-$B4*D12-D$10

Column 5 =E$9-$B$3*E$11-$B4*E12-E$10

Column 6 =F$9-$B$3*F$11-$B4*F12-F$10

Column 7 =G$9-$B$3*G$11-$B4*G12-G$10

Column 8 =H$9-$B$3*H$11-$B4*H12-H$10

Column 9 =I$9-$B$3*I$11-$B4*I12-I$10
Unit margin, ------ on line 2

Column 2 =B$9-$B$3*B$11-$B5*B13-B$10

Column 3 =C$9-$B$3*C$11-$B5*C13-C$10

Column 4 =D$9-$B$3*D$11-$B5*D13-D$10

Column 5 =E$9-$B$3*E$11-$B5*E13-E$10

Column 6 =F$9-$B$3*F$11-$B5*F13-F$10

Column 7 =G$9-$B$3*G$11-$B5*G13-G$10

Column 8 =H$9-$B$3*H$11-$B5*H13-H$10

Column 9 =I$9-$B$3*I$11-$B5*I13-I$10

Assembling, ------- plan (# of computers)

</details>


[↑ Back to the source list](#source-documents)

---

<a name="source-8"></a>

## RBC1.xlsx

<small>File type: XLSX · Reader pages 606–617 · [View source PDF](PDF%20Slides.pdf#page=606)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

### Worksheet: Answer Report 1

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (13 rows, 7 columns).

Worksheet: [RBC1.xlsx]RBC

Report Created: 24/01/2021 13:59:41

Row 3

Microsoft Excel 16.0 Answer Report Result: Solver found a solution. All Constraints and optimality conditions are satisfied.

Solver Engine

Row 5

Column 2 Engine: Simplex LP

Row 6

Column 2 Solution Time: 0.016 Seconds.

Row 7

Column 2 Iterations: 6 Subproblems: 0

Solver Options

Row 9

Column 2 Max Time Unlimited, Iterations Unlimited, Precision 0.000001
Row 10

Column 2 Max Subproblems Unlimited, Max Integer Sols Unlimited, Integer Tolerance 1%, Assume NonNegative

Objective Cell (Max)

Row 12

Column 2 Cell

Column 3 Name

Column 4 Original Value

Column 5 Final Value

Row 13

Column 2 $E$18

Column 3 Contribution Margin Total Contribution

Column 4 676066.6666666666

Column 5 676066.6666666666

### Worksheet: Sensitivity Report 1

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (14 rows, 8 columns).

Worksheet: [RBC1.xlsx]RBC

Report Created: 24/01/2021 13:59:41

Variable Cells

Row 4

Column 4 Final

Column 5 Reduced

Column 6 Objective

Column 7 Allowable

Column 8 Allowable
Row 5

Column 2 Cell

Column 3 Name

Column 4 Value

Column 5 Cost

Column 6 Coefficient

Column 7 Increase

Column 8 Decrease

Row 6

Column 2 $B$4

Column 3 Grade A Whole

Column 4 525

Column 5 0

Column 6 246.66666666666666

Column 7 463.11111111111114

Column 8 64.88888888888886

Row 7

Column 2 $C$4

Column 3 Grade A Juice

Column 4 75

Column 5 0

Column 6 197.99999999999997

Column 7 64.8888888888889

Column 8 463.11111111111114

Row 8

Column 2 $D$4

Column 3 Grade A Paste

Column 4 0

Column 5 0

Column 6 222

Column 7 97.33333333333329

Column 8 1e+30
Row 9

Column 2 $B$5

Column 3 Grade B Whole

Column 4 175

Column 5 0

Column 6 246.66666666666663

Column 7 1389.3333333333335

Column 8 64.88888888888881

Row 10

Column 2 $C$5

Column 3 Grade B Juice

Column 4 225

Column 5 0

Column 6 198

Column 7 42.96296296296295

Column 8 154.37037037037038

Row 11

Column 2 $D$5

Column 3 Grade B Paste

Column 4 2000

Column 5 0

Column 6 222

Column 7 1e+30

Column 8 48.333333333333314

Constraints

Row 13

Column 4 Final

Column 5 Shadow

Column 6 Constraint

Column 7 Allowable

Column 8 Allowable
Row 14

Column 2 Cell

Column 3 Name

Column 4 Value

Column 5 Price

Column 6 R.H. Side

Column 7 Increase

Column 8 Decrease

### Worksheet: Limits Report 1

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (13 rows, 9 columns).

Worksheet: [RBC1.xlsx]RBC

Report Created: 24/01/2021 13:59:42

Row 3

Column 3 Objective

Row 4

Column 2 Cell

Column 3 Name

Column 4 Value

Row 5

Column 2 $E$18

Column 3 Contribution Margin Total Contribution

Column 4 676066.6666666666

Row 6

Column 3 Variable

Column 6 Lower

Column 7 Objective

Column 9 Upper
Row 7

Column 2 Cell

Column 3 Name

Column 4 Value

Column 6 Limit

Column 7 Result

Column 9 Limit

Row 8

Column 2 $B$4

Column 3 Grade A Whole

Column 4 525

Column 6 525

Column 7 676066.6666666666

Column 9 525

Row 9

Column 2 $C$4

Column 3 Grade A Juice

Column 4 75

Column 6 75

Column 7 676066.6666666666

Column 9 75

Row 10

Column 2 $D$4

Column 3 Grade A Paste

Column 4 0

Column 6 0

Column 7 676066.6666666666

Column 9 0

Row 11

Column 2 $B$5

Column 3 Grade B Whole

Column 4 175

Column 6 0

Column 7 632900

Column 9 175
Row 12

Column 2 $C$5

Column 3 Grade B Juice

Column 4 225

Column 6 0

Column 7 631516.6666666666

Column 9 225

Row 13

Column 2 $D$5

Column 3 Grade B Paste

Column 4 2000

Column 6 0

Column 7 232066.66666666666

Column 9 2000

### Worksheet: Sensitivity Report 2

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (14 rows, 8 columns).

Worksheet: [RBC1.xlsx]RBC

Report Created: 24/01/2021 14:17:20

Variable Cells

Row 4

Column 4 Final

Column 5 Reduced

Column 6 Objective

Column 7 Allowable

Column 8 Allowable
Row 5

Column 2 Cell

Column 3 Name

Column 4 Value

Column 5 Cost

Column 6 Coefficient

Column 7 Increase

Column 8 Decrease

Row 6

Column 2 $B$4

Column 3 Grade A Whole

Column 4 525

Column 5 0

Column 6 246.66666666666666

Column 7 463.11111111111114

Column 8 64.88888888888886

Row 7

Column 2 $C$4

Column 3 Grade A Juice

Column 4 75

Column 5 0

Column 6 197.99999999999997

Column 7 64.8888888888889

Column 8 463.11111111111114

Row 8

Column 2 $D$4

Column 3 Grade A Paste

Column 4 0

Column 5 0

Column 6 222

Column 7 97.33333333333329

Column 8 1e+30
Row 9

Column 2 $B$5

Column 3 Grade B Whole

Column 4 175

Column 5 0

Column 6 246.66666666666663

Column 7 1389.3333333333335

Column 8 64.88888888888881

Row 10

Column 2 $C$5

Column 3 Grade B Juice

Column 4 225

Column 5 0

Column 6 198

Column 7 42.96296296296295

Column 8 154.37037037037038

Row 11

Column 2 $D$5

Column 3 Grade B Paste

Column 4 2000

Column 5 0

Column 6 222

Column 7 1e+30

Column 8 48.333333333333314

Constraints

Row 13

Column 4 Final

Column 5 Shadow

Column 6 Constraint

Column 7 Allowable

Column 8 Allowable
Row 14

Column 2 Cell

Column 3 Name

Column 4 Value

Column 5 Price

Column 6 R.H. Side

Column 7 Increase

Column 8 Decrease

### Worksheet: RBC

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (15 rows, 8 columns).

MIX DECISION

Column 2 Whole

Column 3 Juice

Column 4 Paste

Column 5 Total Required

Column 6 Available

Column 8 This answers question 1

Grade A

Column 2 525

Column 3 75

Column 4 0

Column 5 =SUM(B4:D4)

Column 6 600

Column 8 The sensitivity report answers the second bulletpoint in question 2

Grade B

Column 2 175

Column 3 225

Column 4 2000

Column 5 =SUM(B5:D5)

Column 6 2400
Total Production

Column 2 =SUM(B4:B5)

Column 3 =SUM(C4:C5)

Column 4 =SUM(D4:D5)

Demand

Column 2 14400

Column 3 1000

Column 4 2000

Row 6

Column 7 This allows us to answer the

QUALITY

Column 2 Whole

Column 3 Juice

Column 4 Paste

Column 5 Quality

Grade A

Column 2 =$E10*B4

Column 3 =$E10*C4

Column 4 =$E10*D4

Column 5 9

Grade B

Column 2 =$E11*B5

Column 3 =$E11*C5

Column 4 =$E11*D5

Column 5 5

Total Quality

Column 2 =SUM(B10:B11)

Column 3 =SUM(C10:C11)

Column 4 =SUM(D10:D11)
Required Total Quality

Column 2 =B15*B6

Column 3 =C15*C6

Column 4 =D15*D6

Average Quality

Column 2 =B12/B6

Column 3 =C12/C6

Column 4 =D12/D6

Required Average Quality

Column 2 8

Column 3 6

Column 4 5

Contribution

Column 2 Whole

Column 3 Juice

Column 4 Paste

Column 5 Total Contribution

Contribution Margin

Column 2 =1000*4.44/18

Column 3 198

Column 4 222

Column 5 =SUMPRODUCT(B6:D6,B18:D18)

</details>


[↑ Back to the source list](#source-documents)

---

<a name="source-9"></a>

## RBC2.xlsx

<small>File type: XLSX · Reader pages 618–629 · [View source PDF](PDF%20Slides.pdf#page=618)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

### Worksheet: Answer Report 1

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (13 rows, 7 columns).

Worksheet: [RBC1.xlsx]RBC

Report Created: 24/01/2021 13:59:41

Row 3

Microsoft Excel 16.0 Answer Report Result: Solver found a solution. All Constraints and optimality conditions are satisfied.

Solver Engine

Row 5

Column 2 Engine: Simplex LP

Row 6

Column 2 Solution Time: 0.016 Seconds.

Row 7

Column 2 Iterations: 6 Subproblems: 0

Solver Options

Row 9

Column 2 Max Time Unlimited, Iterations Unlimited, Precision 0.000001
Row 10

Column 2 Max Subproblems Unlimited, Max Integer Sols Unlimited, Integer Tolerance 1%, Assume NonNegative

Objective Cell (Max)

Row 12

Column 2 Cell

Column 3 Name

Column 4 Original Value

Column 5 Final Value

Row 13

Column 2 $E$18

Column 3 Contribution Margin Total Contribution

Column 4 676066.6666666666

Column 5 676066.6666666666

### Worksheet: Sensitivity Report 1

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (14 rows, 8 columns).

Worksheet: [RBC1.xlsx]RBC

Report Created: 24/01/2021 13:59:41

Variable Cells

Row 4

Column 4 Final

Column 5 Reduced

Column 6 Objective

Column 7 Allowable

Column 8 Allowable
Row 5

Column 2 Cell

Column 3 Name

Column 4 Value

Column 5 Cost

Column 6 Coefficient

Column 7 Increase

Column 8 Decrease

Row 6

Column 2 $B$4

Column 3 Grade A Whole

Column 4 525

Column 5 0

Column 6 246.66666666666666

Column 7 463.11111111111114

Column 8 64.88888888888886

Row 7

Column 2 $C$4

Column 3 Grade A Juice

Column 4 75

Column 5 0

Column 6 197.99999999999997

Column 7 64.8888888888889

Column 8 463.11111111111114

Row 8

Column 2 $D$4

Column 3 Grade A Paste

Column 4 0

Column 5 0

Column 6 222

Column 7 97.33333333333329

Column 8 1e+30
Row 9

Column 2 $B$5

Column 3 Grade B Whole

Column 4 175

Column 5 0

Column 6 246.66666666666663

Column 7 1389.3333333333335

Column 8 64.88888888888881

Row 10

Column 2 $C$5

Column 3 Grade B Juice

Column 4 225

Column 5 0

Column 6 198

Column 7 42.96296296296295

Column 8 154.37037037037038

Row 11

Column 2 $D$5

Column 3 Grade B Paste

Column 4 2000

Column 5 0

Column 6 222

Column 7 1e+30

Column 8 48.333333333333314

Constraints

Row 13

Column 4 Final

Column 5 Shadow

Column 6 Constraint

Column 7 Allowable

Column 8 Allowable
Row 14

Column 2 Cell

Column 3 Name

Column 4 Value

Column 5 Price

Column 6 R.H. Side

Column 7 Increase

Column 8 Decrease

### Worksheet: Limits Report 1

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (13 rows, 9 columns).

Worksheet: [RBC1.xlsx]RBC

Report Created: 24/01/2021 13:59:42

Row 3

Column 3 Objective

Row 4

Column 2 Cell

Column 3 Name

Column 4 Value

Row 5

Column 2 $E$18

Column 3 Contribution Margin Total Contribution

Column 4 676066.6666666666

Row 6

Column 3 Variable

Column 6 Lower

Column 7 Objective

Column 9 Upper
Row 7

Column 2 Cell

Column 3 Name

Column 4 Value

Column 6 Limit

Column 7 Result

Column 9 Limit

Row 8

Column 2 $B$4

Column 3 Grade A Whole

Column 4 525

Column 6 525

Column 7 676066.6666666666

Column 9 525

Row 9

Column 2 $C$4

Column 3 Grade A Juice

Column 4 75

Column 6 75

Column 7 676066.6666666666

Column 9 75

Row 10

Column 2 $D$4

Column 3 Grade A Paste

Column 4 0

Column 6 0

Column 7 676066.6666666666

Column 9 0

Row 11

Column 2 $B$5

Column 3 Grade B Whole

Column 4 175

Column 6 0

Column 7 632900

Column 9 175
Row 12

Column 2 $C$5

Column 3 Grade B Juice

Column 4 225

Column 6 0

Column 7 631516.6666666666

Column 9 225

Row 13

Column 2 $D$5

Column 3 Grade B Paste

Column 4 2000

Column 6 0

Column 7 232066.66666666666

Column 9 2000

### Worksheet: Sensitivity Report 2

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (14 rows, 8 columns).

Worksheet: [RBC1.xlsx]RBC

Report Created: 24/01/2021 14:17:20

Variable Cells

Row 4

Column 4 Final

Column 5 Reduced

Column 6 Objective

Column 7 Allowable

Column 8 Allowable
Row 5

Column 2 Cell

Column 3 Name

Column 4 Value

Column 5 Cost

Column 6 Coefficient

Column 7 Increase

Column 8 Decrease

Row 6

Column 2 $B$4

Column 3 Grade A Whole

Column 4 525

Column 5 0

Column 6 246.66666666666666

Column 7 463.11111111111114

Column 8 64.88888888888886

Row 7

Column 2 $C$4

Column 3 Grade A Juice

Column 4 75

Column 5 0

Column 6 197.99999999999997

Column 7 64.8888888888889

Column 8 463.11111111111114

Row 8

Column 2 $D$4

Column 3 Grade A Paste

Column 4 0

Column 5 0

Column 6 222

Column 7 97.33333333333329

Column 8 1e+30
Row 9

Column 2 $B$5

Column 3 Grade B Whole

Column 4 175

Column 5 0

Column 6 246.66666666666663

Column 7 1389.3333333333335

Column 8 64.88888888888881

Row 10

Column 2 $C$5

Column 3 Grade B Juice

Column 4 225

Column 5 0

Column 6 198

Column 7 42.96296296296295

Column 8 154.37037037037038

Row 11

Column 2 $D$5

Column 3 Grade B Paste

Column 4 2000

Column 5 0

Column 6 222

Column 7 1e+30

Column 8 48.333333333333314

Constraints

Row 13

Column 4 Final

Column 5 Shadow

Column 6 Constraint

Column 7 Allowable

Column 8 Allowable
Row 14

Column 2 Cell

Column 3 Name

Column 4 Value

Column 5 Price

Column 6 R.H. Side

Column 7 Increase

Column 8 Decrease

### Worksheet: RBC

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (14 rows, 6 columns).

MIX DECISION

Column 2 Whole

Column 3 Juice

Column 4 Paste

Column 5 Total Required

Column 6 Available

Grade A

Column 2 615

Column 3 65.00000000000006

Column 4 0

Column 5 =SUM(B4:D4)

Column 6 680

Grade B

Column 2 204.99999999999997

Column 3 195.00000000000017

Column 4 2000

Column 5 =SUM(B5:D5)

Column 6 2400

Total Production

Column 2 =SUM(B4:B5)

Column 3 =SUM(C4:C5)

Column 4 =SUM(D4:D5)
Demand

Column 2 14400

Column 3 1000

Column 4 2000

QUALITY

Column 2 Whole

Column 3 Juice

Column 4 Paste

Column 5 Quality

Grade A

Column 2 =$E10*B4

Column 3 =$E10*C4

Column 4 =$E10*D4

Column 5 9

Grade B

Column 2 =$E11*B5

Column 3 =$E11*C5

Column 4 =$E11*D5

Column 5 5

Total Quality

Column 2 =SUM(B10:B11)

Column 3 =SUM(C10:C11)

Column 4 =SUM(D10:D11)

Required Total Quality

Column 2 =B15*B6

Column 3 =C15*C6

Column 4 =D15*D6

Average Quality

Column 2 =B12/B6

Column 3 =C12/C6

Column 4 =D12/D6
Required Average Quality

Column 2 8

Column 3 6

Column 4 5

Contribution

Column 2 Whole

Column 3 Juice

Column 4 Paste

Column 5 Total Contribution

Column 6 Additional expense

Contribution Margin

Column 2 =1000*4.44/18

Column 3 198

Column 4 222

Column 5 =SUMPRODUCT(B6:D6,B18:D18)

Column 6 80000

</details>


[↑ Back to the source list](#source-documents)

---

<a name="source-10"></a>

## RBC3.xlsx

<small>File type: XLSX · Reader pages 630–641 · [View source PDF](PDF%20Slides.pdf#page=630)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

### Worksheet: Answer Report 1

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (13 rows, 7 columns).

Worksheet: [RBC1.xlsx]RBC

Report Created: 24/01/2021 13:59:41

Row 3

Microsoft Excel 16.0 Answer Report Result: Solver found a solution. All Constraints and optimality conditions are satisfied.

Solver Engine

Row 5

Column 2 Engine: Simplex LP

Row 6

Column 2 Solution Time: 0.016 Seconds.

Row 7

Column 2 Iterations: 6 Subproblems: 0

Solver Options

Row 9

Column 2 Max Time Unlimited, Iterations Unlimited, Precision 0.000001
Row 10

Column 2 Max Subproblems Unlimited, Max Integer Sols Unlimited, Integer Tolerance 1%, Assume NonNegative

Objective Cell (Max)

Row 12

Column 2 Cell

Column 3 Name

Column 4 Original Value

Column 5 Final Value

Row 13

Column 2 $E$18

Column 3 Contribution Margin Total Contribution

Column 4 676066.6666666666

Column 5 676066.6666666666

### Worksheet: Sensitivity Report 1

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (14 rows, 8 columns).

Worksheet: [RBC1.xlsx]RBC

Report Created: 24/01/2021 13:59:41

Variable Cells

Row 4

Column 4 Final

Column 5 Reduced

Column 6 Objective

Column 7 Allowable

Column 8 Allowable
Row 5

Column 2 Cell

Column 3 Name

Column 4 Value

Column 5 Cost

Column 6 Coefficient

Column 7 Increase

Column 8 Decrease

Row 6

Column 2 $B$4

Column 3 Grade A Whole

Column 4 525

Column 5 0

Column 6 246.66666666666666

Column 7 463.11111111111114

Column 8 64.88888888888886

Row 7

Column 2 $C$4

Column 3 Grade A Juice

Column 4 75

Column 5 0

Column 6 197.99999999999997

Column 7 64.8888888888889

Column 8 463.11111111111114

Row 8

Column 2 $D$4

Column 3 Grade A Paste

Column 4 0

Column 5 0

Column 6 222

Column 7 97.33333333333329

Column 8 1e+30
Row 9

Column 2 $B$5

Column 3 Grade B Whole

Column 4 175

Column 5 0

Column 6 246.66666666666663

Column 7 1389.3333333333335

Column 8 64.88888888888881

Row 10

Column 2 $C$5

Column 3 Grade B Juice

Column 4 225

Column 5 0

Column 6 198

Column 7 42.96296296296295

Column 8 154.37037037037038

Row 11

Column 2 $D$5

Column 3 Grade B Paste

Column 4 2000

Column 5 0

Column 6 222

Column 7 1e+30

Column 8 48.333333333333314

Constraints

Row 13

Column 4 Final

Column 5 Shadow

Column 6 Constraint

Column 7 Allowable

Column 8 Allowable
Row 14

Column 2 Cell

Column 3 Name

Column 4 Value

Column 5 Price

Column 6 R.H. Side

Column 7 Increase

Column 8 Decrease

### Worksheet: Limits Report 1

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (13 rows, 9 columns).

Worksheet: [RBC1.xlsx]RBC

Report Created: 24/01/2021 13:59:42

Row 3

Column 3 Objective

Row 4

Column 2 Cell

Column 3 Name

Column 4 Value

Row 5

Column 2 $E$18

Column 3 Contribution Margin Total Contribution

Column 4 676066.6666666666

Row 6

Column 3 Variable

Column 6 Lower

Column 7 Objective

Column 9 Upper
Row 7

Column 2 Cell

Column 3 Name

Column 4 Value

Column 6 Limit

Column 7 Result

Column 9 Limit

Row 8

Column 2 $B$4

Column 3 Grade A Whole

Column 4 525

Column 6 525

Column 7 676066.6666666666

Column 9 525

Row 9

Column 2 $C$4

Column 3 Grade A Juice

Column 4 75

Column 6 75

Column 7 676066.6666666666

Column 9 75

Row 10

Column 2 $D$4

Column 3 Grade A Paste

Column 4 0

Column 6 0

Column 7 676066.6666666666

Column 9 0

Row 11

Column 2 $B$5

Column 3 Grade B Whole

Column 4 175

Column 6 0

Column 7 632900

Column 9 175
Row 12

Column 2 $C$5

Column 3 Grade B Juice

Column 4 225

Column 6 0

Column 7 631516.6666666666

Column 9 225

Row 13

Column 2 $D$5

Column 3 Grade B Paste

Column 4 2000

Column 6 0

Column 7 232066.66666666666

Column 9 2000

### Worksheet: Sensitivity Report 2

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (14 rows, 8 columns).

Worksheet: [RBC3.xlsx]RBC

Report Created: 24/01/2021 14:21:46

Variable Cells

Row 4

Column 4 Final

Column 5 Reduced

Column 6 Objective

Column 7 Allowable

Column 8 Allowable
Row 5

Column 2 Cell

Column 3 Name

Column 4 Value

Column 5 Cost

Column 6 Coefficient

Column 7 Increase

Column 8 Decrease

Row 6

Column 2 $B$4

Column 3 Grade A Whole

Column 4 615

Column 5 0

Column 6 246.66666666666666

Column 7 463.11111111111114

Column 8 64.88888888888886

Row 7

Column 2 $C$4

Column 3 Grade A Juice

Column 4 65.00000000000006

Column 5 0

Column 6 197.99999999999997

Column 7 64.8888888888889

Column 8 463.11111111111114

Row 8

Column 2 $D$4

Column 3 Grade A Paste

Column 4 0

Column 5 0

Column 6 222

Column 7 97.33333333333329

Column 8 1e+30
Row 9

Column 2 $B$5

Column 3 Grade B Whole

Column 4 204.99999999999997

Column 5 0

Column 6 246.66666666666663

Column 7 1389.3333333333335

Column 8 64.88888888888881

Row 10

Column 2 $C$5

Column 3 Grade B Juice

Column 4 195.00000000000017

Column 5 0

Column 6 198

Column 7 42.96296296296295

Column 8 154.37037037037038

Row 11

Column 2 $D$5

Column 3 Grade B Paste

Column 4 2000

Column 5 0

Column 6 222

Column 7 1e+30

Column 8 48.333333333333314

Constraints

Row 13

Column 4 Final

Column 5 Shadow

Column 6 Constraint

Column 7 Allowable

Column 8 Allowable
Row 14

Column 2 Cell

Column 3 Name

Column 4 Value

Column 5 Price

Column 6 R.H. Side

Column 7 Increase

Column 8 Decrease

### Worksheet: RBC

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (14 rows, 6 columns).

MIX DECISION

Column 2 Whole

Column 3 Juice

Column 4 Paste

Column 5 Total Required

Column 6 Available

Grade A

Column 2 615

Column 3 65.00000000000006

Column 4 0

Column 5 =SUM(B4:D4)

Column 6 680

Grade B

Column 2 204.99999999999997

Column 3 195.00000000000017

Column 4 2000

Column 5 =SUM(B5:D5)

Column 6 2400

Total Production

Column 2 =SUM(B4:B5)

Column 3 =SUM(C4:C5)

Column 4 =SUM(D4:D5)
Demand

Column 2 14400

Column 3 1000

Column 4 2000

QUALITY

Column 2 Whole

Column 3 Juice

Column 4 Paste

Column 5 Quality

Grade A

Column 2 =$E10*B4

Column 3 =$E10*C4

Column 4 =$E10*D4

Column 5 9

Grade B

Column 2 =$E11*B5

Column 3 =$E11*C5

Column 4 =$E11*D5

Column 5 5

Total Quality

Column 2 =SUM(B10:B11)

Column 3 =SUM(C10:C11)

Column 4 =SUM(D10:D11)

Required Total Quality

Column 2 =B15*B6

Column 3 =C15*C6

Column 4 =D15*D6

Average Quality

Column 2 =B12/B6

Column 3 =C12/C6

Column 4 =D12/D6
Required Average Quality

Column 2 8

Column 3 6

Column 4 5

Contribution

Column 2 Whole

Column 3 Juice

Column 4 Paste

Column 5 Total Contribution

Column 6 Additional expense

Contribution Margin

Column 2 =1000*4.44/18

Column 3 198

Column 4 222

Column 5 =SUMPRODUCT(B6:D6,B18:D18)

Column 6 80000

</details>


[↑ Back to the source list](#source-documents)

---

<a name="source-11"></a>

## RBC6.xlsx

<small>File type: XLSX · Reader pages 642–648 · [View source PDF](PDF%20Slides.pdf#page=642)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

### Worksheet: RBC Good Year

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (14 rows, 8 columns).

MIX DECISION

Column 2 Whole

Column 3 Juice

Column 4 Paste

Column 5 Total Required

Column 6 Available

Column 7 Purchased

Column 8 Max Purchase

Grade A

Column 2 230.769230769231

Column 3 0

Column 4 0

Column 5 =SUM(B4:D4)

Column 6 =0.1*G4

Column 7 2307.692307692308

Column 8 15000

Grade B

Column 2 76.923076923077

Column 3 0

Column 4 2000.0000000000002

Column 5 =SUM(B5:D5)

Column 6 =0.9*G4

Total Production

Column 2 =SUM(B4:B5)

Column 3 =SUM(C4:C5)

Column 4 =SUM(D4:D5)
Demand

Column 2 14400

Column 3 1000

Column 4 2000

QUALITY

Column 2 Whole

Column 3 Juice

Column 4 Paste

Column 5 Quality

Grade A

Column 2 =$E10*B4

Column 3 =$E10*C4

Column 4 =$E10*D4

Column 5 9

Grade B

Column 2 =$E11*B5

Column 3 =$E11*C5

Column 4 =$E11*D5

Column 5 5

Total Quality

Column 2 =SUM(B10:B11)

Column 3 =SUM(C10:C11)

Column 4 =SUM(D10:D11)

Required Total Quality

Column 2 =B15*B6

Column 3 =C15*C6

Column 4 =D15*D6

Average Quality

Column 2 =B12/B6

Column 3 =C12/C6

Column 4 =D12/D6
Required Average Quality

Column 2 8

Column 3 6

Column 4 5

Contribution

Column 2 Whole

Column 3 Juice

Column 4 Paste

Column 5 Total Contribution

Column 6 Tomato cost

Column 7 Profit

Contribution Margin

Column 2 =1000*4.44/18

Column 3 198

Column 4 222

Column 5 =SUMPRODUCT(B6:D6,B18:D18)

Column 6 =0.2*G4*1000

Column 7 =E18-F18

### Worksheet: Sheet1

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (5 rows, 8 columns).

N

13000 8000

513533 275333

Column 7 To order

Column 8 Profit

P

13000 2727

513533 77939

Column 7 13000

Column 8 513533
Row 3

Column 5 0.25

Column 6 sunny

Column 8 =H3*0.25

Row 4

Column 5 0.5

Column 6 normal

Column 8 =H3*0.5

Row 5

Column 5 0.25

Column 6 poor

Column 8 =H3*0.25

### Worksheet: Blight

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (14 rows, 8 columns).

MIX DECISION

Column 2 Whole

Column 3 Juice

Column 4 Paste

Column 5 Total Required

Column 6 Available

Column 7 Purchased

Column 8 Max Purchase

Grade A

Column 2 230.769230769231

Column 3 0

Column 4 0

Column 5 =SUM(B4:D4)

Column 6 =0.1*G4

Column 7 2307.692307692308

Column 8 15000
Grade B

Column 2 76.923076923077

Column 3 0

Column 4 2000.0000000000002

Column 5 =SUM(B5:D5)

Column 6 =G4-F4

Total Production

Column 2 =SUM(B4:B5)

Column 3 =SUM(C4:C5)

Column 4 =SUM(D4:D5)

Demand

Column 2 14400

Column 3 1000

Column 4 2000

QUALITY

Column 2 Whole

Column 3 Juice

Column 4 Paste

Column 5 Quality

Grade A

Column 2 =$E10*B4

Column 3 =$E10*C4

Column 4 =$E10*D4

Column 5 9

Grade B

Column 2 =$E11*B5

Column 3 =$E11*C5

Column 4 =$E11*D5

Column 5 5

Total Quality

Column 2 =SUM(B10:B11)

Column 3 =SUM(C10:C11)

Column 4 =SUM(D10:D11)
Required Total Quality

Column 2 =B15*B6

Column 3 =C15*C6

Column 4 =D15*D6

Average Quality

Column 2 =B12/B6

Column 3 =C12/C6

Column 4 =D12/D6

Required Average Quality

Column 2 8

Column 3 6

Column 4 5

Contribution

Column 2 Whole

Column 3 Juice

Column 4 Paste

Column 5 Total Contribution

Column 6 Tomato cost

Column 7 Profit

Contribution Margin

Column 2 =1000*4.44/18

Column 3 198

Column 4 222

Column 5 =SUMPRODUCT(B6:D6,B18:D18)

Column 6 =0.2*G4*1000

Column 7 =E18-F18

### Worksheet: Average

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (4 rows, 9 columns).

Scenarios

Column 2 Probability

Column 3 Profit
No blight

Column 2 0.95

Column 3 685200

Blight

Column 2 =1-B4

Column 3 =Blight!G18

Expected profit

Column 2 =SUMPRODUCT(B4:B5,C4:C5)

</details>


[↑ Back to the source list](#source-documents)

---

<a name="source-12"></a>

## RBCTemplate.xlsx

<small>File type: XLSX · Reader pages 649–651 · [View source PDF](PDF%20Slides.pdf#page=649)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

### Worksheet: RBC

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (14 rows, 6 columns).

MIX DECISION

Column 2 Whole

Column 3 Juice

Column 4 Paste

Column 5 Total Required

Column 6 Available

Grade A

Column 2 1

Column 3 1

Column 4 1

Column 5 =SUM(B4:D4)

Column 6 600

Grade B

Column 2 1

Column 3 1

Column 4 1

Column 5 =SUM(B5:D5)

Column 6 2400

Total Production

Column 2 =SUM(B4:B5)

Column 3 =SUM(C4:C5)

Column 4 =SUM(D4:D5)
Demand

Column 2 14400

Column 3 1000

Column 4 2000

QUALITY

Column 2 Whole

Column 3 Juice

Column 4 Paste

Column 5 Quality

Grade A

Column 2 =$E10*B4

Column 3 =$E10*C4

Column 4 =$E10*D4

Column 5 9

Grade B

Column 2 =$E11*B5

Column 3 =$E11*C5

Column 4 =$E11*D5

Column 5 5

Total Quality

Column 2 =SUM(B10:B11)

Column 3 =SUM(C10:C11)

Column 4 =SUM(D10:D11)

Required Total Quality

Column 2 =B15*B6

Column 3 =C15*C6

Column 4 =D15*D6

Average Quality

Column 2 =B12/B6

Column 3 =C12/C6

Column 4 =D12/D6
Required Average Quality

Column 2 8

Column 3 6

Column 4 5

Contribution

Column 2 Whole

Column 3 Juice

Column 4 Paste

Column 5 Total Contribution

Contribution Margin

Column 2 =1000*4.44/18

Column 3 198

Column 4 222

Column 5 =SUMPRODUCT(B6:D6,B18:D18)

</details>


[↑ Back to the source list](#source-documents)

---

<a name="source-13"></a>

## RBCTemplate.xlsx

<small>File type: XLSX · Reader pages 652–654 · [View source PDF](PDF%20Slides.pdf#page=652)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

### Worksheet: RBC

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (14 rows, 6 columns).

MIX DECISION

Column 2 Whole

Column 3 Juice

Column 4 Paste

Column 5 Total Required

Column 6 Available

Grade A

Column 2 1

Column 3 1

Column 4 1

Column 5 =SUM(B4:D4)

Column 6 600

Grade B

Column 2 1

Column 3 1

Column 4 1

Column 5 =SUM(B5:D5)

Column 6 2400

Total Production

Column 2 =SUM(B4:B5)

Column 3 =SUM(C4:C5)

Column 4 =SUM(D4:D5)
Demand

Column 2 14400

Column 3 1000

Column 4 2000

QUALITY

Column 2 Whole

Column 3 Juice

Column 4 Paste

Column 5 Quality

Grade A

Column 2 =$E10*B4

Column 3 =$E10*C4

Column 4 =$E10*D4

Column 5 9

Grade B

Column 2 =$E11*B5

Column 3 =$E11*C5

Column 4 =$E11*D5

Column 5 5

Total Quality

Column 2 =SUM(B10:B11)

Column 3 =SUM(C10:C11)

Column 4 =SUM(D10:D11)

Required Total Quality

Column 2 =B15*B6

Column 3 =C15*C6

Column 4 =D15*D6

Average Quality

Column 2 =B12/B6

Column 3 =C12/C6

Column 4 =D12/D6
Required Average Quality

Column 2 8

Column 3 6

Column 4 5

Contribution

Column 2 Whole

Column 3 Juice

Column 4 Paste

Column 5 Total Contribution

Contribution Margin

Column 2 =1000*4.44/18

Column 3 198

Column 4 222

Column 5 =SUMPRODUCT(B6:D6,B18:D18)

</details>


[↑ Back to the source list](#source-documents)

---

<a name="source-14"></a>

## Red Brand Canners - Solution.xlsx

<small>File type: XLSX · Reader pages 655–661 · [View source PDF](PDF%20Slides.pdf#page=655)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

### Worksheet: RBC Model

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (13 rows, 9 columns).

Monetary inputs

Column 2 Whole

Column 3 Juice

Column 4 Paste

Contribution per case

Column 2 4.44

Column 3 3.96

Column 4 5.55

pounds per case

Column 2 18

Column 3 20

Column 4 25

Contribution/ pound

Column 2 =B4/B5

Column 3 =C4/C5

Column 4 =D4/D5

Quality level - Inputs

Tomato A

Column 2 9
Tomato B

Column 2 5

Required quality level per output

Column 2 Whole

Column 3 Juice

Column 4 Paste

Row 9

Column 2 8

Column 3 6

Column 4 5

Blending plan

Column 2 Whole

Column 3 Juice

Column 4 Paste

Column 5 Pounds used

Column 7 Pounds available

Tomato A

Column 2 525000

Column 3 75000

Column 4 0

Column 5 =SUM(B16:D16)

Column 6 <=

Column 7 600000

Tomato B

Column 2 175000

Column 3 225000

Column 4 2000000

Column 5 =SUM(B17:D17)

Column 6 <=

Column 7 2400000
Pounds sold

Column 2 =SUM(B16:B17)

Column 3 =SUM(C16:C17)

Column 4 =SUM(D16:D17)

### Worksheet: DifferentSolutions

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (8 rows, 8 columns).

Contribution/case

Whole 4.44

Juice 3.96

Paste 5.55

pounds/case

Whole 18

Juice 20

Paste 25

Contribution/pound

Whole =B2/B3

Juice =C2/C3

Paste =D2/D3

Production in whole cases

Column 5 Contribution

Column 8 Profit

Cooper

Whole =3000000/B3

Juice 0

Paste 0

Column 5 =SUMPRODUCT($B$2:$D$2,B7:D7)

Column 6 not feasible; quality

Column 8 =E7-540000
Tucker

Whole 44444

Juice 80000

Column 5 =SUMPRODUCT($B$2:$D$2,B8:D8)

Column 8 =E8-540000

Myers

Whole 0

Juice 80000

Paste 50000

Column 5 =SUMPRODUCT($B$2:$D$2,B9:D9)

Column 6 =E9/E8-1

Column 8 =E9-540000

LP

Whole 38888.888888888905

Juice 14999.999999999985

Paste 80000

Column 5 =SUMPRODUCT($B$2:$D$2,B10:D10)

Column 6 =E10/E9-1

Column 8 =E10-540000

### Worksheet: CostData

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Tomato Product (per case)

Whole

Juice

Paste

Selling Price

12

13.5

11.4

Direct labour

3.54

3.96

1.62

Variable overhead

0.72

1.08

0.78

Variable selling

1.2

2.55

1.14

Packaging material

2.1

1.95

2.31

Fruit

3.24

3.6

4.5

Total Variable Costs

=SUM(B3:B7)

=SUM(C3:C7)

=SUM(D3:D7)

Contribution

=B2-B8

=C2-C8

=D2-D8

Allocated Overhead

0.84

0.63

0.69

Net Profit

=B9-B10

=C9-C10

=D9-D10

Contribution w/ sunk tomato cost

=B7+B9

=C7+C9

=D7+D9

Pounds (lbs) per case
Tomato Product (per case)

Whole

Juice

Paste

Contribution per pound

=B12/B13

=C12/C13

=D12/D13

Contribution per thousand pounds

=1000*B12/B13

=1000*C12/C13

=1000*D12/D13

### Worksheet: TomatoCostMeyers

> Preview of up to 18 rows and 9 columns. Full spreadsheet formulas and data remain in the source workbook.

Table displayed as labelled records for readability (17 rows, 9 columns).

Y= cost per pound of B tomatoes in cents

Tomato Product (per case) Selling Price

Whole 12

Juice 13.5

Row 2

Tomato Product (per case) Direct labour

Whole 3.54

Juice 3.96

(1) (600,000 lbs * Z) + (2,400,000 * Y) = 3,000,000 * 18

Tomato Product (per case) Variable overhead

Whole 0.72

Juice 1.08

(2) Z/9 = Y/5

Tomato Product (per case) Variable selling

Whole 1.2

Juice 2.55

Row 5

Tomato Product (per case) Packaging material

Whole 2.1

Juice 1.95
Z =

Column 2 27.96

Column 3 cents per pound

Tomato Product (per case) Fruit

Whole 4.47

Juice 3.7199999999999998

Y =

Column 2 15.54

Column 3 cents per pound

Tomato Product (per case) Total Variable Costs

Whole 12.030000000000001

Juice 13.259999999999998

Row 8

Tomato Product (per case) Contribution

Whole -0.030000000000001137

Juice 0.240000000000002

Tomato Product (per case)

Column 2 Whole

Column 3 Juice

Column 4 Paste

Tomato Product (per case) Allocated Overhead

Whole 0.84

Juice 0.63

Selling Price

Column 2 12

Column 3 13.5

Column 4 11.4

Tomato Product (per case) Net Profit

Whole -0.8700000000000011

Juice -0.389999999999998

Direct labour

Column 2 3.54

Column 3 3.96

Column 4 1.62
Variable overhead

Column 2 0.72

Column 3 1.08

Column 4 0.78

Tomato Product (per case) Pounds (lbs) per case

Whole Whole

Juice Juice

Variable selling

Column 2 1.2

Column 3 2.55

Column 4 1.14

Whole 18

Juice 20

Packaging material

Column 2 2.1

Column 3 1.95

Column 4 2.31

Fruit

Column 2 =1.49*3

Column 3 =1.24*3

Column 4 =1.3*3

Total Variable Costs

Column 2 =SUM(B12:B16)

Column 3 =SUM(C12:C16)

Column 4 =SUM(D12:D16)

Column 5 –whole (8 points) = 8/9 * 27.96 = 24.85 cents/pound ($4.47/case)

Contribution

Column 2 =B11-B17

Column 3 =C11-C17

Column 4 =D11-D17

Column 5 –juice (6 points) = 6/9 * 27.96 = 18.64 cents/pound ($3.72/case)

</details>


[↑ Back to the source list](#source-documents)

---

