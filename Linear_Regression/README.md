<link rel="stylesheet" type="text/css" href="data.css" />
<h1> Linear Regression Project </h1>
This project is for an Ecommerce company based in New York City that sells clothing online but they also have in-store style and clothing advise sessions. Customers come in to the store, have sessions/meetings with a personal stylist, then they can go home and order either on a mobile app or website for the clothes they want.
The company is trying to decide whether to focus their efforts on their mobile app experience or their website.
<img src="Capture1.PNG"> </img>
<h1> Simple Linear Regression </h1>

<em> Simple linear regression </em> lives up to its name: it is a very straightforward approach for predicting a quantitative response<em> Y </em> on the basis of a single predictor variable <em> X</em>. It assumes that there is approximately a linear relationship between <em> X </em> and <em> Y </em>. Mathematically, we can write this linear relationship as 
<p><span class="tab">
<math>
		Y  ≈ &#946;<sub>0</sub> + &#946;<sub>1</sub> X  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;  (1)
</math>
</span>
</p>

In equation (1), <math>&#946;<sub>0</sub> </math> and <math>&#946;<sub>1</sub> </math> are two unknown constants that represents the intercept and slope terms in the linear model. Together, <math>&#946;<sub>0</sub> </math> and <math>&#946;<sub>1</sub> </math> are known as the model <em> coefficients </em> or <em> parameters </em>. So before we can use (1) to make predictions, we must use data to estimate the coefficients. Let

<p><span class="tab2">
<math>
	(x<sub>1</sub>, y<sub>1</sub>), (x<sub>2</sub>, y<sub>2</sub>),..., (x<sub>n</sub>, y<sub>n</sub>)
</math>
</span>
</p>

represent n observation pairs, each of which consists of a measurement of X and a measurement of Y. Our goal is to obtain coefficient estimates <math>&#946;'<sub>0</sub> </math>  and <math>&#946;'<sub>1</sub></math> such that the linear model (1) fits the available data well-that is, so that <math>y<sub>i</sub> ≈ <math>&#946;'<sub>0</sub> </math> +  <math>&#946;'<sub>1</sub> x<sub>i</sub></math> 	</math> for <em>1,...,n </em>.

<h3> Regression Evaluation Metrics</h3>    
Here are three common evaluation metrics for regression problems:
<p><strong>Mean Absolute Error </strong> (MAE) is the mean of the absolute value of the errors:</p>

<p><span class="tab2">
<math>
1/n &sum;<sub>i=1</sub><sup>n</sup>  |y<sub>i</sub> - y'<sub>i</sub>|
</math>
</span>
</p>

<p><strong>Mean Squared Error </strong> (MSE) is the mean of the squared errors:</p>

<p><span class="tab2">
<math>
1/n &sum;<sub>i=1</sub><sup>n</sup>  (y<sub>i</sub> - y'<sub>i</sub>)<sup>2</sup>
</math>
</span>
</p>

<p><strong>Root Mean Squared Error </strong> (RMSE) is the square root of the mean of the squared errors:</p>

<p><span class="tab2">
<math>
&#8730;1/n &sum;<sub>i=1</sub><sup>n</sup>  (y<sub>i</sub> - y'<sub>i</sub>)<sup>2</sup>
</math>
</span>
</p>

Comparing these metrics:
<ul>
<li><strong> MAE</strong> is the easiest to understand, because it's the average error.</li>
<li><strong>MSE</strong> is more popular than MAE, because MSE "punishes" larger errors, which tends to be useful in the real world.  </li>
<li><strong> RMSE</strong> is even more popular than MSE, because RMSE is interpretable in the "y" units.</li>
</ul>
All of these are <strong>loss functions</strong>, because we want to minimize them.

<em>* Source: James, Gareth, et al. An introduction to statistical learning.(Vol. 112, p. 61). New York: springer, 2013. </em>
