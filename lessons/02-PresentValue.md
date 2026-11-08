# 2. Present Value


## Notation

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


## Summary


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


## My Examples


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


## Solved Exercises


### Exercise 2

**Question.** Compare the following two three year job offers.

- Company A offers: £65,000 after year 1, £75,000 after year 2 and £115,000 after year 3.

- Company B offers: £15,000 immediate payment followed by £79,000 at the end of each year.

Compare their present values at an annual interest rate of 3.75%, using annual and continuous compounding.

<details>
<summary>Show hint</summary>

Bring every payment back to today's value before adding them together. Company B's signing bonus is already paid today so its discount factor is 1.

</details>

<details>
<summary>Show solution</summary>

**Annual compounding**

Use the discount factor:

$D(t) = \frac{1}{(1+r)^t}$.

Company A's offer has present value:

$\text{PV}_A = \frac{65{,}000}{1.0375} + \frac{75{,}000}{(1.0375)^2} + \frac{115{,}000}{(1.0375)^3} \approx \text{£}235{,}302.31$.

The subscripts $A$ and $B$ identify the company being valued.

Company B's signing bonus needs no discounting, so:

$\text{PV}_B = 15{,}000 + \frac{79{,}000}{1.0375} + \frac{79{,}000}{(1.0375)^2} + \frac{79{,}000}{(1.0375)^3} \approx \text{£}235{,}276.57$.

Subtracting the unrounded values:

$\text{PV}_A - \text{PV}_B \approx \text{£}25.74$.

Company A offers the better deal under annual compounding.

**Continuous compounding**

Use the discount factor:

$D(t) = e^{-rt}$.

Company A's offer has present value:

$\text{PV}_A = 65{,}000 \times e^{-0.0375} + 75{,}000 \times e^{-0.0375 \times 2} + 115{,}000 \times e^{-0.0375 \times 3} \approx \text{£}234{,}952.09$.

Company B's offer has present value:

$\text{PV}_B = 15{,}000 + 79{,}000 \times e^{-0.0375} + 79{,}000 \times e^{-0.0375 \times 2} + 79{,}000 \times e^{-0.0375 \times 3} \approx \text{£}234{,}978.28$.

Subtracting the unrounded values:

$\text{PV}_B - \text{PV}_A \approx \text{£}26.19$.

Company B offers the better deal under continuous compounding.

**Conclusion.** Company A wins annual compounding, while Company B wins continuous compounding. With the same quoted positive rate, continuous compounding discounts later payments more heavily, reducing the relative value of Company A's higher final year salary.

</details>


### Exercise 3

**Question** A car loan worth £12,000 is repaid through 36 equal monthly instalments that start one month after borrowing. What is the monthly payment when the nominal annual interest rate is 6%, compounded monthly.


<details>
<summary>Show hint</summary>

The present value of the 36 repayments must equal the £12,000 borrowed. Use the monthly interest rate $\frac{0.06}{12}$ and then apply the geometric sum formula to the discounted payments.

</details>


<details>
<summary>Show solution</summary>

First we find the monthly rate

$\frac{r}{12} = \frac{0.06}{12} = 0.005$

The monthly interest rate comes out to be $0.5%$ which gives a monthly discount factor of $\frac{1}{1.005}$

Then we equate the loan to the present value of the repayments
Where each monthly instalment is $A$. Since the first payment is one month away:

$12{,}000 = \frac{A}{1.005} + \frac{A}{(1.005)^2} + \cdots + \frac{A}{(1.005)^{36}}$

The first payment is discounted for one month and the final for 36 months.

Finally we apply the geometric sum formula

$12{,}000 = A \times \frac{1-(1.005)^{-36}}{0.005}$

Rearrange to find monthly instalment:

$A = \frac{12{,}000 \times 0.005}{1-(1.005)^{-36}} \approx \text{£}365.06$

**Conclusion** The monthly instalment is approximately £365.06. A small adjustment to the final payment might be needed as instalments are typically rounded to the nearest penny.

</details>


## Spreadsheet


### Sheet 1: NPV and IRR

**What it does** This sheet calculates the present value of a project's cash flows and find its IRR (the discount rate at which the NPV equals 0)

**Inputs** The shaded cells contain the discount rate in B3 (called Discountrate), and the cash flows from B6:B11. My project requires £8000 today and generates annual receipts of £10,000, £6900, £12,000, £13,000 and £37,000 over five years. 
The initial discount rate is 6%


**How it works** 

- The discount factor column uses =1/(1+DiscountRate)^A6 that is adjusted for each row to calculate what £1 received in that year would be worth today

- The present value column multiplies each cash flow by its discount factor using =B6*C6. Cell B13 then adds these values with =SUM(D6:D11) to find NPV

- Cell B14 check this using =B6+NPV(Discountrate,B7:B11). Excel's own NPV then assumes its first cash flow arrives after one period, so the year zero payment is added separately. Both mine and excel's calculations agreed.

- Cell B15 uses =IRR(B6:B11) to find the project’s IRR. Setting Discountrate equal to this cell makes NPV approximately zero.

- The table and scatter chart show NPV at discount rates from 0% to 130%. NPV falls as the rate rises crossing zero between 120% and 130%.


**Result** At a 6% discount rate, NPV is £55,596.14 and the IRR is approximately 125.14%. The positive NPV means the projected receipts exceed the initial investment in today's money at the chosen discount rate. (Depends on the assumed case flows being achieved)


### Sheet 2: Loan schedule

**What it does** This sheet shows a loan being followed through equal monthly repayments. Hence showing how each payment covers interest and reduces the outstanding balance.


**Inputs** The shaded inputs are Loanamount = £45,695, Loanrate = 6.8% nominal annually and compounded monthly and Loanmonths = 72.


**How it works**

- Cell B7 calculates the monthly payment using =PMT(Loanrate/12,Loanmonths,-Loanamount). This rearranges the payment present value formula so that the discounted repayments equal the amount borrowed. (The negative loan amount makes Excel return a positive payment)

- Each row starts with the opening balance. Monthly interest is the opening balance and is multiplied by LoanRate/12, principal repaid is the payment minus interest and the closing balance is the opening balance minus principal repaid.

- This is my annuity calculation done through =LoanAmount*(LoanRate/12)/(1-(1+LoanRate/12)^-LoanMonths) which matches PMT. A separate check confirms that total payments minus the original loan equals the total interest.

- The chart shows the outstanding balance falling towards zero. As the balance falls less interest is charged and more of each equal payment repays principal.

**Result** The monthly payment displays as £774.67 with total payments of £55,776.48 and a total interest of £10,081.48. These totals use Excel's unrounded payment internally by rounding every actual payment to pennies would require a small adjustment for the final payment.