Lesson 5: Stochastic Interest Rates


## Notation

- $P$ — initial deposit

- $n$ — number of years and the index $i$ labels the year from time $i-1$ to time $i$.

- $R$ — random annual interest rate in the fixed interest rate model and one value of $R$ applies throughout the investment.

- $R_i$ — the random interest rate for year $i$ in the varying interest rate model

- $G$ — the growth factor for one year equaling $1+R$ if $R$ is an effective annual rate or $e^R$ if $R$ is continuously compounded.

- $G_i$ — the growth factor for year $i$ that is calculated from $R_i$ using the relevant compounding convention

- $S_n$ — total growth factor over $n$ years which is $G^n$ when the same rate applies throughout and $\prod_{i=1}^{n}G_i$ when the rate can change each year.

- $B_n$ — balance at the end of year $n$ before any new deposit is made for a single initial deposit, $B_n=PS_n$.

- $D_i$ — deposit made at the beginning of year $i$, before that year’s interest is earned. Use $D$ when every regular deposit is the same amount.

- $\mathbb{E}[X]$ — expected value of $X$ or its probability weighted average.

- $\text{Var}(X)$ — variance of $X$ which measures how spread out its values are around the mean. The standard deviation is $\sqrt{\text{Var}(X)}$.

- $\mathbb{P}(X>x)$ — probability that the random variable $X$ exceeds the threshold $x$.

- $\text{i.i.d.}$ — independent and identically distributed (iid) in the varying rate model the yearly rates are independent of one another and follow the same probability distribution.

- $Y\sim\mathcal{N}(\mu,\sigma^2)$ — $Y$ follows a normal distribution with mean $\mu$ and variance $\sigma^2$ and its standard deviation is $\sigma$.

- $X\sim\text{LogNormal}(\mu,\sigma^2)$ — $X$ is log-normal which means $X=e^Y$ with $Y\sim\mathcal{N}(\mu,\sigma^2)$ so $\mu$ and $\sigma^2$ describe $\ln X$.

- $Z\sim\mathcal{N}(0,1)$ — a standard normal variable. A normal variable $Y$ can be written as $Y=\mu+\sigma Z$.

- $\varphi(z)$ — the standard normal density at $z$ which is given by $\varphi(z)=e^{-z^2/2}/\sqrt{2\pi}$.

- $\Phi(z)$ — the standard normal cumulative probability $\mathbb{P}(Z\le z)$.

- $e^x$ and $\ln x$ — the natural exponential and natural logarithm.

- $\sum$ — add the indicated terms by $\prod$ — multiply the indicated terms.


## Summary


### Fixed interest rate model

In a fixed interest rate model the rate is uncertain at the start. But once a value of $R$ is realised then the same rate applies each year. As an example if the rate turns out to be 4% the deposit will earn 4% in every year of the investment.

A single deposit $P$ grows to $B_n=PG^n$

where $G=1+R$ if $R$ is an effective annual rate, and $G=e^R$ if $R$ is continuously compounded.

To find the expected balance we calculate the final balance for each possible rate and then weigh each balance by its probability displayed as:

$\mathbb{E}[B_n]=P\mathbb{E}[G^n]$

Calculating in order is important because compounding is usually non linear so if we use the average rate in the balance formula we can get a different result from averaging the balances after compounding.

The variance is used to measure how much the possible balances spread out around the expected balance:

$\text{Var}(B_n)=P^2\left(\mathbb{E}[G^{2n}]-\left(\mathbb{E}[G^n]\right)^2\right)$

[See Example 1](#example-1-puregym-saving-for-renovations)


### Varying interest rates

In the varying interest rate model each year has its own random rate shown as $R_i$. The balance at the end of one year becomes the starting balance for the next causing the yearly growth factors to multiply as:

$B_n=P\prod_{i=1}^{n}G_i$

Where $G_i = 1 + R_i$ for an effective annual rate and $G_i = e^{R_i}$ for a continuously compounded rate.

If the yearly rates are independent then we multiply the expected growth factors to find the expected balances, being:

$\mathbb{E}[B_n]=P\prod_{i=1}^{n}\mathbb{E}[G_i].$

If rates are also identically distributed then each year has the same expected growth factor. If we write G for a growth factor with the common distribution we get:

$\mathbb{E}[B_n]=P\left(\mathbb{E}[G]\right)^n,$, $\text{Var}(B_n)=P^2\left[\left(\mathbb{E}[G^2]\right)^n-\left(\mathbb{E}[G]\right)^{2n}\right].$

The variance formula then follows by squaring the balance and then applying independence to the squared growth factors. The iid assumption also simplifies both calculations because in practice, rates stay high or low across several years, so one year's rate can give information regarding the next year.

[See Example 2](#example-2-wright-brothers-saves-for-fleet-repairs)


### Regular deposits

When you deposit $D_i$ at the beginning of a year say year $I$, both your existing balance and your new deposit earn that year's interest. Starting from $B_0 = 0$, the balance at the end of the year $I$ is:

$B_i=(B_{i-1}+D_i)G_i.$

If yearly rates are independent and the deposits are fixed in advance then the years growth factor is independent of the balance built up from earlier years, giving:

$\mathbb{E}[B_i]=\bigl(\mathbb{E}[B_{i-1}]+D_i\bigr)\mathbb{E}[G_i].$

If every deposit was the same amount D and the yearly rates are also iid then we write $g = \mathbb{E}[G]$ for the common expected annual growth factor. The first deposit earns interest for $n$ years whilst the last earns interest just for one year. Expected balance therefore turns out to be a geometric sum:

$\mathbb{E}[B_n]=D(g+g^2+\cdots+g^n)=\frac{Dg(1-g^n)}{1-g}, \quad g\ne1.$

If $g=1$ every term then equals $D$ so the expected balance comes out as $nD$.

[See Example 3](#example-3-saving-for-the-phantom-of-the-operas-50th-anniversary)


### Log normal interest rates

A log normal growth factor is one where there logarithm follows a normal distribution. For example, if a continuously compounded annual rate $R$ is normal then the growth factor $G=e^{R}$ is log normal. This is why G stays positive and allows negative interest rates. If R is an effective annual rate instead we model $1+R$ as log normal to get the same kind of growth factor.

If $\ln G\sim\mathcal{N}(\mu,\sigma^2)$ then the expected annual growth factor is:

$\mathbb{E}[G]=e^{\mu+\sigma^2/2}$

Here $\mu$ and $\sigma^2$ describe the logarithm of the growth factor. The variance term is used to explain why the expected growth factor can exceed $e^{\mu}$.

For independent yearly growth factors with the same distribution if we take logs then it will turn their product into a sum:

$\ln S_n=\sum_{i=1}^{n}\ln G_i\sim\mathcal{N}(n\mu,n\sigma^2).$

So $S_n$ is also log normal and a single deposit has expected final balance:

$\mathbb{E}[B_n]=Pe^{n\mu+n\sigma^2/2}.$

To find the probability that $B_n$ exceeds a target of $x$ then we use $B_n = PS_n$ and then take logarithms and convert to a standard normal probability:

$\mathbb{P}(B_n>x)=1-\Phi\left(\frac{\ln(x/P)-n\mu}{\sigma\sqrt{n}}\right).$

[See Example 4](#example-4-pizza-express-saves-for-wood-fired-ovens)


## My examples


### Example 1: PureGym saving for renovations

Imagine a gym chain, PureGym is planning to put £50,000 into a three year fixed rate savings account to help pay for upkeep and renovations across its gyms in Surrey. Upon opening the account there is a 60% chance that the annual rate will be 3% and a 40% it will be 6%. The rate at opening applies for all three years with annual compounding.

What is the expected balance after three years?

First we calculate our balance for each possible rate, for 3% with probability of 60% we calculate:

$50,000(1.03)^3 =$54{,}636.35 £54{,}636.35$

For 6% with probability of 40% we calculate $50{,}000(1.06)^3=£59{,}550.80$

Next, weight each balance by the probability:

$\mathbb{E}[B_3]=0.60(54{,}636.35)+0.40(59{,}550.80)=£56{,}602.13$

Compounding at the expected rate of 4.2% would give £56,568.30. The expected balance is slightly higher because each possible rate compounds for three years before the balances are averaged.


### Example 2: Wright Brothers saves for fleet repairs

Imagine a fishing company, The Wright Bros, have put £500,000 into a savings account for two years to help pay for repairs to its fleet. The interest rate resets at the start of each year. Each year it has an equal chance of being 2% or 7% and the two years rates are independent.

What is the expected balance after two years?

First, multiply the yearly growth factors to give four equally likely outcomes:

2% (Year 1) and 2% (Year 2) gives 500,000(1.02)^2 = £520,200.

2% (Year 1) and 7% (Year 2) gives 500,000(1.02)(1.07) = £545,700.

7% (Year 1) and 2% (Year 2) gives 500,000(1.02)(1.07) = £545,700.

7% (Year 1) and 7% (Year 2) gives 500,000(1.07)^2 = £572,450.

The expected growth factor in each year is:

$\mathbb{E}[G_i]=0.5(1.02)+0.5(1.07)=1.045.$

Because the rates are all independent we multiply the expected growth factors to. Find the expected balance:

$\mathbb{E}[B_2]=500{,}000(1.045)^2=£546{,}012.50.$

Hence the company can budget around an expected balance of £546,012.50, though it would have £520,200 available for repairs if both years are low at 2%.


### Example 3: Saving for The Phantom of the Opera's 50th anniversary

Imagine West End producers, such as The Phantom of the Opera's are depositing £7500 at the beginning of each year for the next three years to help pay for grander props in advance of the show's 50th anniversary. Each year the effective interest rate is equally likely to be 3% or 6.5% (independently of other years).

What is the expected balance at the end of year three?

First we calculate the expected growth factor for each year as

$g=0.5(1.03)+0.5(1.065)=1.0475.$

The first deposit earns interest for three years, the second for two and the third for one. Because the yearly rates are independent we will multiply the expected growth factors for the years each deposit is in the account.

$\mathbb{E}[B_3]=7{,}500\bigl(1.0475^3+1.0475^2+1.0475\bigr)\approx£24{,}705.99.$

The producers deposit £22,500 in total and they are expected to earn £2205.99 in interest. The first deposit contributes the most to the interest because it stays in the account the longest.


### Example 4: Pizza Express saves for wood fired ovens

Imagine an Italian restaurant chain, such as Pizza Express, deposits £340,000 for five years to help install wood fires ovens across their restaurants in the South East of the UK. It models each years continuously compounded interest rate through a normal distribution with a mean of 5% and a standard deviation of 1.5 percentage points. (Yearly rates are independent).

What is the expected balance after five years and what is the probability it rises above £408,000?

First we note that the yearly growth factors multiply so we take logs to turn them into a sum of their yearly rates, where the mean and variances add over the five years.

$\ln S_5\sim\mathcal N\bigl(5(0.05),\,5(0.015)^2\bigr)=\mathcal N(0.25,0.001125).$

We then calculate the expected balance as is below:

$\mathbb E[B_5]=340{,}000e^{0.25+0.001125/2}\approx£436{,}800.$

To exceed £408,000 the deposit needs its growth factor to be above 1.20 (408,000/340,000=1.2). So we take logs and standardise as is below:

$\mathbb P(B_5>408{,}000)=1-\Phi\left(\frac{\ln(1.20)-0.25}{\sqrt{0.001125}}\right)\approx97.8%.$

Using this model Pizza Express should finish £28,800 above its target with only a 2.2% chance of falling short.


## Solved exercises


### Exercise 3

Let $X\sim\text{LogNormal}(\mu,\sigma^2)\), so \(X=e^Y\) with \(Y\sim\mathcal N(\mu,\sigma^2)$. 

a) Explain why $X$ is not normally distributed and why a log normal distribution can be useful in modelling financial assets.

b) Derive $\mathbb E[X]$ using the standard normal density.


<details>
<summary>Show hint</summary>

For part a, think about which values $e^Y$ take.

For part b, write $Y=\mu+\sigma Z$ and complete the square in $\sigma z-z^2/2$.

</details>


<details>
<summary>Show part a</summary>

Because $X = e^{Y}$ it is always positive. As a normal variable with positive variance can take negative values so $X$ cannot follow a normal distribution.
This makes the log normal distribution become useful for modelling asset prices or growth factors. A growth factor between 0 and 1 represents a loss whilst keeping the resulting asset price positive.

</details>


<details>
<summary>Show part b</summary>

First we write $Y=\mu+\sigma Z$ where $Z\sim\mathcal N(0,1)$. Then substitute in our values into the expectation such as:

$\mathbb E[X]=\mathbb E[e^{\mu+\sigma Z}]=e^\mu\mathbb E[e^{\sigma Z}]$

Then we use our standard normal density and combine it with the exponentials to give

$\mathbb E[X]=e^\mu\int_{-\infty}^{\infty}e^{\sigma z}\frac{e^{-z^2/2}}{\sqrt{2\pi}}\,dz=\frac{e^\mu}{\sqrt{2\pi}}\int_{-\infty}^{\infty}e^{\sigma z-z^2/2}\,dz$

Then we complete the square inside of the exponent:

$\sigma z-\frac{z^2}{2}=-\frac{(z-\sigma)^2}{2}+\frac{\sigma^2}{2}$

The term $\sigma^2/2$ is a constant meaning that its exponential can be moved outside of the integral. So now we set $t=z-\sigma$ so that $dt=dz$ and so that the limits remain as $-\infty$ and $\infty$:

$\mathbb E[X]=e^{\mu+\sigma^2/2}\int_{-\infty}^{\infty}\frac{e^{-t^2/2}}{\sqrt{2\pi}}\,dt$

Therefore our integral becomes equal to 1 as it is the total area underneath the standard normal density.
Hence we get:

$\\mathbb E[X]=e^{\mu+\sigma^2/2}.$

</details>


### Exercise 6

You deposit £100 for 10 years. Where the yearly rates $R_i$ (from $t = I-1$ to $t = I$) are i.i.d. and the accumulated value is $B\_{10}=100\prod\_{i=1}^{10}G_i$.

a) Why do we assume the rates are i.i.d. and is that realistic

b) Take $R_i\sim\mathcal N(0.057,0.0008)$ as continuously compounded, so $G_i=e^{R_i}\sim\text{LogNormal}(0.057,0.0008)$. 
- Find the mean of the accumulated value after 10 years and say where you use independence.
- Find the probability that the accumulated value exceeds 110% of its mean.

c) Repeat b with $R_i$ as the effective rate so $G_i=1+R_i\sim\text{LogNormal}(0.057,0.0008)$.

<details>
<summary>Show hint</summary>

For a, think about whether knowing this year's rate tells you anything about next year's and whether the same range of rates is equally likely in every year.

For b, on the mean use the independence to turn the expectation of a product into a product of expectations.

</details>


<details>
<summary>Show part a</summary>

If something is independent then it lets us multiply the expected yearly growth factors. If have identical distribution means then we can use the same expected growth factor for each year.
In the real world, rates often stay high or low for multiple years so this years rate can tell us something about the next years. The distribution can also change over time as economic conditions and monetary policy change.

</details>



<details>
<summary>Show part b</summary>

Firs we calculate the Mean balance. Where each year’s growth factor is $G_i=e^{R_i}$. Using the result from Exercise 3, with mean parameter $0.057$ and variance parameter $0.0008$,

$\mathbb E[G_i]=e^{0.057+0.0008/2}=e^{0.0574}.$

The expected balance is

$\mathbb E[B_{10}]=100\,\mathbb E\left[\prod_{i=1}^{10}G_i\right]=100\prod_{i=1}^{10}\mathbb E[G_i]=100e^{0.574}\approx£177.54.$

Independence is used when we replace the expectation of the product with the product of the expectations. The growth factors are independent because each one depends on its own year’s rate.

For calculating the probability of exceeding 110% of the mean. We take logs and turn the product of growth factors into a sum of yearly rates:

$\ln(B_{10}/100)=\sum_{i=1}^{10}R_i\sim\mathcal N(0.570,0.008)$

We use the independence again so that we are able to add the variances together. Our target is to get $1.10\,\mathbb E[B_{10}]=110e^{0.574}$ which is roughly £195.29. Then we take logs and standardise so we get:

$\mathbb P\left(B_{10}>1.10\mathbb E[B_{10}]\right)=1-\Phi\left(\frac{\ln(1.10)+0.574-0.570}{\sqrt{0.008}}\right)$

$\approx 1-\Phi(1.1103)\approx13.34%$

</details>


<details>
<summary>Show part c</summary>

Now we are using $G_i=1+R_i$ instead, and the question gives us $G_i\sim\text{LogNormal}(0.057,0.0008)$. Which is the same distribution we used for the growth factor in part b meaning we get the same distribution for the final balance.

Calculating the mean, we use independence again to let us multiply the expected growth factors:

$\mathbb E[B_{10}]=100\prod_{i=1}^{10}\mathbb E[1+R_i]=100(e^{0.0574})^{10}\approx£177.54$

For probability, the variables we add are now $\ln(1+R_i)$ and each is normal with a mean of 0.057 and a variance of 0.0008 and they are independent. Hence we get

$\ln(B_{10}/100)=\sum_{i=1}^{10}\ln(1+R_i)\sim\mathcal N(0.570,0.008)$

The target and the log balance distribution is the same as it was in part b meaning the probability of exceeding 110% of the mean is the same as it was in part b, 13.34%.

</details>


## Spreadsheet

[Download the Lesson 5 spreadsheet](../spreadsheets/05-StochasticRates.xlsx)

### Sheet 1: Random fixed rate

**What it does:** It compares the expected balance when a rate is chosen at the start and fixed for the whole term with the balance you get when you compound at the expected rate.


**Inputs:** 

- 'Deposit' (B3) is £50,000 

- 'Years' (B4) is 3

- Rows 8-9 contain the two possible annual rates: 3% with probability 0.6 and 6% with probability 0.4. 


**How it works:** 

- Column C calculates final balance for each rate in the first scenario row. Columns D and E multiply each balance and rate by its probability. The sheet checks that the probabilities add to 1 then sums the weighted values to give an expected balance of £56,602.13 and an expected rate of 4.2%.

- Compounding at 4.2% gives £56,568.30 which is £33.83 less than expected balance's. The difference is an example of Jensen's inequality where the three year growth factor $(1+R)^3$ is convex in $R$, so averaging after compounding gives a higher balance.
 

**Link to the lesson:** The sheet reproduces Example 1 and applies the fixed interest rate model.



### Sheet 2: Lognormal growth

**What it does:** The sheet calculates expected balance and probability of exceeding a target when independent annual growth factors are log normal. Then there is a plot for the range of possible balances and how they change over time.


**Inputs:** 

- 'P0' (B3) is £100

- 'N' (B4) is 10 years

- 'Mu' (B5) is 0.057

- 'Sigma2' (B6) is 0.0008 (variance of the log growth factor)

- 'Frac' (B7) sets the target at 110% of the expected balance 


**How it works:**

- It takes logs and turns the product of annual growth factors into a sum. After 10 years the total log growth has mean 0.5700 and variance 0.0080. Each annual growth factor has mean $e^{\mu+\sigma^2/2}\approx 1.0591$. Independence lets the variances add and the expected growth factors multiply to give an expected balance of £177.54.

- Target is £195.29 or 110% of unrounded expected balance. The sheet standardises the log of the target growth factor to get $z \approx1.1103$ then uses the function '1-NORM.S.DIST(z,TRUE) to find a 13.34% chance of the target getting exceeded.

- The year by year table uses NORM.S.INV to calculate the 5th and 95th percentiles whilst the chart shows the mean and the widening range between those percentiles which is has the middle 90% of modelled balances. At year 10 the range runs from about £152.64 to £204.85.


**Link to the lesson:** Expected growth formula comes from Exercise 3. Mean and probability match Exercise 6 b and c. Both versions give the same log normal distribution for annual growth factor.
