
![Q_banner](https://github.com/QuantLet/Styleguide-and-Validation-procedure/blob/master/pictures/banner.png)

## ![qlogo](https://github.com/QuantLet/Styleguide-and-Validation-procedure/blob/master/pictures/qloqo.png) **SFScola2**

```yaml
Name of QuantLet : SFScola2
Published in : SFS
Description: 'Plots the autocorrelation function of daily stock prices for Coca-Cola company from 1 January 2002 to 30 November 2004.'
Keywords: acf, asset, autocorrelation, data visualization, financial, graphical representation, plot, price, stock-price, time-series, visualization
See also: SFScola1, SFScola3
Submitted: Mon, August 03 2015 by quantomas
Datafiles: Coca_cola.txt
```

![Picture1](SFScola2-1.png)


```r
# clear variables and close windows
rm(list = ls(all = TRUE))
graphics.off()

x = read.table("Coca_cola.txt")     # Stock prices
x = ts(x)                           # transform into time series object

autocorr = acf(x, lag.max = 100, col = "red", main = "Sample Autocorrelation Function (ACF)", 
    ylab = "Sample Autocorrelation") 

```
