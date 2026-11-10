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




## My example

### Example 1:

### Example 2:

### Example 3:

### Example 4:

### Example 5:

## Solved exercises

### Exercise A

### Exercise B

## Spreadsheet