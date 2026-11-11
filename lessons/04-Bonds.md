# Lesson 4: Bonds and the Term Structure of Interest Rates


## Notation

- $P$ — face value of the bond. This is the amount used to calculate its coupons and redemption payment.

- $P_0$ — price paid for the bond at time 0.

- $q$ — annual coupon rate as a decimal applied to the bond’s face value.

- $m$ — number of coupon payments per year. If the coupons are equal each pays $qP/m$.

- $n$ — total number of coupon payments.

- $C_i$ — amount of the $i$th coupon payment for $i=1,\ldots,n$.

- $t_i$ — time in years until the $i$th coupon payment.

- $T$ — time in years until the bond matures.

- $R$ — redemption amount as a fraction of face value. If $R=1$ the bond is redeemed at par.

- $RP$ — redemption payment at maturity paid in addition to any final coupon.

- $r$ — annual market interest rate as a decimal, when one rate is used to discount every payment.

- $D(t)$ — discount factor to time $t$ or what £1 paid at time $t$ is worth today.

- $\text{PV}$ — present value of the bond’s future coupons and redemption payment. Under no arbitrage this is its fair price.

- $V_T$ — price today of a zero coupon bond that pays £1 at time $T$. It equals $D(T)$.

- $y$ — bond yield or the effective annual rate that makes the present value of the bond’s future payments equal to $P_0$.

- $r_T$ — annualised simple rate quoted for a deposit lasting $T$ years. Its growth factor over that term is $1+r_TT$.

- $s_T$ — spot rate for maturity $T$ expressed as an effective annual rate. Applies to an investment starting today and ending at $T$.

- $s'_T$ — continuously compounded equivalent of spot rate for maturity $T$.

- $n_1,n_2$ — start and end times of a forward period (in years from today) with $n_1<n_2$.

- $f_{n_1,n_2}$ — effective annual forward rate fixed today for borrowing or lending between $n_1$ and $n_2$.

- $\sum$ add the terms like present values of the coupons.

- $\prod$ multiply the terms like growth factors over consecutive forward periods.


## Summary


### What a bond is

A bond is a way for a government or company to borrow money from investors. When you buy a newly issues bond you pay the issue price $P_0$. In return the issuer promises to make payments on set dates.

For a fixed rate bond the payments usually come in two forms, being:

- Coupons are regular interest payments. If the annual coupon rate is q and there are m equal payment per year then each coupon is $\frac{qP}{m}$ which is calculated using the face value P.

- Redemption is the other form where a lump sum RP is paid at maturity when the bond ends. If R=1 then the issuer repays the face value and the bond is redeemed at par whilst any final coupon is paid alongside it.

The issue price often isn't the same as the face value however the coupons are still based on the face value. A zero coupon bond makes just one payment which is the redemption amount at maturity.

[See Example 1](#example-1-amsterdam-issues-bonds-for-ferries)


### Present value and the fair price of a bond

The present value of a bond is what its future coupons and redemption payment are worth today. We discount each payment from its own payment date and then we add the results.

$\text{PV}=\sum_{i=1}^{n}C_iD(t_i)+RP\,D(T)$

The sum covers the coupons and the last term covers redemption at maturity. If the final coupon is paid at maturity too then both payments use the same discount factor of $D(T)$ with a single market rate $r$ compounded annually of $D(t)=(1+r)^{-t}$.

Under no arbitrage the present value is the bond's fair price. A portfolio of zero coupon bonds can make the same payments on the same dates. However if the bond and that portfolio had different prices then an investor could buy the cheaper one and then sell the more expensive one which would keep the price difference whilst the future payments cancel each other out. This is known as the law of one price.

[See Example 2](#example-2-jpmorgan-prices-a-japanese-government-bond)


### Bond yield

A bond's yield to maturity is the annual rate that makes the present value of its remaining coupons and redemption payments equal to the price you are paying today. It is the IRR of the bond (internal rate of return). Shown as:

$P_0=\sum_{i=1}^{n}\frac{C_i}{(1+y)^{t_i}}+\frac{RP}{(1+y)^T}$

When pricing a bond we start with a discount rate and calculate for its price. Then to find the yield we work backwards from the known price $P_0$ and solve for $y$.

The coupon rate sets the payments for us based on the bond's face value. Th yield depends on those payments and the price you actually pay. For the same future payments a lower purchase price gives you a higher yield.

[See Example 3](#example-3-finding-the-yield-on-a-disney-bond)


### Spot rates

A spot rate shown as $s_T$ is the effective annual interest rate for an investment that starts today and will end in $T$ years. Different maturities may have different spot rates and together they form the spot rate curve.

The spot rate will give the same growth using annual compounding as when $r_T$ is quoted as an annualised simple rate and the growth factor over $T$ years is $1+{r_T}T$, shown as:

$(1+s_T)^T=1+r_TT \Rightarrow s_T=(1+r_TT)^{1/T}-1.$

To value payment due in T years we would use the spot rate for that payment date:

$D(T)=\frac{1}{(1+s_T)^T}.$

Because $D(T)$ also equals the price $V_T$ of a zero coupon bond paying £1 at maturity we can also works backwards from that price using:

$s_T=V_T^{-1/T}-1.$

Ergo, a coupon bond may use multiple spot rates to find the fair price (one for each payment date). Also it is worth noting as a comparison that its yield is a single rate that fits the whole bond price.

[See Example 4](#example-4-using-spot-rates-to-fund-spacexs-thruster-upgrades)


### Forward rates

Forward rate (shown as $f_{n_1,n_2}$ is the effective annual interest rate agreed today for borrowing or lending that starts at time $n_1$ and ends at time $n_2$. A spot rate applies form today whilst a forward rate applies between two future dates.

Under no arbitrage investing from today to $n_2$ must give us the same growth as investing to $n_1$ and then reinvesting at the forward rate agreed to today. This is written out as:

$(1+s_{n_1})^{n_1}(1+f_{n_1,n_2})^{n_2-n_1}=(1+s_{n_2})^{n_2}.$

We then rearrange to give the fair forward rate by:

$f_{n_1,n_2}=\left(\frac{(1+s_{n_2})^{n_2}}{(1+s_{n_1})^{n_1}}\right)^{1/(n_2-n_1)}-1.$

This ratio isolates the growth between the two dates. We then take the $1/(n_2-n_1)$ power as it converts the growth into a one year growth factor and subtracting 1 gives the annual rate.

(Can also be calculated directly from the prices of unit zero coupon bonds: $(1+f_{n_1,n_2})^{n_2-n_1}=\frac{V_{n_1}}{V_{n_2}}.$)

[See Example 5](#example-5-locking-in-a-forward-rate-for-an-elizabeth-line-upgrade)


## My example


### Example 1: Amsterdam issues bonds for ferries

In this example, let us have the City of Amsterdam issue bonds to install charging points for its public use electric ferries. Each bond has a face value of £1234 and a four year maturity and an annual coupon rate of 4.8% that is paid every six months. It is issued at 98% of face value and it keeps a 2% discount and is redeemed at par.

What does an investor pay today? What do they receive every six months? And what do they receive at maturity?

Investor pays the issue price today of:

$P_0=0.98(1{,}234)=£1{,}209.32$

Each coupon is based on the face value:

$\frac{qP}{m}=\frac{0.048(1{,}234)}{2}=£29.616\approx £29.62$

The investor will receive 8 coupons, one every six months. At the end of year four, Amsterdam will pay back the £1234 face value alongside the final coupon which will bring the last payment to be roughly £1263.62.


### Example 2: JPMorgan prices a Japanese government bond

JPMorgan is considering a purchase of five year Japanese government issues bonds with a total face value equivalent to £47,570,325.27. The bonds have an annual 2.4% coupon that is paid every six months. At Japan's October auction the weighted average price was 100.09% of face value meaning the purchase would cost £47,613,138.56 before accrued interest. 

What is the estimated fair price if JPMorgan discount the payments at 2.38% per year, compounded semi annually?

First we assume that ten evenly spaced coupon payments must remain with each six month coupon being worth:

$\frac{0.024(47{,}570{,}325.27)}{2}\approx £570{,}843.90$

The discount rate per six month period is 1.19%. Next we discount the ten coupons and the face value paid at maturity to give us:

$\text{PV}\approx\sum_{i=1}^{10}\frac{570{,}843.90}{(1.0119)^i}+\frac{47{,}570{,}325.27}{(1.0119)^{10}}\approx £47{,}614{,}925$

Our estimated fair price is very similar to the auction price.


### Example 3: Finding the yield on a Disney bond

Let us have Disney issue a two year bond with a face value of £17 million to fund upgrades at Disney World. It pays 4% annual coupon and is redeemed at par. An investor can buy it for £16.32 million or 96% of face value.

What is the bond's yield to maturity?

The annual coupon is $0.04(17,000,000) =$680,000$. The investor receives £680,000 after one year and £17.68 million after two years when Disney pays the final coupon and returns the face value. 

The yield $y$ makes those payments worth £16.32 million today:

$16{,}320{,}000=\frac{680{,}000}{1+y}+\frac{17{,}680{,}000}{(1+y)^2}$

Let $x=1+y$ multiplying by $x^2$ and dividing by 680,000 gives:

$24x^2-x-26=0$

Since x is a growth factor we take the positive root:

$x=\frac{1+\sqrt{2497}}{48}\approx1.06187 \Rightarrow y\approx6.19\%$

The 6.19% yield exceeds the 4% coupon rate because the investor pays £16.32 million and receives £17 million at maturity in addition to the coupons.


### Example 4: Using spot rates top fund SpaceX's thruster upgrades

SpaceX needs £10 million in one year and £34 million in two years to upgrade its rocket thrusters. It plans to buy government zero coupon bonds with face values that match the two bills. For every £100 paid at maturity the one year bonds cost £97 today and the two year bonds cost £91. 

What spot rates do the bond prices imply and how much does SpaceX need to set aside today?

First we calculate the one year spot rate as:

$s_1=\frac{100}{97}-1\approx 3.09\%$

Then for the two year spot rate we take the square root to convert two years of growth into an annual rate:

$s_2=\left(\frac{100}{91}\right)^{1/2}-1\approx 4.83\%$

The larger bills mean that SpaceX needs to buy more bonds at the same quoted price per £100. we then calculate the one year holding costs £10,000,000 x 0.97 =£9,700,000.00 £9,700,000 and the two year comes out as £34,000,000 x 0.91 =£30,940,000.

Ergo, SpaceX needs £40.64 million today with each bond holding maturing when its corresponding bill is due.


### Example 5: Locking in a forward rate for an Elizabeth line upgrade

Nikolai, an Elizabeth line operator expects to receive £870,000 in two years and plans to use it for a signalling upgrade in four years. He wants to agree today on the rate it will earn while the money is on deposit. Today's two year spot rate is 4% and the four year spot rate is 5%.

What is the fair annual forward rate from year two to year four and how much will the deposit be worth by the end?

First we divide the four year growth factor by the two year growth factor to find the growth between years two and four:

$(1+f_{2,4})^2=\frac{(1.05)^4}{(1.04)^2}\approx1.123804$

Then take the square root to get the one year growth factor and subtract 1 to get:

$f_{2,4}=\left(\frac{(1.05)^4}{(1.04)^2}\right)^{1/2}-1\approx 6.01\%$

Then we use the growth factor to calculate the deposit as:

$870{,}000(1+f_{2,4})^2\approx£977{,}709.35$

By locking the rate in today, Nikolai can budget for £977,709.35 in year four which is two years before it receives the money to deposit.


## Solved exercises

### Exercise A

Bank A offers a monthly compounded interest rate $r_{1M}$ and bank B offers a yearly compounded interest rate $r_{1Y}$. Explain why $1+r_{1Y}>\left(1+\frac{1}{12}r_{1M}\right)^{12}$ also leads to arbitrage.

<details>
<summary>Show hint</summary>

The two sides of the inequality tel you what £1 grows to after one year at each bank. Think which bank should you borrow from and which you should deposit the money with.

</details>

<details>
<summary>Show solution</summary>

You should assume you can borrow and deposit at the quoted rates with no fees. Look at the inequality, it says that Bank B has the higher one year growth factor.

Calculate for today, borrow £1 from Bank A and deposit it with Bank B. The £1 you borrow covers the deposit, so you put in none of your own money.

Now do it for one year. Bank B pays you $1 + r_{1Y}$ pounds. And you will repay Bank A $\left(1+r_{1M}/12\right)^{12}$ pounds because its monthly rate is applied 12 times for the 12 months in a year. Then you keep the difference:

$\text{Profit}=(1+r_{1Y})-\left(1+\frac{r_{1M}}{12}\right)^{12}>0$

This is arbitrage because the two transactions require no initial investment and they lock in a positive profit.

</details>


### Exercise B

Let $f_{n_1,n_2}$ be the fair forward rate from time $n_1$ to time $n_2$. Show that if a bank offers a FRA for a loan from $n_1$ to $n_2$ at a rate $f<f_{n_1,n_2}$, there is an arbitrage.

<details>
<summary>Show hint</summary>

The FRA is letting you borrow £1 at time $n_1$ at below the market rate. So think, to lock in what the £1 can earn between $n_1$ and $n_2$ you should use today's spot rates. How much do you think you need to borrow today so that you owe £1 at time $n_1$?

</details>

<details>
<summary>Show solution</summary>

Calculate for today. If we borrow $(1+s_{n_1})^{-n_1}$ pounds until time $n_1$ and deposit the entire amount until time $n_2$. Then enter the FRA to borrow £1 at time $n_1$ and then repay it at time $n_2$ at rate $f$. The loan today then funds the deposit and the initial net cash flow is zero.

Then calculate at time $n_1$ as your first loan has grown to exactly £1. Then use that £1 borrowed through the FRA to repay it so the net cash flow is zero again.

At time $n_2$ your deposit will pay:

$\frac{(1+s_{n_2})^{n_2}}{(1+s_{n_1})^{n_1}}=(1+f_{n_1,n_2})^{n_2-n_1}$

You then repay $(1+f)^{n_2-n_1}$ under the FRA. And because $f<f_{n_1,n_2}$ you have a strictly positive profit, being:

$(1+f_{n_1,n_2})^{n_2-n_1}-(1+f)^{n_2-n_1}>0$

All the rates are then fixed today which guarantees us profit without an initial investment.

</details>


## Spreadsheet

[Download the Lesson 4 spreadsheet](../spreadsheets/04-Bonds.xlsx)


### Sheet 1: Bond price


**What it does** The first sheet prices a four year bond using different spot rates for each payment date and then finds the single annual yield that reproduces that price.

**Inputs**

- Facevalue (£50,000)

- Couponrate (5% annually)

- Redemptionr (100% so bond is redeemed at par)

- Spot rate in rows 9-12 is 3.0%, 3.4%, 3.7% and 4.0% for years one to four respectively.

**How it works**

- Column C calculates the discount factor for each year whilst Column D lists our cash flows with £2500 in each of the first three years and the larger £52,500 in our fourth year (when the final coupon and redemption is paid together). Column E multiplies each of our cash flows by its discount factor.

- Cell B14 sums our present values, giving us a fair price of 351,884.53. Cell B15 uses the RATE function from Excel to find our annual yield being 3.9626%. Cell B16 then checks the result by discounting all four cash flows at that yield and then recovering the fair price for us.

- The price yield table shows us the price falling as the yield rises, also displayed in the chart. The bond is then worth £60,000 at 0%, £50,000 at 5% and £42,075.34 at 10%. The chart shows the curve flattens as the yield rises.

**Results** The sheet ties the present value and the fair price of a bond, bond yield and spot rates which applies the pricing method from example 2 and the yield calculation from example 3 to the same bond.


### Sheet 2: Spot and forward

**What it does** It converts the zero coupon bond prices into the spot rates and then uses them to calculate forward rates. The chart then compares ht spot curve with the one year forward rates.

**Inputs** We change the unit zero coupon price for years 1 to 5 being 0.97, 0.93, 0.88, 0.83 and 0.78, and then in the calculator we set n1 and n2 to the start and end years of the forward period.

**How it works**

- The sheet converts the zero coupon price into a spot rate which with the given prices raises the spot rate from 3.0928% in year 1 to 5.0948% in year 5.

- The one year forward rate from today is our one year spot rate which for each later year the sheet uses $V_{T-1}/V_T-1$. The forward rates then sit above their corresponding spot rates from year 2 onwards.

- The calculator then uses the function INDEX to look up prices and spot rates for selected years. From year 2 to 5 both methods give 6.0383%. The difference displays zero which confirms the two formulas agree and changing the period from year 1 to 4 gives 5.3330%.

**Results** The sheet uses the zero coupon pricing from example 4 and the forward rate from example 5, which the calculator checks with two equivalent forms of the no arbitrage relationship.