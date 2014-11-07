---
title       : State Data Sorter
subtitle    : Simple Visual Population Filtering
author      : Rob
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Summary

The State Data Sorter application has been designed to provide simple visibility and control over population data from standardized (i.e., CSV) files.  The current proof-of-concept allows the user to select filtering criteria and control the sorting parameter.  Based on initial feedback, further development will enhance its abilites for wider use.

---

## Operation

This application eliminate the need for users to understand data filtering in R.  Using only the two radio buttons and slider, the user could perform the following example R task.


```r
info <- read.csv("states.csv")
filtered <- subset(info, info$Population >= 10000000, select = State:Population)
sortedlist <- filtered[with(filtered, order(State)),]
print(sortedlist)
```

```
##           State Population
## 5    California   38332521
## 9       Florida   19552860
## 13     Illinois   12882135
## 32     New York   19651127
## 35         Ohio   11570808
## 38 Pennsylvania   12773801
## 43        Texas   26448193
```

---

## Target Audience

The design goal of this application is simplicity, enabling a wide range of users easy control over population data.  Specific users identified for further evaluation, based on their interest in data but lack of general programming experience, include:

1. School children
2. Press/reporters
3. Politicians

---

## Extensibility

This proof of concept application is provided to validate interest.

Future enhancements are scheduled to include:

- Map API integration
- Searching and sorting based on multiple criteria
- Greater regional reach (Global/Country down to County/City)
