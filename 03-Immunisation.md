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

If   $$NPV_+(r)=\displaystyle\sum_{i=1}^{n_+} C_i^+e^{-rt_i^+}$$

Then $$NPV_+'(r)=\displaystyle\sum_{i=1}^{n_+} C_i^+(-t_i^+)e^{-rt_i^+}$$

Then, the weighted average of $t_i^+$ weighted by present value of cashflows is called the duration and is denoted by this equation:
$$\frac{NPV'(r)}{NPV(r)}=\displaystyle\sum_{i=1}^{n_+} t_i^+ \frac{C_i^+e^{-rt_i^+}}{\displaystyle\sum_{j=1}^{n_+} C_j^+e^{-rt_j^+}}$$

Convexity of a series of cashflows is:

$$\frac{NPV''(r)}{NPV(r)}$$

  

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

### Exercise 3.3 (from Exercise Sheet 3)

a) For first order immunisation, we need to have all +ve NPV and durations equal to -ve NPV and durations. 

$NPV_-(r)=NPV_+(r):$ (1) $20D(t_{10})+40D(t_{15})=PD(t_{25})+Q$, where $D(t)=e^{-0.07t}$

+ve duration: $$\frac{25PD(t_{25})}{PD(t_{25})+Q}$$

-ve duration: $$\frac{200D(t_{10})+600D(t_{15})}{20D(t_{10})+40D(t_{15})}$$

+ve duration = -ve duration: (2) $$\frac{25PD(t_{25})}{PD(t_{25})+Q}=\frac{200D(t_{10})+600D(t_{15})}{20D(t_{10})+40D(t_{15})}$$

sub equation (1) into (2), then multiply out by $NPV_-(r)$, to get this:

$$25PD(t_{25})=200D(t_{10})+600D(t_{15})$$, 

$\therefore P=\frac{200D(t_{10})+600D(t_{15})}{25D(t_{25})}$, sub in $D(t)=e^{-0.07t}$ to get $P\approx71.191$ & $Q\approx11.558$

b) to be Reddington immunised, $+ve convexity\geq-ve convexity$

-ve convexity: $$\frac{2000D(t_{10})+9000D(t_{15})}{20D(t_{10})+40D(t_{15})}$$

+ve convexity: $$\frac{625PD(t_{25})}{PD(t_{25})+Q}$$

+ve convexity = -ve convexity: $$\frac{625PD(t_{25})}{PD(t_{25})+Q}\geq\frac{2000D(t_{10})+9000D(t_{15})}{20D(t_{10})+40D(t_{15})}$$, sub in all variables.

Then, $323.119...\geq173.119...$, $\therefore$ the cashflows are also Reddington immunised.

c)The assets and liabilities would not be equal if instead they had a five year bond, which is a key qualification for the cashflows to be first order immunised. 

### Exercise 3.6 (from Exercise Sheet 3)

The method for this question is the same as the 3rd question, however this time we are showing the opposite.

Make +ve NPV = -ve NPV, to find the two asset variables.

(1) $$20D(t_{3.5})+18D(t_6)=XD(t_4)+YD(t_7)$$, where X and Y are the zero bond coupons and $D(t)=e^{-0.1t}$.

Make +ve durations = -ve durations:

+ve duration: $\frac{4XD(t_4)+7YD(t_7)}{XD(t_4)+YD(t_7)}$

-ve duration: $\frac{70D(t_{3.5})+108D(t_6)}{20D(t_{3.5})+18D(t_6)}$

(2) $\frac{4XD(t_4)+7YD(t_7)}{XD(t_4)+YD(t_7)}=\frac{70D(t_{3.5})+108D(t_6)}{20D(t_{3.5})+18D(t_6)}$

Sub (1) into (2), and multiply out by -ve NPV to get:

(3) $$4XD(t_4)+7YD(t_7)=70D(t_{3.5})+108D(t_6)$$

Rearrange (1) and sub into (3) to get:

$$X=\frac{70D(t_{3.5})+18D(t_6)}{3D(t_4)}, \therefore X\approx29.442$$, and $$\therefore Y=8.5318$$

Now calculate the convexity for the last condition:

+ve convexity: $\frac{16XD(t_4)+49YD(t_7)}{XD(t_4)+YD(t_7)}$

-ve convexity: $\frac{245D(t_{3.5})+648D(t_6)}{20D(t_{3.5})+18D(t_6)}$

For the cashflows to be Reddington immune, +ve convexity $\geq$ -ve convexity

$$\therefore \frac{16XD(t_4)+49YD(t_7)}{XD(t_4)+YD(t_7)} \geq \frac{245D(t_{3.5})+648D(t_6)}{20D(t_{3.5})+18D(t_6)}$$
For these cashflows to be Reddington immune. 

Subbing in D(t) and X & Y:

$21.83228...\ngeq22.03697...$, the condition is not fulfilled, and $\therefore$ these cashflows are not Reddington immune. 

## Spreadsheet

[01-InterestRates.xlsx](spreadsheets/01-InterestRates.xlsx):

This excel file, calculates the return of a deposit £P after time t and the new payoff of different i/r which are Compounded annually, Compounded monthly, Compounded semi-annually, Compounded continuously.

You need to input three variables: in cell B7 input r, cell B8 input t, cell B9 input P.
