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

- $\operatorname{Var}(X)$ — variance of $X$ which measures how spread out its values are around the mean. The standard deviation is $\sqrt{\operatorname{Var}(X)}$.

- $\mathbb{P}(X>x)$ — probability that the random variable $X$ exceeds the threshold $x$.

- $\text{i.i.d.}$ — independent and identically distributed (iid) in the varying rate model the yearly rates are independent of one another and follow the same probability distribution.

- $Y\sim\mathcal{N}(\mu,\sigma^2)$ — $Y$ follows a normal distribution with mean $\mu$ and variance $\sigma^2$ and its standard deviation is $\sigma$.

- $X\sim\operatorname{LogNormal}(\mu,\sigma^2)$ — $X$ is log-normal which means $X=e^Y$ with $Y\sim\mathcal{N}(\mu,\sigma^2)$ so $\mu$ and $\sigma^2$ describe $\ln X$.

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


### Varying interest rates

In the varying interest rate model each year has its own random rate shown as $R_i$. The balance at the end of one year becomes the starting balance for the next causing the yearly growth factors to multiply as:

$B_n=P\prod_{i=1}^{n}G_i$

Where $G_i = 1 + R_i$ for an effective annual rate and $G_i = e^{R_i}$ for a continuously compounded rate.

If the yearly rates are independent then we multiply the expected growth factors to find the expected balances, being:

$\mathbb{E}[B_n]=P\prod_{i=1}^{n}\mathbb{E}[G_i].$

If rates are also identically distributed then each year has the same expected growth factor. If we write G for a growth factor with the common distribution we get:

$\mathbb{E}[B_n]=P\left(\mathbb{E}[G]\right)^n,$, $\text{Var}(B_n)=P^2\left[\left(\mathbb{E}[G^2]\right)^n-\left(\mathbb{E}[G]\right)^{2n}\right].$

The variance formula then follows by squaring the balance and then applying independence to the squared growth factors. The iid assumption also simplifies both calculations because in practice, rates stay high or low across several years, so one year's rate can give information regarding the next year.


### Regular deposits

When you deposit $D_i$ at the beginning of a year say year $I$, both your existing balance and your new deposit earn that year's interest. Starting from $B_0 = 0$, the balance at the end of the year $I$ is:

$B_i=(B_{i-1}+D_i)G_i.$

If yearly rates are independent and the deposits are fixed in advance then the years growth factor is independent of the balance built up from earlier years, giving:

$\mathbb{E}[B_i]=\bigl(\mathbb{E}[B_{i-1}]+D_i\bigr)\mathbb{E}[G_i].$

If every deposit was the same amount D and the yearly rates are also iid then we write $g = \mathbb{E}[G]$ for the common expected annual growth factor. The first deposit earns interest for $n$ years whilst the last earns interest just for one year. Expected balance therefore turns out to be a geometric sum:

$\mathbb{E}[B_n]=D(g+g^2+\cdots+g^n)=\frac{Dg(1-g^n)}{1-g}, \quad g\ne1.$

If $g=1$ every term then equals $D$ so the expected balance comes out as $nD$.


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


## My examples


### Example 1: 