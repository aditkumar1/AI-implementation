									ANALYSIS OF SUPERVISED AND UNSUPERVISED LEARNING ALGORITHM TO
													PREDICT ELECTION RESULTS

                                                          ADIT KUMAR


                         ABSTRACT                                   increasing order and then first K (=5) of them are selected,
Three supervised (k-nearest, perceptron, ID3 decision tree)         the training county of these are traced and their results are
and two unsupervised (k-means and agglomerative nesting)            determined. The result of test county is decided by majority
learning algorithms are analyzed on the dataset of election         of type of counties in the set (k=5) i.e. if 3 out of 5 county in
results and their accuracy and performance is compared              set is supporter of republican then the test county will be
                                                                    predicted as supporter of republican. A prediction accuracy
                    1. DESCRIPTION                                  of 86% is obtained
In supervised learning algorithm the system is first trained                           Perceptron Learning
with dataset and tested while in unsupervised learning              In this algorithm each attribute of a county are assigned a
algorithm, the dataset are clustered into different classes.        weight. The prediction is done by taking sum of product of
The following procedures are adopted in each algorithms-            each attribute value by its corresponding weight and then
                           K-means                                  compared with expected result. The algorithm starts by
Data is first normalized by recalculating the attribute values      finding the best optimum value for each weights by
of county relative to total US population. The mean of all          modifying them according to expected results while
attribute value is taken, so that a county can be represented       traversing through each county in training phase. After the
by this single value. The clusters are formed by dividing the       weights are trained, these are then tested on counties in test
county into 2 dataset according to their election result. For       set. A prediction accuracy of 76% is obtained. This accuracy
instance if a county voted for republican then it will go into      can be improved if the learning rate is decreased at regular
republican cluster. The centroids of cluster are calculated by      intervals for increasing the convergence of result.
taking average of above county mean value. The data is then                        ID3 Decision Tree Learning
tested, for each county in test data again the mean of              The algorithm works by first constructing the decision tree
attribute value is taken and then result is predicted by            in which each node is associated with a decision and then
selecting minimum Euclidean distance to centroid of both            predicting the output by traversing the tree from root to
clusters. An accuracy of around 86% is obtained.                    leave. The algorithm tries to represent the best attribute
                  Agglomerative Nesting                             value on the decision node. During tree generation phase for
In this algorithm, during training phase each county starts         each columns (attribute) is traversed and checked if it can be
with its own cluster, the cluster value is represented by mean      used to divide the rows into homogeneous groups i.e. the
of all normalized attribute value. The cluster sets of              rows with homogeneous output result. This is measured by
republican counties is separated from democrat counties in          entropy, more is entropy, and the less is the homogeneity in
order to differentiate between them. Each cluster set are           the rows. The attribute value with least entropy is selected
stored in two different priority queue. In each priority queue      and put into decision tree node. At leaf node the final
first two clusters are taken , merged and then put back into        decision result is stored. The tree is generated using training
queue, this process is repeated until 1 cluster is obtained in      data and then classification is done on testing data. The
both queues. The resulting means of these clusters are their        overall accuracy of 81% is obtained
respective centroid. During test phase, the same procedure
as that of k-means is followed and a county result is                                        3. CONCLUSION
predicted by taking the nearest distance to each centroids of       The best predication accuracy was obtained using K-means
clusters. An accuracy of 83% is obtained.                           and K-nearest Neighbor algorithm. The best running time
                    K-Nearest Neighbor                              performance is observed in K-means algorithm. However
This is a lazy learning algorithm, so the processing directly       the worst running time performance is observed in K-
starts with testing phase. A county in test set is compared         Nearest Neighbor algorithm. It is also important to note that
with all the counties in training set by calculating the sum of     accuracy of some supervised algorithms like perceptron
Euclidean distance of each features of both counties and            learning can be improved by using better model like multi-
then storing it in the list along with training county value so     layer models.
that it can be traced later. The values of this list is sorted in
