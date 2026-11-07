# 1. Interest rates

[Back to contents](../README.md)

## Summary

### Notation
- $P$: original principal
- $n$: number of times per year interest is added
- $B(t)$: balance after t years
- $t$: time, (measured in years)
- $T$: total investment period/maturity, (measured in years)
- $r$: annual interest rate as a decimal
- $r_{\text{eff}}$: effective annual interest rate (includes compounding effect)
- $e$: Euler's number
- $i$: annual inflation rate as a decimal
- $r_{\text{real}}$: annual interest rate after adjusting for inflation
- $r(t)$: instantaneous interest rate at time t (with continuous compounding)
- $\bar r(T)$: average of the instantaneous rates from today to time $T$
- $u$: time variable used inside an integral
- $C_k$: the $k$th payment (positive if it is received, negative is paid)
- $t_k$: time in years when the kth payment happens
- $m$: number of future payments
- $\text{NPV}$: total value today of all the incoming and outgoing payments
- $r_{\text{IRR}}$: the interest rate that makes NPV equal to zero  


### Simple vs compound interest
Simple interest is interest that is earned only on the original principal, which is the amount of money initially deposited or invested before interest is added. It follows $B(t) = P(1+rt)$.
Compound interest is interest that is earned on the original principal and any interest that has previously been earned. Each time interest gets added, the increased balance becomes the amount used to calculate the next interest payment. It follows $B(t) = P(1 + r/n)^{nt}$.
Here $n$ is the number of times per year interest is added so the balance is multiplied by $(1 + r/n)$ at each compounding period for a total of $nt$ periods. 
[See Example 1](#example-1-simple-vs-compound)


### Nominal vs effective rates
The nominal annual interest rate is our quoted yearly rate that is divided across the year's compounding periods. It does not include the additional growth from compounding interest in that year. Each compounding period earns a rate of $\text{Rate per compounding period} = r/n$ which is applied to the growing balance n times a year. For example, 3% compounded monthly means 0.25% is applied to the balance each month, so the actual yearly growth is a little bit higher than 3% due to compounding effects.
The effective annual interest rate however measures how much your balance has actually grown over one year, and it includes the compounding effects. It is defined as $r_{\text{eff}} = (1+r/n)^{n} -1$. The brackets give our growth factor for one period. Which raising to the power n compounds it over the full year whilst subtracting 1 leaves the interest earned for every pound invested.
For a positive nominal rate, compounding more than once a year makes the effective rate higher than the nominal because earlier interest will earn further interest. Using annual compounding, the two rates will be equal. Or in short, *Effective rates let you compare accounts fairly when their compounding frequencies are different*
[See Example 2](#example-2-choosing-a-savings-account)


### Continuous compounding
Continuous compounding is when interest is added increasingly often until the balance grows at every instant. Shown as $B(t) = \lim_{n\to\infty} P\left(1+\frac{r}{n}\right)^{nt} = Pe^{rt}$. Euler's number appears because our bracketed function $(1+r/n)^{n}$ approaches $e^{r}$ as the compounding frequency increases (as n tends to infinity). Which means the effective annual rate is $r_{\text{eff}} = e^{r} - 1$.
For our positive nominal rates, continuous compounding will give the highest effective rate possible at that same quoted rate.
[See Example 3](#example-3-continuous-compounding)

### Real vs nominal (inflation)
The nominal interest rate tells you how your money will grow before we account for rising prices. The real interest rate tells you how your purchasing power changes, showing how much your money can actually buy you, whether it be more or less than before.
The real annual interest rate formula is: $r_{\text{real}} = \frac{1+r_{\text{eff}}}{1+i} - 1 = \frac{r_{\text{eff}} - i}{1+i}$.
Dividing the money's growth factor by the price growth factor is how we adjust for inflation. When both rates are small the approximation to use is: $r_{\text{real}} \approx r_{\text{eff}} - i$.
Your purchasing power will rise when interest exceeds the rate of inflation, it will not change when they are equal and it will fall when inflation rises above the interest rate.
[See Example 4](#example-4-saving-for-a-model-train)


### Time-varying rates and the yield curve
A time varying interest rate changes over time instead of staying fixed. The instantaneous rate $r(t)$ describes the rate applying at a specific moment using continuous compounding.
When the rate is varying the balance will grow according to:
$B(T) = P\exp\left(\int_0^T r(u)\,du\right)$.
The integral adds up the rate over the investment period and the exponential turns it into a growth factor.
The yield curve gives the equivalent constant annual rate for each investment length
Where  $\bar r(T) = \frac{1}{T}\int_0^T r(u)\,du$ is the average of the instantaneous rates from time 0 to T.
$\bar r(T)$ is the single constant continuously compounded rate that would give us the same balance after $T$ years as the changing rate $r(t)$ would. Hence:
$B(T) = P\,e^{T\,\bar r(T)}$
The difference here is that $r(t)$ describes the rate at as singular moment whilst $\bar r(T)$ describes the equivalent rate over the entire investment period.
[See Example 5](#example-5-a-varying-rate)

### IRR
The internal rate of return or IRR for short is the annual discount rate that makes an investment's NPV become equal to 0. Meaning it makes the value today of future payments equal to the initial/first investment.
Discounting converts a future payment into its value today displayed as:
$\text{PV}(C_k) = \frac{C_k}{(1+r)^{t_k}}$.
For the initial investment $P$, the IRR satisfies the following equation:
$0 = -P + \sum_{k=1}^{m} \frac{C_k}{(1+r_{\text{IRR}})^{t_k}}$.
The symbol $\sum_{k=1}^{m}$ means add up all the future payments from payment 1 to payment m. Where the greek symbol Sigma represents "Sum of'. The initial investment is negative because it is money paid out.
For an initial outlay followed by positive payments, an IRR above the return available on a comparable investment indicates a better return so long as the risks are also comparable.
[See Example 6](#example-6-irr-of-an-investment)

## My example

### Example 1: Simple vs compound
Let us say £1000 were invested at 3% annually for three years, using simple interest it becomes £1090, compared to £1092.73 with annual compounding interest.
Although the balances are close after 3 years, were we to raise the time to 30 years the gap rises from £2.73 to £527.26, with simple generating £1900 and compounding generating £2427.26.

### Example 2: Choosing a savings account
Let us say we are choosing where to put £800 for one year.
We have two accounts
Account A: 5% nominal interest, compounded monthly.
Account B: 5.1% interest, compounded annually.
Calculating for Account A we calculate our $r_{\text{eff}}$ using our stated formula to get 5.1162%. Then calculating at t=1, (B(1)), using our stated formula we get £840.93.
Calculating for Account B, annual compounding means the effective rate is simply 5.1%. Subbing in as $B(1) = 800(1.051)$ we get £840.80.
Meaning that Account A has the lower quoted rate but still produces slightly more growth, hence showing why the effective rate is our better basis for comparison.

### Example 3: Continuous compounding
As an example, let us say that we have £1200 at 4% continuously compounded for two years.
Where $B(2) = 1200\,e^{0.04\times 2} \approx \text{£}1{,}299.94$
However if we use annual compounding instead we get $B(2) = 1200\,(1.04)^2 = \text{£}1{,}297.92$.
Ergo, we see that continuous compounding will earn us an extra £2.02 thus showing that increasing the compounding frequency will add growth, though the balance will approach a limit.

### Example 4: Saving for a model train
As an example, You set aside £600 for a model train, earning 5% effective annual interest. Over the year model train prices have risen by 3%.
Your savings grow to $600(1.05) = £630$
Here 1.05 = 1 + our effective interest rate of 5% which is 0.05.
The train that originally cost £600 now costs $600(1.03)=£618$
Here 1.03 = 1 + i, where i = 3% =0.03.
Here you can still afford it and you have £12 left to spend as you wish. Your real interest rate is calculated as $r_{\text{real}} = \frac{1.05}{1.03} - 1 \approx 0.019417 = 1.9417\%$
So although your money grew by 5%, your purchasing power has grown by only 1.94% because rising prices from inflation absorbed part of the growth.

### Example 5: A varying rate
As our example, A private equity company has placed £2million into an interest bearing account while preparing to acquire a beverage business in two years. The account pays continuously compounded interest at 2% during the first year and 4% during the second year.
The rate is: 
$r(t) =
\begin{cases}
0.02, & 0 \le t < 1, \\
0.04, & 1 \le t \le 2.
\end{cases}$
First we add the contribution from each year:
$\int_0^2 r(u)\,du = \int_0^1 0.02\,du + \int_1^2 0.04\,du = 0.02(1) + 0.04(1) = 0.06$
Divide by the two year investment period to find the equivalent constant annual rate:
$\bar r(2) = \frac{0.06}{2} = 0.03 = 3\%$
Meaning the amount available for the acquisition after two years is:
$B(2) = 2{,}000{,}000\,e^{2(0.03)} = 2{,}000{,}000\,e^{0.06} \approx \text{£}2{,}123{,}673.09$
The company earned £123,673.09 in interest, the same it would have earned with 3% continuously compounded for both years.


### Example 6: IRR of an investment
As an example, A venture capital firm invests £200,000 in a rail business that transports vegetation. It receives £20,000 after one year and then £220,000 after two years when it sells its stake including the final distribution.
The IRR equation is:
$0 = -200{,}000 + \frac{20{,}000}{1+r_{\text{IRR}}} + \frac{220{,}000}{(1+r_{\text{IRR}})^2}$
Dividing by £200,000 gives:
$1 = \frac{0.1}{1+r_{\text{IRR}}} + \frac{1.1}{(1+r_{\text{IRR}})^2}$
Multiplying both sides by $(1+r_{\text{IRR}})^2$:
$(1+r_{\text{IRR}})^2 = 0.1(1+r_{\text{IRR}}) + 1.1$
Expanding and rearranging gives:
$r_{\text{IRR}}^2 + 1.9\,r_{\text{IRR}} - 0.2 = 0$
Then factorising:
$(r_{\text{IRR}} - 0.1)(r_{\text{IRR}} + 2) = 0$
The solutions are 0.1 and -2. We reject -2 since an effective annual rate must be greater than -1. Hence we get $r_{\text{IRR}}=0.10=10\%$
Checking by discounting both payments at 10%:
$\frac{20{,}000}{1.10} + \frac{220{,}000}{1.10^2} \approx 18{,}181.82 + 181{,}818.18 = 200{,}000$
Ergo the investment's 10% IRR accounts for both the size and timing of the payments, rather than just the total profit received.


## Solved exercises

### Exercise 1.x (from Exercise Sheet 1)

Question, then your solution.

## Spreadsheet

[01-InterestRates.xlsx](../spreadsheets/01-InterestRates.xlsx)
