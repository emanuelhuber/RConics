---
layout: default
title: Home
date: 2021-11-20
---


# RConics: a free and open-source package for computations on conics and much more

The R-package RConics solves some conic related problems
using projective geometry: intersection of conics with lines and conics, arc
length of an ellipse, polar lines, etc.




**This is an ongoing project.**

**If you have any questions, comments or suggestions, feel free to contact me (in english, french or german):**
**emanuel.huber@pm.me**


Thank you!


## How to install

You must first install [R](https://cran.r-project.org/). Then, in R console, enter the following:

```r
if(!require("devtools")) install.packages("devtools")
devtools::install_github("emanuelhuber/RConics")
library(RConics)
```

Alternatively, you can download the package as a zip file and install it in R
following these instructions:

https://riptutorial.com/r/example/5556/install-package-from-local-source
