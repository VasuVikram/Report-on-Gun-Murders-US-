Report on Gun Murders (US)
================
Vasu Vikram
July 10, 2018

In this report we will analyse Gun Murders in United States as reported by the latest data of FBI. We will download data from the URL mentioned below: "<https://raw.githubusercontent.com/rafalab/dslabs/master/inst/extdata/murders.csv>" We will then wrangle data and would make necessary modifications that would help us plot state-wise murder rates in the United States.

``` r
url<-"https://raw.githubusercontent.com/rafalab/dslabs/master/inst/extdata/murders.csv"
dest_file<-"data/murders.csv"
download.file(url, destfile = dest_file)
```

Wrangling Data
--------------

``` r
library(tidyverse)
murders<-read_csv("data/murders.csv")
murders<-murders%>%mutate(region=factor(region), rate=total/population*10^5)
save(murders, file="rda/murders.rda")
```

Note that the `echo = FALSE` parameter was added to the code chunk to prevent printing of the R code that generated the plot.

``` r
load("rda/murders.rda")

murders%>%mutate(abb=reorder(abb,rate))%>%
  ggplot(aes(abb,rate))+geom_bar(width=0.5, stat="identity", color="black")+
  coord_flip()
```

![](Report-on-Gun-Murders-US-/Report_on_Gun_Murders_files/figure-markdown_github/
unnamed-chunk-3-1.png)
In the plot above, we have shown state-wise variability in Gun Murders in the United States. The states are represented as abbreviations of states on the vertical axis. The horzontal axis represents the rate, where the Gun Murders' rate is given by the following formula: rate=total/population\*10^5

From the plot, we can notice that Washington DC has an exceptionally high rate of Gun Murders, about 6 times the mean.
