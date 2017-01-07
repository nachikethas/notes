All problems are taken from [@jam13]

Exercise 1 {#ch5:ex1 .unnumbered}
----------

Let $Z = \alpha X + (1 - \alpha) Y$. Then, $$\begin{aligned}
    \sigma_Z^2 = \alpha^2\sigma_X^2 + {(1-\alpha)}^2\sigma_Y^2 + 2\alpha(1 -
    \alpha)\sigma_{XY}.\end{aligned}$$ Thus, $$\begin{aligned}
    \frac{d\sigma_Z^2}{d\alpha}
    &= 2\alpha\sigma_X^2 - 2(1-\alpha)\sigma_Y^2 + 2(1 -
    2\alpha)\sigma_{XY}.\end{aligned}$$ Setting
$\frac{d\sigma_Z^2}{d\alpha} = 0$, we obtain $$\begin{aligned}
    \alpha = \frac{\sigma_Y^2 - \sigma_{XY}}{\sigma_X^2 + \sigma_Y^2 -
    2\sigma_{XY}}.\end{aligned}$$ To see that this choice of $\alpha$
does minimize the variance, we only need to show that the second
derivative is positive. $$\begin{aligned}
    \frac{d^2\sigma_Z^2}{d\alpha^2}
    &= 2\sigma_X^2 + 2\sigma_Y^2 - 4\sigma_{XY} \\
    &\ge 2\sigma_X^2 + 2\sigma_Y^2 - 4\sigma_X\sigma_Y \\
    &= 2 {\left(\sigma_X - \sigma_Y\right)}^2 \\
    &> 0,\end{aligned}$$ where we’ve assumed that $X$ and $Y$ do not
have the same variance.

Exercise 2 {#ch5:pro2 .unnumbered}
----------

![${\left( 1 - \frac{1}{n}\right)}^n$ vs
$n$[]{data-label="fig:einv"}](img/einv){width="75.00000%"}

1.  The probability that it is the $j$th observation is $\frac{1}{n}$.
    Thus the probability that it is not the $j$th observation is
    $1 - \frac{1}{n}$.

2.  Since we are sampling *with* replacement, the second observation is
    identically distributed as the first. This gives us the same
    probability of $1 - \frac{1}{n}$.

3.  The bootstrap sample consists of $n$ i.i.d observations with the
    distribution given above. Thus the probability that the $j$th
    observation is not in the bootstrap sample is
    ${\left(1 - \frac{1}{n}\right)}^n$.

4.  $1 - {\left(1 - \frac{1}{5}\right)}^5 \approx 0.67232$

5.  $1 - {\left(1 - \frac{1}{100}\right)}^{100} \approx 0.63397$

6.  $1 - {\left(1 - \frac{1}{10^4}\right)}^{10^4} \approx 0.63214$

7.  See Figure \[fig:einv\]. Shows that the convergence $1 - \lim_{n
            \to \infty} {\left( 1 - \frac{1}{n}\right)}^n = 1 - \frac{1}{e}
            \approx 0.63212$ is very quick.

8.  $0.6387$. The bootstrap estimate compares very well to the
    analytical calculation above.

Exercise 3 {#ch5:pro3 .unnumbered}
----------

1.  From the text: This approach involves randomly dividing the set of
    observations into $k$ groups, or folds, of approximately equal size.
    The ﬁrst fold is treated as a validation set, and the method is ﬁt
    on the remaining $k − 1$ folds. The mean squared error, $MSE_1$, is
    then computed on the observations in the held-out fold. This
    procedure is repeated $k$ times; each time, a different group of
    observations is treated as a validation set. This process results in
    $k$ estimates of the test error, $MSE_1, MSE_2, \dots, MSE_k$. The
    $k$-fold CV estimate is computed by averaging these values,
    $$\begin{aligned}
                CV_{(k)} = \frac{1}{k} \sum_{i=1}^k MSE_i
            \end{aligned}$$

2.  The validation set approach has a computational advantage relative
    to $k$-fold CV, but it overestimate the test error rate. LOOCV is
    computationally more expensive, but has lower bias.

Exercise 4 {#ch5:pro4 .unnumbered}
----------

Use the bootstrap method.

In other words, from the original data set (say $Z$) used to make the
prediction, generate $m$ data sets from $Z$ by sampling its elements
with replacement. Use the $m$ bootstrap data sets to generate $m$
estimates. Use the mean of these $m$ estimates as our prediction and
square root of the sample variance as the estimated standard deviation.
