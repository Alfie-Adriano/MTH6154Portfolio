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



### Convexity



### Redington immunisation



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