# Lesson 6: Equities and Derivatives


## Notation

- $t$ — time in years from today with $t=0$ meaning today

- $T$ — delivery date of a forward or expiry date of an option measured in years from today

- $S_t$ or $S(t)$ — spot price of the underlying asset at time $t$. In the currency example $S_t$ is the number of pounds needed to buy €1

- $S_0$ or $S$ is the underlying asset’s price today

- $S_T$ or $S(T)$ is the underlying asset’s price at time $T$.

- $K$ — the agreed delivery price in a forward contract or the strike price at which an option holder can buy or sell the asset.

- $F_T$ — the fair forward price agreed today for delivery at time $T$. A new forward with $K=F_T$ has zero value at the start

- $r$ — annual interest rate as a decimal. When it is continuously compounded the discount factor is $e^{-rT}$.

- $D(T)$ — discount factor to time $T$ or the value today of £1 paid at time $T$.

- $r_{\text{GBP}}$ and $r_{\text{EUR}}$ is the continuously compounded annual interest rates for sterling and euros 

- $C$ — price today of a European call option

- $P$ — price today of a European put option

- $x^+$ — the positive part of $x$ defined as $\max(x,0)$

- $\Delta_C=\frac{\partial C}{\partial S}$ call delta which measures how the call price changes as today’s share price changes, holding other inputs fixed.

- $\Delta_P=\frac{\partial P}{\partial S}$ — put delta which measures how the put price changes as today’s share price changes, holding other inputs fixed.


## Summary


### Forward contracts and the forward price

A forward contract is when two parties commit to trade an asset at a future date $T$ for a price of $K$ agreed today. The buyer takes a long position whilst the seller a short position. At delivery, their payoffs per unit are:

$\text{Long payoff}=S_T-K,\qquad\text{Short payoff}=K-S_T$

The fair forward price of $F_T$ is the delivery price that makes a new contract that is worth zero today. An asset that pays no income before delivery is calculated through:

$F_T=\frac{S_0}{D(T)}$

Using continuous compounding we get:

$F_T=S_0e^{rT}$

This follows from no arbitrage meaning that buying the asset today uses borrowed money costs of $S_0e^{rT}$ to repay at the delivery so purchasing through a forward must have same cost.

For foreign currency though, holding the currency will also earn foreign interest, with the exchange quoted as pounds per euro, making the fair forward rate:

$F_T=S_0e^{(r_{\text{GBP}}-r_{\text{EUR}})T}$

The sterling rate shows the cost of financing the purchase, whilst the euro shows the interest that is earned on the euros that are held until the delivery.


### Options and their payoffs


### Put-call parity


### Sensitivity to the share price (delta)



## My example


### Example 1:


### Example 2:


### Example 3:


### Example 4:


### Example 5:



## Solved exercises


### Exercise 5


### Exercise 7


## Spreadsheet