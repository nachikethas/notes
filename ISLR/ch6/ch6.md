Exercise 1 {#ch6:ex1 .unnumbered}
----------

1.  Best subset selection, since it includes all possible models with
    $k$ predictors, including the models considered by the other two
    methods.

2.  Cannot be determined with certainty. Best subset selection is likely
    to yield the best test error as well if the training set is large
    enough. But this is not guaranteed.

3.  \(i) True (ii) False (iii) False (iv) False (v) True.

Exercise 3 {#ch6:ex3 .unnumbered}
----------

1.  Steadily decrease. The solution to the optimization with the smaller
    $s$ remains feasible on increasing $s$.

2.  Decrease initially, and then eventually start increasing in a U
    shape. You’ll eventually overfit.

3.  Steadily increase. You fit the data better, consequently your fit is
    also very dependent on all the data used.

4.  Steadily decrease. Since we have a better fitting model.

5.  Remain constant. Since it is irreducible.

Exercise 4 {#ch6:ex4 .unnumbered}
----------

1.  Steadily increase. Increasing $\lambda$ causes the solution to focus
    more on reducing the squared sum of the coefficients rather than
    obtaining the best fit for the data.

2.  Decrease initially, and then eventually start increasing in a U
    shape. You’ll eventually end up setting $\bm{\beta} = 0$.

3.  Steadily decrease. You fit the data progressively worse.

4.  Steadily increase. Since we have a progressively worse fitting
    model.

5.  Remain constant. Since it is irreducible.

Exercise 5 {#ch6:ex5 .unnumbered}
----------

Say $x_{11} = x_{12} = x = -x_{21} = -x_{22}$ and $y_1 = -y_2 = y$.
Moreover, $\lambda \ge 0$.

1.  Ignoring the $\beta_0$ term, we may write the ridge regression
    optimization problem as $$\begin{aligned}
                & \underset{\bm{\beta}}{\text{minimize}}
                & & {\left(y - x (\beta_1 + \beta_2)\right)}^2 +
                {\left(-y + x (\beta_1 + \beta_2)\right)}^2 +
                \lambda{(\beta_1^2 + \beta_2^2)},
            \end{aligned}$$ which reduces to $$\begin{aligned}
                & \underset{\bm{\beta}}{\text{minimize}}
                & & 2{\left(y - x(\beta_1 + \beta_2)\right)}^2 +
                \lambda{(\beta_1^2 + \beta_2^2)}.
            \end{aligned}$$

2.   \[ridgesol\] Notice that you can permute the indices of $\beta$ in
    the above expression without affecting the optimization objective.
    In other words, the optimization remains unchanged by swapping
    $\beta_1$ and $\beta_2$. Thus, there exists a solution to the above
    optimization that sets them both to the same value. Indeed, we can
    use this information to rewrite the above optimization problem as
    $$\begin{aligned}
                & \underset{\beta}{\text{minimize}}
                & & {(y - 2x\beta)}^2 + \lambda\beta^2.
            \end{aligned}$$ It can be verified easily that solving this
    unconstrained optimization problem yields the solution
    $$\begin{aligned}
                \hat{\beta}
                &= \hat{\beta_1} = \hat{\beta_2}\\
                &= \frac{2xy}{\lambda + 4x^2}.
            \end{aligned}$$

3.  Ignoring the $\beta_0$ term, we may write the lasso optimization
    problem as $$\begin{aligned}
                & \underset{\bm{\beta}}{\text{minimize}}
                & & 2{\left(y - x(\beta_1 + \beta_2)\right)}^2 +
                \lambda{(|\beta_1| + |\beta_2|)}.
            \end{aligned}$$

4.  Here we need to distinguish between four cases:

    1.   \[pp\] $\beta_1 \ge 0$ and $\beta_2 \ge 0$.

    2.   \[pm\] $\beta_1 \ge 0$ and $\beta_2 < 0$.

    3.   \[mp\] $\beta_1 < 0$ and $\beta_2 \ge 0$.

    4.   \[mm\] $\beta_1 < 0$ and $\beta_2 < 0$.

    For case \[pp\], we have the optimization problem, $$\begin{aligned}
                & \underset{\bm{\beta}}{\text{minimize}}
                & & 2{\left(y - x(\beta_1 + \beta_2)\right)}^2 +
                \lambda{(\beta_1 + \beta_2)} \\
                & \text{subject to}
                & & \beta_1 \ge 0 \\
                &&& \beta_2 \ge 0.
            \end{aligned}$$ The solution to this optimization is given
    by the line segment $$\begin{aligned}
                \hat{\beta_1} + \hat{\beta_2} &= \frac{y}{x} - \frac{\lambda}{4x^2} \\
                \hat{\beta_1} &\ge 0 \\
                \hat{\beta_2} &\ge 0. \\
            \end{aligned}$$ In this case, the solution only exists when
    $\lambda \le 4xy$. For case \[pm\], we have the optimization
    problem, $$\begin{aligned}
                & \underset{\bm{\beta}}{\text{minimize}}
                & & 2{\left(y - x(\beta_1 + \beta_2)\right)}^2 +
                \lambda{(\beta_1 - \beta_2)} \\
                & \text{subject to}
                & & \beta_1 \ge 0 \\
                &&& \beta_2 < 0.
            \end{aligned}$$ The solution to this optimization is given
    by the line segment $$\begin{aligned}
                \hat{\beta_1} + \hat{\beta_2} &= \frac{y}{x} \\
                \hat{\beta_1} &\ge 0 \\
                \hat{\beta_2} &< 0.
            \end{aligned}$$ For case \[mp\], we have the optimization
    problem, $$\begin{aligned}
                & \underset{\bm{\beta}}{\text{minimize}}
                & & 2{\left(y - x(\beta_1 + \beta_2)\right)}^2 +
                \lambda{(-\beta_1 + \beta_2)} \\
                & \text{subject to}
                & & \beta_1 < 0 \\
                &&& \beta_2 \ge 0.
            \end{aligned}$$ The solution to this optimization is given
    by the line segment $$\begin{aligned}
                \hat{\beta_1} + \hat{\beta_2} &= \frac{y}{x} \\
                \hat{\beta_1} &< 0 \\
                \hat{\beta_2} &\ge 0.
            \end{aligned}$$ For case \[mm\], we have the optimization
    problem, $$\begin{aligned}
                & \underset{\bm{\beta}}{\text{minimize}}
                & & 2{\left(y - x(\beta_1 + \beta_2)\right)}^2 -
                \lambda{(\beta_1 + \beta_2)} \\
                & \text{subject to}
                & & \beta_1 < 0 \\
                &&& \beta_2 < 0.
            \end{aligned}$$ The solution to this optimization is given
    by the line segment $$\begin{aligned}
                \hat{\beta_1} + \hat{\beta_2} &= \frac{y}{x} + \frac{\lambda}{4x^2} \\
                \hat{\beta_1} < 0 \\
                \hat{\beta_2} < 0.
            \end{aligned}$$ In this case, the solution only exists when
    $\lambda > 4xy$. Clearly, the lasso coefficients for the given
    problem are not unique.

![Exercise 6a: The minimum solution is indicated by the vertical line.
The parameters were $y_1 = 1$ and
$\lambda = 3$.[]{data-label="fig:ch6e6a"}](../img/ch6e6a.pdf){width="\textwidth"}

![Exercise 6b: The minimum solution is indicated by the vertical line.
The parameters were $y_1 = 1$ and
$\lambda = 3$.[]{data-label="fig:ch6e6b"}](../img/ch6e6b.pdf){width="\textwidth"}

Exercise 7 {#ch6:ex7 .unnumbered}
----------

1.  The likelihood for the data is given by $$\begin{aligned}
                f(Y|X,\bm{\beta})
                &= \prod_{i = 1}^n f(y_i |\bm{x}_i,\bm{\beta})\\
                &= \frac{1}{{(\sqrt{2\pi\sigma^2})}^n}
                \exp\left(-\frac{1}{2\sigma^2} \sum_{i = 1}^n {(y_i -
                \xv_i^\top \bm{\beta})}^2\right),
            \end{aligned}$$ where $\xv_i$ is a column vector consisting
    of elements from the $i$-th row of $X$ and $\bm{\beta}$ is the
    vector of coefficients.

2.  The prior for $\bm{\beta}$ is given by $$\begin{aligned}
                p(\bm{\beta})
                &= \prod_{j=1}^p g(\beta_j) \\
                &= \frac{1}{{(2b)}^p} \exp\left( -\frac{1}{b} \sum_{j=1}^p
                |\beta_j| \right).
            \end{aligned}$$ Thus, the posterior distribution is given by
    $$\begin{aligned}
                p(\bm{\beta}|X, Y)
                &\propto \frac{1}{{(\sqrt{2\pi\sigma^2})}^n}
                \exp\left(-\frac{1}{2\sigma^2} \sum_{i = 1}^n {(y_i -
                \xv_i^\top \bm{\beta})}^2\right) \frac{1}{{(2b)}^p}
                \exp\left( -\frac{1}{b} \sum_{j=1}^p |\beta_j| \right).
            \end{aligned}$$

3.  The mode of the above posterior is given by $$\begin{aligned}
                \bm{\beta}_{mo}
                &= \argmax_{\bm{\beta}} p(\bm{\beta}|X, Y)\\
                &= \argmax_{\bm{\beta}} \log(p(\bm{\beta}|X, Y))\\
                &= \argmin_{\bm{\beta}} \sum_{i = 1}^n {(y_i - \xv_i^\top
                \bm{\beta})}^2 + \frac{2\sigma^2}{b} \sum_{j=1}^p
                |\beta_j|,\label{eq:ch6ex7c}
            \end{aligned}$$ which is the lasso estimate for an
    appropriate choice of $\lambda$. Note that the equality  was
    obtained after dropping terms that do not depend on $\bm{\beta}$ and
    scaling the objective function by $2\sigma^2$.

4.  In ridge regression, the posterior distribution is given by
    $$\begin{aligned}
                p(\bm{\beta}|X, Y)
                &\propto \frac{1}{{(\sqrt{2\pi\sigma^2})}^n}
                \exp\left(-\frac{1}{2\sigma^2} \sum_{i = 1}^n {(y_i -
                \xv_i^\top \bm{\beta})}^2\right) \frac{1}{{(\sqrt{2\pi c^2})}^p}
                \exp\left( -\frac{1}{2c^2} \sum_{j=1}^p \beta_j^2 \right).
            \end{aligned}$$

5.  The mode of the above posterior is given by $$\begin{aligned}
                \bm{\beta}_{mo}
                &= \argmax_{\bm{\beta}} p(\bm{\beta}|X, Y)\\
                &= \argmax_{\bm{\beta}} \log(p(\bm{\beta}|X, Y))\\
                &= \argmin_{\bm{\beta}} \sum_{i = 1}^n {(y_i - \xv_i^\top
                \bm{\beta})}^2 + \frac{\sigma^2}{c^2} \sum_{j=1}^p
                \beta_j^2,
            \end{aligned}$$ which is the ridge regression estimate for
    an appropriate choice of $\lambda$. The posterior
    $p(\bm{\beta}|X, Y)$ is symmetric about the above estimate.
    Consequently the mean, mode and median coincide.
