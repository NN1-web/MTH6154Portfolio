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

Therefore, the pay out is equal to $£3560*(e^{(\frac{\ln (10)}{10}+0.075+\frac{0.009}{2}10)10})$, in 10 years time.
             
## Solved exercises

### Exercise 1.1 (from Exercise Sheet 1)

Suppose you put £700 in a bank account with nominal interest rate 3%. 
(a) How much money will be in the bank account three years from now if the interest is:
(i)Compounded annually?
(ii)Compounded monthly?
(iii)Compounded semi-annually?
(iv)Compounded continuously?

Solutions:
a)i) we use this formula referenced in the notes earlier: $(1+r*\frac{1}{365})^m$, this was adjusted to give a daily rate as interest rates are normally given annually, we need to change this back to an annual rate. 
Thus the new formula is - $(1+r)^t$, with t = years instead. 
Using the formula we obtain - $£700*(1+0.03)^3 \approx 764.91$

a)ii) now convert to monthly rates - $(1+r*\frac{1}{12})^n$, with n= months instead. Therefore, solution - $£700*((1+0.03*\frac{1}{12})^{36} \approx 765.84$

a)iii) convert to semi-annually - $£700*(1+0.03*\frac{1}{2})^6 \approx 765.41$

a)iv) use continuously compounded formula - $e^{rt}$, $£700*e^{0.03*3} \approx 765.92$

(b) Find the effective interest rates for each case (i)–(iv) from part (a).

b)i) the effective i/r is annualised i/r for the rate given, it is the how much return that rate gives in a year. for i) the rate is already annualised, therefore the effective rate is simply 3%. we can use the formula0.0305 to check: the rate given annualised minus 1.
$(1+0.03)-1=0.03$

b)ii) the rate given annualised - $(1+\frac{0.03}{12})^12-1 \approx 0.0304$

b)iii) $(1+\frac{0.03}{2})^2-1 \approx 0.0302$

b)iv) set t = 1, $e^{0.03}-1 \approx 0.0305$

(c)Suppose the inflation rate is 2%. Calculate the ‘inflation adjusted interest rate’ for each case (i)–(iv) from part (a).

c)i) the inflation adjusted i/r is simply the real rate, for this we can use the formula referenced above - $r=\frac{1+i}{1+\pi}-1$, where $i$ = nominal i/r, $\pi$ = inflation rate.
Therefore, the real rate is equal to $r=\frac{1+0.03}{1+0.02}-1 \approx 0.009804$

c)ii) we use the effective rate for one year for the rest of the questions. $r=\frac{1+0.0304}{1+0.02}-1 \approx 0.0102$

c)iii) $r=\frac{1+0.0302}{1+0.02}-1 \approx 0.01$

c)iv) $r=\frac{1+0.0305}{1+0.02}-1 \approx 0.01029$

(d) Suppose interest is compounded semi-annually. How long will it take for the bank balance to grow to £1000?

d) now we focus on the way we calculated semi-annually compounded rates in part iii) and work backwards with time t as the unknown. remembering that t in semi-annual rates is equal to 1/2 of a year.

$$£700*(1+\frac{0.03}{2})^t=£100$$

$$(1+\frac{0.03}{2})^t=£10/7$$

$$t*\log(1+0.03/2)=\log(10/7)$$

$$\therefore t=\frac{\log(10/7)}{\log(1+0.03/2)} \approx 23.956$$

$$t/2 \approx 11.978 years$$

### Exercise 1.3 (from Exercise Sheet 1)

Suppose $P$ is deposited in a bank account with interest continuously compounded at rate $r(t)$. Write down an expression, in terms of 
$r(t)$, for:
(a)The yield curve $\bar{r}(t)$.

(b)The bank balance at time $T$.

a) using the reasoning used in the notes earlier, $$\bar{r}=\frac{1}{T}\int_0^\{t} \mathrm{r(t)}\,\mathrm{d}t$$, $\bar{r}(t)$ is basically the average of different i/r in the time period.

b) using the reasoning in the notes earlier, bank balance at time T would be equal to, the return of the investment - using continuously compounded rates in terms of r(t), times by the orginal amount of money - here notated as £P.

Thus the bank balance at time T is equal to - $$£P*e^{(\frac{1}{T}\int_0^\{t} \mathrm{r(t)}\,\mathrm{d}t)T}$$ 

## Spreadsheet

[01-InterestRates.xlsx](../spreadsheets/01-InterestRates.xlsx): what it
does, which cells to change and what to look at.
