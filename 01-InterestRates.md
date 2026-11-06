# 1. Interest rates

[Back to contents](README.md)

## Summary

**Topics covered this week include:** 
- Base rate
- SONIA/Instantaneous rate
- Compounding rate
- Yield curve
- Annual percentage rate
- Continuously compounded interest rates
- [Real rate](https://github.com/NN1-web/MTH6154Portfolio/blob/60b1c02967eeb7b4673d837fe3ce3e904f6e7d5f/01-InterestRates.md#L42)

**Base Rate**

Central Banks set a Base interest rate - this is the rate for overnight deposits. This base rate is intended only for certain institutions. The return on deposits are annualised, and this is referred to as the annualised return, $R=rt$. Annualised interest rates are therefore $r=R/t$.

The Base rate is used in certain institutions, but other bodies also deposit/loan. Transactions at different rates occur between these different institutions.

**SONIA/Instantaneous rate**

SONIA - Sterling overnight Index Average, this is the average of the different interest rates used in all transactions over night. Hence, this is the instantaneous rate for that night, valid for this overnight period. 

**Compounding rate**

Instead of depositing in a bank, and leaving that said amount for how many days, compounding is when you reinvest the money you deposited into the bank. 

Lets say you have £10, instead of depositing in a bank and forgetting about it for 5 days, you deposit it on the first day - take it out, and then deposit it again - repeating this for five days. 
This formula is used to calculate the amount you have after five days:

$$
£P\left(1+\frac{r}{365}\right)^5
$$

$r$ being either base rate or SONIA, $£P=10$

**Yield curve**

Interest rate in reality, do not stay the same - they change for different times.
A yield curve shows the way interest rates increase or decrease with time - essentially it shows the relationship between these two variables. 

To model this yield curve, we need to use continuously compounded interest rates.

**Continuously compounded interest rates**

Thinking back to compounded rates, the general formula for calculating the amount earnt is $(1+r*\frac{1}{365})^m$, where m is the number of days compounded. 

To try and model the yield we want to see how this equation reacts when ${n\to\infty}$, compounding the rate every milisecond.

Through some maths and calculus, we discover that it can be modelled by this

$$
e^{rt}
$$

where r is the continuously compounded rate.
But this only gives us the picture for one r, we want to model when this r changes dependant on time t.

Thus, we repeat the same steps for when r is a function of t, r(t). Through some more maths and confusing calculus, we discover that it can be modelled by this 

$$
£P*e^{\int_0^\t \mathrm{r(t)}\,\mathrm{d}t}
$$


In your own words, the main ideas of the lesson. Short sentences are fine.


Maths is written between dollar signs. For example `$A = P(1+i)^n$` shows
as $A = P(1+i)^n$, and a displayed formula uses double dollars:

$$
\left(1+\frac{i^{(m)}}{m}\right)^m = 1+i
$$

Or more commonly written, 

## My example

A situation you made up (your own numbers, not the ones in the lecture
notes), worked step by step.

## Solved exercises

### Exercise 1.x (from Exercise Sheet 1)

Question, then your solution.

Real rate

## Spreadsheet

[01-InterestRates.xlsx](../spreadsheets/01-InterestRates.xlsx): what it
does, which cells to change and what to look at.
