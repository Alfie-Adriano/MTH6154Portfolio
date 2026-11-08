# 2. Present Value

##Summary

### Notation

- $P$: Amount of money paid or received at a future time. 

- $t$: Time in years. 

- $r$: Annual interest rate as a decimal, compounded yearly unless stated otherwise.
 
- $n$: Number of compounding periods per year. 

- $D(t)$: Discount factor to time $t$: what £1 paid at time $t$ is worth today. 

- $\text{PV}$: Present value: what a future payment is worth today. 

- $\beta$: One-year discount factor: $\beta=\frac{1}{1+r}$. 

- $C_k$: The k-th cash flow: positive if received, negative if paid. 

- $t_k$: Time in years when the k-th cash flow occurs. 

- $m$: Number of cash flows. 

- $\text{NPV}$: Net present value: the sum of the present values of all cash flows. 

- $r_{\text{IRR}}$: The discount rate that makes NPV equal to zero. 

- $A$: Amount of each equal regular payment. 

- $x$: Common ratio in a geometric sum: the factor multiplying each term to get the next. 

- $a,b$: First and last exponents in a geometric sum.

- $\sum\$: “Sum of”: add together the specified terms. 

- $e$: Euler’s number, approximately $2.71828$, used in continuous compounding. 


### Time value of money

Money that is available today can be invested and earn interest before any future payments arrive. When interest rates are positive, £1 today is therefore worth more than £1 received in a year because the pound from today has time to grow.

For annual compounding, £1 invested today becomes:

$1(1+r)=1+r$

After one year

To compare money received at different times fairly we must express the amounts at the same date.

[See Example 1](#example-1-money-today-vs-later)


### Present value and the discount factor

Present value of a future payment is the amount you would need to invest today to grow into said payment. Discounting works backwards from a future amount to its value right now.

$\text{PV}=P\cdot D(t)$

Here, PV is present value, P is the amount paid at time t and D(t) is the discount factor (the present value of £1 paid at time t)

With annual compounding:

$D(t) = \frac{1}{(1+r)^t}$, so $\text{PV} = \frac{P}{(1+r)^t}$.

Dividing by growth factor reverses the interest accumulation. When interest rates are positive, the discount factor is still below 1 meaning a future payment is worth less today.

[See Example 2](#example-2-setting-money-aside-for-a-purchase)


### Ways of quoting the rate

Annual interest rates can be quoted using different compounding frequencies. However the discount factor must match the way the rate is quoted, otherwise we cannot correctly reverse the growth of the money.

Looking at yearly compounding:

$D(t) = \frac{1}{(1+r)^t}$

Interest is added once every year, so we divide by the annual growth factor raised to the number of years.

Monthly compounding:

$D(t) = \left(1+\frac{r}{12}\right)^{-12t}$

The nominal annual rate is divided into monthly rates, with $12t$ compounding periods over the investment.

Continuous compounding:

$D(t) = e^{-rt}$

Since money grows by $e^{rt}$ multiplying by $e^{-rt}$ reverses that growth.

For the same positive quoted annual rate, the more regular the compounding, the greater the growth, so a smaller deposit today is needed to reach the desired fixed future amount.

[See Example 3](#example-3-same-rate-different-compounding)


### Net present value (NPV)

The net present value (or NPV) brings all incoming and outgoing payments into today's value and then adds them together. This allows us to compare cash flows fairly as payments received at different times have different opportunities to earn interest.

$\text{NPV} = \sum_{k=1}^{m} C_k D(t_k)$

Each cash flow is multiplied by its discount factor. Money received is counted positive and money paid negative. Using yearly compounding we use the formula:

$\text{NPV} = \sum_{k=1}^{m} \frac{C_k}{(1+r)^{t_k}}$

A payment made today has a discount factor of 1. For an investment a positive NPV simply means that the future receipts are worth more today than the costs. Negative means the inverse.

[See Example 4](#example-4-npv-of-an-investment)


### Geometric sums and regular payments

A geometric sum is a type of sum that adds terms where each term is the previous one multiplied by the same factor. For a finite sum it is written as:

$\sum_{k=a}^{b} x^k = x^a + x^{a+1} + \cdots + x^b = \frac{x^a - x^{b+1}}{1-x}$, for $x \ne 1$.

In the formula k counts through the exponents from a to b. If x=1, the sum would be the number of terms b-a+1.

Geometric sums occur when equal payments arrive at regular intervals. This is because each payment is discounted by one additional period. For $m$ annual payments of $A$, with the first arriving in a year:

$\text{PV} = A\beta + A\beta^2 + \cdots + A\beta^m$

Now using the geometric sum formula:

$\text{PV} = A \times \frac{\beta(1-\beta^m)}{1-\beta} = A \times \frac{1-(1+r)^{-m}}{r}$, for $r \ne 0$.

This values the entire payment stream into one calculation. If $r=0$ then no discounting is needed and the present value is $mA$.

[See Example 5](#example-5-value-of-a-grant)


### Perpetuities

A perpetuity is a stream of equal payments that is made at regular intervals and continues forever. Although the total paid is technically unlimited, its present value can be finite because each future payment gets discounted more heavily.

For annual payments the first payment in one year is written as:

$\text{PV} = A\beta + A\beta^2 + A\beta^3 + \cdots = A\sum_{k=1}^{\infty} \beta^k$

The symbol infinity means the payments continue without an end date. When r > 0, we have 0 < $beta$ <1 so the geometric sum converges to a finite value:

$\text{PV} = \frac{A\beta}{1-\beta} = \frac{A}{r}$

Payment timing also matters for if the first payment is today we must add the immediate payment:

$\text{PV} = A + \frac{A}{r}$

However if the first payment is at the end of year $t$, we discount the standard perpetuity back another $t-1$ years:

$\text{PV} = \frac{A}{r}(1+r)^{-(t-1)}$

For positive payments, the present value is not finite when $r<=0$. When interest is zero the payments never shrink when discounted and at a negative interest rate their present value grows.

[See Example 6](#example-6-a-fund-that-pays-forever)


##My Examples


### Example 1: Money today vs later

For example, A model train business can receive £500 today or £500 in one year. If it takes the money today and deposits in to an account paying 4% annual interest, after a year it will have:

$500(1.04)=£520$

Taking £500 today leaves the business £20 better off after a year hence showing why equal amounts paid at different times do not have equal value.


### Example 2: Setting money aside for a purchase

For example, A machine learning company expects to spend £1,500,500 on new chips for its data centres in two years. If set aside today it can earn 5% interest compounded annually. How much does it need to deposit?

First we would calculate the discount factor:

$D(2) = \frac{1}{(1.05)^2} \approx 0.907029$

This means that each £1 needed in two years is worth roughly £0.907 today. The present value of the chip purchase would be:

$\text{PV} = 1{,}500{,}500 \times D(2) = \frac{1{,}500{,}500}{(1.05)^2} \approx \text{£}1{,}360{,}997.73$

The company needs to set aside £1,360,997,73 today, allowing the interest earned over two years to cover the expected amount of £1,500,500 for chip purchases.


### Example 3: Same rate, different compounding

Let us for this example use a more complex accurate scenario.
A defence company must pay £25,000,000 for materials in three years. It compares accounts quoting an annual rate of 6.7% with different compounding methods in order to determine how much it needs to set aside today.

With yearly compounding the company would need to set aside:

$\text{PV} = \frac{25{,}000{,}000}{(1.067)^3} \approx \text{£}20{,}580{,}065.39$

Using monthly compounding, the rate per month would be $\frac{0.067}{12}$ applied over $12x3=36$ periods:

$\text{PV} = 25{,}000{,}000 \times \left(1+\frac{0.067}{12}\right)^{-36} \approx \text{£}20{,}459{,}245.23$

Using continuous:

$\text{PV} = 25{,}000{,}000 \times e^{-0.067 \times 3} \approx \text{£}20{,}447{,}810.79$

Ergo, the company needs to set aside less when compounding is more frequent. Which also shows that the same quoted annual rate can give different present values depending on how interest is compounded.


### Example 4: NPV of an investment

For example, a derivatives trading firm takes bullish positions on US crude oil, meaning it expects to benefit from rising oil prices. The trades require $£550,000$ today and are expected to produce net cash receipts of $£370,000$ at the end of each of the next two years, including any recovery of the initial investment. The firm uses an annual discount rate of $4%$.

The initial outlay is already at today's value, whilst the expected future receipts must be discounted:

$\text{NPV} = -550{,}000 + \frac{370{,}000}{1.04} + \frac{370{,}000}{(1.04)^2}$

$\text{NPV} \approx -550{,}000 + 355{,}769.23 + 342{,}085.80 = \text{£}147{,}855.03$

The positive NPV means the expected receipts exceed initial costs in today's money at the chosen 4% discount rate, although the trading returns remain uncertain.


### Example 5: Value of a grant

For our example, suppose the Natural History Museum receives a grant as part of a government backed scheme that pays £42,000 at the end of each year for 5 years. Using an annual discount rate of 4.6%, calculate what the grant is worth today.

First we calculate the yearly discount factor:

$\beta = \frac{1}{1.046}$

Each successive payment is discounted for one additional year, which gives us:

$\text{PV} = 42{,}000 \times \left(\beta + \beta^2 + \beta^3 + \beta^4 + \beta^5\right)$

Since this is a geometric sum we calculate the total directly as:

$\text{PV} = 42{,}000 \times \frac{1-(1.046)^{-5}}{0.046} \approx \text{£}183{,}866.35$

Meaning although the grant pays £210,000 total, its actual present value is £183,866.35 because the museum is receiving money gradually rather than in a one time payment today.


### Example 6: A fund that pays forever

As our example, let us suppose Arsenal football club are establishing a fund through a shareholder initiative to support talented children from low income backgrounds, by helping them access youth football programs and opportunities to be noticed. The fund pays £10,000 at the end of each year forever and earns a constant 3% effective annual return.

To calculate the amount needed today we plug our values into our formula to get:

$\text{PV} = \frac{A}{r} = \frac{10{,}000}{0.03} \approx \text{£}333{,}333.33$

Each year the fund would earn approximately:

$333{,}333.33 \times 0.03 \approx \text{£}10{,}000$

Withdrawing the interest earned funds the programmes whilst leaving the original investment untouched.

Ergo, the fund can support £10,000 annually forever under our assumptions. However that fixed payment's purchasing power will fall if prices rise.

