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


### Present value and the fair price of a bond

The present value of a bond is what its future coupons and redemption payment are worth today. We discount each payment from its own payment date and then we add the results.

$\text{PV}=\sum_{i=1}^{n}C_iD(t_i)+RP\,D(T)$

The sum covers the coupons and the last term covers redemption at maturity. If the final coupon is paid at maturity too then both payments use the same discount factor of $D(T)$ with a single market rate $r$ compounded annually of $D(t)=(1+r)^{-t}$.

Under no arbitrage the present value is the bond's fair price. A portfolio of zero coupon bonds can make the same payments on the same dates. However if the bond and that portfolio had different prices then an investor could buy the cheaper one and then sell the more expensive one which would keep the price difference whilst the future payments cancel each other out. This is known as the law of one price.


### Bond yield

A bond's yield to maturity is the annual rate that makes the present value of its remaining coupons and redemption payments equal to the price you are paying today. It is the IRR of the bond (internal rate of return). Shown as:

$P_0=\sum_{i=1}^{n}\frac{C_i}{(1+y)^{t_i}}+\frac{RP}{(1+y)^T}$

When pricing a bond we start with a discount rate and calculate for its price. Then to find the yield we work backwards from the known price $P_0$ and solve for $y$.

The coupon rate sets the payments for us based on the bond's face value. Th yield depends on those payments and the price you actually pay. For the same future payments a lower purchase price gives you a higher yield.


### Spot rates

A spot rate shown as $s_T$ is the effective annual interest rate for an investment that starts today and will end in $T$ years. Different maturities may have different spot rates and together they form the spot rate curve.

The spot rate will give the same growth using annual compounding as when $r_T$ is quoted as an annualised simple rate and the growth factor over $T$ years is $1+{r_T}T$, shown as:

$(1+s_T)^T=1+r_TT \Rightarrow s_T=(1+r_TT)^{1/T}-1.$

To value payment due in T years we would use the spot rate for that payment date:

$D(T)=\frac{1}{(1+s_T)^T}.$

Because $D(T)$ also equals the price $V_T$ of a zero coupon bond paying £1 at maturity we can also works backwards from that price using:

$s_T=V_T^{-1/T}-1.$

Ergo, a coupon bond may use multiple spot rates to find the fair price (one for each payment date). Also it is worth noting as a comparison that its yield is a single rate that fits the whole bond price.


### Forward rates

Forward rate (shown as $f_{n_1,n_2}$ is the effective annual interest rate agreed today for borrowing or lending that starts at time $n_1$ and ends at time $n_2$. A spot rate applies form today whilst a forward rate applies between two future dates.

Under no arbitrage investing from today to $n_2$ must give us the same growth as investing to $n_1$ and then reinvesting at the forward rate agreed to today. This is written out as:

$(1+s_{n_1})^{n_1}(1+f_{n_1,n_2})^{n_2-n_1}=(1+s_{n_2})^{n_2}.$

We then rearrange to give the fair forward rate by:

$f_{n_1,n_2}=\left(\frac{(1+s_{n_2})^{n_2}}{(1+s_{n_1})^{n_1}}\right)^{1/(n_2-n_1)}-1.$

This ratio isolates the growth between the two dates. We then take the $1/(n_2-n_1)$ power as it converts the growth into a one year growth factor and subtracting 1 gives the annual rate.

(Can also be calculated directly from the prices of unit zero coupon bonds: $(1+f_{n_1,n_2})^{n_2-n_1}=\frac{V_{n_1}}{V_{n_2}}.$)


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

$\text{PV}\approx\sum_{i=1}^{10}\frac{570{,}843.90}{(1.0119)^i}+\frac{47{,}570{,}325.27}{(1.0119)^{10}}\approx \boxed{£47{,}614{,}925}$

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


### Example 4:

### Example 5:

## Solved exercises

### Exercise A

### Exercise B

## Spreadsheet