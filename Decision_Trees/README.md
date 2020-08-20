<h1> Decision Trees </h1>

A tree has many analogies in real life, and turns out that it has influenced a wide area of machine learning, covering both  <strong>classification and regression</strong>. In decision analysis, a decision tree can be used to visually and explicitly represent decisions and decision making. As the name goes, it uses a tree-like model of decisions.

<img src="tree_example.png"> </img>
<h6 style="text-align:center;"><em> Image from wikipedia</em></h6> 
<p>
A decision tree is drawn upside down with its root at the top. In the image on the top, the bold text in black represents a condition/<strong>internal node</strong>, based on which the tree splits into <strong>branches/edges</strong>. The end of the branch that doesn’t split anymore is the decision/<strong>leaf</strong>, in this case, whether the passenger died or survived, represented as red and green text respectively.</p>
<p>Although, a real dataset will have a lot more features and this will just be a branch in a much bigger tree, but you can’t ignore the simplicity of this algorithm. The <strong>feature importance is clear </strong>and relations can be viewed easily. This methodology is more commonly known as <strong>learning decision tree from data</strong> and above tree is called <strong>Classification tree</strong> as the target is to classify passenger as survived or died.<strong>Regression trees</strong> are represented in the same manner, just they predict continuous values like price of a house. In general, Decision Tree algorithms are referred to as CART or Classification and Regression Trees.</p>
So, what is actually going on in the background? Growing a tree involves deciding on which features to choose and what conditions to use for splitting, along with knowing when to stop. As a tree generally grows arbitrarily, you will need to trim it down for it to look beautiful. Lets start with a common technique used for splitting.

<h2> Recursive Binary Splitting </h2>

In this procedure all the features are considered and different split points are tried and tested using a cost function. The split with the best cost (or lowest cost) is selected. This <strong>algorithm is recursive in nature</strong> as the groups formed can be sub-divided using same strategy. Due to this procedure, this algorithm is also known as the greedy algorithm, as we have an excessive desire of lowering the cost. This makes the root node as best predictor/classifier.

<h2> Cost of a Split</h2>

Lets take a closer look at <strong>cost functions used for classification and regression</strong>. In both cases the cost functions try to <strong>find most homogeneous branches, or branches having groups with similar responses</strong>. This makes sense we can be more sure that a test data input will follow a certain path.

<span>
<math>
		<strong>Regression: sum(y-prediction)<sup>2</sup>  </strong>
</math>
</span>

Lets say, we are predicting the price of houses. Now the decision tree will start splitting by considering each feature in training data. The mean of responses of the training data inputs of particular group is considered as prediction for that group. The above function is applied to all data points and cost is calculated for all candidate splits. <em>Again the split with lowest cost is chosen</em>. 


<span>
<math>
		<strong>Classification: G=sum(pk*(1-pk)) </strong>
</math>
</span>

A Gini score gives an idea of how good a split is by how mixed the response classes are in the groups created by the split. Here, pk is proportion of same class inputs present in a particular group. A perfect class purity occurs when a group contains all inputs from the same class, in which case pk is either 1 or 0 and G = 0, where as a node having a 50–50 split of classes in a group has the worst purity, so for a binary classification it will have pk = 0.5 and G = 0.5.

<h2>When to stop splitting?</h2>

As a problem usually has a large set of features, it results in large number of split, which in turn gives a huge tree. Such trees are complex and can lead to overfitting. So, we need to know when to stop? One way of doing this is to <strong>set a minimum number of training inputs to use on each leaf</strong>. For example we can use a minimum of 10 passengers to reach a decision(died or survived), and ignore any leaf that takes less than 10 passengers. Another way is to set maximum depth of your model. <strong>Maximum depth refers to the the length of the longest path from a root to a leaf.</strong>

<h2> Pruning </h2>

The performance of a tree can be further increased by <strong>pruning</strong>. It involves <strong>removing the branches that make use of features having low importance.</strong> This way, we reduce the complexity of tree, and thus increasing its predictive power by reducing overfitting.

Pruning can start at either root or the leaves. The simplest method of pruning starts at leaves and removes each node with most popular class in that leaf, this change is kept if it doesn't deteriorate accuracy. Its also called reduced error pruning. More sophisticated pruning methods can be used such as cost complexity pruning where a learning parameter (alpha) is used to weigh whether nodes can be removed based on the size of the sub-tree. This is also known as weakest link pruning.

<h2>Advantages of CART</h2>
<ul>
<li>Simple to understand, interpret, visualize.</li>
<li>Decision trees implicitly perform variable screening or feature selection.</li>
<li>Can handle both numerical and categorical data. Can also handle multi-output problems.</li>
<li>Decision trees require relatively little effort from users for data preparation.</li>
<li>Nonlinear relationships between parameters do not affect tree performance.</li>
</ul>

<h2>Disadvantages of CART</h2>
<ul>
<li>Decision-tree learners can create over-complex trees that do not generalize the data well. This is called overfitting.</li>
<li>Decision trees can be unstable because small variations in the data might result in a completely different tree being generated. This is called variance, which needs to be lowered by methods like bagging and boosting.</li>
<li>Greedy algorithms cannot guarantee to return the globally optimal decision tree. This can be mitigated by training multiple trees, where the features and samples are randomly sampled with replacement.</li>
<li>Decision tree learners create biased trees if some classes dominate. It is therefore recommended to balance the data set prior to fitting with the decision tree.</li>
</ul>

<em> * Source: <a href="https://towardsdatascience.com/decision-trees-in-machine-learning-641b9c4e8052">https://towardsdatascience.com/decision-trees-in-machine-learning-641b9c4e8052</a></em>