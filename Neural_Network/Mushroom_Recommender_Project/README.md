<img src="/images/unice_logo.png"> </img>

# Neural Networks and Learning

## Mushroom Recommender Project Report

### Begüm SARIGUZEL

Instructor

### Enrico FORMENTI

3 December 2019

### **CONTENTS**

About the project 3

Data preparation 3

Model selection 9

Linear support vector classifier 9

Decision tree classifier 11

Multi layer perceptron classifier 12

### Conclusion 14

About the project

This project aims to study about machine learning models considering real observations. It consists of data preprocessing, feature elimination, model selection and interpretation of results. Data contains certain type of mushrooms with their physical descriptions. The main goal is to find or build a model which is able to identify the edible mushrooms from the poisonous ones regarding their features.

### **Data preparation**

The data includes 8124 observations which means 8124 mushrooms and 1 target class and 22 feature classes (Figure 1).

<img src="/images/dataframe.png"> </img>

<h6 style="text-align:center;"><em>Figure 1: Raw data</em></h6> 

Type of the data is categorical so it contains only characters. Before using it as input we should convert them into binary form.

Firstly, there are some verifications about content of the data to be sure that we have an executable data. I started by looking for any missing values such as zeros or NaNs (Figure2).

<img src="/images/Missingvalue.png"> </img>
<h6 style="text-align:center;"><em>Figure 2: Checking missing values</em></h6> 


Then, I looked at the target class if the distribution of the labelled data is balanced. Figure 3 shows that the data can be considered as balanced and there are approximately same amount of edible and poisonous mushrooms.


<img src="/images/balance.png"> </img>
<h6 style="text-align:center;"><em>Figure 3: Distribution in target class</em></h6> 


I preferred to transfer all object type values into categorical type which can improve the execution time.


<img src="/images/objettype.png"> </img>
<img src="/images/allcategorydtype.png"> </img>
<h6 style="text-align:center;"><em>Figure 4: Dtype conversion from object to category</em></h6> 


The next step is the label encoding which allowed to convert each value in a column to a number. As numerical labels are always between 0 and n-1 categories. For example, &#39;cap-shape&#39; feature has 6 different types (bell, conical, convex, flat, knobbed, sunken). So, after label encoding it has values between 0 and 5 and each number represents a type of cap shape (Figure 5).

<img src="/images/label_encoder.png"> </img>
<h6 style="text-align:center;"><em>Figure 5: Data after label encoding</em></h6> 


Furthermore, a deeper analysis of data revealed that there exist 3 features which do not give any information about the data (Figure 6). Therefore, removing these features from the data changes nothing.

<img src="/images/Gillattachement_plot.png"> </img>
<img src="/images/sporeprintcolor_plot.png"> </img>
<img src="/images/ringnumber_color.png"> </img>
<h6 style="text-align:center;"><em>Figure 6: Gill attachment, veil color and ring number features</em></h6> 


The correlation between features is also important. Since the data is categorical, I computed uncertainty coeffient which gives associations between categorical features. It is based on the conditional entropy between two discrete random variables x and y and it calculates the conditional entropy as shown in Figure 7a and then we can calculate the degree of association between these two variables. Similarly to the correlation the output is in the range of [0,1], where 0 means no association and 1 is full association (Figure 7b).

<img src="/images/ThailsU.png"> </img>
<img src="/images/correlation2.png"> </img>
<h6 style="text-align:center;"><em>Figure 7: (a) Conditional entropy on top, (b) uncertainty coefficient at bottom</em></h6>

According to the uncertainty coefficient result (Figure 8), &#39;veil-type&#39; feature has 0 association with other features. It means that this feature can not contribute to our calculations.

<img src="/images/coefficints.png"> </img>
<h6 style="text-align:center;"><em>Figure 8: Uncertainty coefficients</em></h6>


For the next step, I applied one hot encoding to data (Figure 9). The basic strategy is to convert each category value into a new column and assign a 1 or 0 (True/False) value to the column. The reason of why the label encoding is not sufficient because label encoding assumes higher the categorical value, better the category. So, one hot encoder performs &quot;binarization&quot; of the category.

<img src="/images/getdummies.png"> </img>
<h6 style="text-align:center;"><em>Figure 9: One hot encoded data</em></h6>


Lastly, I remarked something interesting in the data which is that it seems that the odor feature has important information. Figure 10 shows that almost each case the mushroom is either poisonous or edible unless for the odorless mushrooms. It means that if I eliminate all the data except the odorless mushrooms calculations could be more simple.

<img src="/images/odordetail.png"> </img>
<h6 style="text-align:center;"><em>Figure 10: Odor feature</em></h6>


I checked the association this time between the features of odorless mushrooms (Figure 11). It revealed that the there is a relatively high association (0.68) between target class and the &#39;spore-color&#39; feature.

<img src="/images/odorindetail.png"> </img>
<h6 style="text-align:center;"><em>Figure 11: Associations between target class and the other features for odorless mushrooms</em></h6>


Then I looked at spore color feature to better understand its characteristics. In Figure 12, it is clearly seen that again we can classify the mushrooms considering only spore colors unless for white and odorless mushrooms.

<img src="/images/spore_print_color.png"> </img>
<h6 style="text-align:center;"><em>Figure 12: Spore color feature of odorless mushrooms</em></h6>


Apart from scented and colorful mushrooms, the other mushrooms make only 8% of all the data. I will keep this in my mind and I will use this small data for each classifier and verify if it gives better result or not.

### **Model selection**

Since our aim is predicting a category and the data is labeled, I chose support vector classifier as first model. Then decision tree and multi layer perceptron classifiers are chosen to classify the data.

**Linear support vector classifier**

I started by splitting the data as training and testing data. Testing data is 30% all of the data. The accuracy score obtained after training the model is 1 (Figure 13).

<img src="/images/SVC/alldata.png"> </img>
<h6 style="text-align:center;"><em>Figure 13: Accuracy score for SVC using all data</em></h6>


Having 1 accuracy score seems suspicious so I decided to use cross validation. I applied K-fold cross validation for K=10. The result is shown in Figure 14 with learning curves. Learning curves shows the training and test scores at each step while the k-fold cross validation divides the data into train and validation sets for given k value. We can see clearly that the training score is around the maximum and the validation score could be increased with more training samples.

<img src="/images/SVC/learningcurve_alldata_crossvalidation.png"> </img>
<h6 style="text-align:center;"><em>Figure 14: Learning curves for SVC using all data</em></h6>

Then I used small data for the same model which represents 8% of the data. Again it gives a very good accuracy score and it is able to predict all the classes correctly (Figure 15).

<img src="/images/SVC/predicition_evaluation.png"> </img>
<h6 style="text-align:center;"><em>Figure 15: Accuracy score for SVC using small data</em></h6>


When learning curves are found for the small data, we see that they converge both to 1 even with very smaller training data (Figure 16). But the problem is that since this small data is not representative of all the population of mushroom, the model could vary very easily with different type test data. What I mean is that the model could not be able to generalize accurately on the data that hasn&#39;t seen before.

<img src="/images/SVC/learningcurve_smalldata.png"> </img>
<h6 style="text-align:center;"><em>Figure 16: Learning curves for SVC using small data</em></h6>


The execution time for all data is 17.8 ms while it is 2.22 ms for small data.

**Decision tree classifier**

Second model that I used is decision tree classifier. I used again all data and small data to compare the performance of the model.

<img src="/images/Decision_tree/dtree_render.png"> </img>
<img src="/images/Decision_tree/desicion_tree.png"> </img>
<h6 style="text-align:center;"><em>Figure 17: Decision trees for all data (top) and for small data (bottom)</em></h6>


Since for small data I already did an elimination the model could predict with 5 depths (Figure 17). It results in faster execution (49 ms faster) for small data. Also with all data randomly splitting leads to a misclassifying which can be seen in confusion matrix (Figure 18).

<img src="/images/Decision_tree/alldata_confusionmatrix.png"> </img>
<h6 style="text-align:center;"><em>Figure 18: Confusion matrix for Decision Tree using all data</em></h6>


**Multi layer perceptron classifier**

The last model is multi layer perceptron classifier. Parameters chosen for this model are shown in Figure 19. First I started with a simple model with 1 neuron in the first layer and 2 neurons in the second layer and activation function is rectified linear unit function.

<img src="/images/MLP/MLP_alldata.png"> </img>
<h6 style="text-align:center;"><em>Figure 19: MLP parameters</em></h6>


The accuracy score of this model is very weak (Figure 20). It can be improved so for this purpose I applied grid search to determine the best parameters for the model. It is found that having 2 layers with 5 neurons would improve the model. Indeed, when the model is used with recommended parameters gives 1 accuracy score (Figure 22).

<img src="/images/MLP/accuracy_alldata.png"> </img>
<h6 style="text-align:center;"><em>Figure 20: Accuracy score for MLP in Figure 19 using all data</em></h6>

<img src="/images/MLP/gridsearchparameters.png"> </img>
<img src="/images/MLP/gridsearch.png"> </img>
<h6 style="text-align:center;"><em>Figure 21: Grid search for MLP</em></h6>


<img src="/images/MLP/aftergridsearch.png"> </img>
<img src="/images/MLP/accuracy_secondtry.png"> </img>
<h6 style="text-align:center;"><em>Figure 22: MLP with best parameters</em></h6>



For small data the model in Figure 19 is applied and it gives the accuracy in Figure 22.

<img src="/images/MLP/accuracy_smalldata.png"> </img>
<h6 style="text-align:center;"><em>Figure 22: Accuracy score for MLP in Figure 19 using small data</em></h6>


The result could be improved again by using grid search but I did not use it this time due to very long execution time. And there is a remarkable difference between the execution times of small data and all data which is 8.7 seconds.

### **Conclusion**

In this project 3 models are used in order to classify edible and poisonous mushrooms. Each model gives quite good results (always around 1 accuracy score). For MLP it is possible to improve the model by choosing the best parameters.

In terms of time, SVC give better performance than the two other models.

Feature extraction and having very small data helps decision tree classifier to learn faster and converge to 1 in less depths than the other decision tree classifier for all data.

Having 1 accuracy score so easily, especially for SVC, is not easy to interpret. The first thing that the training set is easy to learn so the model does not do any error. Or/and the test data is not various enough so predicting the test data is not challenging. Maybe with more observations more realistic results could be obtained. Because the models could have difficulties to generalize for the data that has not seen before.


