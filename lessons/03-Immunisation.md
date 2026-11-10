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

[See Example 1](#example-1-rising-rates-effect-on-future-funding)


### Effective duration and duration

Effective duration is used to measure how sensitive present value is to a small change in interest rate, written as:

$\nu=-\frac{V'(r)}{V(r)}$

Dividing by $V(r)$ expresses this sensitivity in relation to the stream's value so we can compare any smaller or bigger streams. The reason it has a minus sign is to make effective duration positive when present value falls and rates rise. For instance, if $v=4$ rises by 0.1 percentage points it would give us an estimated 0.4% fall in present value.

Duration however measures the average time until payment which gives more weight to payments that are worth more today, written through:

$\tau=\frac{\sum_{i=1}^{m} t_i C_i D(t_i;r)}{\sum_{i=1}^{m} C_i D(t_i;r)}$

For a stream of positive payments each payment's weight is its share of total present value. The weights add up to 1 hence duration lies between the first and last payment dates. For one payment the duration would be the time until that payment.

In short, duration describes when the value is received, effective duration is how that value responds to interest rates.

[See Example 2](#example-2-a-skiers-redbull-sponsorship-deal)


### How duration and effective duration are related

With continuous compounding we have $\nu=\tau$. When we differentiate the discount factor $e^{-rt_i}$ brings down a factor of $-t_i$ so $-V'(r)/V(r)$ giving us the same weighted average as duration.

Using annual compounding our differentiation introduces an additional factor being $1/(1+r)$, which is why we get:

$\nu=\frac{\tau}{1+r}=\beta\tau$

[See Example 3](#example-3-red-bull-deal-continued-with-continuous-compounding)


### Convexity

Convexity is how much our present value curve bends in comparison to its value, it is written as:

$c=\frac{V''(r)}{V(r)}$

In order to help us understand let us use an analogy. Imagine you are in Wales and you are driving on a sloping road, a sign says the road is steep at 9% you are halfway up but you do not know if you have reached its maximum steepness of 9% yet and are nervous. Our effective duration would tell us how steep the road is where you stand right now. Convexity however would tell us how the slope is changing as we move. Convexity gives a better estimate of present value after rate change when added. It is written as:

$V(r_0+\varepsilon)\approx V(r_0)\left(1-\nu\varepsilon+\frac12 c\varepsilon^2\right)$

Where $\varepsilon$ and $c$ are calculated at starting rate $r_0$.

For a stream of positive payments the convexity will add an upward correction as to whether the rate is rising or falling because $\varepsilon^2$ is positive in either case. Hence we can see that duration alone is overestimating the loss when rates rise and that it is underestimating the gain when rates fall.

[See Example 4](#example-4-valuing-leanders-licence-fee)


### Redington immunisation

Redington immunisation means that we want to choose assets so that they cover our liabilities with respect to the current interest rate whilst the funding position is also protected against small rate fluctuations. Our net position is $V_A(r)-V_L(r)$ where $V_L(r)$ is our present value of the amount(/s) owed (expressed as a positive number).

We do it step by step, starting with step one.

- First we match present values (zero order). So set $V_A(r_0)=V_L(r_0)$. The assets exactly cover the liabilities at current rate.

- Second we match effective durations (first order). So we set $\nu_A=\nu_L$ and since the present values already match, the equal effective durations mean the two values will initially rise or fall by the same amount when the rate changes.

- Finally we check convexity where it requires the condition $c_A\ge c_L$. With the starting values and slopes now matched, convexity can determine how the two curves begin to separate.

If we put all three steps together it will give the equation:

$V_A(r_0+\varepsilon)-V_L(r_0+\varepsilon)\approx \frac12 V_A(r_0)(c_A-c_L)\varepsilon^2$

As $\varepsilon^2$ is positive for a rate rise or fall the greater asset convexity will give a surplus for any sufficiently small moves for any direction. However if the convexities are equal then the second order effect will be zero and any higher order terms will determine whether a surplus will appear or a shortfall.

[See Example 5](#example-5-immunisation-of-hounslow-renovation-costs)


### Immunisation in practice

Zero coupon bonds pay once, because of this its duration equals its maturity. A portfolio's duration however is the average of its bond maturities, weighted by their present values.

In order to match the liability duration with positive holding in two bonds we choose one that will mature before the desired duration and one after it. This is called bracketing. We match both present value and duration for first order immunisation and then check that asset's convexity is at least as large as the liability convexity for Redington immunisation.

[See Example 6](#example-6-building-uk-infrastructure-reserve-through-foreign-bonds)


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


### Example 5: Immunisation of Hounslow renovation costs.

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


## Example 6: Building UK infrastructure reserve through foreign bonds

Using a potential scenario, imagine the UK is currently fearing sabotage from other states resulting in the British market being unsettled. The government responds by setting up a reserve to fund £138.915. million of infrastructure security upgrades that will be due in three years time. The government can buy one year and four year zero coupon bonds issued by foreign governments and payable in sterling. Assume the same annual discount rate of 5% applies to the bonds and the future bill. 

Does the reserve meet the three Redington immunisation conditions? And what does this tell us about whether the reserve will cover the bill in present value terms if the discount rate rises or falls?

Calculate the bill's present value as:

$V_L(0.05)=\frac{138.915}{(1.05)^3}=\text{£}120$ million.

The government decides to invest £40 million in one year bonds and £80 million in four year bonds. Calculating the maturities bracket for the three year liability duration as:

$V_A(0.05)=\text{£}120$ million, $\tau_A=\frac{1(40)+4(80)}{120}=3$ years.

Our present value and duration both match meaning the reserve achieves first order immunisation. Convexity is also higher than the bills, hence:

$c_A=\frac{\frac13(1)(2)+\frac23(4)(5)}{(1.05)^2}=\frac{14}{(1.05)^2}$, $c_L=\frac{3(4)}{(1.05)^2}=\frac{12}{(1.05)^2}$

The reserve now has met all Redington conditions for small changes in the shared discount rate. As for immunisation in practice, the foreign bonds' yield could move independently of the rate used to value the UK bill which would leave the reserve exposed to that difference.


## Solved exercises

### Exercise 3

**Question:** A pension fund owes £20 million in 10 years and £40 million in 15 years. Its assets are 25 year zero coupon bonds that will pay £P million at maturity and £Q million held in the bank. The interest rate is 7%, compounded continuously.

- a) Find P and Q so the fund achieves first order immunisation

- b) Compare the asset and liability convexities to see whether the fund also achieves Redington immunisation.

- c) Explain why replacing the 25 year bonds with 5 year bonds makes first order immunisation impossible.


<details>
<summary>Show hint</summary>

First order immunisation requires the assets and liabilities to have the same present value and duration. Use $e^{-0.07t}$ to discount each payment.

</details>


<details>
<summary>Show part a</summary>

First, discount the two liabilities:

$V_L(0.07)=20e^{-0.07(10)}+40e^{-0.07(15)} \approx 9.9317+13.9975=23.9292.$

The liability duration is the average of the two payment times weighted by their present values:

$\tau_L= \frac{10(20e^{-0.70})+15(40e^{-1.05})} {20e^{-0.70}+40e^{-1.05}} \approx 12.9248\text{ years}.$

The assets have present value $Pe^{-1.75}+Q$. The bonds are discounted over 25 years while the bank balance is already at today’s value. Matching present values gives:

$Pe^{-1.75}+Q\approx 23.9292.$

Under continuous compounding duration equals effective duration so matching durations is enough for the second condition. The bonds contribute 25 years to weighted average and the bank balance contributes zero:

$\tau_A=\frac{25Pe^{-1.75}+0(Q)}{Pe^{-1.75}+Q}.$

Since the denominator already matches the liabilities’ present value we match the two duration numerators:

$25Pe^{-1.75}=10(20e^{-0.70})+15(40e^{-1.05}).$

Solving gives:

$Pe^{-1.75}\approx 12.3712,$

$P\approx 71.1913,$

$Q=V_L(0.07)-Pe^{-1.75}\approx 11.5580.$

So the fund needs bonds that pay £71.19 million at maturity, worth about £12.37 million today, and £11.56 million in the bank.

</details>


<details>
<summary>Show part b</summary>

With continuous compounding convexity as the present value weighted average of the squared payment times. Using our values from part (a):

$c_A=\frac{25^2Pe^{-1.75}+0^2Q}{Pe^{-1.75}+Q} \approx 323.12,$

$c_L= \frac{10^2(20e^{-0.70})+15^2(40e^{-1.05})} {20e^{-0.70}+40e^{-1.05}} \approx 173.12.$

Since $c_A>c_L$ the fund meets the third condition and achieves Redington immunisation. At 7% the assets exactly cover the liabilities in present value terms. A sufficiently small rate rise or fall makes a present value surplus.

</details>


<details>
<summary>Show part c</summary>

The bank balance has duration zero and a 5 year zero coupon bond has duration five years. Any portfolio made up of positive holdings in these two assets has a duration between 0 & 5 years. The liability duration is about 12.92 years so the fund can match present values but cannot match durations. Which rules out first order immunisation.

</details>


### Exercise 7

**Question:** Suppose that interest is paid at nominal rate r and compounded $n$ times a year. Consider a cash flow stream consisting of payments $C_1,\ldots,C_m$ at the end of years $t_1,\ldots,t_m.$.

- a) Prove that the effective duration $\nu$ and the duration $\tau$ of a cash flow stream with yearly payments are related via

$\nu=\left(1+\frac{r}{n}\right)^{-1}\tau.$

- b) Prove that the convexity is equal to 

$c=\frac{\sum_{i=1}^{m}t_i\left(t_i+\frac{1}{n}\right)C_i\left(1+\frac{r}{n}\right)^{-nt_i}}{\sum_{i=1}^{m}C_i\left(1+\frac{r}{n}\right)^{-nt_i}}\left(1+\frac{r}{n}\right)^{-2}.$

<details>
<summary>Show hint</summary>

Write present value using the discount factor $(1+r/n)^{-nt_i}.$. Then differentiate once to get the effective duration and twice to get the convexity. 

</details>


<details>
<summary>Show part a</summary>

A payment at time $t_i$ is discounted over $nt_i$ compounding periods, giving the total present value as 

$V(r)=\sum_{i=1}^{m}C_i\left(1+\frac{r}{n}\right)^{-nt_i}.$

Then we differentiate with respect to r. The power rule brings down the $-nt_i$ and the chain rule introduces $1/n$. We cancel the $n$ which gives

$\frac{d}{dr}\left(1+\frac{r}{n}\right)^{-nt_i}=-t_i\left(1+\frac{r}{n}\right)^{-nt_i-1}.$

Then our extra factor of $(1+r/n)^{-1}.$ is the same for every payment, so we get

$-V'(r)=\left(1+\frac{r}{n}\right)^{-1}\sum_{i=1}^{m}t_i C_i\left(1+\frac{r}{n}\right)^{-nt_i}.$

The sum is the numerator of the duration formula. We divide by $V(r)$ to give $\tau$ and we get

$\nu=-\frac{V'(r)}{V(r)}=\left(1+\frac{r}{n}\right)^{-1}\tau.$

</details>


<details>
<summary>Show part b</summary>

First we look to differentiate the discount factor for a second time. Our exponent is $-nt_{i}-1$ and the chain rule contributes $1/n$ which we calculate as:

$\frac{d^2}{dr^2}\left(1+\frac{r}{n}\right)^{-nt_i}=(-t_i)(-nt_i-1)\frac{1}{n}\left(1+\frac{r}{n}\right)^{-nt_i-2}$

With our result we multiply by $C_i$ and sum over the payments and take the common factor of $=t_i\left(t_i+\frac{1}{n}\right)\left(1+\frac{r}{n}\right)^{-nt_i-2}.$ outside, giving

$V''(r)=\left(1+\frac{r}{n}\right)^{-2}\sum_{i=1}^{m}t_i\left(t_i+\frac{1}{n}\right)C_i\left(1+\frac{r}{n}\right)^{-nt_i}.$

Convexity is $V''(r)/V(r).$ Then we substitute the expression for our $V(r)$ from part a to give us

$c=\frac{\sum_{i=1}^{m}t_i\left(t_i+\frac{1}{n}\right)C_i\left(1+\frac{r}{n}\right)^{-nt_i}}{\sum_{i=1}^{m}C_i\left(1+\frac{r}{n}\right)^{-nt_i}}\left(1+\frac{r}{n}\right)^{-2}.$

</details>


## Spreadsheet

[Download the Lesson 3 spreadsheet](../spreadsheets/03-Immunisation.xlsx)

### Sheet 1: Duration and Convexity


**What it does:** The sheet calculates the present value, duration, effective duration and convexity of the Red Bull sponsorship payments from my example 2.


**Inputs:** The named cell Rate (B3) is set as 8% compounded annually. The table in A7:B9 has payments £100,000 for year 1, £0 in year 2 and £550,000 in year 3.


**How it works:** 

- Column C is used to calculate the discount factor and column D multiplies each payment by the discount factor to find its present value.

- Column E calculates t times each present value and divides its total by V to get duration. Effective duration is then calculated through $\nu=\tau/(1+r)$.

- Column F is used to calculate t(t+1) times each present value. Then it divides the total by V and then calculates the convexity multiplying by $(1+r)^{-2}$. (Formulas derived from exercise 7).


**Result:** Cells B13:B16 give present value of £529,200.33 and duration of 2.6501 years, an effective of 2.4538 years and convexity 8.7880.


### Sheet 2: Exercise 3


**What it does:** Recreates pension fund calculations from exercise 3. Finds how much to hold in zero coupon bonds and cash and checks Redington conditions.


**Inputs:** Our input is ContRate and is set to 7% compounded continuously and BondYears to 25 years. Liabilities are £20 million in year 10 and £40 million in year 15.


**How it works:**

- Liability table uses $e^{r}{t}$ to discount each payment. It also calculates t and $t^2$ times the present values to find the duration and convexity.

- Bond's present value is calculated $\tau_LV_L/25$ which matches the liability duration due to the bonds pay in year 25 and that cash has duration zero. The sheet grows the bonds' present value forward to find the face value of P and puts the rest of $V_L$ into cash $Q$.

- Checks then compare assets and liabilities by present value, duration and convexity.

**Result:** The liabilities are worth £23.92 million today and have a duration of 12.92 years. The fund holds bonds worth £12.37 million today and pay £71.19 million at maturity and £11.56 million in cash. The present values match the durations and asset convexity (323.12) exceeds the liability convexity (173.12) so Redington check returns as YES.


### Sheet 3: Rate shocks


**What it does:** Shows the pension fund's surplus changes when interest rate moves away from 7% with the bond and cash holdings fixed.


**Inputs:** Bond face value $P$, Cash holding $Q$ and liability payments from sheet 2. Testing interest rates from 3% to 11%.


**How it works:**

- The sheet recalculates $V_A$ and $V_L$ at each rate and subtracts the liability value from the asset value to find the surplus.

- The chart plots the surplus against interest rate. At around 7% the curve bends up on both sides of zero. (Shows the effect of greater asset convexity)

**Result:** The surplus is zero at 7% and positive at other rates tested. Its £4.865 million at 3% and £0.20 million at 6% and £0.16 million at 8%