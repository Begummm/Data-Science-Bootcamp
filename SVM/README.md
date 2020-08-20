<h2>Support Vector Machine </h2>

The objective of the support vector machine algorithm is to find a hyperplane in an N-dimensional space(N — the number of features) that distinctly classifies the data points.
To separate the two classes of data points, there are many possible hyperplanes that could be chosen. Our objective is to find a plane that has the maximum margin, i.e the maximum distance between data points of both classes. Maximizing the margin distance provides some reinforcement so that future data points can be classified with more confidence.

<h3> Hyperplanes and Support Vectors</h3>

<img src="hyperplanes.png"></img>
<h6 style="text-align:center;"><em> Hyperplanes in 2D and 3D feature space
</em></h6>

Hyperplanes are decision boundaries that help classify the data points. Data points falling on either side of the hyperplane can be attributed to different classes. Also, the dimension of the hyperplane depends upon the number of features. If the number of input features is 2, then the hyperplane is just a line. If the number of input features is 3, then the hyperplane becomes a two-dimensional plane. It becomes difficult to imagine when the number of features exceeds 3.

<img src="support_vectors.jpg"></img>
<h6 style="text-align:center;"><em> Support Vectors
</em></h6>
Support vectors are data points that are closer to the hyperplane and influence the position and orientation of the hyperplane. Using these support vectors, we maximize the margin of the classifier. Deleting the support vectors will change the position of the hyperplane. These are the points that help us build our SVM.

<em>*Source: <a href="https://towardsdatascience.com/support-vector-machine-introduction-to-machine-learning-algorithms-934a444fca47">https://towardsdatascience.com/support-vector-machine-introduction-to-machine-learning-algorithms-934a444fca47</a></em>