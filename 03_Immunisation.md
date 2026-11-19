# 1. Immunisation

[Back to contents](README.md)

## Summary

**Reddington Imunisation**

The NPV of different cashflows are dependent on r - NPV goes down and up when r changes. This is market risk, to try and control this unpredictability, we need the NPV to conform to certian conditions - this is called Reddington immunisation.

For cashflows to be hedged against risk and be considered Reddington immune, must fulfill these conditions:
- $NPV(r_{0})=0$ (0-order immune)
- $NPV'(r_{0})=0$ (1-order immune)
- $NPV''(r_{0})\geq0$

Which means the $NPV(r_{0})$ function looks like a +ve quadratic function, the NPV=0 where $r=r_{0}$. This immunisation only accounts for changes in r close to the $r_{0}$ value, with large changes the function is different, and thus the NPV is no longer guaranteed hedged. 

If you are 1st order/Reddington immunised with continuously compounded rate then you are 1st order/Reddington immunised with annual compounded rate. 
Proof involves comparing both NPVs, with different discount rates - they do not retain the same deltas however the conditions still hold over both rates. 

**Assets and Liabilites**

Cashflows $\geq0$ are classified as assets and are denoted by:

$$C_1^+,......,C_{n_+}^+$$,  at  $$t_1^+,......,t_{n_+}^+$$

Cashflows $\leq0$ are classified as liabilities and are denoted in absolute value by:

$$C_1^-,......,C_{n_-}^-$$,  at  $$t_1^-,......,t_{n_-}^-$$

Present value of +ve cashflow is denoted as $NPV_+(r)$, present value of -ve cashflows is denoted as $NPV_(r)$.

Then the overall $NPV(r)=NPV_+(r)-NPV_(r)$, as derivation is linear, we can rewrite the Reddington immunisation conditions in terms of +ve and -ve cashflows. 

A series of cashflows are Reddington Immune if
- $NPV_+(r_0)=NPV_-(r_0)$ - this means the assets and liabilities are balanced. 
- $NPV_+'(r_0)=NPV_-'(r_0)$
- $NPV_+''(r_0)\geq NPV_-''(r_0)$

If   $$NPV_+(r)=\displaystyle\sum_{i=1}^{n_+} C_i^+e^{-rti^+}$$

Then $$NPV_+'(r)=\displaystyle\sum_{i=1}^{n_+} C_i^+(-ti^+)e^{-rti^+}$$

  

## My example

Consider this series of cashflows:
- Deposit of £X
- Cash in flow of £3000, in year 1
- Cash out flow of Y
- Cash in flow of £600

Using continuously compounded i/r and r=2.5%, figure out X,Y such that these cashflows are both 0 and 1st order immune and then evaluate whether or not they are Reddington immune.

Firstly, we start with the NPV equation, 

$$NPV(r)=X+3000* D(1)-Y* D(2)+600*D(3)$$

The i/r is continuously compounding, therefore $D(t)=e^{-rt}$

Subbing this into the equation, we get $NPV(r)=X+3000e^{-r}-Ye^{-2r}+600e^{-3r}$

For 0-order immunisation, NPV=0 & r=2.5%. 

1. $$0=X+3000e^{-0.025}-Ye^{-0.05}+600e^{-0.075}$$

For 1st-order immunisation, NPV'=0.

$$NPV'(r)=X-3000e^{-r}+2Ye^{-2r}-1800e^{-3r}$$ So, 2. $$0=X-3000e^{-0.025}+2Ye^{-0.05}-1800e^{-0.075}$$

We now use equation 1 and 2 to solve for the variables X and Y. 

Equation 1*2 plus equation 2, gives us - $$X=200e^{-0.075}-1000e^{-0.025}$$
and therefore $$Y=\frac{800e^{-0.075}+2000e^{-0.025}}{e^{-0.05}}$$

To see if these cashflows are Reddington Immune, we need to calculate NPV''(r).

$$NPV(r)=X+3000e^{-r}-4Ye^{-2r}+5400e^{-3r}$$, when r=2.5% - $$NPV(0.025)=X+3000e^{-0.025}-4Ye^{-0.05}+5400e^{-0.075}$$, subbing in X and Y.

$$NPV(0.025)=2400e^{-0.075}+10000e^{-0.025}\geq0$$, therefore with these values of X and Y, the cashflows are Reddington immune.


             
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

[01-InterestRates.xlsx](spreadsheets/01-InterestRates.xlsx):

This excel file, calculates the return of a deposit £P after time t and the new payoff of different i/r which are Compounded annually, Compounded monthly, Compounded semi-annually, Compounded continuously.

You need to input three variables: in cell B7 input r, cell B8 input t, cell B9 input P.
