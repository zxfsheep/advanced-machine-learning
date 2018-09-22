* [**Learning from Simulated and Unsupervised Images through Adversarial Training**](https://arxiv.org/pdf/1612.07828.pdf): See [Computer Vision](https://github.com/zxfsheep/advanced-machine-learning/blob/master/summaries/Vision.md).

* [**Semi-Supervised Text Classification using EM(Expectation-Maximization)**](https://www.cs.cmu.edu/~tom/pubs/NigamEtAl-bookChapter.pdf): See [NLP](https://github.com/zxfsheep/advanced-machine-learning/blob/master/summaries/NLP.md).

* [**Combining Labeled and Unlabeled Data with Co-Training**](http://www.cs.cmu.edu/afs/cs.cmu.edu/Web/People/avrim/Papers/cotrain.pdf): The abstract idea is that, if the features of each sample can be separated into two discrete subsets, which are conditionally independent(which is a strong theoretical assumption!) given the label, then we can use them in an collaborative fashion to utilize unlabeled data, starting with a possibly very small set of labeled data. For example, a captioned picture can be separated into the caption and the image. 

  The algorithm is the following. Keep a randomly chosen pool of unlabeled data. Use the currently labeled data to train two classifiers, one for each subset of features. Then we apply these two classifiers to the pool of unlabeled data, and actually label those with highest confidence scores. The pool of unlabeled data is then replenished with new unlabeled data, and we repeat above.

* [**Transductive Support Vector Machines(TSVM)**](http://lasa.epfl.ch/teaching/lectures/ML_MSc_Advanced/Slides/Transductive-SVMs.pdf): This is a generalization of SVM incorporating unlabeled data. The word "transductive", versus the usual "inductive", means that instead of learning a general rule of classification from the training data, we assume that we know ahead all test data, and only focus on classifying those test data correctly.

  Under this setting, the decision boundaries of SVM should take into account not only of the labeled data, but also all the unlabeled data. We want to find a labeling of all the data which satisfy the usual goal of SVM, that is either no violation in the hard-margin case, or minimization of violation errors in the soft-margin case.


