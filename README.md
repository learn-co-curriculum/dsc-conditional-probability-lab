
# Conditional Probability - Lab

## Introduction

In order to be ready for real world applications of probability, it is important to understand what happens when probabilities are not independent. Very often, the probability of a certain event depends on other events happening! Let's see how this all works in this lab.

## Objectives

You will be able to:

- Understand and explain the conditional probability - $P(A \cap B) = P(A \mid B) P(B)$
- Use the multiplication rule to find the probability of the intersection of two events
- Apply the techniques learned in the lesson to simple problems

## Exercise 1
A coin is tossed and a single 6-sided dice is rolled. Find the probability of landing on the head side of the coin and rolling a 3 on the dice.


```python
P_h =1/2
  
P_3	= 1/6

#As the events are independent 
P = P_h*P_3
P
```




    0.08333333333333333



## Exercise 2
A school survey found that 9 out of 10 students like pizza. If three students are chosen at random **with replacement**, what is the probability that all three students like pizza?


```python
#Probabilities
P_student1 = P_student2 = P_student3 = 9/10
    
# Probability that student 1 and student 2 and student 3 like pizza
# Remember (With replacement) makes these trials independent
P_1_2_3 = P_student1*P_student2*P_student3


P_1_2_3
```




    0.7290000000000001



## Exercise 3
70% of your friends like chocolate flavored ice cream , and 35% like chocolate AND like strawberry flavors.

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
# Let Event A is drawing the first ace, and Event B is drawing a second ace

#For the first card the chance of drawing an ace is 4 out of 52 (there are 4 aces in a deck of 52 cards):

P_A = 4/52

# But after removing an ace from the deck the probability of the 2nd card drawn is less likely to be a ace (only 3 of the 51 cards left are aces):

P_B_given_A = 3/51

#And so according to the product rule:

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

## Exercise 6

Let's consider the example where 2 dice are thrown. Given that **at least one** of the dice has come up on a number higher than 4, what is the probability that the sum is 8?

Let $i,j$ be the numbers shown on the dice. The events $A$ and $B$ are described below:

* **Event $A$ is when either $i$ or $j$ is 5 or 6** (keep an eye on either - or)
* **Event $B$ is when $i + j = 8$**


* What is the size of sample space $\Omega$ ?
* What is $P(A \cap B)$ ?
* What is $P(A)$ ?
* Use above to calculate $P(B \mid A)$

### solution

* $A:= \{(i,j) \in \Omega \mid \text{either $i$ or $j$ is 5 or 6}\}$

* $B:= \{(i,j)\in \Omega \mid i+j = 8\}$

* In total, there are possible 36 outcomes, so $\Omega = 36$.

* $P(A) = 20/36$ - Event $A$ has 20 possible outcomes out of 36 - ( five in each case * 4 ) 
* $P(A \cap B) = 4/36$ - Event $B$ has 4 possible outcomes out of 36 - (2 and 6, 3 and 5, 6 and 2, 5 and 3)


 We want to know what the probability of $B$ is given $A$, so $P(B \mid A)= \dfrac{P(B\cap A)}{P(A)}$. This leads to:




```python
p_B_given_A = (4/36)/(20/36) 
p_B_given_A  
```




    0.19999999999999998



## Exercise 7

Let's consider a credit card example. At a supermarket, we randomly select customers and make notes of whether a given customer owns a Visa card (event A) or an Amex credit card (event B). Some customers own both cards.
You can assume that:

- P(A) = 0.5
- P(B) = 0.4
- both A and B = 0.25.


With the knowledge we have about conditional probabilities, compute and interpret the following probabilities:

- $P(B \mid A)$
- $P(B'\mid A)$
- $P(A\mid B)$
- $P(A'\mid B)$


### Solution

* $P(B \mid A)$

Probability of having an Amex credit card given that they have a Visa card

$P(B \mid A)= \dfrac{P(B\cap A)}{P(A)}$


```python
p_B_given_A = 0.25/0.5  
p_B_given_A # correct answer: 0.5
```




    0.5



#### - $P(B' \mid A)$

Probability of not having an Amex credit card given that they have a Visa card


```python
p_Bcomp_given_A = 1 - 0.5
p_Bcomp_given_A # correct answer: 0.5
```




    0.5



#### - $P(A \mid B)$

$P(A \mid B)= \dfrac{P(B\cap A)}{P(B)}$

Probability of having a Visa credit card given that they have an Amex card


```python
p_A_given_B = 0.25/0.4
p_A_given_B # correct answer: 0.625
```




    0.625



#### - $P(A'\mid B)$

Probability of not having a Visa credit card given that they have an Amex card


```python
p_A_prime_given_B = 1 - 0.625 
p_A_prime_given_B  # correct answer: 0.375
```




    0.375



## Summary 

In this lab we practiced around conditional probability and its theorem with some simple problems. The key takeaway from this lab is to to be able to identify random events as dependent or independent and calculating the probability of their occurrence using appropriate methods. Next we'll start focusing on the some more conditional probability axioms, building on the knowledge we have thus far. 
