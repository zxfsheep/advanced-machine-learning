* [**Learning from Simulated and Unsupervised Images through Adversarial Training**](https://arxiv.org/pdf/1612.07828.pdf): See [Computer Vision](https://github.com/zxfsheep/advanced-machine-learning/blob/master/summaries/Vision.md).

* [**Semi-Supervised Text Classification using EM(Expectation-Maximization)**](https://www.cs.cmu.edu/~tom/pubs/NigamEtAl-bookChapter.pdf): See [NLP](https://github.com/zxfsheep/advanced-machine-learning/blob/master/summaries/NLP.md).

* [**Semi-Supervised Classification with Graph Convolutional Networks**](https://arxiv.org/pdf/1609.02907.pdf) as well as [**Learning from Labeled and Unlabeled Data with Label Propagation**](http://mlg.eng.cam.ac.uk/zoubin/papers/CMU-CALD-02-107.pdf): Even though the first recent work is on neural network, while the second work is much more traditional, they have similar underlying ideas: given the graph structure with the data points as vertices,  we can train a model in a semi-supervised fashion, by propagating along the graph. This makes use of the unlabeled data, because they provide information about the graph structure, and serve as messengers to transport label information.

  Propagation on the graph is usually realized by an adjacency matrix. This has another interpretation as random walks on graphs. Maybe this can be made into a probabilistic method for better performance?

  Added: [**DeepWalk**](https://arxiv.org/pdf/1403.6652.pdf) seems to be along this line of thoughts.

* [**Combining Labeled and Unlabeled Data with Co-Training**](http://www.cs.cmu.edu/afs/cs.cmu.edu/Web/People/avrim/Papers/cotrain.pdf): The abstract idea is that, if the features of each sample can be separated into two discrete subsets, which are conditionally independent(which is a strong theoretical assumption!) given the label, then we can use them in an collaborative fashion to utilize unlabeled data, starting with a possibly very small set of labeled data. For example, a captioned picture can be separated into the caption and the image. 

  The algorithm is the following. Keep a randomly chosen pool of unlabeled data. Use the currently labeled data to train two classifiers, one for each subset of features. Then we apply these two classifiers to the pool of unlabeled data, and actually label those with highest confidence scores. The pool of unlabeled data is then replenished with new unlabeled data, and we repeat above.

* [**Transductive Support Vector Machines(TSVM)**](http://lasa.epfl.ch/teaching/lectures/ML_MSc_Advanced/Slides/Transductive-SVMs.pdf): This is a generalization of SVM incorporating unlabeled data. The word "transductive", versus the usual "inductive", means that instead of learning a general rule of classification from the training data, we assume that we know ahead all test data, and only focus on classifying those test data correctly.

  Under this setting, the decision boundaries of SVM should take into account not only of the labeled data, but also all the unlabeled data. We want to find a labeling of all the data which satisfy the usual goal of SVM, that is either no violation in the hard-margin case, or minimization of violation errors in the soft-margin case.

* [**Spectral Methods for Dimensionality Reduction**](https://cseweb.ucsd.edu/~saul/papers/smdr_ssl05.pdf): 

  **PCA** and **MDS** are dual to each other. PCA works on covariance matrix, and MDS works on Gram matrix of the sample vectors, but their results are mathematically equivalent. In fact, the kernel PCA with rbf kernel is solved by converting to MDS.

  The manifold learning methods basically all start with building a graph based on k-nearest neighbor relations, and choosing the edge weight according to the distance. The goal is to embed the samples in a lower dimensional space.

  **Isomap** attempts to preserve the manifold geodesic distance. This is approximated by the graph shortest distance. The distances are fed into MDS to find the solution.

  **Maximum variation unfolding** tries to maximize the total variance of the embedding, while preserving the local metric and angle. The solution is found using semidefinite programming. Compared to isomap, the global structure is not guaranteed to be preserved.

  The two algorithms above can be seen as choosing a specific kernel matrix, and the solution correspond to top eigenvectors. The spectral gap can be used to estimate the right dimension.

  **Locally linear embedding** writes every point approximately as a linear combination of its neighbors, and then realizes those linear combinations in the embedding.

  **Spectral embedding** uses the bottom eigenvectors of the Laplacian matrix to construct the low dimensional embedding.

  Two algorithms above can also be seen as certain kernel methods. In particular, bottom eigenvectors of the Laplacian matrix correspond to top eigenvectors of the inverse Laplacian, which yields commuting time between points. The downside is that bottom eigenvectors are often tightly spaced, so one cannot tell the right dimension to embed in.






