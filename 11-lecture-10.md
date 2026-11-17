# Lecture 10

**Decision trees and classification**

[← All chapters](README.md) · [Original PDF](PDF%20Slides.pdf#page=662)

## Overview

- Constructing classification rules from categorical and continuous features.
- CART splitting using Gini impurity and entropy/information gain.
- Depth, overfitting, out-of-sample accuracy, confusion matrices, precision and recall.

## Source documents

1. [Decision Trees Table.pdf](#source-1) — PDF, reader page 663
2. [DecisionTrees.pdf](#source-2) — PDF, reader page 664
3. [DecisionTrees.html](#source-3) — HTML, reader page 693

---

<a name="source-1"></a>

## Decision Trees Table.pdf

<small>File type: PDF · Reader pages 663–663 · [View source PDF](PDF%20Slides.pdf#page=663)</small>

<small>Source Page 1 of 1</small>

### Subscriber Renewal Data

User Region Plan Type Viewing Pattern Renew

CJ63R4 Urban Basic Casual No

QP42M6 Rural Premium Binge Yes

GB72L5 Rural Basic Casual Yes

HM84P1 Urban Basic Casual No

LK91T3 Urban Premium Binge Yes

PS48Y2 Urban Premium Casual Yes

TW15N8 Urban Basic Casual No

NR58B2 Rural Basic Binge Yes

DK96F3 Urban Premium Casual Yes

VX29D7 Urban Basic Casual No

EF77X8 Urban Basic Binge Yes

AZ36K9 Urban Basic Binge Yes


[↑ Back to the source list](#source-documents)

---

<a name="source-2"></a>

## DecisionTrees.pdf

<small>File type: PDF · Reader pages 664–692 · [View source PDF](PDF%20Slides.pdf#page=664)</small>

<small>Source Page 1 of 58</small>

### Decision Trees

Rohit Mattu

<small>Source Page 2 of 58</small>

### Who Is About to Cancel Their Netflix Subscription?

Following a recent subscription fee increase, Netflix UK has observed a noticeable rise in subscriber churn. Concerned by this trend, the Head of Growth calls an urgent meeting with the Analytics team:

“We expected some churn. We could offer discounts or other incentives, but our retention budget is limited. Targeting every subscriber would be expensive and inefficient, particularly because many would renew without an incentive.

If we cannot target everyone, which subscribers should we prioritise? Can we predict who is likely to cancel before they actually do?

My sense is that churn is not random. It may be linked to subscribers’ viewing behaviour, the plan they are on, or where they live. If we can identify clear patterns, we can focus our retention efforts on subscribers who appear most likely to leave.”

Your task: Using past data, develop a simple set of rules that identifies subscribers at the greatest risk of leaving.

<small>Source Page 3 of 58</small>

### Past data

USER REGION PLAN TYPE VIEWING PATTERN RENEW

Features

CJ63R4 Urban Basic Casual No

Viewing Pattern: Binge or Casual

QP42M6 Rural Premium Binge Yes

Plan Type: Basic (1-screen) or Premium (4-screen)
GB72L5 Rural Basic Casual Yes

Region: Urban or Rural

HM84P1 Urban Basic Casual No

Target

LK91T3 Urban Premium Binge Yes

Does the subscriber renew (Yes) or leave (No)?

PS48Y2 Urban Premium Casual Yes TW15N8 Urban Basic Casual No NR58B2 Rural Basic Binge Yes DK96F3 Urban Premium Casual Yes

Can you find simple rules using these three features that

VX29D7 Urban Basic Casual No

predict who renews?

EF77X8 Urban Basic Binge Yes AZ36K9 Urban Basic Binge Yes

<small>Source Page 4 of 58</small>

### Large dataset

SUPPORT CONTACTS / 90 DAYS RENEW

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

No

No

Yes

Yes

Yes

Yes

Yes
No

Yes

Yes

No

Yes

Yes

No

Yes

Yes

Yes

Yes

Yes

No

Yes

No

Yes

No

Yes

Yes

No

No

Yes

No

No

Yes

Yes

Yes

No

No

No

Yes
Yes

Yes

No

Yes

USER REGION PLAN VIEWING PATTERN SUBSCRIPTION LENGTH (MONTHS) RY19Q6 Urban Basic Binge

YK92D7 Urban Premium Binge

BA65N8 Urban Basic Binge

ER38X9 Urban Basic Binge

HG11G0 Rural Premium Casual

QT84V1 Urban Premium Casual

TJ57E2 Urban Premium Binge

WZ30P3 Rural Basic Binge

ZQ03Y4 Urban Basic Casual

GB76M5 Urban Basic Casual

KS49W6 Urban Premium Binge

NH22F7 Rural Premium Casual

VU95U8 Rural Basic Binge

YK68D9 Rural Basic Binge

BA41N0 Urban Basic Binge

ER14X1 Urban Basic Casual

MC87L2 Urban Premium Casual

QT60V3 Rural Premium Binge

TJ33E4 Urban Basic Casual

WZ06P5 Rural Premium Casual

DL79C6 Urban Premium Casual

GB52M7 Urban Basic Casual

KS25W8 Rural Premium Binge

SD98K9 Rural Basic Casual

VU71U0 Urban Basic Binge

YK44D1 Urban Premium Casual
BA17N2 Rural Premium Binge

JM90B3 Urban Basic Casual

MC63L4 Rural Basic Casual

QT36V5 Urban Basic Casual

TJ09E6 Rural Basic Casual

AV82T7 Urban Basic Casual

DL55C8 Rural Basic Binge

GB28M9 Rural Premium Binge

KS01W0 Urban Basic Casual

SD74K1 Urban Basic Casual

VU47U2 Rural Premium Binge

YK20D3 Urban Basic Casual

FW93S4 Urban Basic Casual

JM66B5 Urban Basic Binge

MC39L6 Rural Basic Casual

QT12V7 Rural Premium Casual

XE85J8 Urban Basic Casual

AV58T9 Urban Basic Casual

DL31C0 Urban Basic Casual

GB04M1 Urban Premium Binge

PN77A2 Urban Premium Casual

SD50K3 Urban Premium Binge

VU23U4 Urban Basic Casual

CF96H5 Urban Basic Binge

HOURS WATCHED / MONTH DAYS SINCE LAST WATCH DEVICES USED PAYMENT FAILURES

<small>Source Page 5 of 58</small>

### Subscribers Sorted by Region

USER REGION PLAN TYPE VIEWING PATTERN RENEW

QP42M6 Rural Premium Binge Yes ✓
GB72L5 Rural Basic Casual Yes ✓

NR58B2 Rural Basic Binge Yes ✓

CJ63R4 Urban Basic Casual No ✗

HM84P1 Urban Basic Casual No ✗

LK91T3 Urban Premium Binge Yes ✓

PS48Y2 Urban Premium Casual Yes ✓

TW15N8 Urban Basic Casual No ✗

DK96F3 Urban Premium Casual Yes ✓

VX29D7 Urban Basic Casual No ✗

EF77X8 Urban Basic Binge Yes ✓

AZ36K9 Urban Basic Binge Yes ✓

<small>Source Page 6 of 58</small>

### Subscribers Sorted by Plan Type

USER REGION PLAN TYPE VIEWING PATTERN RENEW

CJ63R4 Urban Basic Casual No ✗

GB72L5 Rural Basic Casual Yes ✓

HM84P1 Urban Basic Casual No ✗

TW15N8 Urban Basic Casual No ✗

NR58B2 Rural Basic Binge Yes ✓

VX29D7 Urban Basic Casual No ✗

EF77X8 Urban Basic Binge Yes ✓

AZ36K9 Urban Basic Binge Yes ✓

QP42M6 Rural Premium Binge Yes ✓

LK91T3 Urban Premium Binge Yes ✓

PS48Y2 Urban Premium Casual Yes ✓

DK96F3 Urban Premium Casual Yes ✓
<small>Source Page 7 of 58</small>

### Subscribers Sorted by Viewing Pattern

USER REGION PLAN TYPE VIEWING PATTERN RENEW

QP42M6 Rural Premium Binge Yes ✓

LK91T3 Urban Premium Binge Yes ✓

NR58B2 Rural Basic Binge Yes ✓

EF77X8 Urban Basic Binge Yes ✓

AZ36K9 Urban Basic Binge Yes ✓

CJ63R4 Urban Basic Casual No ✗

GB72L5 Rural Basic Casual Yes ✓

HM84P1 Urban Basic Casual No ✗

PS48Y2 Urban Premium Casual Yes ✓

TW15N8 Urban Basic Casual No ✗

DK96F3 Urban Premium Casual Yes ✓

VX29D7 Urban Basic Casual No ✗

<small>Source Page 8 of 58</small>

### Sort by Viewing Pattern

USER VIEWING PATTERN PLAN TYPE REGION RENEW

EF77X8 Binge Basic Urban Yes ✓

QP42M6 Binge Premium Rural Yes ✓

LK91T3 Binge Premium Urban Yes ✓

NR58B2 Binge Basic Rural Yes ✓

AZ36K9 Binge Basic Urban Yes ✓

HM84P1 Casual Basic Urban No ✗

VX29D7 Casual Basic Urban No ✗

CJ63R4 Casual Basic Urban No ✗

TW15N8 Casual Basic Urban No ✗

GB72L5 Casual Basic Rural Yes ✓

PS48Y2 Casual Premium Urban Yes ✓
DK96F3 Casual Premium Urban Yes ✓

<small>Source Page 9 of 58</small>

### The Remaining 7 Casual Users

USER VIEWING PATTERN PLAN TYPE REGION RENEW

HM84P1 Casual Basic Urban No ✗

VX29D7 Casual Basic Urban No ✗

CJ63R4 Casual Basic Urban No ✗

TW15N8 Casual Basic Urban No ✗

GB72L5 Casual Basic Rural Yes ✓

PS48Y2 Casual Premium Urban Yes ✓

DK96F3 Casual Premium Urban Yes ✓

Binge viewers are classified. Now we focus on the 7 Casual users: 3 Yes, 4 No. Still mixed, we need another feature.

Which feature separates them next?

<small>Source Page 10 of 58</small>

### Sort Casual Users by Plan Type

USER VIEWING PATTERN PLAN TYPE REGION RENEW

HM84P1 Casual Basic Urban No ✗

VX29D7 Casual Basic Urban No ✗

CJ63R4 Casual Basic Urban No ✗

TW15N8 Casual Basic Urban No ✗

GB72L5 Casual Basic Rural Yes ✓

PS48Y2 Casual Premium Urban Yes ✓

DK96F3 Casual Premium Urban Yes ✓

<small>Source Page 11 of 58</small>

### Sort Casual Users by Region

USER VIEWING PATTERN PLAN TYPE REGION RENEW
GB72L5 Casual Basic Rural Yes ✓

HM84P1 Casual Basic Urban No ✗

VX29D7 Casual Basic Urban No ✗

CJ63R4 Casual Basic Urban No ✗

TW15N8 Casual Basic Urban No ✗

PS48Y2 Casual Premium Urban Yes ✓

DK96F3 Casual Premium Urban Yes ✓

<small>Source Page 12 of 58</small>

### Which Split Works Best for Casual Users?

Plan Type

Region

Basic: 1 renews, 4 leave Premium: 2 renew, 0 leave

Rural: 1 renews, 0 leave Urban: 2 renew, 4 leave

Plan Type wins. Its pure group contains two subscribers. Its mixed group has one renewal out of five, compared with two out of six for Region.

Predict renewal for Casual Premium subscribers. Next, split the five Casual Basic subscribers by Region.

<small>Source Page 13 of 58</small>

### Split Casual Users by Plan Type

USER VIEWING PATTERN PLAN TYPE REGION RENEW

PS48Y2 Casual Premium Urban Yes ✓

DK96F3 Casual Premium Urban Yes ✓

HM84P1 Casual Basic Urban No ✗

VX29D7 Casual Basic Urban No ✗

CJ63R4 Casual Basic Urban No ✗

TW15N8 Casual Basic Urban No ✗

GB72L5 Casual Basic Rural Yes ✓

If Casual + Premium → Renew If Casual + Basic → Split by Region
<small>Source Page 14 of 58</small>

### Sort Casual Basic Users by Region

USER VIEWING PATTERN PLAN TYPE REGION RENEW

HM84P1 Casual Basic Urban No ✗

VX29D7 Casual Basic Urban No ✗

CJ63R4 Casual Basic Urban No ✗

TW15N8 Casual Basic Urban No ✗

GB72L5 Casual Basic Rural Yes ✓

If Casual + Basic + Urban → Leave If Casual + Basic + Rural → Renew

<small>Source Page 15 of 58</small>

### Summary of Rules

IF THEN PREDICT SUBSCRIBERS

Viewing Pattern = Binge Renew ✓ 5 subscribers

Viewing Pattern = Casual and Plan Type = Premium Renew ✓ 2 subscribers

Viewing Pattern = Casual, Plan Type = Basic and Region = Urban Leave ✗ 4 subscribers

Viewing Pattern = Casual, Plan Type = Basic and Region = Rural Renew ✓ GB72L5

Every subscriber in the past data is now assigned to a renewal outcome.

<small>Source Page 16 of 58</small>

### The Complete Decision Tree

Viewing Pattern?

Binge Casual

Yes

Plan Type?

Premium Basic

Yes

Region?

Urban Rural
No

Yes

A Decision tree is a collection of rules used to determine a course of action.

We focus on a specific type of decision tree: Classification and Regression Trees (CART), a predictive model used to draw conclusions from data (a set of

observations).

<small>Source Page 17 of 58</small>

### Anatomy of a Decision Tree

Root node

Components

Root node: The top node of the tree. It contains the complete dataset and represents the first decision rule.

Internal node

Internal node: A non-terminal node that represents a decision rule, such as x > 7 or y = 7.

Terminal node: A node with no descendants (child nodes). It is also called a "leaf node."

Terminal node

<small>Source Page 18 of 58</small>

### The 12 Subscribers in Two Dimensions

Plan Type

Premium

Basic

Binge Casual Viewing Pattern

Renewed Left Each dot is one subscriber.

<small>Source Page 19 of 58</small>

### The 12 Subscribers in the Feature Space
<small>Source Page 20 of 58</small>

### Depiction of Decision Boundaries

Decision tree

Select a cube region to trace its rule through the tree.

Viewing pattern?

Binge Casual

Renew

Plan type?

5 users

Premium Basic

Renew

Region?

2 users

Rural Urban

Renew

Leave

1 user

4 users

Highlighted path = selected volume

<small>Source Page 21 of 58</small>

### How does a CART algorithm decide which variable to split first to build a

**tree?**

<small>Source Page 22 of 58</small>

### Reduction in Impurity

Pure Group

Maximum Impurity

A group is pure if everyone in it has the same outcome (all Yes or all No). It’s impure if it’s a mix.
Y Y Y Y

Y N Y N

Our Root Node

Y Y Y Y Y N N N N Y Y Y

The Intuition If a split produces one group that’s all Yes and another that’s all No, we can predict perfectly. The goal at every step is to get closer to that ideal.

CART The algorithm picks the split that creates the purest child groups, and thereby produces the biggest drop in impurity.

<small>Source Page 23 of 58</small>

### Gini Impurity

G0

G0 is the impurity at the parent node before we split.

```r
G(L)  and G(R)  are the impurities of the two child nodes after the split.
G(L) G(R) Internal node
```

What matters is the drop.

Reduction in Gini = G0 - [weighted G(L) + weighted G(R)]

Interpretation

A split is useful when the child nodes are less mixed than the parent node.

The bigger the reduction, the more that split improves purity, so CART prefers it.

Terminal node

<small>Source Page 24 of 58</small>

### Gini Impurity Formula

Gini = 1 − ∑ pi²

In our case: Gini = 1 − pY² − pN²

pY = proportion of subscribers in the node who renew (Yes)

pN = proportion of subscribers in the node who leave (No)

Interpretation
0 = perfectly pure 0.5 = maximum impurity for two classes

Intuition Draw two members of this node independently with replacement. Gini impurity is the probability that their outcomes differ.

<small>Source Page 25 of 58</small>

### Root Node Calculation

Our 12 subscribers: 8 Yes, 4 No

pYes = 8/12 = 2/3

pNo = 4/12 = 1/3

Gini = 1 − (2/3)² − (1/3)²

= 1 − 4/9 − 1/9

= 4/9 ≈ 0.444

This is our starting impurity. Close to the maximum of 0.5 because our data has a genuine mix of outcomes.

<small>Source Page 26 of 58</small>

### Splitting on Viewing Pattern

```r
Binge (5 users)
Casual (7 users)
```

5 subscribers → All Yes

3 Yes | 4 No

Gini = 1 − 1.0² − 0.0² = 0.000

Gini = 1 − (3/7)² − (4/7)² ≈ 0.490

Perfectly pure!

Nearly a coin flip.

Gini Gain

Weighted average of child impurities:

Weighted = (5/12) × 0 + (7/12) × (24/49) = 2/7 ≈ 0.286

Gain = 4/9 − 2/7
Gini Gain ≈ 0.159

Viewing Pattern reduces impurity by 36% in a single split, with one side becoming perfectly pure.

<small>Source Page 27 of 58</small>

### Splitting on Plan Type

```r
Basic (8 users)
Premium (4 users)
```

4 Yes | 4 No

All Yes

Gini = 1 − (4/8)² − (4/8)² = 0.500

Gini = 1 − 1.0² − 0.0² = 0.000

Maximum impurity!

Perfectly pure!

Gini Gain

Weighted average of child impurities:

Weighted = (8/12) × 0.500 + (4/12) × 0 = 1/3 ≈ 0.333

Gain = 4/9 − 1/3

Gini Gain ≈ 0.111

Plan Type is weaker than Viewing Pattern.

<small>Source Page 28 of 58</small>

### Splitting on Region

```r
Urban (9 users)
Rural (3 users)
```

5 Yes | 4 No

All Yes
Gini = 1 − (5/9)² − (4/9)² ≈ 0.494

Gini = 1 − 1.0² − 0.0² = 0.000

Nearly balanced.

Perfectly pure!

Gini Gain

Weighted average of child impurities:

Weighted = (9/12) × (40/81) + (3/12) × 0 = 10/27 ≈ 0.370

Gain = 4/9 − 10/27

Gini Gain ≈ 0.074

Region is the weakest split among the three.

<small>Source Page 29 of 58</small>

### Which feature creates the Purest Split?

Viewing Pattern

0.159 0.159

Plan Type

0.111 0.111

Region

0.074 0.074

<small>Source Page 30 of 58</small>

### Level 1: Viewing Pattern Wins

Viewing Pattern?

Binge Casual

Yes

No

3Y / 4N

Left child node: 100% pure; right child node: impure.
<small>Source Page 31 of 58</small>

### Gini Impurity of the Casual Node

Casual node: 3 Yes, 4 No

pY = 3/7 ≈ 0.429

pN = 4/7 ≈ 0.571

Gini = 1 − (3/7)² − (4/7)²

= 1 − 9/49 − 16/49 = 24/49 ≈ 0.490

This is the baseline impurity for evaluating the next split.

<small>Source Page 32 of 58</small>

### Splitting the Casual Branch

USER PLAN TYPE REGION RENEW

HM84P1 Basic Urban No ✗ VX29D7 Basic Urban No ✗ CJ63R4 Basic Urban No ✗ TW15N8 Basic Urban No ✗ GB72L5 Basic Rural Yes ✓ PS48Y2 Premium Urban Yes ✓ DK96F3 Premium Urban Yes ✓

Split by Plan Type

Split by Region

```r
Basic (5): 1Y / 4N, Gini = 0.320
Urban (6): 2Y / 4N, Gini ≈ 0.444
Premium (2): All Yes, Gini = 0.000
Rural (1): All Yes, Gini = 0.000
```

Gain ≈ 0.261

Gain ≈ 0.109

Plan Type is the winner for splitting the Casual branch.

<small>Source Page 33 of 58</small>

### Level 2: Plan Type Wins

Viewing Pattern?
Binge Casual

Yes

Plan Type?

Premium Basic

Yes

No

1Y / 4N

Left child node: 100% pure; right child node: impure.

<small>Source Page 34 of 58</small>

### Gini Impurity of the Casual + Basic Node

Casual + Basic node: 1 Yes, 4 No

pY = 1/5 = 0.200

pN = 4/5 = 0.800

Gini = 1 − (1/5)² − (4/5)²

= 1 − 0.040 − 0.640 = 0.320

This is the baseline impurity for evaluating the next split.

<small>Source Page 35 of 58</small>

### Splitting the Casual + Basic Branch

USER REGION RENEW

HM84P1 Urban No ✗ VX29D7 Urban No ✗ CJ63R4 Urban No ✗ TW15N8 Urban No ✗ GB72L5 Rural Yes ✓

Split by Region

```r
Urban (4): All No, Gini = 0.000 (Pure!) Rural (1): All Yes, Gini = 0.000 (Pure!)
```

Gain = 0.320

Region perfectly separates the Casual Basic users.
<small>Source Page 36 of 58</small>

### Complete Tree

Viewing Pattern?

Gini = 0.444

Binge Casual

Yes

Plan Type?

Gini = 0.490

Premium Basic

Gini = 0.000

Yes

Region?

Gini = 0.320

Gini = 0.000

Urban Rural

No

Yes

Gini = 0.000

Gini = 0.000

<small>Source Page 37 of 58</small>

### Depiction of Decision Boundaries

Decision tree

Select a cube region to trace its rule through the tree.

Viewing pattern?

Binge Casual

Renew

Plan type?

5 users

Premium Basic
Renew

Region?

2 users

Rural Urban

Renew

Leave

1 user

4 users

Highlighted path = selected volume

<small>Source Page 38 of 58</small>

### Does Depth Matters?

Viewing Pattern?

Binge Casual

Yes

Depth 1 75%

Viewing only: 9/12 correct

Add Plan Type: 11/12 correct

Plan Type?

Premium Basic

Yes

Region?

Urban Rural

No

Yes

Depth 2 92%

Depth 3 100%

Add Region: 12/12 correct
<small>Source Page 39 of 58</small>

### Does It Work on New Data?

TRAINED TREE AT DEPTH 3

Viewing Pattern?

Binge Casual

USER VIEWING PLAN REGION PREDICTED ACTUAL MATCH?

RM54Q7 Binge Premium Urban Yes Yes ✓

Yes Plan Type?

XT83C6 Binge Basic Rural Yes Yes ✓

Premium Basic

FN27H4 Casual Basic Rural Yes No ✗ BV61K9 Casual Premium Urban Yes Yes ✓

Yes Region?

YP35A2 Casual Basic Urban No Yes ✗

Urban Rural

JL90W5 Casual Basic Urban No Yes ✗

No Yes

Training accuracy 100% (12/12) ---- accuracy 50% (3/6)

The region split sends the only actual churner to a renewal leaf based on one training subscriber.

<small>Source Page 40 of 58</small>

### Does It Work on New Data?

TRAINED TREE AT DEPTH 1

USER VIEWING PLAN REGION PREDICTED ACTUAL MATCH?

Viewing Pattern?

RM54Q7 Binge Premium Urban Yes Yes ✓ XT83C6 Binge Basic Rural Yes Yes ✓

Binge Casual

FN27H4 Casual Basic Rural No No ✓ BV61K9 Casual Premium Urban No Yes ✗

Yes No

YP35A2 Casual Basic Urban No Yes ✗ JL90W5 Casual Basic Urban No Yes ✗
Training accuracy 75% (9/12) ---- accuracy 50% (3/6)

The viewing-only tree predicts churn for every casual viewer, including three who renewed.

<small>Source Page 41 of 58</small>

### Does It Work on New Data?

TRAINED TREE AT DEPTH 2

Viewing Pattern?

USER VIEWING PLAN REGION PREDICTED ACTUAL MATCH?

RM54Q7 Binge Premium Urban Yes Yes ✓

Binge Casual

XT83C6 Binge Basic Rural Yes Yes ✓

Yes Plan Type?

FN27H4 Casual Basic Rural No No ✓ BV61K9 Casual Premium Urban Yes Yes ✓

Premium Basic

YP35A2 Casual Basic Urban No Yes ✗ JL90W5 Casual Basic Urban No Yes ✗

Yes No

Training accuracy 92% (11/12) ---- accuracy 67% (4/6)

The plan split correctly predicts renewal for the casual Premium subscriber.

<small>Source Page 42 of 58</small>

### Always Predict Renewal

Predict Renew for Everyone

USER VIEWING PLAN REGION PREDICTED ACTUAL MATCH?

RM54Q7 Binge Premium Urban Yes Yes ✓

BASELINE RULE

XT83C6 Binge Basic Rural Yes Yes ✓ FN27H4 Casual Basic Rural Yes No ✗ BV61K9 Casual Premium Urban Yes Yes ✓ YP35A2 Casual Basic Urban Yes Yes ✓ JL90W5 Casual Basic Urban Yes Yes ✓

Training accuracy 67% (8/12) ---- accuracy 83% (5/6)
<small>Source Page 43 of 58</small>

### Training and ---- Accuracy

PREDICTION RULE TRAINING ACCURACY ---- ACCURACY

Depth 1 75% (9/12) 50% (3/6) Depth 2 92% (11/12) 67% (4/6) Depth 3 100% (12/12) 50% (3/6) Always predict renewal 67% (8/12) 83% (5/6)

The always-renew rule gets the most ---- cases right. Among the trees, adding the region split at depth 3 fixes one training error and

introduces one ---- error.

Lesson

Perfect training accuracy does not mean good predictions on new data. Always ---- on held-out data.

<small>Source Page 44 of 58</small>

### Overfitting

As the tree grows deeper:

Training accuracy keeps increasing (the tree

memorizes more)

---- accuracy first increases, then decreases

(overfitting begins)

The optimal depth is where the ---- accuracy is

maximized.

Training data

Accuracy

Unseen data

Sweet spot Depth →

<small>Source Page 45 of 58</small>

### Ways to overcome Overfitting

To avoid overfitting the training data, you need to restrict the Decision Tree's freedom during training, also known as regularization.

- Pre-pruning
Key hyperparameters: Maximum depth, minimum samples to split, minimum samples per leaf, maximum leaf nodes and maximum features.

Increasing the min* hyperparameters and reducing the max* hyperparameters will regularize the model.

- Post-pruning

Grow the full tree first, then remove the branches that add more complexity than they do accuracy.

```r
CCPα(T) = err(T) + αL(T)
err(T) is the fraction of training records that are misclassified; L(T) is the number of
leaf nodes (terminal nodes); and α is the penalty ("complexity parameter") for tree size.
```

<small>Source Page 46 of 58</small>

### Depth 1 75% (9/12) 50% (3/6) Depth 2 92% (11/12) 67% (4/6)

PREDICTION RULE TRAINING ACCURACY ---- ACCURACY

Depth 3 100% (12/12) 50% (3/6) Always predict renewal 67% (8/12) 83% (5/6)

Which rule would you use to decide whom to contact: the always-renew rule with 83% ---- set accuracy or the depth-two tree with 67% accuracy?

<small>Source Page 47 of 58</small>

### Confusion Matrices

Predicting renewal for everyone misses the only churner. Depth 2 is preferable here if missing that churner costs more than following up with two subscribers who renewed.

Same six ---- subscribers. Leaving is the positive outcome (Renew = No).

Depth 2 Tree

Actual outcome Predicted leave Predicted renew

Left

True positive

False negatives

Renewed

False positives

True negatives
Always Predict Renewal

Actual outcome Predicted leave Predicted renew

Left

True positives

False negative

Renewed

False positives

True negatives

<small>Source Page 48 of 58</small>

### Churn Precision and Recall

Depth 1 1 / 4 (25%) 1 / 1 (100%)

Depth 2 1 / 3 (33.3%) 1 / 1 (100%)

Always predict leave 1 / 6 (16.7%) 1 / 1 (100%)

Each dot is one ---- subscriber.

Predicted to leave Predicted to renew

Prediction rule Actually

left Actually renewed Precision

Always predict renewal Undefined

Precision = TP / (TP + FP) Recall = TP / (TP + FN)

```r
TP (true positives) Predicted to leave and actually left.
FP (false positives) Predicted to leave and actually renewed.
```

Recall

Correct alerts / all alerts

Churners caught / all churners

No one flagged 0 / 1 (0%)

```r
FN (false negatives) Predicted to renew and actually left.
```
<small>Source Page 49 of 58</small>

### Strengths and Weaknesses

Strengths

Weaknesses

Interpretability

Greedy algorithm

Non-linear relationships

Overfitting

Built-in feature selection

Orthogonal decision boundaries

Faster training and inference

Bias toward imbalanced classes

Sensitive to variations in training data

<small>Source Page 50 of 58</small>

### Thank You

Questions & Discussion

Rohit Mattu

<small>Source Page 51 of 58</small>

### Continuous Features

<small>Source Page 52 of 58</small>

### Continuous Feature: Viewing Hours

Suppose we observe weekly viewing hours instead of classifying subscribers as Binge or Casual.

Where could CART split?

CART first sorts the observed values:

SUBSCRIBER VIEWING HOURS RENEW?
A

No B

No C

No

1, 2, 3, 5, 7, 8, 10

D

Yes

It then ----- the midpoint of every gap:

E

No F

Yes

1.5, 2.5, 4, 6, 7.5, 9

G

Yes

<small>Source Page 53 of 58</small>

### Choosing the Split Point

For every threshold t, CART compares subscribers with viewing hours ≤ t against those with viewing hours > t.

THRESHOLD LEFT CHILD RIGHT CHILD WEIGHTED GINI

1.5 0 Yes, 1 No 3 Yes, 3 No 0.429 2.5 0 Yes, 2 No 3 Yes, 2 No 0.343 4.0 0 Yes, 3 No 3 Yes, 1 No 0.214 6.0 1 Yes, 3 No 2 Yes, 1 No 0.405 7.5 1 Yes, 4 No 2 Yes, 0 No 0.229 9.0 2 Yes, 4 No 1 Yes, 0 No 0.381

Lowest weighted Gini: split at viewing hours ≤ 4.

<small>Source Page 54 of 58</small>

### Efficient Gini Calculation

CART scans the sorted observations once. In this example, each step moves one observation from the right child to the left child and updates the class counts.

SCAN POSITION LEFT CHILD RIGHT CHILD WEIGHTED GINI

Start 0 Yes, 0 No 3 Yes, 4 No — After 1 hour 0 Yes, 1 No 3 Yes, 3 No 0.429 After 2 hours 0 Yes, 2 No 3 Yes, 2 No 0.343 After 3 hours 0 Yes, 3 No 3 Yes, 1 No 0.214
Giniafter = (3/7)(0) + (4/7)[1 − (3/4)² − (1/4)²] ≈ 0.214

CART updates the class counts rather than rereading every observation in each child node.

<small>Source Page 55 of 58</small>

### Entropy

<small>Source Page 56 of 58</small>

### Entropy & Information Gain

Entropy Formula

```r
H(S) = − ∑ pi log2 pi
```

For two classes, H = −pY log2 pY − pN log2 pN.

Entropy ranges from 0 bits for a pure node to 1 bit for an even split between the two classes.

Root Node Calculation

8 Yes, 4 No (pY = 2/3, pN = 1/3)

H = −(2/3) log2(2/3) − (1/3) log2(1/3)

```r
log2(2/3) ≈ −0.585 and log2(1/3) ≈ −1.585
```

H ≈ 0.918 bits

<small>Source Page 57 of 58</small>

### Entropy Reduction for Each Feature

Viewing Pattern

Plan Type

Region

Information Gain = entropy before the split − weighted entropy after the split.

Each child is weighted by its share of subscribers. Gains are rounded at the end.

```r
Binge (5): H = 0
```
```r
Basic (8): H = 1
Urban (9): H ≈ 0.991
Casual (7): H ≈ 0.985
Premium (4): H = 0
Rural (3): H = 0
```

Information Gain ≈ 0.344 bits

Information Gain ≈ 0.252 bits

Information Gain ≈ 0.175 bits

<small>Source Page 58 of 58</small>

### Gini vs. Entropy: Same Answer

MEASURE VIEWING PATTERN PLAN TYPE REGION

Gini Gain 0.159 0.111 0.074

Information Gain (bits) 0.344 0.252 0.175

Winner ✓ ✗ ✗

Both measures rank these three splits in the same order. Gini is faster (no logarithms).

Entropy is more theoretically grounded (information theory).


[↑ Back to the source list](#source-documents)

---

<a name="source-3"></a>

## DecisionTrees.html

<small>File type: HTML · Reader pages 693–712 · [View source PDF](PDF%20Slides.pdf#page=693)</small>

> This source was converted from HTML to PDF before upload; some inline code is fragmented. Use an adjacent `.Rmd` source when provided.

### Decision Trees

### Who Is About to Cancel Their Netflix Subscription?

Following a recent subscription fee increase , Netflix UK has observed a noticeable rise in subscriber churn . Concerned by this trend, the Head of Growth calls an urgent meeting with the Analytics team :

“We expected some churn. We could offer discounts or other incentives, but our retention budget is limited . Targeting every subscriber would be expensive and inefficient, particularly because many would renew without an incentive.

If we cannot target everyone, which subscribers should we prioritise? Can we predict who is likely to cancel before they actually do?

My sense is that churn is not random . It may be linked to subscribers’ viewing behaviour , the plan they are on , or where they live. If we can identify clear patterns, we can focus our retention efforts on subscribers who appear most likely to leave.”

Your task: Using past data, develop a simple set of rules that identifies subscribers at the greatest risk of leaving.

### Past data

### Features

Viewing Pattern: Binge or Casual Plan Type: Basic (1-screen) or Premium (4-screen) Region: Urban or Rural

### Target

Does the subscriber renew (Yes) or leave (No) ?

Can you find simple rules using these three features that predict who renews?

User

Region

Plan Type

Viewing Pattern

Renew

CJ63R4

Urban

Basic

Casual

No

QP42M6

Rural

Premium

Binge

Yes

GB72L5

Rural

Basic

Casual

Yes

HM84P1

Urban

Basic

Casual

No

LK91T3

Urban

Premium

Binge

Yes

PS48Y2

Urban

Premium

Casual

Yes

TW15N8

Urban

Basic

Casual

No

NR58B2

Rural

Basic

Binge

Yes
User

Region

Plan Type

Viewing Pattern

Renew

DK96F3

Urban

Premium

Casual

Yes

VX29D7

Urban

Basic

Casual

No

EF77X8

Urban

Basic

Binge

Yes

AZ36K9

Urban

Basic

Binge

Yes

### Large dataset

User

Region

Plan

Viewing pattern

Subscription length (months)

Hours watched / month

Days since last watch

Devices used

Payment failures

Support contacts / 90 days

Renew

### Subscribers Sorted by Region

User

Region

Plan Type

Viewing Pattern

Renew

QP42M6

Rural

Premium

Binge

Yes ✓

GB72L5

Rural

Basic

Casual

Yes ✓

NR58B2

Rural

Basic

Binge

Yes ✓

CJ63R4

Urban

Basic

Casual

No ✗

HM84P1

Urban

Basic

Casual

No ✗

LK91T3

Urban

Premium

Binge

Yes ✓

PS48Y2

Urban

Premium

Casual

Yes ✓

TW15N8

Urban

Basic

Casual

No ✗

DK96F3

Urban

Premium

Casual

Yes ✓

VX29D7

Urban

Basic

Casual

No ✗

EF77X8

Urban

Basic

Binge

Yes ✓

AZ36K9

Urban

Basic

Binge

Yes ✓

### Subscribers Sorted by Plan Type

User

Region

Plan Type

Viewing Pattern

Renew

CJ63R4

Urban

Basic

Casual

No ✗

GB72L5

Rural

Basic

Casual

Yes ✓

HM84P1

Urban

Basic

Casual

No ✗

TW15N8

Urban

Basic

Casual

No ✗
User

Region

Plan Type

Viewing Pattern

Renew

NR58B2

Rural

Basic

Binge

Yes ✓

VX29D7

Urban

Basic

Casual

No ✗

EF77X8

Urban

Basic

Binge

Yes ✓

AZ36K9

Urban

Basic

Binge

Yes ✓

QP42M6

Rural

Premium

Binge

Yes ✓

LK91T3

Urban

Premium

Binge

Yes ✓

PS48Y2

Urban

Premium

Casual

Yes ✓

DK96F3

Urban

Premium

Casual

Yes ✓

### Subscribers Sorted by Viewing Pattern

User

Region

Plan Type

Viewing Pattern

Renew

QP42M6

Rural

Premium

Binge

Yes ✓

LK91T3

Urban

Premium

Binge

Yes ✓

NR58B2

Rural

Basic

Binge

Yes ✓

EF77X8

Urban

Basic

Binge

Yes ✓

AZ36K9

Urban

Basic

Binge

Yes ✓

CJ63R4

Urban

Basic

Casual

No ✗

GB72L5

Rural

Basic

Casual

Yes ✓

HM84P1

Urban

Basic

Casual

No ✗

PS48Y2

Urban

Premium

Casual

Yes ✓

TW15N8

Urban

Basic

Casual

No ✗

DK96F3

Urban

Premium

Casual

Yes ✓

VX29D7

Urban

Basic

Casual

No ✗

### Sort by Viewing Pattern

User

Viewing Pattern

Plan Type

Region

Renew

EF77X8

Binge

Basic

Urban

Yes ✓

QP42M6

Binge

Premium

Rural

Yes ✓

LK91T3

Binge

Premium

Urban

Yes ✓

NR58B2

Binge

Basic

Rural

Yes ✓

AZ36K9

Binge

Basic

Urban

Yes ✓

HM84P1

Casual

Basic

Urban

No ✗

VX29D7

Casual

Basic

Urban

No ✗
User

Viewing Pattern

Plan Type

Region

Renew

CJ63R4

Casual

Basic

Urban

No ✗

TW15N8

Casual

Basic

Urban

No ✗

GB72L5

Casual

Basic

Rural

Yes ✓

PS48Y2

Casual

Premium

Urban

Yes ✓

DK96F3

Casual

Premium

Urban

Yes ✓

### The Remaining 7 Casual Users

User

Viewing Pattern

Plan Type

Region

Renew

HM84P1

Casual

Basic

Urban

No ✗

VX29D7

Casual

Basic

Urban

No ✗

CJ63R4

Casual

Basic

Urban

No ✗

TW15N8

Casual

Basic

Urban

No ✗

GB72L5

Casual

Basic

Rural

Yes ✓

PS48Y2

Casual

Premium

Urban

Yes ✓

DK96F3

Casual

Premium

Urban

Yes ✓

Binge viewers are classified. Now we focus on the 7 Casual users: 3 Yes, 4 No. Still mixed, we need another feature.

Which feature separates them next?

### Sort Casual Users by Plan Type

User

Viewing Pattern

Plan Type

Region

Renew

HM84P1

Casual

Basic

Urban

No ✗

VX29D7

Casual

Basic

Urban

No ✗

CJ63R4

Casual

Basic

Urban

No ✗

TW15N8

Casual

Basic

Urban

No ✗

GB72L5

Casual

Basic

Rural

Yes ✓

PS48Y2

Casual

Premium

Urban

Yes ✓

DK96F3

Casual

Premium

Urban

Yes ✓

### Sort Casual Users by Region

User

Viewing Pattern

Plan Type

Region

Renew

GB72L5

Casual

Basic

Rural

Yes ✓

HM84P1

Casual

Basic

Urban

No ✗
User

Viewing Pattern

Plan Type

Region

Renew

VX29D7

Casual

Basic

Urban

No ✗

CJ63R4

Casual

Basic

Urban

No ✗

TW15N8

Casual

Basic

Urban

No ✗

PS48Y2

Casual

Premium

Urban

Yes ✓

DK96F3

Casual

Premium

Urban

Yes ✓

### Which Split Works Best for Casual Users?

### Plan Type

Basic: 1 renews, 4 leave

Premium: 2 renew, 0 leave

### Region

Rural: 1 renews, 0 leave

Urban: 2 renew, 4 leave

Plan Type wins. Its pure group contains two subscribers. Its mixed group has one renewal out of five, compared with two out of six for Region.

Predict renewal for Casual Premium subscribers. Next, split the five Casual Basic subscribers by Region.

### Split Casual Users by Plan Type

User

Viewing Pattern

Plan Type

Region

Renew

PS48Y2

Casual

Premium

Urban

Yes ✓

DK96F3

Casual

Premium

Urban

Yes ✓

HM84P1

Casual

Basic

Urban

No ✗

VX29D7

Casual

Basic

Urban

No ✗

CJ63R4

Casual

Basic

Urban

No ✗

TW15N8

Casual

Basic

Urban

No ✗

GB72L5

Casual

Basic

Rural

Yes ✓

If Casual + Premium → Renew

If Casual + Basic → Split by Region

### Sort Casual Basic Users by Region

User

Viewing Pattern

Plan Type

Region

Renew

HM84P1

Casual

Basic

Urban

No ✗
User

Viewing Pattern

Plan Type

Region

Renew

VX29D7

Casual

Basic

Urban

No ✗

CJ63R4

Casual

Basic

Urban

No ✗

TW15N8

Casual

Basic

Urban

No ✗

GB72L5

Casual

Basic

Rural

Yes ✓

If Casual + Basic + Urban → Leave

If Casual + Basic + Rural → Renew

### Summary of Rules

If

Then predict

Subscribers

Viewing Pattern = Binge

Renew ✓

5 subscribers

Viewing Pattern = Casual and Plan Type = Premium

Renew ✓

2 subscribers

Viewing Pattern = Casual, Plan Type = Basic and Region = Urban

Leave ✗

4 subscribers

Viewing Pattern = Casual, Plan Type = Basic and Region = Rural

Renew ✓

GB72L5

Every subscriber in the past data is now assigned to a renewal outcome.

### The Complete Decision Tree

A Decision tree is a collection of rules used to determine a course of action .

We focus on a specific type of decision tree: Classification and Regression Trees (CART), a predictive model used to draw conclusions from data (a set of observations).

### Anatomy of a Decision Tree

### Components

Root node: The top node of the tree. It contains the complete dataset and represents the first decision rule.

Internal node: A non-terminal node that represents a decision rule, such as x > 7 or y = 7 .

Terminal node: A node with no descendants (child nodes). It is also called a "leaf node."

### The 12 Subscribers in Two Dimensions

### The 12 Subscribers in the Feature Space

### Depiction of Decision Boundaries

### Decision tree

Select a cube region to trace its rule through the tree.
### Reduction in Impurity

### Pure Group

### Maximum Impurity

A group is pure if everyone in it has the same outcome (all Yes or all No). It’s impure if it’s a mix.

### Our Root Node

### The Intuition

If a split produces one group that’s all Yes and another that’s all No, we can predict perfectly. The goal at every step is to get closer to that ideal.

### CART

The algorithm picks the split that creates the purest child groups, and thereby produces the biggest drop in impurity.

### Gini Impurity

G0 is the impurity at the parent node before we split.

G(L) and G(R) are the impurities of the two child nodes after the split.

What matters is the drop.

### Interpretation

A split is useful when the child nodes are less mixed than the parent node.

The bigger the reduction, the more that split improves purity, so CART prefers it.

### Gini Impurity Formula

In our case: Gini = 1 − p Y ² − p N ²

### Interpretation

0 = perfectly pure

0.5 = maximum impurity for two classes

### Intuition

Draw two members of this node independently with replacement. Gini impurity is the probability that their outcomes differ.

### Root Node Calculation

Our 12 subscribers: 8 Yes , 4 No

This is our starting impurity . Close to the maximum of 0.5 because our data has a genuine mix of outcomes.
### Splitting on Viewing Pattern

### Binge (5 users)

5 subscribers → All Yes

Perfectly pure!

### Casual (7 users)

3 Yes | 4 No

Nearly a coin flip.

### Gini Gain

Weighted average of child impurities:

Viewing Pattern reduces impurity by 36% in a single split, with one side becoming perfectly pure.

### Splitting on Plan Type

### Basic (8 users)

4 Yes | 4 No

Maximum impurity!

### Premium (4 users)

All Yes

Perfectly pure!

### Gini Gain

Weighted average of child impurities:

Plan Type is weaker than Viewing Pattern.

### Splitting on Region

### Urban (9 users)

5 Yes | 4 No

Nearly balanced.

### Rural (3 users)

All Yes

Perfectly pure!

### Gini Gain

Weighted average of child impurities:

Region is the weakest split among the three.
### Which feature creates the Purest Split?

### Level 1: Viewing Pattern Wins

Left child node: 100% pure ; right child node: impure .

### Gini Impurity of the Casual Node

Casual node: 3 Yes , 4 No

This is the baseline impurity for evaluating the next split.

### Splitting the Casual Branch

User

Plan Type

Region

Renew

HM84P1

Basic

Urban

No ✗

VX29D7

Basic

Urban

No ✗

CJ63R4

Basic

Urban

No ✗

TW15N8

Basic

Urban

No ✗

GB72L5

Basic

Rural

Yes ✓

PS48Y2

Premium

Urban

Yes ✓

DK96F3

Premium

Urban

Yes ✓

### Split by Plan Type

Basic (5): 1Y / 4N, Gini = 0.320

Premium (2): All Yes, Gini = 0.000

Gain ≈ 0.261

### Split by Region

Urban (6): 2Y / 4N, Gini ≈ 0.444

Rural (1): All Yes, Gini = 0.000

Gain ≈ 0.109

Plan Type is the winner for splitting the Casual branch.

### Level 2: Plan Type Wins

Left child node: 100% pure ; right child node: impure .

### Gini Impurity of the Casual + Basic Node

Casual + Basic node: 1 Yes , 4 No

This is the baseline impurity for evaluating the next split.
### Splitting the Casual + Basic Branch

User

Region

Renew

HM84P1

Urban

No ✗

VX29D7

Urban

No ✗

CJ63R4

Urban

No ✗

TW15N8

Urban

No ✗

GB72L5

Rural

Yes ✓

### Split by Region

Urban (4): All No, Gini = 0.000 (Pure!)

Rural (1): All Yes, Gini = 0.000 (Pure!)

Gain = 0.320

Region perfectly separates the Casual Basic users.

### Complete Tree

### Depiction of Decision Boundaries

### Decision tree

Select a cube region to trace its rule through the tree.

### Does Depth Matters?

### Depth 1

Viewing only: 9/12 correct

### Depth 2

Add Plan Type: 11/12 correct

### Depth 3

Add Region: 12/12 correct

### Does It Work on New Data ?

Trained Tree at Depth 3

Table displayed as labelled records for readability (6 rows, 7 columns).
RM54Q7

Viewing Binge

Plan Premium

Region Urban

Predicted ? Yes

Actual Yes

Match? ✓

XT83C6

Viewing Binge

Plan Basic

Region Rural

Predicted ? Yes

Actual Yes

Match? ✓

FN27H4

Viewing Casual

Plan Basic

Region Rural

Predicted ? Yes

Actual No

Match? ✗

BV61K9

Viewing Casual

Plan Premium

Region Urban

Predicted ? Yes

Actual Yes

Match? ✓

YP35A2

Viewing Casual

Plan Basic

Region Urban

Predicted ? No

Actual Yes

Match? ✗
JL90W5

Viewing Casual

Plan Basic

Region Urban

Predicted ? No

Actual Yes

Match? ✗

Training accuracy 100% (12/12)

---- accuracy 50% (3/6)

The region split sends the only actual churner to a renewal leaf based on one training subscriber.

### Does It Work on New Data ?

Trained Tree at Depth 1

Table displayed as labelled records for readability (6 rows, 7 columns).

RM54Q7

Viewing Binge

Plan Premium

Region Urban

Predicted Yes

Actual Yes

Match? ✓

XT83C6

Viewing Binge

Plan Basic

Region Rural

Predicted Yes

Actual Yes

Match? ✓

FN27H4

Viewing Casual

Plan Basic

Region Rural

Predicted No

Actual No

Match? ✓
BV61K9

Viewing Casual

Plan Premium

Region Urban

Predicted No

Actual Yes

Match? ✗

YP35A2

Viewing Casual

Plan Basic

Region Urban

Predicted No

Actual Yes

Match? ✗

JL90W5

Viewing Casual

Plan Basic

Region Urban

Predicted No

Actual Yes

Match? ✗

Training accuracy 75% (9/12)

---- accuracy 50% (3/6)

The viewing-only tree predicts churn for every casual viewer, including three who renewed.

### Does It Work on New Data ?

Trained Tree at Depth 2

Table displayed as labelled records for readability (6 rows, 7 columns).

RM54Q7

Viewing Binge

Plan Premium

Region Urban

Predicted Yes

Actual Yes

Match? ✓
XT83C6

Viewing Binge

Plan Basic

Region Rural

Predicted Yes

Actual Yes

Match? ✓

FN27H4

Viewing Casual

Plan Basic

Region Rural

Predicted No

Actual No

Match? ✓

BV61K9

Viewing Casual

Plan Premium

Region Urban

Predicted Yes

Actual Yes

Match? ✓

YP35A2

Viewing Casual

Plan Basic

Region Urban

Predicted No

Actual Yes

Match? ✗

JL90W5

Viewing Casual

Plan Basic

Region Urban

Predicted No

Actual Yes

Match? ✗

Training accuracy 92% (11/12)

---- accuracy 67% (4/6)

The plan split correctly predicts renewal for the casual Premium subscriber.
### Always Predict Renewal

Baseline Rule

Table displayed as labelled records for readability (6 rows, 7 columns).

RM54Q7

Viewing Binge

Plan Premium

Region Urban

Predicted Yes

Actual Yes

Match? ✓

XT83C6

Viewing Binge

Plan Basic

Region Rural

Predicted Yes

Actual Yes

Match? ✓

FN27H4

Viewing Casual

Plan Basic

Region Rural

Predicted Yes

Actual No

Match? ✗

BV61K9

Viewing Casual

Plan Premium

Region Urban

Predicted Yes

Actual Yes

Match? ✓

YP35A2

Viewing Casual

Plan Basic

Region Urban

Predicted Yes

Actual Yes

Match? ✓
JL90W5

Viewing Casual

Plan Basic

Region Urban

Predicted Yes

Actual Yes

Match? ✓

Training accuracy 67% (8/12)

---- accuracy 83% (5/6)

### Training and ---- Accuracy

Prediction rule

Training Accuracy

---- Accuracy

Depth 1

75% (9/12)

50% (3/6)

Depth 2

92% (11/12)

67% (4/6)

Depth 3

100% (12/12)

50% (3/6)

Always predict renewal

67% (8/12)

83% (5/6)

The always-renew rule gets the most ---- cases right. Among the trees, adding the region split at depth 3 fixes one training error and introduces one ---- error.

### Lesson

Perfect training accuracy does not mean good predictions on new data. Always ---- on held-out data.

### Overfitting

As the tree grows deeper:

Training accuracy keeps increasing (the tree memorizes more)

---- accuracy first increases, then decreases (overfitting begins)

The optimal depth is where the ---- accuracy is maximized.

### Ways to overcome Overfitting

To avoid overfitting the training data, you need to restrict the Decision Tree's freedom during training, also known as regularization .

### 1. Pre-pruning

Key hyperparameters: Maximum depth, minimum samples to split, minimum samples per leaf, maximum leaf nodes and maximum features.

Increasing the min* hyperparameters and reducing the max* hyperparameters will regularize the model.
### 2. Post-pruning

Grow the full tree first, then remove the branches that add more complexity than they do accuracy.

err ( T ) is the fraction of training records that are misclassified; L ( T ) is the number of leaf nodes (terminal nodes); and α is the penalty ("complexity parameter") for tree size.

Prediction rule

Training Accuracy

---- Accuracy

Depth 1

75% (9/12)

50% (3/6)

Depth 2

92% (11/12)

67% (4/6)

Depth 3

100% (12/12)

50% (3/6)

Always predict renewal

67% (8/12)

83% (5/6)

Which rule would you use to decide whom to contact: the always-renew rule with 83% ---- set accuracy or the depth-two tree with 67% accuracy?

### Confusion Matrices

Same six ---- subscribers. Leaving is the positive outcome (Renew = No).

Actual outcome

Predicted leave

Predicted renew

Left

1 True positive

0 False negatives

Renewed

2 False positives

3 True negatives

Actual outcome

Predicted leave

Predicted renew

Left

0 True positives

1 False negative

Renewed

0 False positives

5 True negatives

Predicting renewal for everyone misses the only churner. Depth 2 is preferable here if missing that churner costs more than following up with two subscribers who renewed.

### Churn Precision and Recall

Prediction rule

Actually left

Actually renewed

Precision Correct alerts / all alerts

Recall Churners caught / all churners

Depth 1

Depth 2

Depth 3

Always predict renewal

Always predict leave
Precision = TP / (TP + FP)

Recall = TP / (TP + FN)

### Strengths and Weaknesses

### Strengths

Interpretability

Non-linear relationships

Built-in feature selection

Faster training and inference

### Weaknesses

Greedy algorithm

Overfitting

Orthogonal decision boundaries

Bias toward imbalanced classes

Sensitive to variations in training data

### Thank You

Questions & Discussion

### Continuous Features

### Continuous Feature: Viewing Hours

Suppose we observe weekly viewing hours instead of classifying subscribers as Binge or Casual.

Subscriber

Viewing hours

Renew?

A

No

B

No

C

No

D

Yes

E

No

F

Yes

G

Yes

### Where could CART split?

CART first sorts the observed values:

It then ----- the midpoint of every gap:
### Choosing the Split Point

For every threshold t , CART compares subscribers with viewing hours ≤ t against those with viewing hours > t .

Threshold

Left child

Right child

Weighted Gini

1.5

0 Yes, 1 No

3 Yes, 3 No

0.429

2.5

0 Yes, 2 No

3 Yes, 2 No

0.343

4.0

0 Yes, 3 No

3 Yes, 1 No

0.214

6.0

1 Yes, 3 No

2 Yes, 1 No

0.405

7.5

1 Yes, 4 No

2 Yes, 0 No

0.229

9.0

2 Yes, 4 No

1 Yes, 0 No

0.381

Lowest weighted Gini: split at viewing hours ≤ 4.

### Efficient Gini Calculation

CART scans the sorted observations once. In this example, each step moves one observation from the right child to the left child and updates the class counts.

Scan position

Left child

Right child

Weighted Gini

Start

0 Yes, 0 No

3 Yes, 4 No

—

After 1 hour

0 Yes, 1 No

3 Yes, 3 No

0.429

After 2 hours

0 Yes, 2 No

3 Yes, 2 No

0.343

After 3 hours

0 Yes, 3 No

3 Yes, 1 No

0.214

CART updates the class counts rather than rereading every observation in each child node.

### Entropy

### Entropy & Information Gain

### Entropy Formula

For two classes, H = −p Y log 2 p Y − p N log 2 p N .

Entropy ranges from 0 bits for a pure node to 1 bit for an even split between the two classes.

### Root Node Calculation

8 Yes, 4 No (p Y = 2/3, p N = 1/3)

### Entropy Reduction for Each Feature

Information Gain = entropy before the split − weighted entropy after the split. Each child is weighted by its share of subscribers. Gains are rounded at the end.
### Viewing Pattern

Binge (5): H = 0

Casual (7): H ≈ 0.985

Information Gain ≈ 0.344 bits

### Plan Type

Basic (8): H = 1

Premium (4): H = 0

Information Gain ≈ 0.252 bits

### Region

Urban (9): H ≈ 0.991

Rural (3): H = 0

Information Gain ≈ 0.175 bits

### Gini vs. Entropy: Same Answer

Measure

Viewing Pattern

Plan Type

Region

Gini Gain

0.159

0.111

0.074

Information Gain (bits)

0.344

0.252

0.175

Winner

✓

✗

✗

Both measures rank these three splits in the same order. Gini is faster (no logarithms). Entropy is more theoretically grounded (information theory).


[↑ Back to the source list](#source-documents)

---

