# 4. Bonds

[Back to contents](README.md)

## Summary

**Bonds**

Bonds are similar to loans, however they are standardised, not just between two parties, therefore they can be brought and sold in a market. 

If you are a bond holder, the bond issuer states they will give back a larger sum at the end - face value, or give smaller regular fixed amounts as well - coupons. 

If i/r increases - value of the bond decreases, if i/r decreases - value of the bond increases. 



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

[03-Immunisation.xlsx](spreadsheets/03-Immunisation.xlsx):

This excel file calculates for both +ve and -ve cashflows: NPV, duration and convexity - shown by the last three yellow tables. 

Inputting: r in cell B2, Liabilities in column D and the liabilities t in column E, Assets in column H and the assets t in column I. All the blue tables.
