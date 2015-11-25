
![Q_banner](https://github.com/QuantLet/Styleguide-and-Validation-procedure/blob/master/pictures/banner.png)

## ![qlogo](https://github.com/QuantLet/Styleguide-and-Validation-procedure/blob/master/pictures/qloqo.png) **SFSacfMA3**

```yaml
Name of QuantLet : SFSacfMA3
Published in: SFS
Description: 'Plots the autocorrelation function of an MA(3) (moving average) process.'
Keywords: acf, autocorrelation, discrete, graphical representation, linear, moving-average, plot, process, simulation, stationary, stochastic, stochastic-process, time-series
Submitted: Wed, July 29 2015 by quantomas
Example: 'The simulation is produced for the random sample of 1000 observations.'
```

![Picture1](SFSacfMA3-1.png)


```r
# clear variables and close windows
rm(list = ls(all = TRUE))
graphics.off()
set.seed(0)
x = rnorm(1002, 0, 1)
y = filter(filt = c(1, -1, 1), x = x)

autocorr = acf(y[2:1001], lag.max = 20, col = "red", main = "Sample Autocorrelation Function (ACF)", 
    ylab = "Sample Autocorrelation")
print(cbind(autocorr$lag, autocorr$acf)) 

```
