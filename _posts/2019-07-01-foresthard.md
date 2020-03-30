---
layout: post
title: A surprisingly roundabout path to a forest plot 
categories: [Visualisation, tidyverse, ggplot2, R, SSC Case Contest]
---

In the course of deciding how to display data for our SSC Case Contest [poster](https://hana-dampf.github.io/SSC_Poster/), the forest plot was an obvious choice for an analysis focused on effect sizes and the error estimates of a multivariate regression model. 

The forest plot is ubiquitous in metanalysis and other applications. While there are several prebuilt packages available, as the group member coding this visualisation, it was immediately clear they would not provide enough control for the level of focus we were placing on aesthetics.

Thus, this far more roundabout ggplot2 code was the best option available in R:

```
#Data was reformatted as df with estimates and sandwich error estimates
graph<- ggplot(data=df,
          aes(x=Data,y = Estimate, ymin = Lower, ymax = Upper)) +
  geom_pointrange(aes(col=Data),shape=15,size=0.3) +
  geom_hline(aes(fill=Data),yintercept =1, linetype=2) +
  xlab("Covariates")+ ylab("Odds Ratio (95% Wald CI)") +
  geom_errorbar(aes(ymin=Lower, ymax=Upper,col=Data),width=0.5,cex=1) +
  facet_wrap(~Label,strip.position="left",nrow=44,scales="free_y") +
  #Flip axes
  theme(plot.title=element_text(size=16,face="bold"),
        axis.text.y=element_blank(),
        axis.ticks.y=element_blank(),
        axis.text.x=element_text(face="bold",size = 11),
        axis.title=element_text(size=14,face="bold"),
        strip.text.y = element_text(hjust=0,vjust = 1,angle=180,size=14),
        strip.background = element_blank(),
        legend.position="top") +
  coord_flip() +
  #Match poster colours
  scale_color_manual(values=c("#7030A0","#148AAD","#032B5B"))
  ```
  
  By individually faceting each element, and using some unusual solutions for which geoms would make my desired graphic, it's fully possible (and not even that painful) to get a fully controllable forest plot graphic using the lovely layer and facet structure of ggplot2 in R.
