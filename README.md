
# Poisson Distribution - Lab

## Introduction

In this lab, we'll put our knowledge of the Poisson Distribution to use to answer solve some sample real-world problems!

## Objectives

You will be able to:

* Understand and explain the Poisson Distribution and its use cases.


## Instructions

Solve the following sample problems by using python and your knowledge of the Poisson Distribution.

## Getting Started

Good Data Scientists plan ahead! Since you're going to be solving Poisson Distribution problems in this lab, it's probably a good idea to write a function that calculates Poisson Probability for us first. 

Recall that the Poisson Probability Formula is:

$$p(x) = \frac{\lambda^xe^{-x}}{x!}$$

Write a generalized that takes in the appropriate parameters and returns the Poisson Probability.

**_NOTE:_**  You can use `np.exp()` to quickly calculate $e$, and `math.factorial` (from the `math` library, not numpy) to calculate factorials. 

**_HINT:_** It's up to you whether or not you have your function calculate the value for lambda given $\mu$ and the interval, or whether you calculate lambda yourself beforehand and just pass it into the function. 


```python
import numpy as np
from math import factorial
```


```python
def poisson_probability(lambd, x):
    return ((lambd)**x * (np.exp(-x))) / factorial(x)
```

## Question 1

A fireman fights, on average, 4 fires per month. What is the probability that a fireman is called to two different fires this week?


```python
lambd_q1 = 4 / 4
prob_q1 = poisson_probability(lambd_q1, 2)
print(prob_q1)
```

    0.06766764161830635


## Question 2

A car salesman sells an average of 4 cars per week.  What is the probability they sell a car today?


```python
lambd_q2 = 4 / 7
prob_q2 = poisson_probability(lambd_q2, 1)
print(prob_q2)
```

    0.21021682352653848


## Question 3

A website makes an average of 50 sales per day.  What is the probability that they make 3 sales in an hour? 


```python
lambd_q3 = 50 / 24
prob_q3 = poisson_probability(lambd_q3, 3)
print(prob_q3)
```

    0.07503114807560515


## Question 4

A factory produces 250 cars per week (assume that the factory runs day and night all week with no down time). What is the probability that they produce 3 cars in the next hour?


```python
lambd_q4 = 250 / (24 * 7 )
prob_q4 = poisson_probability(lambd_q4, 3)
print(prob_q4) 
```

    0.02734371285554123


## Question 5

The following table shows the number of houses sold by a realtor each week for the month of May. What is the probability that they sell 3 houses next week?

| Week | Houses Sold |
|:----:|:-----------:|
|   1  |      6      |
|   2  |      2      |
|   3  |      5      |
|   4  |      4      |


```python
mean_weekly_sales = (6+2+5+4)  / 4 
print(mean_weekly_sales)
lambd_q5 = mean_weekly_sales # Already in weekly format, no need to reduce further
prob_q5 = poisson_probability(lambd_q5, 3)
print(prob_q5)
```

    4.25
    0.6369892366961343


## Summary

In this lab, we got some practice making use of our knowledge of the Poisson Distribution to answer some real-world questions!
