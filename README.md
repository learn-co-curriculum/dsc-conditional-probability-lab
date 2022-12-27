# Conditional Probability - Lab

## Introduction

In order to be ready for real-world applications of probability, it is important to understand what happens when probabilities are not independent. Very often, the probability of a certain event depends on other events happening! Let's see how this all works in this lab.

## Objectives

You will be able to:

* Differentiate between independent and dependent events
* Use the multiplication rule to find the probability of the intersection of two events

## Exercise 1
A coin is tossed and a single 6-sided die is rolled. Find the probability of landing on the head side of the coin and rolling a 3 on the die.


```python
P_h =1/2
  
P_3	= 1/6

# As the events are independent 
P = P_h*P_3
P
```




    0.08333333333333333



## Exercise 2


After conducting a survey, one of the outcomes was that 8 out of 10 of the survey subjects liked chocolate chip cookies. If three survey subjects are chosen at random **with replacement**, what is the probability that all three like chocolate chip cookies?


```python
#Probabilities
P_subject1 = P_subject2 = P_subject3 = 8/10
    
# Probability that subject 1 and subject 2 and subject 3 like chocolate chip cookies
# Remember (With replacement) makes these trials independent
P_1_2_3 = P_subject1*P_subject2*P_subject3


P_1_2_3
```




    0.5120000000000001



## Exercise 3
70% of your friends like chocolate flavored ice cream, and 35% like chocolate AND like strawberry flavors.

What percent of those who like chocolate also like strawberry?


```python
# P(Strawberry|Chocolate) = P(Chocolate and Strawberry) / P(Chocolate)

p_strberry_given_choc = 0.35 / 0.7
p_strberry_given_choc
```




    0.5



50% of your friends who like chocolate also like strawberry

## Exercise 4
What is the probability of drawing 2 consecutive aces from a deck of cards. 


```python
# Let Event A be drawing the first ace, and Event B be drawing a second ace

# For the first card, the chance of drawing an ace is 4 out of 52 (there are 4 aces in a deck of 52 cards):

P_A = 4/52

# But after removing an ace from the deck the probability of the 2nd card drawn is less likely to be a ace (only 3 of the 51 cards left are aces):

P_B_given_A = 3/51

# And so according to the product rule:

P_A_and_B = P_A * P_B_given_A
P_A_and_B
```




    0.004524886877828055



## Exercise 5
In a manufacturing factory that produces a certain product, there are 100 units of the product, 5 of which are defective. We pick three units from the 100 units at random. 

What is the probability that none of them are defective?
Hint: Use the chain rule here!


```python
# Let us define Ai as the event that the ith chosen unit is not defective, for i=1,2,3. 
# We are interested in P(A1∩A2∩A3). Note that
P_A1=95/100.

#Given that the first chosen item was good, the second item will be chosen from 94 good units and 5 defective units
P_A2_given_A1=94/99

# Given that the first and second chosen items were okay, the third item will be chosen from 93 good units and 5 defective units, thus
P_A3_given_A2_A1=93/98

# Accoring to chain rule
P_A1_A2_A3=P_A1*P_A2_given_A1*P_A3_given_A2_A1

P_A1_A2_A3
```




    0.8559987631416203



## Exercise 6

Let's consider the example where 2 dice are thrown. Given that **at least one** of the die has come up on a number higher than 4, what is the probability that the sum is 8?

Let $i,j$ be the numbers shown on the dice. The events $A$ and $B$ are described below:

* **Event $A$ is when either $i$ or $j$ is 5 or 6** (keep an eye on either - or)
* **Event $B$ is when $i + j = 8$**


* What is the size of sample space $\Omega$ ?
* What is $P(A \cap B)$ ?
* What is $P(A)$ ?
* Use above to calculate $P(B \mid A)$


```python
p_B_given_A = (4/36)/(20/36) 
p_B_given_A

# Explanation
# total possible outcome = 36
# total possible outcomes that met the condition of one of the two dice having a 
# value greater than 4 is {[1,5], [1,6], [2,5], [2,6], ....[6,5], [6,6]} = 20
# P(at least 1 die is greater than 4) = P(A) = 20/36 = 0.5556
# P(B and A) is the probability that the sum of two dice equal 8 and one of the
# dice is greater than 4, which the possible outcomes are {[2,6], [3,5], [5,3], [6,2]},
# so the P(B and A) is 4/36 = 0.1111
# dividing P(B and A) by P(A) returns the conditional probability P(B|A) = (4/36)/(20/36)
```




    0.19999999999999998



## Exercise 7

Let's consider a credit card example. At a supermarket, customers are selected randomly, the store owner recorded whether costumers owned a Visa card (event A) or an Amex credit card (event B). Some customers own both cards.
You can assume that:

- $P(A)$ = 0.5
- $P(B)$ = 0.4
- both $A$ and $B$ = 0.25.


With the knowledge we have about conditional probabilities, compute and interpret the following probabilities:

- $P(B \mid A)$
- $P(B' \mid A)$
- $P(A \mid B)$
- $P(A' \mid B)$



```python
p_B_given_A = 0.25/0.5  
p_B_given_A # correct answer: 0.5
```




    0.5




```python
p_B_prime_given_A = 1 - 0.5
p_B_prime_given_A # correct answer: 0.5
```




    0.5




```python
p_A_given_B = 0.25/0.4
p_A_given_B # correct answer: 0.625
```




    0.625




```python
p_A_prime_given_B = 1 - 0.625 
p_A_prime_given_B  # correct answer: 0.375
```




    0.375



## Summary 

In this lab, you practiced conditional probability and its theorem with some simple problems. The key takeaway from this lab is to be able to identify random events as dependent or independent and calculating the probability of their occurrence using appropriate methods. Next, you'll learn about some more conditional probability axioms, building on the knowledge we have so far. 
