
![Q_banner](https://github.com/QuantLet/Styleguide-and-Validation-procedure/blob/master/pictures/banner.png)

## ![qlogo](https://github.com/QuantLet/Styleguide-and-Validation-procedure/blob/master/pictures/qloqo.png) **SFSBSCopt1**

```yaml
Name of QuantLet : SFSBSCopt1 
Published in: SFS
Description: 'Calculates the price of a European call option according to Black Scholes.'
Keywords: asset, black-scholes, call, european-option, financial, option, option-price, price, simulation, stock-price
See also: SFSIBTbc, SFSIBTdk, SFSbitreeNDiv, SFSgreeks, SFSgreeks
Author: Zografia Anastasiadou
Submitted: Wed, August 05 2015 by quantomas
Input:
- K - strike price
- S - stock price
- r - interest rate
- sigma - volatility
- tau - time to maturity
Example: 'The example is produced for the values: S=78.05174, K=80, r=0.07, sigma = 0.25 and tau=1.'
```


```r
# clear variables and close windows
rm(list = ls(all = TRUE))
graphics.off()

# parameter settings
K     = 80
r     = 0.07
sigma = 0.25
tau   = 1

# present value of the expected dividends
d = exp(-(tau/4) * r) + exp(-(tau/2) * r)
# stock price
S = K - d

y     = (log(S/K) + (r - sigma^2/2) * tau)/(sigma * sqrt(tau))
(cdfy = pnorm(y))
(cdfn = pnorm(y + sigma * sqrt(tau)))

# BS formula
(cs = S * cdfn - (K * exp(-r * tau) * cdfy))
```
