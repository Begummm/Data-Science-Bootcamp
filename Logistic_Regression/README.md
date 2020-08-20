<link rel="stylesheet" type="text/css" href="data.css" />
<h1> Logistic Regression Project </h1>
In this project I worked with a fake advertising data set, indicating whether or not a particular internet user clicked on an Advertisement on a company website. I tried to create a model that will predict whether or not they will click on an ad based off the features of that user.
<img src="Capture.png"> </img>

<h1> Logistic Regression </h1>

Logistic regression uses an equation as the representation, very much like linear regression.

Input values <em>X</em> are combined linearly using weights or coefficient values <math>&#946;<sub>0</sub> </math> and <math>&#946;<sub>1</sub> </math> to predict an output value <em>Y</em>. A key difference from linear regression is that the output value being modeled is a binary values (0 or 1) rather than a numeric value.

Below is an example logistic regression equation:
<p><span class="tab">
<math>
		Y  = [e<sup>( &#946;<sub>0</sub> + &#946;<sub>1</sub> X)</sup> ]/[1+e<sup>( &#946;<sub>0</sub> + &#946;<sub>1</sub> X)</sup>]  
</math>
</span>
</p>
Where <em>Y</em> is the predicted output, <math>&#946;<sub>0</sub> </math> is the bias or intercept term and <math>&#946;<sub>1</sub> </math> is the coefficient for the single input value <em>X</em>.

There are several analogies between linear regression and logistic regression. Just as ordinary least square regression is the method used to estimate coefficients for the best fit line in linear regression, logistic regression uses <strong>maximum likelihood estimation (MLE)</strong> to obtain the model coefficients that relate predictors to the target. After this initial function is estimated, the process is repeated until LL (Log Likelihood) does not change significantly. 


<p>The decision for the value of the threshold value is majorly affected by the values of precision and recall. Ideally, we want both precision and recall to be 1, but this seldom is the case. In case of a Precision-Recall tradeoff we use the following arguments to decide upon the thresold:-</p>

1. Low Precision/High Recall: In applications where we want to reduce the number of false negatives without necessarily reducing the number false positives, we choose a decision value which has a low value of Precision or high value of Recall. For example, in a cancer diagnosis application, we do not want any affected patient to be classified as not affected without giving much heed to if the patient is being wrongfully diagnosed with cancer. This is because, the absence of cancer can be detected by further medical diseases but the presence of the disease cannot be detected in an already rejected candidate.

2. High Precision/Low Recall: In applications where we want to reduce the number of false positives without necessarily reducing the number false negatives, we choose a decision value which has a high value of Precision or low value of Recall. For example, if we are classifying customers whether they will react positively or negatively to a personalised advertisement, we want to be absolutely sure that the customer will react positively to the advertisemnt because otherwise, a negative reaction can cause a loss potential sales from the customer.

Based on the number of categories, Logistic regression can be classified as:

<strong>binomial: </strong> target variable can have only 2 possible types: “0” or “1” which may represent “win” vs “loss”, “pass” vs “fail”, “dead” vs “alive”, etc.

<strong>multinomial:</strong> target variable can have 3 or more possible types which are not ordered(i.e. types have no quantitative significance) like “disease A” vs “disease B” vs “disease C”.

<strong>ordinal:</strong>it deals with target variables with ordered categories. For example, a test score can be categorized as:“very poor”, “poor”, “good”, “very good”. Here, each category can be given a score like 0, 1, 2, 3.


<em>* Source: James, Gareth, et al. An introduction to statistical learning.(Vol. 112, p. 130). New York: springer, 2013. </em>