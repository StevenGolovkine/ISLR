# An Overview of Statistical Learning {#overview}







## Conceptual Exercises

### Exercise 1.

This exercise is about *flexible* and *inflexible* statistical learning methods. First, let's recall what are the differences between these methods. The aim of statistical learning is to estimate a function $f$ such that $f$ is a link between the input $X$ and the output $Y$. A *flexible* model means that we do not assume a particular form for $f$. So, an advantage of such models is to generally provide a better fit to the data (however, be careful with the overfitting) but the number of parameters to estimate is usually large. At the contrary, an *inflexible* model has less parameters but we have to prespecified a particular form for the data (for example linear), even if it poorly fits the data.

* *Question (a)*

The case of sample size $n$ extremely large and number of predictors $p$ small is the ideal case in statistical learning. A flexible method should perform very well in this case. The flexible method will tend to reduce the bias and won't be too sensitive to the noise thanks to the large size of the sample. 

* *Question (b)*

The case of sample size $n$ small and number of predictors $p$ very large refers to the high dimensional settings. An inflexible method should show better performance than a flexible one in this case. Here, the trade-off between bias and variance is very important. We allow some bias by using an inflexible model with the hope to reduce a lot the noise in the data.

* *Question (c)*

In the case of highly non-linear relationship between predictors and reponse, a flexible model will perform better than an inflexible one. In case of inflexible model, we set a particular form for $f$ and we usually can not specified a function for $f$ if $f$ is highly non-linear.

* *Question (d)*

If the variance of the error terms is extremely high, an inflexible model will perform better than a flexible one. Because, if we set a flexible method, the function $f$ will tend to follow the error and thus will overfit.

### Exercise 2.

This exercise is about the difference between *regression* and *classification* problems and the *inference* or *prediction* purposes. Let's recall what these different terms mean. A *regression* task is done when we try to infer or predict an output which takes continuous values. A *classification* task is done when we try to infer or predict an output which takes discrete values. An *inference* purpose consists in the understanding of how the features have an influence on the response, whereas a *prediction* purpose is to find a value of the output variable based on a new realisation of the dependant variables and the knowledge of some features and outputs.  

* *Question (a)*

This is a regression problem because the CEO salary is a continuous variable. We aim to do inference here (*understanding which factors*). $n$ is equal to 500 (top 500 firms in the US), $p$ equals to 3 (profit, number of employees and industry) and the output is the CEO salary.

* *Question (b)*

This is a classification problem because the output varible is discrete (*success* or *failure*). We aim to do prediction (*launching a new product and wish to know whether it will be a success or a failure*). $n$ is equal to 20, $p$ equals to 13 (price charged for the product, marketing budget, competition price, and ten other variables) and the output variable is *success or failure*.

* *Question (c)*

This is a regression problem because the % change in the US dollar is continuous. We aim to do prediction (*We are interesting in predicting*). $n$ is equal to 52 (number of week in 2012), $p$ equals to 3 (the % change in the US market, the % change in the British market, and the % change in the German market) and the output variable is the % change in the dollar.

### Exercise 3.

This exercise is about the bias-variance decomposition of the mean square error. 

Consider the following model: $y = f(x) + \epsilon$. We denote by $\widehat{y}$ and $\widehat{f}$ the estimation of $y$ and $f$. The mean square error is:


\[MSE = \mathbb{E}\left[(\widehat{y} - y)^2\right].\]


As a more complex model leads to a better estimation of the function $f$, the training error decreases as the model complexity increases. The MSE can be decomposed into three terms: variance, squared bias and irreducible error. "Variance refers to the amount by which $\widehat{f}$ would change if we estimated it using a different training data set." So, the variance increases with the model complexity because a complex model is very flexible and gives a different function for each training data set. Conversely, the bias decreases with the model complexity because such a model will fit perfectly the data. The irreducible error is equal to $Var(\epsilon)$. The test error has a U-shape because it is the sum of the three previous curves. 

\begin{figure}

{\centering \includegraphics{01-overview_files/figure-latex/ex3-1} 

}

\caption{Model complexity.}(\#fig:ex3)
\end{figure}

### Exercise 4.

This exercise is about giving examples of real-life applications of statistical learning.

<div class="figure"><span id="fig:ml_appli"></span>
<img src="https://res.cloudinary.com/golovkine/image/upload/v1560169346/machine-learning1.png" alt="Application of Machine Learning" width="1000" />
<p class="caption">
From Armando Arroyo GeekStyle on <a href="https://www.linkedin.com//pulse/business-intelligence-its-relationship-big-data-geekstyle">Linkedin</a>.
</p>
</div>

### Exercise 5.

This exercise is about the difference between flexible and non-flexible statistical learning methods. 

A very flexible method has for main advantage over a less flexible methods the large number of functional forms that it can take. It shows two majors drawbacks: the first one is the number of parameters to fit (usually, way more larger than the non-flexible methods) and the second one, its propension to overfit the data. Moreover, they can exhibit less interpretability. 

We can prefer a less flexible approach when we want to do inference of the dataset because of the interpretability of such models. However, when the goal is prediction, we may use very flexible methods in order to (hopefully) have better results. The choice of between a very flexible and a less flexible method refers closely with the bias-variance tradeoff. In general, a very flexible one will lead to small bias, large variance and a less flexible one to large bias, small variance. 

### Exercise 6.

This exercise is about the difference between parametric and non-parametric approaches.

Consider the following model: $Y = f(X) + \epsilon$. We aim to estimate the function $f$. For the parametric approaches, we assume a particular form for $f$, linear for example, and then, estimate some parameters. However, if the form we assume is not the right one, our estimate won't be very accurate. At the opposite, non-parametric approaches do not assume a particular form for $f$. So, the estimate of $f$ will be close to the true functional form of $f$. But, we need a lot of data (compare to parametric approches) to obtain an accurate estimate of $f$.

### Exercise 7.

This exercise is an application of $K$-nearest neighbors.

| Obs | $X_1$ | $X_2$ | $X_3$ |  $Y$  |
|:---:|:-----:|:-----:|:-----:|:-----:|
|  1  |   0   |   3   |   0   |  Red  |
|  2  |   2   |   0   |   0   |  Red  |
|  3  |   0   |   1   |   3   |  Red  |
|  4  |   0   |   1   |   2   | Green |
|  5  |   -1  |   0   |   1   | Green |
|  6  |   1   |   1   |   1   |  Red  |
Table: Data




* *Question (a)*

The euclidean distance between to two $n$-dimensional vectors $X$ and $Y$ is defined by
$$ d(X, Y) = \sqrt{\sum_{i = 1}^n (X_i - Y_i)^2}$$

|    Obs   | 1 | 2 |      3      |     4      |     5      |     6      |
|:--------:|:-:|:-:|:-----------:|:----------:|:----------:|:----------:|
| $d(0/i)$ | 3 | 2 | $\sqrt{10}$ | $\sqrt{5}$ | $\sqrt{2}$ | $\sqrt{3}$ |

* *Question (b)*

For $K = 1$, we classify the test point where the closest observation is. The closest point is the point 5, so the test point will be _Green_.

* *Question (c)*

For $K = 3$, we classify the test point where the three closest observation are. The three closest points are the 2, 5 and 6. Two points are red and one is green, so the test point will be _Red_.

* *Question (d)*

If the Bayes decision boundary in this problem is highly non-linear, we would expect the best value for K to be small because the smaller $K$ is, the more flexible the model is. So, if the model is very flexible, it will adapt to highly non-linear problem.


## Applied Exercises

### Exercise 8.

This exercise is about the `College` dataset. It contains 777 observations of 18 variables about the universities and colleges in the United States. For a description of the variables, please refer to the page 54 of the book or in **R** by typing `help(College)` after loading the package `ISLR`. 

* *Question (a) and (b)*


```r
College <- as_tibble(College, rownames = NA)
```

* *Question (c) i* 


```r
College %>% summary_df() %>% print_summary_df()
```

<ul><li> **Factor variables** </li>
<ul><li> Private </li>
<div style="overflow-x:auto;">
<table class="kable_wrapper table table-striped table-hover table-condensed table-responsive" style="margin-left: auto; margin-right: auto;">
<tbody>
  <tr>
   <td> 

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> Private </th>
   <th style="text-align:right;"> Count </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> No </td>
   <td style="text-align:right;"> 212 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Yes </td>
   <td style="text-align:right;"> 565 </td>
  </tr>
</tbody>
</table>

 </td>
  </tr>
</tbody>
</table>
</div></ul>

</ul><ul><li> **Numeric variables** </li>
<div style="overflow-x:auto;">
<table class="table table-striped table-hover table-condensed table-responsive" style="margin-left: auto; margin-right: auto;">
 <thead>
  <tr>
   <th style="text-align:left;"> Name </th>
   <th style="text-align:right;"> NA_num </th>
   <th style="text-align:right;"> Unique </th>
   <th style="text-align:right;"> Range </th>
   <th style="text-align:right;"> Mean </th>
   <th style="text-align:right;"> Variance </th>
   <th style="text-align:right;"> Minimum </th>
   <th style="text-align:right;"> Q05 </th>
   <th style="text-align:right;"> Q10 </th>
   <th style="text-align:right;"> Q25 </th>
   <th style="text-align:right;"> Q50 </th>
   <th style="text-align:right;"> Q75 </th>
   <th style="text-align:right;"> Q90 </th>
   <th style="text-align:right;"> Q95 </th>
   <th style="text-align:right;"> Maximum </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> Apps </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 711 </td>
   <td style="text-align:right;"> 48013.0 </td>
   <td style="text-align:right;"> 3001.64 </td>
   <td style="text-align:right;"> 14978459.53 </td>
   <td style="text-align:right;"> 81.0 </td>
   <td style="text-align:right;"> 329.8 </td>
   <td style="text-align:right;"> 457.6 </td>
   <td style="text-align:right;"> 776.0 </td>
   <td style="text-align:right;"> 1558.0 </td>
   <td style="text-align:right;"> 3624.0 </td>
   <td style="text-align:right;"> 7675.0 </td>
   <td style="text-align:right;"> 11066.2 </td>
   <td style="text-align:right;"> 48094.0 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Accept </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 693 </td>
   <td style="text-align:right;"> 26258.0 </td>
   <td style="text-align:right;"> 2018.80 </td>
   <td style="text-align:right;"> 6007959.70 </td>
   <td style="text-align:right;"> 72.0 </td>
   <td style="text-align:right;"> 272.4 </td>
   <td style="text-align:right;"> 361.6 </td>
   <td style="text-align:right;"> 604.0 </td>
   <td style="text-align:right;"> 1110.0 </td>
   <td style="text-align:right;"> 2424.0 </td>
   <td style="text-align:right;"> 4814.2 </td>
   <td style="text-align:right;"> 6979.2 </td>
   <td style="text-align:right;"> 26330.0 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Enroll </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 581 </td>
   <td style="text-align:right;"> 6357.0 </td>
   <td style="text-align:right;"> 779.97 </td>
   <td style="text-align:right;"> 863368.39 </td>
   <td style="text-align:right;"> 35.0 </td>
   <td style="text-align:right;"> 118.6 </td>
   <td style="text-align:right;"> 154.0 </td>
   <td style="text-align:right;"> 242.0 </td>
   <td style="text-align:right;"> 434.0 </td>
   <td style="text-align:right;"> 902.0 </td>
   <td style="text-align:right;"> 1903.6 </td>
   <td style="text-align:right;"> 2757.0 </td>
   <td style="text-align:right;"> 6392.0 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Top10perc </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 82 </td>
   <td style="text-align:right;"> 95.0 </td>
   <td style="text-align:right;"> 27.56 </td>
   <td style="text-align:right;"> 311.18 </td>
   <td style="text-align:right;"> 1.0 </td>
   <td style="text-align:right;"> 7.0 </td>
   <td style="text-align:right;"> 10.0 </td>
   <td style="text-align:right;"> 15.0 </td>
   <td style="text-align:right;"> 23.0 </td>
   <td style="text-align:right;"> 35.0 </td>
   <td style="text-align:right;"> 50.4 </td>
   <td style="text-align:right;"> 65.2 </td>
   <td style="text-align:right;"> 96.0 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Top25perc </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 89 </td>
   <td style="text-align:right;"> 91.0 </td>
   <td style="text-align:right;"> 55.80 </td>
   <td style="text-align:right;"> 392.23 </td>
   <td style="text-align:right;"> 9.0 </td>
   <td style="text-align:right;"> 25.8 </td>
   <td style="text-align:right;"> 30.6 </td>
   <td style="text-align:right;"> 41.0 </td>
   <td style="text-align:right;"> 54.0 </td>
   <td style="text-align:right;"> 69.0 </td>
   <td style="text-align:right;"> 85.0 </td>
   <td style="text-align:right;"> 93.0 </td>
   <td style="text-align:right;"> 100.0 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> F.Undergrad </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 714 </td>
   <td style="text-align:right;"> 31504.0 </td>
   <td style="text-align:right;"> 3699.91 </td>
   <td style="text-align:right;"> 23526579.33 </td>
   <td style="text-align:right;"> 139.0 </td>
   <td style="text-align:right;"> 509.8 </td>
   <td style="text-align:right;"> 641.0 </td>
   <td style="text-align:right;"> 992.0 </td>
   <td style="text-align:right;"> 1707.0 </td>
   <td style="text-align:right;"> 4005.0 </td>
   <td style="text-align:right;"> 10024.4 </td>
   <td style="text-align:right;"> 14477.8 </td>
   <td style="text-align:right;"> 31643.0 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> P.Undergrad </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 566 </td>
   <td style="text-align:right;"> 21835.0 </td>
   <td style="text-align:right;"> 855.30 </td>
   <td style="text-align:right;"> 2317798.85 </td>
   <td style="text-align:right;"> 1.0 </td>
   <td style="text-align:right;"> 20.0 </td>
   <td style="text-align:right;"> 35.0 </td>
   <td style="text-align:right;"> 95.0 </td>
   <td style="text-align:right;"> 353.0 </td>
   <td style="text-align:right;"> 967.0 </td>
   <td style="text-align:right;"> 2016.6 </td>
   <td style="text-align:right;"> 3303.6 </td>
   <td style="text-align:right;"> 21836.0 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Outstate </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 640 </td>
   <td style="text-align:right;"> 19360.0 </td>
   <td style="text-align:right;"> 10440.67 </td>
   <td style="text-align:right;"> 16184661.63 </td>
   <td style="text-align:right;"> 2340.0 </td>
   <td style="text-align:right;"> 4601.6 </td>
   <td style="text-align:right;"> 5568.8 </td>
   <td style="text-align:right;"> 7320.0 </td>
   <td style="text-align:right;"> 9990.0 </td>
   <td style="text-align:right;"> 12925.0 </td>
   <td style="text-align:right;"> 16552.8 </td>
   <td style="text-align:right;"> 18498.0 </td>
   <td style="text-align:right;"> 21700.0 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Room.Board </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 553 </td>
   <td style="text-align:right;"> 6344.0 </td>
   <td style="text-align:right;"> 4357.53 </td>
   <td style="text-align:right;"> 1202743.03 </td>
   <td style="text-align:right;"> 1780.0 </td>
   <td style="text-align:right;"> 2735.8 </td>
   <td style="text-align:right;"> 3051.2 </td>
   <td style="text-align:right;"> 3597.0 </td>
   <td style="text-align:right;"> 4200.0 </td>
   <td style="text-align:right;"> 5050.0 </td>
   <td style="text-align:right;"> 5950.0 </td>
   <td style="text-align:right;"> 6382.0 </td>
   <td style="text-align:right;"> 8124.0 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Books </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 122 </td>
   <td style="text-align:right;"> 2244.0 </td>
   <td style="text-align:right;"> 549.38 </td>
   <td style="text-align:right;"> 27259.78 </td>
   <td style="text-align:right;"> 96.0 </td>
   <td style="text-align:right;"> 350.0 </td>
   <td style="text-align:right;"> 400.0 </td>
   <td style="text-align:right;"> 470.0 </td>
   <td style="text-align:right;"> 500.0 </td>
   <td style="text-align:right;"> 600.0 </td>
   <td style="text-align:right;"> 700.0 </td>
   <td style="text-align:right;"> 765.6 </td>
   <td style="text-align:right;"> 2340.0 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Personal </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 294 </td>
   <td style="text-align:right;"> 6550.0 </td>
   <td style="text-align:right;"> 1340.64 </td>
   <td style="text-align:right;"> 458425.75 </td>
   <td style="text-align:right;"> 250.0 </td>
   <td style="text-align:right;"> 500.0 </td>
   <td style="text-align:right;"> 600.0 </td>
   <td style="text-align:right;"> 850.0 </td>
   <td style="text-align:right;"> 1200.0 </td>
   <td style="text-align:right;"> 1700.0 </td>
   <td style="text-align:right;"> 2200.0 </td>
   <td style="text-align:right;"> 2488.8 </td>
   <td style="text-align:right;"> 6800.0 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> PhD </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 78 </td>
   <td style="text-align:right;"> 95.0 </td>
   <td style="text-align:right;"> 72.66 </td>
   <td style="text-align:right;"> 266.61 </td>
   <td style="text-align:right;"> 8.0 </td>
   <td style="text-align:right;"> 43.8 </td>
   <td style="text-align:right;"> 50.6 </td>
   <td style="text-align:right;"> 62.0 </td>
   <td style="text-align:right;"> 75.0 </td>
   <td style="text-align:right;"> 85.0 </td>
   <td style="text-align:right;"> 92.0 </td>
   <td style="text-align:right;"> 95.0 </td>
   <td style="text-align:right;"> 103.0 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Terminal </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 65 </td>
   <td style="text-align:right;"> 76.0 </td>
   <td style="text-align:right;"> 79.70 </td>
   <td style="text-align:right;"> 216.75 </td>
   <td style="text-align:right;"> 24.0 </td>
   <td style="text-align:right;"> 52.8 </td>
   <td style="text-align:right;"> 59.0 </td>
   <td style="text-align:right;"> 71.0 </td>
   <td style="text-align:right;"> 82.0 </td>
   <td style="text-align:right;"> 92.0 </td>
   <td style="text-align:right;"> 96.0 </td>
   <td style="text-align:right;"> 98.0 </td>
   <td style="text-align:right;"> 100.0 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> S.F.Ratio </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 173 </td>
   <td style="text-align:right;"> 37.3 </td>
   <td style="text-align:right;"> 14.09 </td>
   <td style="text-align:right;"> 15.67 </td>
   <td style="text-align:right;"> 2.5 </td>
   <td style="text-align:right;"> 8.3 </td>
   <td style="text-align:right;"> 9.9 </td>
   <td style="text-align:right;"> 11.5 </td>
   <td style="text-align:right;"> 13.6 </td>
   <td style="text-align:right;"> 16.5 </td>
   <td style="text-align:right;"> 19.2 </td>
   <td style="text-align:right;"> 21.0 </td>
   <td style="text-align:right;"> 39.8 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> perc.alumni </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 61 </td>
   <td style="text-align:right;"> 64.0 </td>
   <td style="text-align:right;"> 22.74 </td>
   <td style="text-align:right;"> 153.56 </td>
   <td style="text-align:right;"> 0.0 </td>
   <td style="text-align:right;"> 6.0 </td>
   <td style="text-align:right;"> 8.0 </td>
   <td style="text-align:right;"> 13.0 </td>
   <td style="text-align:right;"> 21.0 </td>
   <td style="text-align:right;"> 31.0 </td>
   <td style="text-align:right;"> 40.0 </td>
   <td style="text-align:right;"> 46.0 </td>
   <td style="text-align:right;"> 64.0 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Expend </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 744 </td>
   <td style="text-align:right;"> 53047.0 </td>
   <td style="text-align:right;"> 9660.17 </td>
   <td style="text-align:right;"> 27266865.64 </td>
   <td style="text-align:right;"> 3186.0 </td>
   <td style="text-align:right;"> 4795.8 </td>
   <td style="text-align:right;"> 5558.2 </td>
   <td style="text-align:right;"> 6751.0 </td>
   <td style="text-align:right;"> 8377.0 </td>
   <td style="text-align:right;"> 10830.0 </td>
   <td style="text-align:right;"> 14841.0 </td>
   <td style="text-align:right;"> 17974.8 </td>
   <td style="text-align:right;"> 56233.0 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Grad.Rate </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 81 </td>
   <td style="text-align:right;"> 108.0 </td>
   <td style="text-align:right;"> 65.46 </td>
   <td style="text-align:right;"> 295.07 </td>
   <td style="text-align:right;"> 10.0 </td>
   <td style="text-align:right;"> 37.0 </td>
   <td style="text-align:right;"> 44.6 </td>
   <td style="text-align:right;"> 53.0 </td>
   <td style="text-align:right;"> 65.0 </td>
   <td style="text-align:right;"> 78.0 </td>
   <td style="text-align:right;"> 89.0 </td>
   <td style="text-align:right;"> 94.2 </td>
   <td style="text-align:right;"> 118.0 </td>
  </tr>
</tbody>
</table>
</div>
</ul>

* *Question (c) ii*

\begin{figure}

{\centering \includegraphics{01-overview_files/figure-latex/ex8cii-1} 

}

\caption{Pair plots.}(\#fig:ex8cii)
\end{figure}

* *Question (c) iii*

\begin{figure}

{\centering \includegraphics{01-overview_files/figure-latex/ex8ciii-1} 

}

\caption{Boxplots of the variable Outstate by Private.}(\#fig:ex8ciii)
\end{figure}

* *Question (c) iv*


```r
College <- College %>% mutate(Elite = factor(Top10perc > 50))
```


```r
College %>% select(Elite) %>% summary_df() %>% print_summary_df()
```

<ul><li> **Factor variables** </li>
<ul><li> Elite </li>
<div style="overflow-x:auto;">
<table class="kable_wrapper table table-striped table-hover table-condensed table-responsive" style="margin-left: auto; margin-right: auto;">
<tbody>
  <tr>
   <td> 

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> Elite </th>
   <th style="text-align:right;"> Count </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> FALSE </td>
   <td style="text-align:right;"> 699 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> TRUE </td>
   <td style="text-align:right;"> 78 </td>
  </tr>
</tbody>
</table>

 </td>
  </tr>
</tbody>
</table>
</div></ul>

</ul>

\begin{figure}

{\centering \includegraphics{01-overview_files/figure-latex/ex8civ3-1} 

}

\caption{Boxplots of the variable Outstate vs Elite.}(\#fig:ex8civ3)
\end{figure}

* *Question (c) v*

<center>
\begin{figure}

{\centering \includegraphics{01-overview_files/figure-latex/ex8cv-1} 

}

\caption{Histograms of the variable Apps for different binwidth.}(\#fig:ex8cv)
\end{figure}
</center>

* *Question (c) vi*

As a brief summary, we found that there is a huge correlation between the number of full-time undergraduates and the number of applications received, accepted and students enrolled. The price to be enrolled in a private university is in mean twice as the price for a public one. But the variance of the price for the private colleges is very important. Moreover, the maximum value of the price for public universities is almost equal to the mean of the private ones (except outliers). Finally, the elite universities (the ones with new students from top 10\% of high school class) are usually more expensive than the other ones.

### Exercise 9.

This exercise is about the `Auto` dataset. It contains 392 observations of 9 variables about vehicles. For a description of the variables, please refer to **R** by typing `help(Auto)` after loading the package `ISLR`. 


```r
Auto <- as_tibble(Auto, rownames = NA)
Auto <- Auto %>% select(-name) %>% 
  mutate(cylinders = as.factor(cylinders), year = as.factor(year), origin = as.factor(origin))
```

* *Question (a), (b) and (c)*


```r
Auto %>% summary_df() %>% print_summary_df()
```

<ul><li> **Factor variables** </li>
<ul><li> cylinders </li>
<div style="overflow-x:auto;">
<table class="kable_wrapper table table-striped table-hover table-condensed table-responsive" style="margin-left: auto; margin-right: auto;">
<tbody>
  <tr>
   <td> 

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> cylinders </th>
   <th style="text-align:right;"> Count </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 3 </td>
   <td style="text-align:right;"> 4 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 4 </td>
   <td style="text-align:right;"> 199 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 5 </td>
   <td style="text-align:right;"> 3 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 6 </td>
   <td style="text-align:right;"> 83 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 8 </td>
   <td style="text-align:right;"> 103 </td>
  </tr>
</tbody>
</table>

 </td>
  </tr>
</tbody>
</table>
</div></ul>

<ul><li> year </li>
<div style="overflow-x:auto;">
<table class="kable_wrapper table table-striped table-hover table-condensed table-responsive" style="margin-left: auto; margin-right: auto;">
<tbody>
  <tr>
   <td> 

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> year </th>
   <th style="text-align:right;"> Count </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 70 </td>
   <td style="text-align:right;"> 29 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 71 </td>
   <td style="text-align:right;"> 27 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 72 </td>
   <td style="text-align:right;"> 28 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 73 </td>
   <td style="text-align:right;"> 40 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 74 </td>
   <td style="text-align:right;"> 26 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 75 </td>
   <td style="text-align:right;"> 30 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 76 </td>
   <td style="text-align:right;"> 34 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 77 </td>
   <td style="text-align:right;"> 28 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 78 </td>
   <td style="text-align:right;"> 36 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 79 </td>
   <td style="text-align:right;"> 29 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 80 </td>
   <td style="text-align:right;"> 27 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 81 </td>
   <td style="text-align:right;"> 28 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 82 </td>
   <td style="text-align:right;"> 30 </td>
  </tr>
</tbody>
</table>

 </td>
  </tr>
</tbody>
</table>
</div></ul>

<ul><li> origin </li>
<div style="overflow-x:auto;">
<table class="kable_wrapper table table-striped table-hover table-condensed table-responsive" style="margin-left: auto; margin-right: auto;">
<tbody>
  <tr>
   <td> 

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> origin </th>
   <th style="text-align:right;"> Count </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:right;"> 245 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 2 </td>
   <td style="text-align:right;"> 68 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 3 </td>
   <td style="text-align:right;"> 79 </td>
  </tr>
</tbody>
</table>

 </td>
  </tr>
</tbody>
</table>
</div></ul>

</ul><ul><li> **Numeric variables** </li>
<div style="overflow-x:auto;">
<table class="table table-striped table-hover table-condensed table-responsive" style="margin-left: auto; margin-right: auto;">
 <thead>
  <tr>
   <th style="text-align:left;"> Name </th>
   <th style="text-align:right;"> NA_num </th>
   <th style="text-align:right;"> Unique </th>
   <th style="text-align:right;"> Range </th>
   <th style="text-align:right;"> Mean </th>
   <th style="text-align:right;"> Variance </th>
   <th style="text-align:right;"> Minimum </th>
   <th style="text-align:right;"> Q05 </th>
   <th style="text-align:right;"> Q10 </th>
   <th style="text-align:right;"> Q25 </th>
   <th style="text-align:right;"> Q50 </th>
   <th style="text-align:right;"> Q75 </th>
   <th style="text-align:right;"> Q90 </th>
   <th style="text-align:right;"> Q95 </th>
   <th style="text-align:right;"> Maximum </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> mpg </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 127 </td>
   <td style="text-align:right;"> 37.6 </td>
   <td style="text-align:right;"> 23.45 </td>
   <td style="text-align:right;"> 60.92 </td>
   <td style="text-align:right;"> 9 </td>
   <td style="text-align:right;"> 13.000 </td>
   <td style="text-align:right;"> 14 </td>
   <td style="text-align:right;"> 17.000 </td>
   <td style="text-align:right;"> 22.75 </td>
   <td style="text-align:right;"> 29.000 </td>
   <td style="text-align:right;"> 34.19 </td>
   <td style="text-align:right;"> 37.000 </td>
   <td style="text-align:right;"> 46.6 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> displacement </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 81 </td>
   <td style="text-align:right;"> 387.0 </td>
   <td style="text-align:right;"> 194.41 </td>
   <td style="text-align:right;"> 10950.37 </td>
   <td style="text-align:right;"> 68 </td>
   <td style="text-align:right;"> 85.000 </td>
   <td style="text-align:right;"> 90 </td>
   <td style="text-align:right;"> 105.000 </td>
   <td style="text-align:right;"> 151.00 </td>
   <td style="text-align:right;"> 275.750 </td>
   <td style="text-align:right;"> 350.00 </td>
   <td style="text-align:right;"> 400.000 </td>
   <td style="text-align:right;"> 455.0 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> horsepower </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 93 </td>
   <td style="text-align:right;"> 184.0 </td>
   <td style="text-align:right;"> 104.47 </td>
   <td style="text-align:right;"> 1481.57 </td>
   <td style="text-align:right;"> 46 </td>
   <td style="text-align:right;"> 60.550 </td>
   <td style="text-align:right;"> 67 </td>
   <td style="text-align:right;"> 75.000 </td>
   <td style="text-align:right;"> 93.50 </td>
   <td style="text-align:right;"> 126.000 </td>
   <td style="text-align:right;"> 157.70 </td>
   <td style="text-align:right;"> 180.000 </td>
   <td style="text-align:right;"> 230.0 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> weight </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 346 </td>
   <td style="text-align:right;"> 3527.0 </td>
   <td style="text-align:right;"> 2977.58 </td>
   <td style="text-align:right;"> 721484.71 </td>
   <td style="text-align:right;"> 1613 </td>
   <td style="text-align:right;"> 1931.600 </td>
   <td style="text-align:right;"> 1990 </td>
   <td style="text-align:right;"> 2225.250 </td>
   <td style="text-align:right;"> 2803.50 </td>
   <td style="text-align:right;"> 3614.750 </td>
   <td style="text-align:right;"> 4277.60 </td>
   <td style="text-align:right;"> 4464.000 </td>
   <td style="text-align:right;"> 5140.0 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> acceleration </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 95 </td>
   <td style="text-align:right;"> 16.8 </td>
   <td style="text-align:right;"> 15.54 </td>
   <td style="text-align:right;"> 7.61 </td>
   <td style="text-align:right;"> 8 </td>
   <td style="text-align:right;"> 11.255 </td>
   <td style="text-align:right;"> 12 </td>
   <td style="text-align:right;"> 13.775 </td>
   <td style="text-align:right;"> 15.50 </td>
   <td style="text-align:right;"> 17.025 </td>
   <td style="text-align:right;"> 19.00 </td>
   <td style="text-align:right;"> 20.235 </td>
   <td style="text-align:right;"> 24.8 </td>
  </tr>
</tbody>
</table>
</div>
</ul>

* *Question (d)*

```r
Auto %>% slice(-c(10:85)) %>% summary_df() %>% print_summary_df()
```

<ul><li> **Factor variables** </li>
<ul><li> cylinders </li>
<div style="overflow-x:auto;">
<table class="kable_wrapper table table-striped table-hover table-condensed table-responsive" style="margin-left: auto; margin-right: auto;">
<tbody>
  <tr>
   <td> 

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> cylinders </th>
   <th style="text-align:right;"> Count </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 3 </td>
   <td style="text-align:right;"> 3 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 4 </td>
   <td style="text-align:right;"> 166 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 5 </td>
   <td style="text-align:right;"> 3 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 6 </td>
   <td style="text-align:right;"> 71 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 8 </td>
   <td style="text-align:right;"> 73 </td>
  </tr>
</tbody>
</table>

 </td>
  </tr>
</tbody>
</table>
</div></ul>

<ul><li> year </li>
<div style="overflow-x:auto;">
<table class="kable_wrapper table table-striped table-hover table-condensed table-responsive" style="margin-left: auto; margin-right: auto;">
<tbody>
  <tr>
   <td> 

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> year </th>
   <th style="text-align:right;"> Count </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 70 </td>
   <td style="text-align:right;"> 9 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 71 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 72 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 73 </td>
   <td style="text-align:right;"> 39 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 74 </td>
   <td style="text-align:right;"> 26 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 75 </td>
   <td style="text-align:right;"> 30 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 76 </td>
   <td style="text-align:right;"> 34 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 77 </td>
   <td style="text-align:right;"> 28 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 78 </td>
   <td style="text-align:right;"> 36 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 79 </td>
   <td style="text-align:right;"> 29 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 80 </td>
   <td style="text-align:right;"> 27 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 81 </td>
   <td style="text-align:right;"> 28 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 82 </td>
   <td style="text-align:right;"> 30 </td>
  </tr>
</tbody>
</table>

 </td>
  </tr>
</tbody>
</table>
</div></ul>

<ul><li> origin </li>
<div style="overflow-x:auto;">
<table class="kable_wrapper table table-striped table-hover table-condensed table-responsive" style="margin-left: auto; margin-right: auto;">
<tbody>
  <tr>
   <td> 

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> origin </th>
   <th style="text-align:right;"> Count </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:right;"> 194 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 2 </td>
   <td style="text-align:right;"> 54 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 3 </td>
   <td style="text-align:right;"> 68 </td>
  </tr>
</tbody>
</table>

 </td>
  </tr>
</tbody>
</table>
</div></ul>

</ul><ul><li> **Numeric variables** </li>
<div style="overflow-x:auto;">
<table class="table table-striped table-hover table-condensed table-responsive" style="margin-left: auto; margin-right: auto;">
 <thead>
  <tr>
   <th style="text-align:left;"> Name </th>
   <th style="text-align:right;"> NA_num </th>
   <th style="text-align:right;"> Unique </th>
   <th style="text-align:right;"> Range </th>
   <th style="text-align:right;"> Mean </th>
   <th style="text-align:right;"> Variance </th>
   <th style="text-align:right;"> Minimum </th>
   <th style="text-align:right;"> Q05 </th>
   <th style="text-align:right;"> Q10 </th>
   <th style="text-align:right;"> Q25 </th>
   <th style="text-align:right;"> Q50 </th>
   <th style="text-align:right;"> Q75 </th>
   <th style="text-align:right;"> Q90 </th>
   <th style="text-align:right;"> Q95 </th>
   <th style="text-align:right;"> Maximum </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> mpg </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 125 </td>
   <td style="text-align:right;"> 35.6 </td>
   <td style="text-align:right;"> 24.40 </td>
   <td style="text-align:right;"> 61.89 </td>
   <td style="text-align:right;"> 11.0 </td>
   <td style="text-align:right;"> 13.0 </td>
   <td style="text-align:right;"> 15.0 </td>
   <td style="text-align:right;"> 18.00 </td>
   <td style="text-align:right;"> 23.95 </td>
   <td style="text-align:right;"> 30.55 </td>
   <td style="text-align:right;"> 35.4 </td>
   <td style="text-align:right;"> 37.775 </td>
   <td style="text-align:right;"> 46.6 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> displacement </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 70 </td>
   <td style="text-align:right;"> 387.0 </td>
   <td style="text-align:right;"> 187.24 </td>
   <td style="text-align:right;"> 9935.78 </td>
   <td style="text-align:right;"> 68.0 </td>
   <td style="text-align:right;"> 85.0 </td>
   <td style="text-align:right;"> 90.0 </td>
   <td style="text-align:right;"> 100.25 </td>
   <td style="text-align:right;"> 145.50 </td>
   <td style="text-align:right;"> 250.00 </td>
   <td style="text-align:right;"> 350.0 </td>
   <td style="text-align:right;"> 360.000 </td>
   <td style="text-align:right;"> 455.0 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> horsepower </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 84 </td>
   <td style="text-align:right;"> 184.0 </td>
   <td style="text-align:right;"> 100.72 </td>
   <td style="text-align:right;"> 1275.12 </td>
   <td style="text-align:right;"> 46.0 </td>
   <td style="text-align:right;"> 60.0 </td>
   <td style="text-align:right;"> 65.0 </td>
   <td style="text-align:right;"> 75.00 </td>
   <td style="text-align:right;"> 90.00 </td>
   <td style="text-align:right;"> 115.00 </td>
   <td style="text-align:right;"> 150.0 </td>
   <td style="text-align:right;"> 170.000 </td>
   <td style="text-align:right;"> 230.0 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> weight </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 279 </td>
   <td style="text-align:right;"> 3348.0 </td>
   <td style="text-align:right;"> 2935.97 </td>
   <td style="text-align:right;"> 658208.03 </td>
   <td style="text-align:right;"> 1649.0 </td>
   <td style="text-align:right;"> 1934.0 </td>
   <td style="text-align:right;"> 1985.0 </td>
   <td style="text-align:right;"> 2213.75 </td>
   <td style="text-align:right;"> 2792.50 </td>
   <td style="text-align:right;"> 3508.00 </td>
   <td style="text-align:right;"> 4177.5 </td>
   <td style="text-align:right;"> 4391.250 </td>
   <td style="text-align:right;"> 4997.0 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> acceleration </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 92 </td>
   <td style="text-align:right;"> 16.3 </td>
   <td style="text-align:right;"> 15.73 </td>
   <td style="text-align:right;"> 7.26 </td>
   <td style="text-align:right;"> 8.5 </td>
   <td style="text-align:right;"> 11.4 </td>
   <td style="text-align:right;"> 12.5 </td>
   <td style="text-align:right;"> 14.00 </td>
   <td style="text-align:right;"> 15.50 </td>
   <td style="text-align:right;"> 17.30 </td>
   <td style="text-align:right;"> 19.0 </td>
   <td style="text-align:right;"> 20.475 </td>
   <td style="text-align:right;"> 24.8 </td>
  </tr>
</tbody>
</table>
</div>
</ul>

* *Question (e)*

\begin{figure}

{\centering \includegraphics{01-overview_files/figure-latex/ex9e-1} 

}

\caption{Pairs plot}(\#fig:ex9e)
\end{figure}

* *Question (f)*

The variables _displacement_, _weight_ and _origin_ have a huge correlation with the variable to predict, _mpg_. So, this ones could particularly useful for the prediction. The relation between these variables does not seem to be linear but instead in $\exp(-x)$. Moreover, the miles per gallon look very different depending on the origin of the car. 

### Exercise 10.

This exercise is about the `Boston` dataset.

* *Question (a)*


```r
Boston <- as_tibble(Boston, rownames = NA)
Boston <- Boston %>% mutate(chas = as.logical(chas), rad = as.factor(rad))
```

It contains 506 observations of 14 variables about housing values in suburbs of Boston. Each of the observation represents a suburb of Boston. For a description of the variables, please refer to **R** by typing `help(Boston)` after loading the package `MASS`. 

* *Question (b)*

\begin{figure}

{\centering \includegraphics{01-overview_files/figure-latex/ex10b-1} 

}

\caption{Pairs plot}(\#fig:ex10b)
\end{figure}

We can see some interesting correlations in this dataset. For exemple, the mean distances to five Boston employement has a correlation of -0.77 with the nitrogen oxides concentration. Or, the lower status of the population are related to the average number of rooms per dwelling (-0.61 for correlation). The variable that are the most related with the crime rate by town is the full-value property-tax rate per \$10,000.

* *Question (c)*

The variable _crim_ seems to be associated with the variables _tax_, _lstat_ and _nox_ because they have quite a large correlation with the variable of interest (cf. previous question).

* *Question (d)*

\begin{figure}

{\centering \includegraphics{01-overview_files/figure-latex/ex10d-1} 

}

\caption{Boxplots of some variables.}(\#fig:ex10d)
\end{figure}

Half of the suburbs have less than 10% of crime rates, but for three of them, this rate is greater than 70%. The range for this variable is very important. The tax rates do not seem to have outliers but the range is also very important. Indeed, the tax can go from under \$200,000 to above \$700,000. Finally, there are some suburbs in Boston that have a very low pupil-teacher ratio compare to the others. However, the range is not very wide.

* *Question (e)*

There are 35 suburbs that bound the Charles river.

* *Question (f)*

The median pupil-teacher ratio among the towns of Boston is 19.05%.

* *Question (g)*


```r
Boston[which(Boston$medv == min(Boston$medv)),] %>% print_df() 
```

<div style="overflow-x:auto;">
<table class="table table-striped table-hover table-condensed table-responsive" style="margin-left: auto; margin-right: auto;">
 <thead>
  <tr>
   <th style="text-align:right;"> crim </th>
   <th style="text-align:right;"> zn </th>
   <th style="text-align:right;"> indus </th>
   <th style="text-align:left;"> chas </th>
   <th style="text-align:right;"> nox </th>
   <th style="text-align:right;"> rm </th>
   <th style="text-align:right;"> age </th>
   <th style="text-align:right;"> dis </th>
   <th style="text-align:left;"> rad </th>
   <th style="text-align:right;"> tax </th>
   <th style="text-align:right;"> ptratio </th>
   <th style="text-align:right;"> black </th>
   <th style="text-align:right;"> lstat </th>
   <th style="text-align:right;"> medv </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:right;"> 38.3518 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 18.1 </td>
   <td style="text-align:left;"> FALSE </td>
   <td style="text-align:right;"> 0.693 </td>
   <td style="text-align:right;"> 5.453 </td>
   <td style="text-align:right;"> 100 </td>
   <td style="text-align:right;"> 1.4896 </td>
   <td style="text-align:left;"> 24 </td>
   <td style="text-align:right;"> 666 </td>
   <td style="text-align:right;"> 20.2 </td>
   <td style="text-align:right;"> 396.90 </td>
   <td style="text-align:right;"> 30.59 </td>
   <td style="text-align:right;"> 5 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 67.9208 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 18.1 </td>
   <td style="text-align:left;"> FALSE </td>
   <td style="text-align:right;"> 0.693 </td>
   <td style="text-align:right;"> 5.683 </td>
   <td style="text-align:right;"> 100 </td>
   <td style="text-align:right;"> 1.4254 </td>
   <td style="text-align:left;"> 24 </td>
   <td style="text-align:right;"> 666 </td>
   <td style="text-align:right;"> 20.2 </td>
   <td style="text-align:right;"> 384.97 </td>
   <td style="text-align:right;"> 22.98 </td>
   <td style="text-align:right;"> 5 </td>
  </tr>
</tbody>
</table>
</div></ul>

Two suburbs share the lowest median value of owner-occupied homes in \$1000s. They have pretty the same values for the other predictors (except maybe for the crime rate). 

* *Question (h)*

There are 64 suburbs with an average of number of rooms per dwelling larger than 7 and  13 with more than 8.


```r
Boston[which(Boston$rm > 8),] %>% print_df()
```

<div style="overflow-x:auto;">
<table class="table table-striped table-hover table-condensed table-responsive" style="margin-left: auto; margin-right: auto;">
 <thead>
  <tr>
   <th style="text-align:right;"> crim </th>
   <th style="text-align:right;"> zn </th>
   <th style="text-align:right;"> indus </th>
   <th style="text-align:left;"> chas </th>
   <th style="text-align:right;"> nox </th>
   <th style="text-align:right;"> rm </th>
   <th style="text-align:right;"> age </th>
   <th style="text-align:right;"> dis </th>
   <th style="text-align:left;"> rad </th>
   <th style="text-align:right;"> tax </th>
   <th style="text-align:right;"> ptratio </th>
   <th style="text-align:right;"> black </th>
   <th style="text-align:right;"> lstat </th>
   <th style="text-align:right;"> medv </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:right;"> 0.12083 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 2.89 </td>
   <td style="text-align:left;"> FALSE </td>
   <td style="text-align:right;"> 0.4450 </td>
   <td style="text-align:right;"> 8.069 </td>
   <td style="text-align:right;"> 76.0 </td>
   <td style="text-align:right;"> 3.4952 </td>
   <td style="text-align:left;"> 2 </td>
   <td style="text-align:right;"> 276 </td>
   <td style="text-align:right;"> 18.0 </td>
   <td style="text-align:right;"> 396.90 </td>
   <td style="text-align:right;"> 4.21 </td>
   <td style="text-align:right;"> 38.7 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 1.51902 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 19.58 </td>
   <td style="text-align:left;"> TRUE </td>
   <td style="text-align:right;"> 0.6050 </td>
   <td style="text-align:right;"> 8.375 </td>
   <td style="text-align:right;"> 93.9 </td>
   <td style="text-align:right;"> 2.1620 </td>
   <td style="text-align:left;"> 5 </td>
   <td style="text-align:right;"> 403 </td>
   <td style="text-align:right;"> 14.7 </td>
   <td style="text-align:right;"> 388.45 </td>
   <td style="text-align:right;"> 3.32 </td>
   <td style="text-align:right;"> 50.0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 0.02009 </td>
   <td style="text-align:right;"> 95 </td>
   <td style="text-align:right;"> 2.68 </td>
   <td style="text-align:left;"> FALSE </td>
   <td style="text-align:right;"> 0.4161 </td>
   <td style="text-align:right;"> 8.034 </td>
   <td style="text-align:right;"> 31.9 </td>
   <td style="text-align:right;"> 5.1180 </td>
   <td style="text-align:left;"> 4 </td>
   <td style="text-align:right;"> 224 </td>
   <td style="text-align:right;"> 14.7 </td>
   <td style="text-align:right;"> 390.55 </td>
   <td style="text-align:right;"> 2.88 </td>
   <td style="text-align:right;"> 50.0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 0.31533 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 6.20 </td>
   <td style="text-align:left;"> FALSE </td>
   <td style="text-align:right;"> 0.5040 </td>
   <td style="text-align:right;"> 8.266 </td>
   <td style="text-align:right;"> 78.3 </td>
   <td style="text-align:right;"> 2.8944 </td>
   <td style="text-align:left;"> 8 </td>
   <td style="text-align:right;"> 307 </td>
   <td style="text-align:right;"> 17.4 </td>
   <td style="text-align:right;"> 385.05 </td>
   <td style="text-align:right;"> 4.14 </td>
   <td style="text-align:right;"> 44.8 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 0.52693 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 6.20 </td>
   <td style="text-align:left;"> FALSE </td>
   <td style="text-align:right;"> 0.5040 </td>
   <td style="text-align:right;"> 8.725 </td>
   <td style="text-align:right;"> 83.0 </td>
   <td style="text-align:right;"> 2.8944 </td>
   <td style="text-align:left;"> 8 </td>
   <td style="text-align:right;"> 307 </td>
   <td style="text-align:right;"> 17.4 </td>
   <td style="text-align:right;"> 382.00 </td>
   <td style="text-align:right;"> 4.63 </td>
   <td style="text-align:right;"> 50.0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 0.38214 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 6.20 </td>
   <td style="text-align:left;"> FALSE </td>
   <td style="text-align:right;"> 0.5040 </td>
   <td style="text-align:right;"> 8.040 </td>
   <td style="text-align:right;"> 86.5 </td>
   <td style="text-align:right;"> 3.2157 </td>
   <td style="text-align:left;"> 8 </td>
   <td style="text-align:right;"> 307 </td>
   <td style="text-align:right;"> 17.4 </td>
   <td style="text-align:right;"> 387.38 </td>
   <td style="text-align:right;"> 3.13 </td>
   <td style="text-align:right;"> 37.6 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 0.57529 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 6.20 </td>
   <td style="text-align:left;"> FALSE </td>
   <td style="text-align:right;"> 0.5070 </td>
   <td style="text-align:right;"> 8.337 </td>
   <td style="text-align:right;"> 73.3 </td>
   <td style="text-align:right;"> 3.8384 </td>
   <td style="text-align:left;"> 8 </td>
   <td style="text-align:right;"> 307 </td>
   <td style="text-align:right;"> 17.4 </td>
   <td style="text-align:right;"> 385.91 </td>
   <td style="text-align:right;"> 2.47 </td>
   <td style="text-align:right;"> 41.7 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 0.33147 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 6.20 </td>
   <td style="text-align:left;"> FALSE </td>
   <td style="text-align:right;"> 0.5070 </td>
   <td style="text-align:right;"> 8.247 </td>
   <td style="text-align:right;"> 70.4 </td>
   <td style="text-align:right;"> 3.6519 </td>
   <td style="text-align:left;"> 8 </td>
   <td style="text-align:right;"> 307 </td>
   <td style="text-align:right;"> 17.4 </td>
   <td style="text-align:right;"> 378.95 </td>
   <td style="text-align:right;"> 3.95 </td>
   <td style="text-align:right;"> 48.3 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 0.36894 </td>
   <td style="text-align:right;"> 22 </td>
   <td style="text-align:right;"> 5.86 </td>
   <td style="text-align:left;"> FALSE </td>
   <td style="text-align:right;"> 0.4310 </td>
   <td style="text-align:right;"> 8.259 </td>
   <td style="text-align:right;"> 8.4 </td>
   <td style="text-align:right;"> 8.9067 </td>
   <td style="text-align:left;"> 7 </td>
   <td style="text-align:right;"> 330 </td>
   <td style="text-align:right;"> 19.1 </td>
   <td style="text-align:right;"> 396.90 </td>
   <td style="text-align:right;"> 3.54 </td>
   <td style="text-align:right;"> 42.8 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 0.61154 </td>
   <td style="text-align:right;"> 20 </td>
   <td style="text-align:right;"> 3.97 </td>
   <td style="text-align:left;"> FALSE </td>
   <td style="text-align:right;"> 0.6470 </td>
   <td style="text-align:right;"> 8.704 </td>
   <td style="text-align:right;"> 86.9 </td>
   <td style="text-align:right;"> 1.8010 </td>
   <td style="text-align:left;"> 5 </td>
   <td style="text-align:right;"> 264 </td>
   <td style="text-align:right;"> 13.0 </td>
   <td style="text-align:right;"> 389.70 </td>
   <td style="text-align:right;"> 5.12 </td>
   <td style="text-align:right;"> 50.0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 0.52014 </td>
   <td style="text-align:right;"> 20 </td>
   <td style="text-align:right;"> 3.97 </td>
   <td style="text-align:left;"> FALSE </td>
   <td style="text-align:right;"> 0.6470 </td>
   <td style="text-align:right;"> 8.398 </td>
   <td style="text-align:right;"> 91.5 </td>
   <td style="text-align:right;"> 2.2885 </td>
   <td style="text-align:left;"> 5 </td>
   <td style="text-align:right;"> 264 </td>
   <td style="text-align:right;"> 13.0 </td>
   <td style="text-align:right;"> 386.86 </td>
   <td style="text-align:right;"> 5.91 </td>
   <td style="text-align:right;"> 48.8 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 0.57834 </td>
   <td style="text-align:right;"> 20 </td>
   <td style="text-align:right;"> 3.97 </td>
   <td style="text-align:left;"> FALSE </td>
   <td style="text-align:right;"> 0.5750 </td>
   <td style="text-align:right;"> 8.297 </td>
   <td style="text-align:right;"> 67.0 </td>
   <td style="text-align:right;"> 2.4216 </td>
   <td style="text-align:left;"> 5 </td>
   <td style="text-align:right;"> 264 </td>
   <td style="text-align:right;"> 13.0 </td>
   <td style="text-align:right;"> 384.54 </td>
   <td style="text-align:right;"> 7.44 </td>
   <td style="text-align:right;"> 50.0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 3.47428 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 18.10 </td>
   <td style="text-align:left;"> TRUE </td>
   <td style="text-align:right;"> 0.7180 </td>
   <td style="text-align:right;"> 8.780 </td>
   <td style="text-align:right;"> 82.9 </td>
   <td style="text-align:right;"> 1.9047 </td>
   <td style="text-align:left;"> 24 </td>
   <td style="text-align:right;"> 666 </td>
   <td style="text-align:right;"> 20.2 </td>
   <td style="text-align:right;"> 354.55 </td>
   <td style="text-align:right;"> 5.29 </td>
   <td style="text-align:right;"> 21.9 </td>
  </tr>
</tbody>
</table>
</div></ul>

