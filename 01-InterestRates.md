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
- Real rate

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
£P*e^{\int_0^\{t} \mathrm{r(t)}\,\mathrm{d}t}
$$

Or more commonly written, where T is the time when the deposit is paid to us

$$
£P*e^{(\frac{1}{T}\int_0^\{t} \mathrm{r(t)}\,\mathrm{d}t)T}
$$ 

or 

$$
£P*e^{\bar{r}T}$$ where $$\bar{r}=\frac{1}{T}\int_0^\{t} \mathrm{r(t)}\,\mathrm{d}t
$$

$\bar{r}$= rate for maturity T (i/r for a deposit to time T), $\bar{r}$ as a function of T, $\bar{r}(T)$, is equal to the yield curve. This function is equivalent to the average of all instantaneous rates.

**Annual percentage rate**

This annualises a rate offered to you, and gives you its effective rate for 1 year, i.e. it gives you the rate equivalent to holding a 1 year debt of the rate offered to you. 

**Real rate**

The inflation rate is calculated using the CPI (consumer price index)

$\pi_t=\frac{CPI_t-CPI_{t-1}}{CPI_{t-1}}$

Inflation degrades the value of money as time goes on (or increases it with deflation), this then in turn degraded the real value of your returns.
Therefore, taking into account inflation, the real i/r is

$r=\frac{1+i}{1+\pi}-1$
where $i$ = nominal i/r, $\pi$ = inflation rate.


## My example

Yield curve example:

Find the yield curve equation for r(t) = $\frac{1}{t}+0.075+0.009t$

Firstly, calculate $\bar{r}(t)$. $\bar{r}(t)$ is equal to the integral of $r(t)*\frac{1}{T}$

$\bar{r}(t)$ = $\frac{1}{T}(\int_0^\{t} \mathrm{\frac{1}{t}+0.075+0.009t}\)\mathrm{d}t$
             = $\frac{1}{T}(\ln (T)+0.075T+\frac{0.009}{2}T^2)$
             = $\frac{\ln (T)}{T}+0.075+\frac{0.009}{2}T$

If you deposited £3560 into a bank, how much will it pay out in 10 years time?

To calculate this, we need the equation referenced above, $\bar{r}(t)$, P and T. £P=£3560, T=10 and $\bar{r}(t)$ = $\frac{\ln (T)}{T}+0.075+\frac{0.009}{2}T$
             


A situation you made up (your own numbers, not the ones in the lecture
notes), worked step by step.

## Solved exercises

### Exercise 1.x (from Exercise Sheet 1)

Question, then your solution.

Real rate

## Spreadsheet

[01-InterestRates.xlsx](../spreadsheets/01-InterestRates.xlsx): what it
does, which cells to change and what to look at.
