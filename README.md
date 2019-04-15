---
title: "volcano position"
author: "Jeff Halley"
date: "April 15, 2019"
output: html_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

## Interactive Scatter Plot of Active Volcano Locations around the Globe

This markdown file describes the creation of an interactive scatter plot created with plotly that does some exploratory data analsysis on whether there is a correspondance between global position and number of active volcanos. The results suggest that active Volcanos are more common in the northern hemisphere (above the equator at lattitude = 0).
```{r}
#create volcano data frame using volcano data from http://volcano.oregonstate.edu/volcano_table
volcanos<-read.csv("volcanos.csv")

#load plotly library
library(plotly)

#make graph

plot_ly(y=volcanos$Lat,x=volcanos$Long,hoverinfo='text', text=volcanos$Name)%>%layout(title = 'Lattitude and Longitude of Active Volcanos',
       yaxis = list(title = 'Lattitude'),xaxis = list(title = 'Longitude'))

```


