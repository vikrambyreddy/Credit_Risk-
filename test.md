---
title: "Credit Risk Modelling using Logistic Regression"
output: html_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

## Introduction
Modeling credit risk for both personal and company loans is of major importance for banks and financial institutions. The probability that a debtor will default is a key component in getting to a measure for credit risk.

In this,we will be building one of the widely used machine learning techniques for solving classification problem, i.e, logistic regression.


##Data
The original data used in this exercise comes from publicly available data set 'german credit' data set present in it 

```{r}
credit = read.csv('german_credit.csv')
summary(credit)

```




```{r}
F=c(1,2,4,5,7,8,9,10,11,12,13,15,16,17,18,19,20)

for(i in F) credit[,i]=as.factor(credit[,i])

```


```{r}
i_test <- sample(1:nrow(credit),size=333)

```


```{r}
colnames(credit)


```
```{r}

credit$response <- credit$response - 1
credit$response <- as.factor(credit$response)
```


```{r}

hist(credit$Age..years.,colour='red')



```

```{r}
hist(credit$Account.Balance)

boxplot(credit$Creditability,credit$Account.Balance)

```