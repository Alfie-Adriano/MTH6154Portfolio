# Lesson 3: Immunisation of Assets and Liabilities

[Back to contents](../README.md)

## Notation

- $r$: nominal interest rate with $n$ compounding periods per year

- $C_i$: is the payment at time $t_i$, for $i=1,\dots,m$

- $D(t;r)$: discount factor for time $t$ at rate $r$. This is $e^{-rt}$ for continuous compounding or $(1+r/n)^{-nt}$ when compounded $n$ times a year.

- $V(r)=\sum_{i=1}^m C_i D(t_i;r)$ the present value of a stream

- $V_A(r)$, $V_L(r)$ the present value of the assets and of the liabilities

- $\nu=-V'(r)/V(r)$ the effective duration (measured in years)

- $\tau=\sum t_iC_iD(t_i)/V(r)$ the duration the present value weighted average of the payment times

- $c=V''(r)/V(r)$ the convexity

- $\nu_A,\nu_L$ and $c_A,c_L$: effective durations and convexities of the assets and liabilities

- $\beta=1/(1+r)$: yearly discount factor

- $r_0$: the current rate and $\varepsilon$: a small change in the rate


## Summary


### Effect of varying interest rates

$V(r)$ is our total present value of a store of payments at the interest rate $r$. We find it by discounting each payment up to today and adding the results, shown as:

$V(r)=\sum_{i=1}^{m} C_i D(t_i;r)$.

If the rate rises any money set aside today will grow faster, so less is needed to cover any fixed future payment. As a result, this lowers the present value of future receipts and bills. Payments due today are unaffected and the total effect on a mix of receipts and bills depends on which are more sensitive to the rate.

We use the derivative $V'(r)$ to see how quickly the present value changes, where for a small rate change $\varepsilon$:

$V(r_0+\varepsilon)-V(r_0)\approx V'(r_0)\,\varepsilon$.


### Effective duration and duration

Effective duration is used to measure how sensitive present value is to a small change in interest rate, written as:

$\nu=-\frac{V'(r)}{V(r)}$

Dividing by $V(r)$ expresses this sensitivity in relation to the stream's value so we can compare any smaller or bigger streams. The reason it has a minus sign is to make effective duration positive when present value falls and rates rise. For instance, if $v=4$ rises by 0.1 percentage points it would give us an estimated 0.4% fall in present value.

Duration however measures the average time until payment which gives more weight to payments that are worth more today, written through:

$\tau=\frac{\sum_{i=1}^{m} t_i C_i D(t_i;r)}{\sum_{i=1}^{m} C_i D(t_i;r)}$

For a stream of positive payments each payment's weight is its share of total present value. The weights add up to 1 hence duration lies between the first and last payment dates. For one payment the duration would be the time until that payment.

In short, duration describes when the value is received, effective duration is how that value responds to interest rates.

### How duration and effective duration are related

With continuous compounding we have $\nu=\tau$. When we differentiate the discount factor $e^{-rt_i}$ brings down a factor of $-t_i$ so $-V'(r)/V(r)$ giving us the same weighted average as duration.

Using annual compounding our differentiation introduces an additional factor being $1/(1+r)$, which is why we get:

$\nu=\frac{\tau}{1+r}=\beta\tau$


### Convexity

Convexity is how much our present value curve bends in comparison to its value, it is written as:

$c=\frac{V''(r)}{V(r)}$

In order to help us understand let us use an analogy. Imagine you are in Wales and you are driving on a sloping road, a sign says the road is steep at 9% you are halfway up but you do not know if you have reached its maximum steepness of 9% yet and are nervous. Our effective duration would tell us how steep the road is where you stand right now. Convexity however would tell us how the slope is changing as we move. Convexity gives a better estimate of present value after rate change when added. It is written as:

$V(r_0+\varepsilon)\approx V(r_0)\left(1-\nu\varepsilon+\frac12 c\varepsilon^2\right)$

Where $\var$ and $c$ are calculated at starting rate $r_0$.

For a stream of positive payments the convexity will add an upward correction as to whether the rate is rising or falling because $\epsilon^2$ is positive in either case. Hence we can see that duration alone is overestimating the loss when rates rise and that it is underestimating the gain when rates fall.


### Redington immunisation

Remington immunisation means that we want to choose assets so that they cover our liabilities with respect to the current interest rate whilst the funding position is also protected against small rate fluctuations. Our net position is $V_A(r)-V_L(r)$ where $V_L(r)$ is our present value of the amount(/s) owed (expressed as a positive number).

We do it step by step, starting with step one.

- First we match present values (zero order). So set $V_A(r_0)=V_L(r_0)$. The assets exactly cover the liabilities at current rate.

- Second we match effective durations (first order). So we set $\nu_A=\nu_L$ and since the present values already match, the equal effective durations mean the two values will initially rise or fall by the same amount when the rate changes.

- Finally we check convexity where it requires the condition $c_A\ge c_L$. With the starting values and slopes now matched, convexity can determine how the two curves begin to separate.

If we put all three steps together it will give the equation:

$V_A(r_0+\varepsilon)-V_L(r_0+\varepsilon)\approx \frac12 V_A(r_0)(c_A-c_L)\varepsilon^2$

As $\epsilon^2$ is positive for a rate rise or fall the greater asset convexity will give a surplus for any sufficiently small moves for any direction. However if the convexities are equal then the second order effect will be zero and any higher order terms will determine whether a surplus will appear or a shortfall.

### Immunisation in practice



## My example



### Example 1: Rising rates affect on future funding.

For example, University of London's Senate house expects to spend £37,670 in three years on refurbishing its library and book collection. With our rate at 4% compounded annually, it needs to set aside:

$V(0.04)=\frac{37{,}670}{(1.04)^3}\approx \text{£}33{,}488.49$

If the rate rises to 5% the amount they would need today would become:

$V(0.05)=\frac{37{,}670}{(1.05)^3}\approx \text{£}32{,}540.76$

The single percentage point rise allows senate house to set aside £947.73 less today for the same bill.


### Example 2: A skier's RedBull sponsorship deal

A skier signs a daredevil sponsorship deal with Red Bull that pays £100,000 at the end of year one and £550,000 at the end of year three. Interest rate is currently 8% compounded annually.

First we calculate the present value of each payment:

$\frac{100{,}000}{1.08}\approx \text{£}92{,}592.59$ and $\frac{550{,}000}{(1.08)^3}\approx \text{£}436{,}607.73$.

Then using the unrounded values we add them to see the deal is worth £529,200.33 today.

Next we calculate the duration:

$\tau=\frac{1\left(\frac{100{,}000}{1.08}\right)+3\left(\frac{550{,}000}{(1.08)^3}\right)}{\frac{100{,}000}{1.08}+\frac{550{,}000}{(1.08)^3}}\approx 2.65$ years.

The bigger payment is accounting for roughly 82.5%of the deal's present value so the duration becomes closer to the three years than to the one.

Finally let us calculate the effective duration.
Differentiate the present value with respect to the interest rate:

$V'(r)=-\frac{100{,}000}{(1+r)^2}-\frac{3(550{,}000)}{(1+r)^4}$

At 8%, $V'(0.08)$ approximately equals -1,298,533.14, which gives us:

$\nu=-\frac{V'(0.08)}{V(0.08)}\approx 2.45$ years.

Should the rate rise up by 0.5 percentage points to 8.5%, effective duration estimates that the deal's value today would fall by about 1.23% even though the payments are unchanged.


### Example 3: Red Bull deal continued with continuous compounding

Here our skier still gets £100,000 (year 1), £550,000 (year 3) but the 8% nominal annual rate is now compounded continuously.

Our discount factor is $D(t) = e^{-0.08t}$ making the factors for year one as $e^{-0.08}$ and year three $e^{-0.24}$. Our present values give:

$100{,}000e^{-0.08}\approx \text{£}92{,}311.63$ and $550{,}000e^{-0.24}\approx \text{£}432{,}645.32$, so $V\approx \text{£}524{,}956.96$.

Using unrounded figures the deal is worth £524,956.96 today making its duration:

$\tau\approx\frac{1(92{,}311.63)+3(432{,}645.32)}{524{,}956.96}\approx 2.65$ years.

Next we differentiate the present value which gives $V'(r)=-\sum_{i=1}^{m}t_iC_ie^{-rt_i}$. If we reverse the sign to get the numerator of the duration formula which gives:

$\nu=-\frac{V'(r)}{V(r)}=\tau\approx 2.65$ years

With annual compounding the duration also rounded to 2.65 years however the effective did not being 2.45 years due to $\nu=\tau/1.08$. Continuous compounding however gives the two measures as equal at 2.65 years.


### Example 4: Valuing Leander's licence fee

Leander Rowing Club have just started producing their own wine and champagne, the club owes £10,000 in licensing fees for the alcohol as part of their new deal with British Airways. At a continuously compounded rate of 4% what is the amount needed to set aside today?

Let us calculate it using our formula:

$V(0.04)=10{,}000e^{-0.04(5)}\approx \text{£}8{,}187.31$

As $V(r)=10{,}000e^{-5r}$ if we differentiate once we get $V'(r)=-5V(r)$, and if we do it twice we get $V''(r)=25V(r)$. So the effective duration is $\nu=5$ and the convexity is $c=25$.

If our rate increases from 4 to 6% then our epsilon gives 0.02. Now using effective duration alone we get:

$V(0.06)\approx V(0.04)\left(1-5(0.02)\right)\approx \text{£}7{,}368.58$

Now if we add convexity we get the following:

$V(0.06)\approx V(0.04)\left(1-5(0.02)+\frac12(25)(0.02)^2\right)\approx \text{£}7{,}409.51$

The amount Leander would need is $10{,}000e^{-0.06(5)}\approx \text{£}7{,}408.18$. Introducing the convexity term in reduces the estimation error down from £39.61 to the much smaller £1.33.


### Exercise 5: Immunisation of Hounslow renovation costs.

Hounslow council currently owe £59,300 in two years for the Thames Path to be renovated in Chiswick. A government scheme for all UK councils to maintain roads and paths will pay Hounslow two grants, one in a year the other in three. The current interest rate is 10% compounded annually, how large should the grants be to achieve Redington immunisation?

First we match present values to find the bill:

$V_L(0.10)=\frac{59{,}300}{(1.10)^2}\approx \text{£}49{,}008.26$

Then we give each grant half of that present value (£24,504.13). To find the grant amounts we grow that share forwards to each payment date, calculating as:

$\text{Year 1 grant}=\frac{59{,}300}{2(1.10)}\approx \text{£}26{,}954.55$

$\text{Year 3 grant}=\frac{59{,}300(1.10)}{2}=\text{£}32{,}615$

Using our amounts the grants combined present value matches the bill.

Secondly we match our effective durations.
Our grants have equal present values meaning their payment times also carry equal weight:

$\tau_A=\frac{1+3}{2}=2$ years, $\tau_L=2$ years.

Using annual compounding both the effective durations are equal to $\frac{2}{1.10}$. The grant and liability values therefore have the same slope as each other at the current rate.

Finally we compare convexities, with annual compounding we get a payment contribution from each of $t_i(t_i+1)/(1+r)^2$ which is weighted by its share of present value. Then with the grants having a weight of $1/2$ and the bill a weight of 1 we calculate:

$c_A=\frac{\frac12(1)(2)+\frac12(3)(4)}{(1.10)^2}\approx 5.79$, $c_L=\frac{(2)(3)}{(1.10)^2}\approx 4.96$

And we can conclude that the grants meet all three Redington conditions. They cover the bill in present value terms at 10%, greater convexity gives the council a small surplus if the rate moves slightly in either direction as well.


## Solved exercises

### Exercise 3

**Question:** 

<details>
<summary>Show hint</summary>



</details>

<details>
<summary>Show solution</summary>



</details>

### Exercise 7

**Question:** 

<details>
<summary>Show hint</summary>



</details>

<details>
<summary>Show solution</summary>



</details>

## Spreadsheet



### Sheet 1: 

**What it does:** 

**Inputs:** 

**How it works:**

 

**Result:** 


### Sheet 2:

**What it does:** 

**Inputs:** 

**How it works:**



**Result:**