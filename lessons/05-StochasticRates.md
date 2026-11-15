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

PureGym is planning to put £50,000 into a three year fixed rate savings account to help pay for upkeep and renovations across its gyms in Surrey. Upon opening the account there is a 60% chance that the annual rate will be 3% and a 40% it will be 6%. The rate at opening applies for all three years with annual compounding.

What is the expected balance after three years?

First we calculate our balance for each possible rate, for 3% with probability of 60% we calculate:

$50,000(1.03)^3 =$54{,}636.35 £54{,}636.35$

For 6% with probability of 40% we calculate $50{,}000(1.06)^3=£59{,}550.80$

Next, weight each balance by the probability:

$\mathbb{E}[B_3]=0.60(54{,}636.35)+0.40(59{,}550.80)=£56{,}602.13$

Compounding at the expected rate of 4.2% would give £56,568.30. The expected balance is slightly higher because each possible rate compounds for three years before the balances are averaged.


### Example 2: Wright Brothers saves for fleet repairs

The Wright Bros, a fishing company, have put £500,000 into a savings account for two years to help pay for repairs to its fleet. The interest rate resets at the start of each year. Each year it has an equal chance of being 2% or 7% and the two years rates are independent.

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

The West End producers of The Phantom of the Opera are depositing £7500 at the beginning of each year for the next three years to help pay for grander props in advance of the show's 50th anniversary. Each year the effective interest rate is equally likely to be 3% or 6.5% (independently of other years).

What is the expected balance at the end of year three?

First we calculate the expected growth factor for each year as

$g=0.5(1.03)+0.5(1.065)=1.0475.$

The first deposit earns interest for three years, the second for two and the third for one. Because the yearly rates are independent we will multiply the expected growth factors for the years each deposit is in the account.

$\mathbb{E}[B_3]=7{,}500\bigl(1.0475^3+1.0475^2+1.0475\bigr)\approx£24{,}705.99.$

The producers deposit £22,500 in total and they are expected to earn £2205.99 in interest. The first deposit contributes the most to the interest because it stays in the account the longest.


### Example 4: Pizza Express saves for wood fired ovens

Pizza Express deposits £340,000 for five years to help install wood fires ovens across its restaurants in the South East of the UK. It models each years continuously compounded interest rate through a normal distribution with a mean of 5% and a standard deviation of 1.5 percentage points. (Yearly rates are independent).

What is the expected balance after five years and what is the probability it rises above £408,000?

First we note that the yearly growth factors multiply so we take logs to turn them into a sum of their yearly rates, where the mean and variances add over the five years.

$\ln S_5\sim\mathcal N\bigl(5(0.05),\,5(0.015)^2\bigr)=\mathcal N(0.25,0.001125).$

We then calculate the expected balance as is below:

$\mathbb E[B_5]=340{,}000e^{0.25+0.001125/2}\approx£436{,}800.$

To exceed £408,000 the deposit needs its growth factor to be above 1.20 (408,000/340,000=1.2). So we take logs and standardise as is below:

$\mathbb P(B_5>408{,}000)=1-\Phi\left(\frac{\ln(1.20)-0.25}{\sqrt{0.001125}}\right)\approx97.8%.$

Using this model Pizza Express should finish £28,800 above its target with only a 2.2% chance of falling short.



