# 1. Present Value

[Back to contents](README.md)

## Summary

Lets say, that you will take out a deposit you've kept in the bank for 10 years. The value of that deposit is now £P*. The present value of this deposit is how much £P you must deposit in the bank to get £P* in 10 years time.

For example, you take out a deposit of £650, its been in the bank for 5 years and with a continuously compounded rate of 2%.
We can write out the formula, with £P*=£650, r=0.02, t=5.

$£650=e^{0.02*5}*£P$ we rearrange this to get, $£P=\frac{$650}{e^{0.02*5}} \approx 588.144$

Because of the different rates and ways of calculating rates, this division of the rate, in the example it was $e^{-0.02*5}$, is generalised and called the discount factor - $D(t)$.
Officially, the discount factor at time t is the present value if £1 - therefore, the present value of £P at time t is $£P*D(t)$.

#Net Present value

If we have many cashflows happening at different times, then the net present value is the sum of the cashflows present values.
For example with cashflows $C_{1},C_{2}$ at times $t_{1},t_{2}$ respectively, the net present value is = $C_{1}*D(t_{1}) + C_{2}*D(t_{2})$.

Using this definition and geometric series equations, assuming r is +ve, we can calculate the net present value of many cashflows.  

So far we have assumed that i/r stay the same throughout the cashflows, however what if they do not?

If i/r decreases, then the NPV increases as the return on investment is less, vise versa for if the i/r increases. This uncertainty is classified as market risk. 

#Internal rate of return

In order to check whether or not our investments were good or not, we use this formula to check the annualised rate of return, $r=\frac{p_{1}-p_{0}}{p_{0}*t}$
If $r\leq$ rate given for you deposit - then it is a bad investment. If $r\geq$ rate given for you deposit - then it is a good investment. 
However, this method of evaluation only works if there is one cashinflow and one cashoutflow.

We use the internal rate of return instead, when there are multiple cashflows.

We combine use the NPV equation, equaling it to zero - thus the IRR is the rate at which NPV=0: 

The internal rate of return (IRR) is r, such that at times $t_{0},...,t_{n}$ cash flows are $C_{0},...,C_{n}$ respectively.

$$C_{0}-\frac{C_{1}}{(1+r)^{t_{1}}}-......-\frac{C_{n}}{(1+r)^{t_{n}}}=0$$

Similarly, we can use this equation with a given r instead, simply change the signs and then if the NPV $\leq0$ then is it bad deal (IRR<r), if NPV $\geq0$ then it is a good deal (IRR>r) - as your return is higher than your original £P.

Theorem: At times $t_{0},...,t_{n}$ if there are cashflows $C_{0},...,C_{n}$ respectively, then there is one unique solution to r when NPV=0, this is called the IRR. 
The proof for this is, a) this function is defined at zero - to prove a solution of r exists at NPV=0 and b) it is a decreasing function - to prove uniqueness.

Multiple cashflows are referred to as balanced, net to zero or flat iff NPV=0 or if PV of +ve cashflows = PV of the -ve casflows.

## My example

Say we deposited £800 in a bank, the annualised i/r given to us is 3%. I would like to take out these cashflows in the future. In year 1, I take out £500. In year 2, I take out $350. 
Calculate if the i/r given to me is a good deal or not, using the IRR method.

Using equation we get:

$$800-\frac{500}{(1+r)}-\frac{350}{(1+r)^2}=0$$

$$Let \frac{1}{1+r}=x$$

$$\therefore 800-500x-350x^2=0$$
                                                                                                                                                                                          

A situation you made up (your own numbers, not the ones in the lecture
notes), worked step by step.

## Solved exercises

### Exercise 1.x (from Exercise Sheet 1)

Question, then your solution.

## Spreadsheet

[01-InterestRates.xlsx](../spreadsheets/01-InterestRates.xlsx): what it
does, which cells to change and what to look at.
