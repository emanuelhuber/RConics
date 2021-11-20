---
layout: page
title: Basics
date: 2021-11-20
---

**Note**:

-   This R-package is still in development, and therefore some of the
    functions may change in a near future.
-   If you have any questions, comments or suggestions, feel free to
    contact me (in english, french or german):
    <a href="mailto:emanuel.huber@pm.me" class="email">emanuel.huber@pm.me</a>.

Install/load `RConics`
----------------------

``` r
# install "devtools" if not already done
if(!require("devtools")) install.packages("devtools")
devtools::install_github("emanuelhuber/RConics")
library(RConics)       # load RGPR in the current R session
```

Projective geometry
-------------------

Many of the functions of the R-package RConics are based on projective
geometry. In projective geometry parallel lines meet at an infinite
point and all infinite points are incident to a line at infinity. Points
and lines of a projective plane are represented by homogeneous
coordinates, that means by 3D vectors:

-   point representation: $(x, y, z)$ -   line representation: $(a, b, c)$     such that $ax + by + c = 0$
In projective geometry:

-   Euclidean points correspond to $(x, y, 1)$ -   infinite points correspond to $(x, y, 0)$ -   Euclidean lines correspond to $(a, b, c)$     with $a\neq 0$     or $b\neq 0$ -   the line at infinity correspond to $(0, 0, 1)$.

The vector $(x, y, z)$ and $(\lambda x,\lambda y,\lambda z)$
define the same geometric point!

In projective geometry, points and lines have the same algebraic
construction. A point can be viewed as a line and a line can be viewed
as a point:

$$
\text{points}\leftrightarrow\text{line}
$$


The interested reader is referred to the excellent book of Jürgen
Richter-Gebert on projective geometry (Richter-Gebert, 2011). We
recommend to use the R-package conics from Bernard Desgraupes to plot
conics.

``` r
# two points in homogeneous coordinates
p1 <- c(3, 1, 1)
p2 <- c(0, 2, 1)

plot(rbind(p1, p2), xlab = "", ylab = "")
grid()
```

Meet and join
-------------

A point $(x, y, z)$ is contained in the line $(a, b, c)$ if $a\cdot x + b\cdot y + c\cdot z = 0$. That means that the vectors $(x, y, z)$ and $(a, b, c)$
are orthogonal.

Now assume that points $p = (p_1, p_2, p_3)$ and $q = (q_1, q_2, q_3)$ are on the same line $l = (l_1, l_2, l_3)$. Then, $l$ is orthogonal to $p$ and $q$
and is given by

$$
p\times q =\begin{pmatrix} p_1\\ p_2\\ p_3\end{pmatrix}\times\begin{pmatrix} q_1\\ q_2\\ q_3\end{pmatrix}  =\begin{pmatrix} +p_2 q_3 - p_3 q_2\\ -p_1 q_3 + p_3 q_1\\ +p_1 q_2 - p_2 q_1\end{pmatrix}
$$

It can be easily shown that this vector (i.e., the cross-product $p\times q$) is orthogonal to $p$ and $q$. For example, we obtain for $p$
:

$$
p_1\cdot\left( p_2 q_3 - p_3 q_2\right) + p_2\cdot\left( -p_1 q_3 + p_3 q_1\right) + p_2\cdot\left( p_1 q_2 - p_2 q_1\right) = 0
$$


``` r
# homogeneous line joining p1 and p2
l_12 <- join(p1,p2)
l_12
```
