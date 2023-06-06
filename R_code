---
title: "Grouping Bar Code"
output: html_notebook
---

#### Import libraries 

```{r}
library(ggplot2)
library(ggthemes)
library(ggpubr)
library(Cairo)
```

#### Read data

```{r}
data<-read.csv(file.choose())
```

```{r}
ggplot(data=data, aes(x= NES, y= reorder(Description, -NES),
                      fill=Condition, group=Condition, shape=Condition)) +
  geom_bar(stat="identity")+theme(text = element_text(size = 20))+
  labs(x="Normalized Enrichment Score (NES)", y="", 
       title="Classification of GO Terms")+
  labs(fill="Condition:")+
  scale_fill_manual(values = c("#D92353","#01A07B","#0F7EFF"),
                    labels=c('TRUE'='>0','FALSE'='<0'))+
  geom_col(width = 0.5)+theme_linedraw()+
  theme(axis.text.y = element_text(size = 9.5, face = "bold", color="black")) +
  facet_grid(factor(Contion1, levels=unique(data$Contion1))~factor(Condition, levels=unique(data$Condition)), scales = 'free',space = "free")+
  theme(strip.background =element_rect(fill="black"))+
  theme(strip.text = element_text(face= "bold", colour = 'white'))+
  theme(strip.text.x = element_text(size = 10))+theme(strip.text.y = element_text(size = 9, angle = 0))+
  theme(text = element_text(family = "Times New Roman"))
```

#### Export Image: 

```{r}
ggsave("Significant GO.tiff", units = "mm",
       device = NULL,
       path = NULL,
       scale = 1,
       width = 500,
       height = 250,
       #units = c("in", "cm", "mm", "px"),
       dpi = 700,
       limitsize = 1,
       bg = NULL)

```
