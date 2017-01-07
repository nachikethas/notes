Problem 1 {#ch2:prob1 .unnumbered}
---------

1.  Use a flexible method. Given that we have a small number of
    predictors and that there is a lot of data, we are unlikely to
    suffer from overfitting the data.

2.  Use an inflexible method. A flexible method is likely to overfit the
    small dataset, especially since we have large number of parameters.

3.  Use a flexible method as they help in fitting more complex
    functions.

4.  Use an inflexible method since we don’t want to add to the variance
    of the error terms by choosing a flexible method that has a high
    variance by itself.

Problem 2 {#ch2:prob2 .unnumbered}
---------

1.  $n = 500$ and $p = 3$. This is a *regression* problem where we are
    interested *inference* as we are trying to find out how the given
    factors affect the CEO’s salary.

2.  *Classification* problem where we are interested in the *prediction*
    of success or failure of the product. $n = 20$ and $p = 13$.

3.  *Prediction* problem, with the focus on using *regression* to find
    trends in the data. $n = 52$ and $p =
            3$.

Problem 3 {#ch2:prob3 .unnumbered}
---------

![Error curves as a function of
flexibility[]{data-label="fig:errorCurves"}](../img/ch2Q3.png){width="75.00000%"}

1.  See Figure \[fig:errorCurves\].

2.  Bias and training error decrease with flexibility since we are
    fitting the training data better with the expanded choice of
    functions made available to us. The variance and test error increase
    since with too much flexibility the model tends to overfit training
    data. The irreducible error is the variance of the noise term and
    that does not change with model flexibility.

Problem 4 {#ch2:prob4 .unnumbered}
---------

1.  Recognizing handwritten (pin code) numbers, character recognition
    and image classification. The response is a number and character and
    image label respectively. The predictors for the first two cases
    could be the percentage of black pixels in the image, the presence
    of symmetry across the one or two axes and the aspect ratio of the
    image. For image classification, the features depend on the image
    label itself. Assume that we are interested in identifying images of
    a sunset. Then the features, could be the amount of orange cast in
    the image. The brightness of the image near the center and the
    presence of reflections. Note that in all the above examples, we are
    interested in prediction.

2.  Predicting how the final grade of a student in class. The predictors
    could be the grades in all previous classes taken and the
    performance in the in-class quizzes. Another example is predicting
    the stock market price of a company based on predictors such as past
    company performance, current global market conditions and the budget
    allocation of the company. Finally, we may use regression to find
    out which factors most influence an athlete’s performance in a
    tennis match. The predictors could be the court surface, player
    performance in the past few months, the player’s ranking and the
    ranking of the opponent. In this case, we are interested more in
    inference to identify the areas that most affect the performance.

3.  Image classification where we have a bunch of images of faces and we
    want to group the images of the same person. Analysis of documents
    where we want to group together documents that have a similar
    ‘style’ and hence is possibly written by the same person. Analysis
    of tweets where we want to cluster together tweets that pertain to
    the same topic.

Problem 5 {#ch2:prob5 .unnumbered}
---------

A flexible approach tries a greater range of possibilities for
estimating $f$. Especially when the functional form is not adequately
captured by the more restrictive methods, the flexible approach can
improve the model accuracy. For instance, if the data seems to follow a
highly non-linear pattern, a flexible approach might help compared to
linear regression. We might prefer the restrictive approach if we value
the interpretability of the model more than absolute performance.
Identifying which predictors mainly influence the output and by how
much, is one such example.

Problem 6 {#ch2:prob6 .unnumbered}
---------

The parametric approach assumes a functional model. The estimation of
$f$ then just boils down to finding the right parameters of our model to
yield the best fitting functional form. The advantage of this approach
is that our search space (over the parameters) is comparatively small.
Consequently, it is easier to find the best fitting $f$. On the other
hand the performance of the fitting function is entirely dependent on
the model assumptions being satisfied. Faced with data whose structure
is *a priori* unclear, a non-parametric approach can try out a broader
range of functional forms to capture the underlying structure.

Problem 7 {#ch2:prob7 .unnumbered}
---------

1.  
       Observation   Euclidean Distance
      ------------- --------------------
            1                3
            2                2
            3           $\sqrt{10}$
            4            $\sqrt{5}$
            5            $\sqrt{2}$
            6            $\sqrt{3}$

2.  With $K = 1$, we are going to respond identically to the data point
    that is closest to the test point. In this case, observation $5$ is
    closest to the test point and hence we shall predict *Green*

3.  With $K = 3$, the observations $2, 5$ and $6$ are closest to the
    test point. Among them, *Red* is the most commonly occurring class
    and consequently, it is chosen as our prediction.

4.  If the Bayes decision boundary is highly non-linear, then the best
    value for $K$ is likely to be small. This is a consequence of the
    fact that low values of $K$ allows for greater flexibility in
    choosing the decision boundary.
