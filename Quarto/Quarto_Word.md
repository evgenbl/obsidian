---
title: "Example knitr/R Markdown document"
author: "Your name"
date: "22/5/2020"
output:
  word_document:
    reference_docx: colonTemplate.docx
---

```{r setup, include=FALSE}
# Load data into global environment.
library(finalfit)
library(dplyr)
library(knitr)
load(here::here("data", "out.rda"))
```

## Table 1 - Demographics
```{r table1, echo = FALSE}
kable(table1, row.names=FALSE, align=c("l", "l", "r", "r", "r", "r"))
```

## Table 2 - Association between tumour factors and 5 year mortality
```{r table2, echo = FALSE}
kable(table2, row.names=FALSE, align=c("l", "l", "r", "r", "r", "r"))
```

## Figure 1 - Association between tumour factors and 5 year mortality
```{r figure1, echo=FALSE, message=FALSE, warning=FALSE, fig.width=10}
explanatory = c( "differ.factor", "age", "sex.factor",
                "extent.factor", "obstruct.factor",
                "nodes")
dependent = "mort_5yr"
colon_s %>%
  or_plot(dependent, explanatory,
          breaks = c(0.5, 1, 5, 10, 20, 30))
```
