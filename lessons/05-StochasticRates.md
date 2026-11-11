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