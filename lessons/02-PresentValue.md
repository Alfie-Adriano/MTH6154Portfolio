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

For example, A model train business can receive £500 today or £500 in one year. If it takes the money today and deposits in to an account paying 4% annual interest, after a year it will have:

$500(1.04)=£520$

Taking £500 today leaves the business £20 better off after a year hence showing why equal amounts paid at different times do not have equal value.

### Present value and the discount factor

Present value of a future payment is the amount you would need to invest today to grow into said payment. Discounting works backwards from a future amount to its value right now.

$\text{PV}=P\cdot D(t)$

Here, PV is present value, P is the amount paid at time t and D(t) is the discount factor (the present value of £1 paid at time t)

With annual compounding:

$D(t) = \frac{1}{(1+r)^t}$, so $\text{PV} = \frac{P}{(1+r)^t}$.

Dividing by growth factor reverses the interest accumulation. When interest rates are positive, the discount factor is still below 1 meaning a future payment is worth less today.

For example, A machine learning company expects to spend £1,500,500 on new chips for its data centres in two years. If set aside today it can earn 5% interest compounded annually. How much does it need to deposit?

First we would calculate the discount factor:

$D(2) = \frac{1}{(1.05)^2} \approx 0.907029$

This means that each £1 needed in two years is worth roughly £0.907 today. The present value of the chip purchase would be:

$\text{PV} = 1{,}500{,}500 \times D(2) = \frac{1{,}500{,}500}{(1.05)^2} \approx \text{£}1{,}360{,}997.73$

The company needs to set aside £1,360,997,73 today, allowing the interest earned over two years to cover the expected amount of £1,500,500 for chip purchases.

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

Let us for this example use a more complex accurate scenario.
A defence company must pay £25,000,000 for materials in three years. It compares accounts quoting an annual rate of 6.7% with different compounding methods in order to determine how much it needs to set aside today.

With yearly compounding the company would need to set aside:

$\text{PV} = \frac{25{,}000{,}000}{(1.067)^3} \approx \text{£}20{,}580{,}065.39$

Using monthly compounding, the rate per month would be $\frac{0.067}{12}$ applied over $12x3=36$ periods:

$\text{PV} = 25{,}000{,}000 \times \left(1+\frac{0.067}{12}\right)^{-36} \approx \text{£}20{,}459{,}245.23$

Using continuous:

$\text{PV} = 25{,}000{,}000 \times e^{-0.067 \times 3} \approx \text{£}20{,}447{,}810.79$

Ergo, the company needs to set aside less when compounding is more frequent. Which also shows that the same quoted annual rate can give different present values depending on how interest is compounded.

### Net present value (NPV)

The net present value (or NPV) brings all incoming and outgoing payments into today's value and then adds them together. This allows us to compare cash flows fairly as payments received at different times have different opportunities to earn interest.

$\text{NPV} = \sum_{k=1}^{m} C_k D(t_k)$

Each cash flow is multiplied by its discount factor. Money received is counted positive and money paid negative. Using yearly compounding we use the formula:

$\text{NPV} = \sum_{k=1}^{m} \frac{C_k}{(1+r)^{t_k}}$

A payment made today has a discount factor of 1. For an investment a positive NPV simply means that the future receipts are worth more today than the costs. Negative means the inverse.

For example, a derivatives trading firm takes bullish positions on US crude oil, meaning it expects to benefit from rising oil prices. The trades require $£550,000$ today and are expected to produce net cash receipts of $£370,000$ at the end of each of the next two years, including any recovery of the initial investment. The firm uses an annual discount rate of $4%$.

The initial outlay is already at today's value, whilst the expected future receipts must be discounted:

$\text{NPV} = -550{,}000 + \frac{370{,}000}{1.04} + \frac{370{,}000}{(1.04)^2}$

$\text{NPV} \approx -550{,}000 + 355{,}769.23 + 342{,}085.80 = \text{£}147{,}855.03$

The positive NPV means the expected receipts exceed initial costs in today's money at the chosen 4% discount rate, although the trading returns remain uncertain.


### Geometric sums and regular payments


### Perpetuities


[See Example 1](#example-1-your-title)
