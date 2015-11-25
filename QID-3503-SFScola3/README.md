
![Q_banner](https://github.com/QuantLet/Styleguide-and-Validation-procedure/blob/master/pictures/banner.png)

## ![qlogo](https://github.com/QuantLet/Styleguide-and-Validation-procedure/blob/master/pictures/qloqo.png) **SFScola3**

```yaml
Name of QuantLet : SFScola3
Published in: SFS
Description: 'Plots the time series of daily returns and log returns for Coca-Cola company from 1 January 2002 to 30 November 2004.'
Keywords: asset, data visualization, financial, graphical representation, log-returns, plot, price, returns, stock-price, time-series, visualization
See also: SFScola1, SFScola2
Submitted: Mon, August 03 2015 by quantomas
Datafiles: Coca_cola.txt
```

![Picture1](SFScola3-1.png)


```r
# clear variables and close windows
rm(list = ls(all = TRUE))
graphics.off()

x = read.table("Coca_cola.txt")     # Stock prices
x = ts(x)                           # transform to time series object

# Returns
r1 = (x[2:length(x)] - x[1:length(x) - 1])/x[1:length(x) - 1]   # Returns
r2 = log(x[2:length(x)]) - log(x[1:length(x) - 1])              # Log returns
split.screen(c(2, 1))

# Time series r1
screen(1)
plot(r1, type = "l", col = "blue", xlab = "Time (days)", ylab = "Returns")
# Time series r2
screen(2)
plot(r2, type = "l", col = "blue", xlab = "Time (days)", ylab = "Log Returns") 

```
