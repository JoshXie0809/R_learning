---
title: "learning_R_9"
author: "謝錚奇＿D54079012"
date: "2020/4/3"
output: html_document
---

# apply( )
```{r}
an_info <- matrix(1:9, ncol = 3)

colnames(an_info) <- c('Tiger', 'Lion', 'Leopard')
rownames(an_info) <- c('Day1', 'Day2', 'Day3')

an_info
apply(an_info, 2, max)

## NA ? na.rm=T
an_info1 <- matrix(c(1:8,NA), ncol = 3)

colnames(an_info1) <- c('Tiger', 'Lion', 'Leopard')
rownames(an_info1) <- c('Day1', 'Day2', 'Day3')

an_info1
apply(an_info1, 2, max, na.rm=T)
```

# sapply( )
```{r}
## 計算電力
## 每度電$50, 超過150 打八折
## government -> 0.8 company ->1.2 consumer ->1

## 用電數: 100, 200, 400, 120
## 身份  : 'government', 'company', 'company','consumer'

deg.info <- c(100, 200, 400, 120)
cust.info <-c('government', 'company', 'company','consumer')

list.price <- deg.info*50*ifelse(deg.info>150,0.8,1)
adj <- sapply(cust.info, switch, customer=0.8, company=1.2, 1)
adj
final.price <- list.price*adj
final.price
```

## iris
```{r}
head(iris)
sapply(iris[-5], mean)
```
