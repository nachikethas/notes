Exercise 1 {#ch4:ex1 .unnumbered}
----------

The logistic function is given by $$\begin{aligned}
    p(\Xv) = \frac{e^{\beta_0 + \beta_1\Xv}}{1 + e^{\beta_0 +
    \beta_1\Xv}}.\end{aligned}$$ Therefore, $$\begin{aligned}
    1 - p(\Xv) &= 1 - \frac{e^{\beta_0 + \beta_1\Xv }}{1 + e^{\beta_0 +
                    \beta_1\Xv }}\\
               &= \frac{1}{1 + e^{\beta_0 + \beta_1\Xv }}.\end{aligned}$$
This yields the odds, $$\begin{aligned}
    \frac{p(\Xv)}{1 - p(\Xv)} = e^{\beta_0 + \beta_1\Xv }.\end{aligned}$$

Exercise 2 {#ch4:ex2 .unnumbered}
----------

$$\begin{aligned}
    \argmax_k p_k(x)
    &= \argmax_k \pi_k \exp(-\frac{1}{2\sigma^2} {(x - \mu_k)}^2)\\
    &= \argmax_k \log(\pi_k) - \frac{1}{2\sigma^2} {(x - \mu_k)}^2\\
    &= \argmax_k \log(\pi_k) - \frac{x^2 - 2x\mu_k +
        {\mu_k}^2}{2\sigma^2}\\
    &= \argmax_k \log(\pi_k) + x\frac{\mu_k}{\sigma^2} -
        \frac{{\mu_k}^2}{2\sigma^2}.\end{aligned}$$

Exercise 3 {#ch4:ex3 .unnumbered}
----------

$$\begin{aligned}
    \argmax_k p_k(x)
    &= \argmax_k \frac{\pi_k}{\sigma_k} \exp(-\frac{1}{2{\sigma_k}^2}
        {(x - \mu_k)}^2)\\
    &= \argmax_k \log(\frac{\pi_k}{\sigma_k}) - \frac{1}{2{\sigma_k}^2}
        {(x - \mu_k)}^2\\
    &= \argmax_k \log(\frac{\pi_k}{\sigma_k}) - \frac{x^2 - 2x\mu_k +
        {\mu_k}^2}{2{\sigma_k}^2}\\
    &= \argmax_k \log(\frac{\pi_k}{\sigma_k}) +
        x\frac{\mu_k}{{\sigma_k}^2} - \frac{{\mu_k}^2}{2{\sigma_k}^2} -
        \frac{x^2}{2{\sigma_k}^2}.\end{aligned}$$

Thus, we see the presence of a term that’s quadratic in $x$ which makes
the Bayes’s classifier non-linear.

Exercise 4 {#ch4:ex4 .unnumbered}
----------

### 4a {#ch4:ex4a .unnumbered}

For any given observation $x$, the fraction $0.1$ of the observations
will lie close to $x$. In other words, $$\begin{aligned}
    \Pr\left[ |X-x| < \frac{1}{10}\right] = \frac{1}{10},\end{aligned}$$
since $X$ is uniformly distributed.

### 4b {#ch4:ex4b .unnumbered}

$$\begin{aligned}
    \Pr\left[ |X_1-x_1| < \frac{1}{10} , |X_2-x_2| <
    \frac{1}{10}\right]
    &=\Pr\left[|X_1-x_1| < \frac{1}{10}\right]
        \Pr\left[|X_2-x_2| < \frac{1}{10}\right]\\
    &= {\left(\frac{1}{10}\right)}^2 = 0.01.\end{aligned}$$

### 4c {#ch4:ex4c .unnumbered}

$$\begin{aligned}
    \Pr\left[ |X_i-x_i| < \frac{1}{10} \forall 1\le i\le p\right]
    = \frac{1}{10^p}.\end{aligned}$$

For this question, $p=100$, so the required fraction is $10^{-100}$.

### 4d {#ch4:ex4d .unnumbered}

In such large dimensional space, very few observations are close to each
other. In particular from the above analysis, we see that KNN makes its
prediction by using only $10^{-98}\%$ of the observational data.

Moreover, the situation does not get much better if we look at a larger
fraction of the range. For example, say we use observations that are
within $90\%$ of the range of $X$ closest to a test observation. For
$p=100$, we see that this corresponds to using a fraction of $0.9^{100}
\approx 2.66 \times 10^{-5}$ or $0.00266\%$ of the observational data.

### 4e {#ch4:ex4e .unnumbered}

Assuming that the observations are uniformly distributed over the unit
cube, to capture $10\%$ of the observations, we need a hypercube that
covers a volume of $\frac{1}{10}$. This gives us the length of each side
of the cube to be ${\left(\frac{1}{10}\right)}^{\frac{1}{p}}$. For
$p=100$, this implies that the length of each side is $97.72\%$ of a
side of the original unit cube containing all the observations.

Exercise 5 {#ch4:ex5 .unnumbered}
----------

1.  The training set is unlikely to show a perfectly linear decision
    boundary, so QDA will learn a non-linear boundary that’ll better fit
    on the training set but poorly fit the test set. In short, QDA
    performs better in training, while LDA performs better on the test
    set.

2.  QDA performs better on both, assuming we have enough samples in the
    training set.

3.  The prediction accuracy will improve. With enough training samples,
    QDA will outperform LDA when the Bayes decision boundary is
    non-linear and there are enough samples in the training set.

4.  False. QDA will probably overfit the training data.

Exercise 6 {#ch4:ex6 .unnumbered}
----------

It’s given that $\bm{\hat{\beta}} = [-6 \; 0.05 \; 1]'$.

### 6a {#ch4:ex6a .unnumbered}

The estimated probability is given by $$\begin{aligned}
    \hat{p}(\xv)
    &= \frac{\exp(\bm{\hat{\beta}}' \xv)}{1 + \exp(\bm{\hat{\beta}}' \xv)}\\
    &\approx 0.378,\end{aligned}$$ where $\xv = [1 \; 40 \; 3.5]'$.

### 6b {#ch4:ex6b .unnumbered}

We use the fact that $$\begin{aligned}
\label{eq:ch4:ex6b}
    \log\left(\frac{p(\xv)}{1 - p(\xv)}\right)
    = \bm{\hat{\beta}}' \xv,\end{aligned}$$ where
$\xv = [1 \; y \; 3.5]'$ and $y$ represents the number of hours of study
required. Solving equation  with $p(\xv) = 0.5$ yields $y = 50$.

Exercise 7 {#ch4:ex7 .unnumbered}
----------

Assume that $X \vert Y=k \sim \mathcal{N}(\mu_k, \sigma^2)$ where $\mu_0
= 0$ and $\mu_1 = 10$. The prior probabilities are given to be $\pi_0 =
0.2$ and $\pi_1 = 0.8$ and the variance estimate is given by
$\hat{\sigma}^2 = 36$. Then, $$\begin{aligned}
    p_1(x) = \frac{\pi_1 \exp(-\frac{1}{2{\sigma}^2} {(x -
            \mu_1)}^2)}{\pi_1 \exp(-\frac{1}{2{\sigma}^2} {(x -
            \mu_1)}^2) + \pi_0 \exp(-\frac{1}{2{\sigma}^2} {(x -
            \mu_0)}^2)}.\end{aligned}$$ Thus, $$\begin{aligned}
    \hat{p_1}(x) &= \frac{\pi_1 \exp(-\frac{1}{2{\hat{\sigma}}^2} {(x -
        \mu_1)}^2)}{\pi_1 \exp(-\frac{1}{2{\hat{\sigma}}^2} {(x -
        \mu_1)}^2) + \pi_0 \exp(-\frac{1}{2{\hat{\sigma}}^2} {(x -
        \mu_0)}^2)}.\end{aligned}$$ Plugging in the values, we get
$$\begin{aligned}
    \hat{p_1}(4) \approx 0.752.\end{aligned}$$

Exercise 8 {#ch4:ex8 .unnumbered}
----------

On the training data, 1-nearest neighbour method has no errors since it
labels a training observation according to its closest observation
namely, itself. Since the test and training sets are equal in size, the
error in test set alone is 36% which is less that 30% error by logistic
regression. Hence, prefer logistic regression in this case.

Exercise 9 {#ch4:ex9 .unnumbered}
----------

### 9a {#ch4:ex9a .unnumbered}

Let $p$ be the required fraction of people who will default. Then,
$$\begin{aligned}
    \frac{p}{1-p} = 0.37,\end{aligned}$$ which yields $p \approx 0.27$.

### 9b {#ch4:ex9b .unnumbered}

Let $p$ denote the chance of defaulting on the payment. It’s given that
$p = 0.16$. Then, $$\begin{aligned}
    odds &= \frac{p}{1-p}\\
         &\approx 0.19.\end{aligned}$$
