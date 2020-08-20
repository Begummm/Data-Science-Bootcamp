<h2> K-nearest Neighbours </h2>

The KNN algorithm assumes that similar things exist in close proximity. In other words, similar things are near to each other.
The KNN algorithm hinges on this assumption being true enough for the algorithm to be useful. KNN captures the idea of similarity (sometimes called distance, proximity, or closeness) by calculating the distance between points on a graph.

<h3> The KNN Algorithm </h3>

<ol>
<li>Load the data
</li>
<li> Initialize K to your chosen number of neighbours</li>
<li> For each example in the data</li>
<ol>
<li> Calculate the distance between the query example and the current example from the data
<li>Add the distance and the index of the example to an ordered collection
</li>
</ol>
<li>Sort the ordered collection of distances and indices from smallest to largest (in ascending order) by the distances
</li> 
<li>Pick the first K entries from the sorted collection
</li>
<li>Get the labels of the selected K entries
</li>
<li>If regression, return the mean of the K labels
</li>
<li>If classification, return the mode of the K labels
</li>
</ol>

<h3> Choosing the right value for K </h3>

To select the K that’s right for your data, we run the KNN algorithm several times with different values of K and choose the K that reduces the number of errors we encounter while maintaining the algorithm’s ability to accurately make predictions when it’s given data it hasn’t seen before.
Here are some things to keep in mind:

<ol>
<li>As we decrease the value of K to 1, our predictions become less stable. Just think for a minute, imagine K=1 and we have a query point surrounded by several reds and one green (I’m thinking about the top left corner of the colored plot above), but the green is the single nearest neighbor. Reasonably, we would think the query point is most likely red, but because K=1, KNN incorrectly predicts that the query point is green.
</li>
<li>Inversely, as we increase the value of K, our predictions become more stable due to majority voting / averaging, and thus, more likely to make more accurate predictions (up to a certain point). Eventually, we begin to witness an increasing number of errors. It is at this point we know we have pushed the value of K too far.
</li>
<li>In cases where we are taking a majority vote (e.g. picking the mode in a classification problem) among labels, we usually make K an odd number to have a tiebreaker.
</li>
</ol>

<h4> Advantages </h4>
<ol>
<li>The algorithm is simple and easy to implement.
</li>
<li>There’s no need to build a model, tune several parameters, or make additional assumptions.
</li>
<li>The algorithm is versatile. It can be used for classification, regression, and search.
</li>
</ol>


<h4> Disadvantages </h4>
<ul>
<li>The algorithm gets significantly slower as the number of examples and/or predictors/independent variables increase.
</li>
</ul>

<em>*Source: <a href="https://towardsdatascience.com/machine-learning-basics-with-the-k-nearest-neighbors-algorithm-6a6e71d01761"> https://towardsdatascience.com/machine-learning-basics-with-the-k-nearest-neighbors-algorithm-6a6e71d01761</a></em>