# ID5-algorithm - Incremental decision tree

ID5 is an incremental method for building a decision tree that builds the decision tree incrementally. This method updates the decision tree structure as each sample is received and it is different from the ID3 method, which must have all the samples to build a tree, and whenever a new sample enters the tree, it should have rebuilt again. The main difference between ID4 and ID5 is that in ID4 the subtrees will be pruned but in ID5 the structure of the tree will be retained but updated as needed when an additional instance is added without data loss.  The article related to the ID5 method is also uploaded into the repository. 

In this algorithm, regardless of the received data's features, the tree is maintained, if the new data's tag matches the previous samples. Whenever a sample with an inconsistent label is received, it should be decided whether to expand or pull up the tree based on the entropy criterion.

# Steps

The algorithm for handling an instance is:
1. For each potential test attribute at a node, update the count of positive and negative instances for that attribute, and the positive and negative count for the observed value of that attribute.
2. If the lowest INFO measure for a non-test attribute is lower than that of the current test attribute, then reshape the tree by pulling the desired test attribute "A_best" up from below.
3. If only positive instances or only negative instances have been observed at the given node, then store the rest of the training instance. Stop.
4. Recursively update the decision tree below the value of "A_best" in the instance description.

NOTE: INFO phrase in article considered as Entropy-score.


# Evaluation:

5-fold cross validation.

accuracy.

Reducing Error, Proning-4 different depths accuracies.
