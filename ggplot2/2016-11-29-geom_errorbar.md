---
name: geom_errorbar
permalink: ggplot2/geom_errorbar/
description: Examples of geom_errobar in R and ggplot2
layout: base
thumbnail: thumbnail/error-bar.jpg
language: ggplot2
page_type: example_index
display_as: statistics
order: 2
output:
  html_document:
    keep_md: true
---



### New to Plotly?

Plotly's R library is free and open source!<br>
[Get started](https://plot.ly/r/getting-started/) by downloading the client and [reading the primer](https://plot.ly/r/getting-started/).<br>
You can set up Plotly to work in [online](https://plot.ly/r/getting-started/#hosting-graphs-in-your-online-plotly-account) or [offline](https://plot.ly/r/offline/) mode.<br>
We also have a quick-reference [cheatsheet](https://images.plot.ly/plotly-documentation/images/r_cheat_sheet.pdf) (new!) to help you get started!

### Version Check

Version 4 of Plotly's R package is now [available](https://plot.ly/r/getting-started/#installation)!<br>
Check out [this post](http://moderndata.plot.ly/upgrading-to-plotly-4-0-and-above/) for more information on breaking changes and new features available in this version.


```r
library(plotly)
packageVersion('plotly')
```

```
## [1] '4.9.1'
```

### Basic Error Bar


```r
library(plotly)

df <- data.frame(x = 1:10,
                 y = 1:10,
                 ymin = (1:10) - runif(10),
                 ymax = (1:10) + runif(10),
                 xmin = (1:10) - runif(10),
                 xmax = (1:10) + runif(10))

p <- ggplot(data = df,aes(x = x,y = y)) + 
    geom_point() + 
    geom_errorbar(aes(ymin = ymin,ymax = ymax)) + 
    geom_errorbarh(aes(xmin = xmin,xmax = xmax))

p <- ggplotly(p)

p
```

<div id="htmlwidget-7407259de2670b9ad34f" style="width:672px;height:480px;" class="plotly html-widget"></div>
<script type="application/json" data-for="htmlwidget-7407259de2670b9ad34f">{"x":{"data":[{"x":[1,2,3,4,5,6,7,8,9,10],"y":[1,2,3,4,5,6,7,8,9,10],"text":["x:  1<br />y:  1","x:  2<br />y:  2","x:  3<br />y:  3","x:  4<br />y:  4","x:  5<br />y:  5","x:  6<br />y:  6","x:  7<br />y:  7","x:  8<br />y:  8","x:  9<br />y:  9","x: 10<br />y: 10"],"type":"scatter","mode":"markers","marker":{"autocolorscale":false,"color":"rgba(0,0,0,1)","opacity":1,"size":5.66929133858268,"symbol":"circle","line":{"width":1.88976377952756,"color":"rgba(0,0,0,1)"}},"hoveron":"points","showlegend":false,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"x":[1,2,3,4,5,6,7,8,9,10],"y":[1,2,3,4,5,6,7,8,9,10],"text":["ymin: 0.9247583<br />ymax:  1.883140<br />x:  1<br />y:  1","ymin: 1.2439833<br />ymax:  2.834524<br />x:  2<br />y:  2","ymin: 2.2831024<br />ymax:  3.987013<br />x:  3<br />y:  3","ymin: 3.2754943<br />ymax:  4.757368<br />x:  4<br />y:  4","ymin: 4.8675480<br />ymax:  5.850977<br />x:  5<br />y:  5","ymin: 5.7309738<br />ymax:  6.108399<br />x:  6<br />y:  6","ymin: 6.1031669<br />ymax:  7.910918<br />x:  7<br />y:  7","ymin: 7.8235724<br />ymax:  8.671196<br />x:  8<br />y:  8","ymin: 8.5449527<br />ymax:  9.024241<br />x:  9<br />y:  9","ymin: 9.8483845<br />ymax: 10.956730<br />x: 10<br />y: 10"],"type":"scatter","mode":"lines","opacity":1,"line":{"color":"transparent"},"error_y":{"array":[0.883139805868268,0.834524319507182,0.987012595403939,0.757367789745331,0.850977319292724,0.108399092452601,0.910917746368796,0.671195713337511,0.0242409016937017,0.956730029080063],"arrayminus":[0.0752417074982077,0.756016718689352,0.716897625243291,0.724505748832598,0.132452019490302,0.269026161171496,0.896833079401404,0.176427551778033,0.455047256778926,0.151615549344569],"type":"data","width":18.5056493383791,"symmetric":false,"color":"rgba(0,0,0,1)"},"showlegend":false,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"x":[1,2,3,4,5,6,7,8,9,10],"y":[1,2,3,4,5,6,7,8,9,10],"text":["xmin: 0.958655<br />xmax:  1.272131<br />x:  1<br />y:  1","xmin: 1.057155<br />xmax:  2.595033<br />x:  2<br />y:  2","xmin: 2.027438<br />xmax:  3.971729<br />x:  3<br />y:  3","xmin: 3.221363<br />xmax:  4.649174<br />x:  4<br />y:  4","xmin: 4.278907<br />xmax:  5.462358<br />x:  5<br />y:  5","xmin: 5.661895<br />xmax:  6.254969<br />x:  6<br />y:  6","xmin: 6.787000<br />xmax:  7.959097<br />x:  7<br />y:  7","xmin: 7.237919<br />xmax:  8.876793<br />x:  8<br />y:  8","xmin: 8.990156<br />xmax:  9.333452<br />x:  9<br />y:  9","xmin: 9.766307<br />xmax: 10.453610<br />x: 10<br />y: 10"],"type":"scatter","mode":"lines","opacity":1,"line":{"color":"transparent"},"error_x":{"array":[0.272131040459499,0.595033145043999,0.971729278564453,0.649174118414521,0.462358040036634,0.254968610592186,0.959096625680104,0.876793398987502,0.333451895508915,0.453609644901007],"arrayminus":[0.0413450363557786,0.942844739183784,0.972562365001068,0.778636645758525,0.721093234606087,0.338104514405131,0.213000463088974,0.762081111781299,0.0098441073205322,0.233693008776754],"type":"data","width":12.5792723115988,"symmetric":false,"color":"rgba(0,0,0,1)"},"showlegend":false,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null}],"layout":{"margin":{"t":26.2283105022831,"r":7.30593607305936,"b":40.1826484018265,"l":31.4155251141553},"plot_bgcolor":"rgba(235,235,235,1)","paper_bgcolor":"rgba(255,255,255,1)","font":{"color":"rgba(0,0,0,1)","family":"","size":14.6118721461187},"xaxis":{"domain":[0,1],"automargin":true,"type":"linear","autorange":false,"range":[0.0548195177549497,10.9487901271461],"tickmode":"array","ticktext":["2.5","5.0","7.5","10.0"],"tickvals":[2.5,5,7.5,10],"categoryorder":"array","categoryarray":["2.5","5.0","7.5","10.0"],"nticks":null,"ticks":"outside","tickcolor":"rgba(51,51,51,1)","ticklen":3.65296803652968,"tickwidth":0.66417600664176,"showticklabels":true,"tickfont":{"color":"rgba(77,77,77,1)","family":"","size":11.689497716895},"tickangle":-0,"showline":false,"linecolor":null,"linewidth":0,"showgrid":true,"gridcolor":"rgba(255,255,255,1)","gridwidth":0.66417600664176,"zeroline":false,"anchor":"y","title":{"text":"x","font":{"color":"rgba(0,0,0,1)","family":"","size":14.6118721461187}},"hoverformat":".2f"},"yaxis":{"domain":[0,1],"automargin":true,"type":"linear","autorange":false,"range":[0.0296634985459969,11.4770665305341],"tickmode":"array","ticktext":["3","6","9"],"tickvals":[3,6,9],"categoryorder":"array","categoryarray":["3","6","9"],"nticks":null,"ticks":"outside","tickcolor":"rgba(51,51,51,1)","ticklen":3.65296803652968,"tickwidth":0.66417600664176,"showticklabels":true,"tickfont":{"color":"rgba(77,77,77,1)","family":"","size":11.689497716895},"tickangle":-0,"showline":false,"linecolor":null,"linewidth":0,"showgrid":true,"gridcolor":"rgba(255,255,255,1)","gridwidth":0.66417600664176,"zeroline":false,"anchor":"x","title":{"text":"y","font":{"color":"rgba(0,0,0,1)","family":"","size":14.6118721461187}},"hoverformat":".2f"},"shapes":[{"type":"rect","fillcolor":null,"line":{"color":null,"width":0,"linetype":[]},"yref":"paper","xref":"paper","x0":0,"x1":1,"y0":0,"y1":1}],"showlegend":false,"legend":{"bgcolor":"rgba(255,255,255,1)","bordercolor":"transparent","borderwidth":1.88976377952756,"font":{"color":"rgba(0,0,0,1)","family":"","size":11.689497716895}},"hovermode":"closest","barmode":"relative"},"config":{"doubleClick":"reset","showSendToCloud":false},"source":"A","attrs":{"41974736b0f1":{"x":{},"y":{},"type":"scatter"},"419753ea8cda":{"ymin":{},"ymax":{},"x":{},"y":{}},"4197af7f0de":{"xmin":{},"xmax":{},"x":{},"y":{}}},"cur_data":"41974736b0f1","visdat":{"41974736b0f1":["function (y) ","x"],"419753ea8cda":["function (y) ","x"],"4197af7f0de":["function (y) ","x"]},"highlight":{"on":"plotly_click","persistent":false,"dynamic":false,"selectize":false,"opacityDim":0.2,"selected":{"opacity":1},"debounce":0},"shinyEvents":["plotly_hover","plotly_click","plotly_selected","plotly_relayout","plotly_brushed","plotly_brushing","plotly_clickannotation","plotly_doubleclick","plotly_deselect","plotly_afterplot","plotly_sunburstclick"],"base_url":"https://plot.ly"},"evals":[],"jsHooks":[]}</script>

### Margin Error Bar


```r
library(plotly)

population <- data.frame(Year=seq(1790, 1970, length.out=length(uspop)), 
                         Population=uspop, 
                         Error=rnorm(length(uspop), 5))

library(ggplot2)
p <- ggplot(population, aes(x=Year, y=Population, 
                       ymin=Population-Error, ymax=Population+Error))+
  geom_line()+
  geom_point(pch=2)+
  geom_errorbar(width=0.9)

p <- ggplotly(p)

p
```

<div id="htmlwidget-503d410c074f65f6412a" style="width:672px;height:480px;" class="plotly html-widget"></div>
<script type="application/json" data-for="htmlwidget-503d410c074f65f6412a">{"x":{"data":[{"x":[1790,1800,1810,1820,1830,1840,1850,1860,1870,1880,1890,1900,1910,1920,1930,1940,1950,1960,1970],"y":[3.93,5.31,7.24,9.64,12.9,17.1,23.2,31.4,39.8,50.2,62.9,76,92,105.7,122.8,131.7,151.3,179.3,203.2],"text":["Year: 1790<br />Population:   3.93<br />Population - Error:  -1.3218792<br />Population + Error:   9.181879","Year: 1800<br />Population:   5.31<br />Population - Error:   0.5056383<br />Population + Error:  10.114362","Year: 1810<br />Population:   7.24<br />Population - Error:   3.6345199<br />Population + Error:  10.845480","Year: 1820<br />Population:   9.64<br />Population - Error:   3.0374012<br />Population + Error:  16.242599","Year: 1830<br />Population:  12.90<br />Population - Error:   8.6395433<br />Population + Error:  17.160457","Year: 1840<br />Population:  17.10<br />Population - Error:  11.4460758<br />Population + Error:  22.753924","Year: 1850<br />Population:  23.20<br />Population - Error:  15.7333655<br />Population + Error:  30.666635","Year: 1860<br />Population:  31.40<br />Population - Error:  27.6292748<br />Population + Error:  35.170725","Year: 1870<br />Population:  39.80<br />Population - Error:  33.4486318<br />Population + Error:  46.151368","Year: 1880<br />Population:  50.20<br />Population - Error:  44.9803208<br />Population + Error:  55.419679","Year: 1890<br />Population:  62.90<br />Population - Error:  56.7078601<br />Population + Error:  69.092140","Year: 1900<br />Population:  76.00<br />Population - Error:  70.2287292<br />Population + Error:  81.771271","Year: 1910<br />Population:  92.00<br />Population - Error:  86.8660805<br />Population + Error:  97.133919","Year: 1920<br />Population: 105.70<br />Population - Error:  98.0176053<br />Population + Error: 113.382395","Year: 1930<br />Population: 122.80<br />Population - Error: 118.4198270<br />Population + Error: 127.180173","Year: 1940<br />Population: 131.70<br />Population - Error: 126.9235776<br />Population + Error: 136.476422","Year: 1950<br />Population: 151.30<br />Population - Error: 149.1007864<br />Population + Error: 153.499214","Year: 1960<br />Population: 179.30<br />Population - Error: 174.6955442<br />Population + Error: 183.904456","Year: 1970<br />Population: 203.20<br />Population - Error: 197.5561282<br />Population + Error: 208.843872"],"type":"scatter","mode":"lines+markers","line":{"width":1.88976377952756,"color":"transparent","dash":"solid"},"hoveron":"points","showlegend":false,"xaxis":"x","yaxis":"y","hoverinfo":"text","marker":{"autocolorscale":false,"color":"rgba(0,0,0,1)","opacity":1,"size":5.66929133858268,"symbol":"triangle-up-open","line":{"width":1.88976377952756,"color":"rgba(0,0,0,1)"}},"opacity":1,"error_y":{"array":[5.25187915275294,4.80436173518854,3.60548014108546,6.6025987517781,4.26045672151984,5.65392420203898,7.46663452949021,3.77072518437409,6.35136818125627,5.2196791700064,6.19213987478316,5.77127082010864,5.13391948826651,7.68239469356192,4.38017301916447,4.77642237497491,2.19921360969101,4.60445582868846,5.64387180596253],"arrayminus":[5.25187915275294,4.80436173518854,3.60548014108546,6.6025987517781,4.26045672151984,5.65392420203898,7.46663452949021,3.77072518437409,6.35136818125627,5.2196791700064,6.19213987478315,5.77127082010864,5.13391948826651,7.68239469356192,4.38017301916447,4.77642237497493,2.19921360969101,4.60445582868846,5.64387180596253],"type":"data","width":1.01311623699693,"symmetric":false,"color":"rgba(0,0,0,1)"},"frame":null}],"layout":{"margin":{"t":26.2283105022831,"r":7.30593607305936,"b":40.1826484018265,"l":43.1050228310502},"plot_bgcolor":"rgba(235,235,235,1)","paper_bgcolor":"rgba(255,255,255,1)","font":{"color":"rgba(0,0,0,1)","family":"","size":14.6118721461187},"xaxis":{"domain":[0,1],"automargin":true,"type":"linear","autorange":false,"range":[1780.505,1979.495],"tickmode":"array","ticktext":["1800","1850","1900","1950"],"tickvals":[1800,1850,1900,1950],"categoryorder":"array","categoryarray":["1800","1850","1900","1950"],"nticks":null,"ticks":"outside","tickcolor":"rgba(51,51,51,1)","ticklen":3.65296803652968,"tickwidth":0.66417600664176,"showticklabels":true,"tickfont":{"color":"rgba(77,77,77,1)","family":"","size":11.689497716895},"tickangle":-0,"showline":false,"linecolor":null,"linewidth":0,"showgrid":true,"gridcolor":"rgba(255,255,255,1)","gridwidth":0.66417600664176,"zeroline":false,"anchor":"y","title":{"text":"Year","font":{"color":"rgba(0,0,0,1)","family":"","size":14.6118721461187}},"hoverformat":".2f"},"yaxis":{"domain":[0,1],"automargin":true,"type":"linear","autorange":false,"range":[-11.8301667006887,219.352159353898],"tickmode":"array","ticktext":["0","50","100","150","200"],"tickvals":[0,50,100,150,200],"categoryorder":"array","categoryarray":["0","50","100","150","200"],"nticks":null,"ticks":"outside","tickcolor":"rgba(51,51,51,1)","ticklen":3.65296803652968,"tickwidth":0.66417600664176,"showticklabels":true,"tickfont":{"color":"rgba(77,77,77,1)","family":"","size":11.689497716895},"tickangle":-0,"showline":false,"linecolor":null,"linewidth":0,"showgrid":true,"gridcolor":"rgba(255,255,255,1)","gridwidth":0.66417600664176,"zeroline":false,"anchor":"x","title":{"text":"Population","font":{"color":"rgba(0,0,0,1)","family":"","size":14.6118721461187}},"hoverformat":".2f"},"shapes":[{"type":"rect","fillcolor":null,"line":{"color":null,"width":0,"linetype":[]},"yref":"paper","xref":"paper","x0":0,"x1":1,"y0":0,"y1":1}],"showlegend":false,"legend":{"bgcolor":"rgba(255,255,255,1)","bordercolor":"transparent","borderwidth":1.88976377952756,"font":{"color":"rgba(0,0,0,1)","family":"","size":11.689497716895}},"hovermode":"closest","barmode":"relative"},"config":{"doubleClick":"reset","showSendToCloud":false},"source":"A","attrs":{"41972c3e2eed":{"x":{},"y":{},"ymin":{},"ymax":{},"type":"scatter"},"419721b6d14f":{"x":{},"y":{},"ymin":{},"ymax":{}},"419762291651":{"x":{},"y":{},"ymin":{},"ymax":{}}},"cur_data":"41972c3e2eed","visdat":{"41972c3e2eed":["function (y) ","x"],"419721b6d14f":["function (y) ","x"],"419762291651":["function (y) ","x"]},"highlight":{"on":"plotly_click","persistent":false,"dynamic":false,"selectize":false,"opacityDim":0.2,"selected":{"opacity":1},"debounce":0},"shinyEvents":["plotly_hover","plotly_click","plotly_selected","plotly_relayout","plotly_brushed","plotly_brushing","plotly_clickannotation","plotly_doubleclick","plotly_deselect","plotly_afterplot","plotly_sunburstclick"],"base_url":"https://plot.ly"},"evals":[],"jsHooks":[]}</script>
