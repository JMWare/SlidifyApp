---
title       : The 'Seatbelt' App
subtitle    : Using 'ggplot2' Graphics to Visualise the Effects of Legislation Requiring Compulsory Use of Seatbelts in the United Kingdom
author      : John Ware
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

<H2 ALIGN=center>The 'Seatbelt' App</H2>
<BR>
<P><H3> Road transport is at the heart of our industrialised civilisation, but it exacts a high 
a high price in terms of deaths and injuries.</H3></P>
<BR>
<P><H3> In this application we use a dataset consisting of monthly counts of fatalities and
serious injuries to the occupants of passenger cars in the United Kingdom to explore the
effects of the introduction of compulsory wearing of seatbelts on 31 January 1983;
and the relationship between casualty rates and seasonal effects, average mileage and petrol prices.</H3></P>

---

<H2 ALIGN=center>The App uses a graphical presentation</H2>

<BR>
<P><H4>The App uses 'R' code in a 'Slidify' application to generate a 'ggplot2'
graphical presentation; a sample of the code and its output is shown below</H4></P>
<BR>


```r
library(ggplot2)
library(datasets)
Data <- data.frame(Seatbelts[ , c(2:6)], law = as.factor(Seatbelts[ ,8]))
TITLE <- "DRIVER CASUALTIES BY ANNUAL KILOMETRES DRIVEN"
XLAB <- "KILOMETRES"
YLAB <- "DRIVER CASUALTIES PER MONTH"
qplot(kms, drivers, data=Data, geom=c("point", "smooth"),  method="loess",
		col=law, main=TITLE, xlab=XLAB, ylab=YLAB, asp=0.8)
```


---

<H3 ALIGN=center>Example graph</H3>

<H4>This example graph shows the relationship between casualty rate and 
mileage, the red and blue symbols represent casualty rates pre and post seatbelt 
legislation introduction; we can infer that the legislation was effective in 
reducing the casualty rate.</H4>


![plot of chunk unnamed-chunk-2](assets/fig/unnamed-chunk-2-1.png) 

---

<H3 ALIGN=center>Acknowledgments :</H3><BR>

The data used by the App is derived from a study by A. C. Harvey and J. Durbin :
'The effects of seat belt legislation on British road casualties' (1986).

