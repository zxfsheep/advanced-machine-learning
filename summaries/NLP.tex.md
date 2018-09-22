* [**Semi-Supervised Text Classification using EM(Expectation-Maximization)**](https://www.cs.cmu.edu/~tom/pubs/NigamEtAl-bookChapter.pdf):  The base model is the **mixture of multinomials** generative model, which models a bag of words ignoring the ordering. Given a set of parameters $\theta$, the model first selects a class label $c_j$ with probability measure $P(c_j|\theta)$, and then generates the document $x_i$ (represented by its word count vector) according to the naive Bayes assumption:

  $$P(x_i|c_j, \theta)\propto P(|x_i|)\prod_{w_t\in \chi}P(w_t|c_j, \theta)^{x_{i,t}}$$

  where $\chi$ is the set of vocabulary and $x_{i,t}$ are the word count vector components. 

  The prior distribution is assumed to be product of Dirichlet distribution. In the supervised case, naive Bayes uses maximum a posteriori (MAP) estimate to obtain $\theta$ based on the prior and training data. Then we can use $\theta$ for classification.

  In the semi-supervised setting, ie. with a mixture of labeled and unlabeled data, we first use the labeled data to initialize a choice of parameter using naive Bayes. Then we iterate Expectation and Maximization steps, where the Expectation step uses the current parameter to produce class probabilities for unlabeled data, and the Maximization step use all labeled and unlabeled data to obtain a new $\theta$. More specifically, each unlabeled sample is treated as a mixture of samples with different classes weighted by class probabilities. EM procedure is iterated until convergence. This only converges to a local maximum. 

  **Warning:** Using unlabeled data could degrade the learning performance. This happens especially when the assumed model is incorrect. However, when there are too few labeled data, unlabeled data can help reduce variance, and thus improve performance even if it has a larger bias.

  So far classes and mixtures have 1-to-1 correspondence. This is not always sufficiently expressive, for example when a *negative* class contains a wide range of different subtopics. Therefore the model is strengthened to model many-to-1 correspondence from mixture to class, where each class also has a probability measure on different subtopics. Now even for labeled data, an EM iteration is needed because subtopics are unknown. 

  Furthermore, in order to avoid local maxima, **Deterministic Annealing** can be used. This technique starts with a target function almost convex, in which case the global maximum is easy to find, and gradually transition to the likelihood function that we actually want to maximize, where each EM procedure is initialized with the parameters found in the previous step. This hopefully will lead to a final result close to a global maximum. However this is not always the case, as the iterations might not be able to correct the wrong class-subtopic correspondences decided earlier. One can try to correct the class-subtopic correspondence by human inspection or by the basic EM algorithms described above.

* [**Word2Vec**](https://arxiv.org/pdf/1301.3781.pdf): The goal is to learn word embedding as vectors. There are two types of auxiliary training tasks: the Continuous Bag-of-Words model (CBOW) and the Skip-Gram model. CBOW predicts target from context, and Skip-Gram vice versa. For larger dataset, Skip-Gram performs better. The naive approach is to let the NN output a probability vector for all words, and minimize the logloss. However in practice, we use Monte Carlo to randomly sample wrong words to do a binary classification with the correct word. This is called **Noise-Contrastive Training**.

  The output of NN is the embedding. In order to [make prediction](https://www.tensorflow.org/api_docs/python/tf/nn/nce_loss) of a context word (in Skip-Gram model), the model also trains a weight and bias for the entire vocabulary. Suppose the embedding vector has dimension $n$, then the weight of each word also has dimension $n$, and to make prediction, the context word embedding is multiplied by the weight matrix, then adding bias term. These are passed to a sigmoid function to output probability. Therefore, the weight and bias can be thought of as describing how each context word **interacts** with all other words, while the embedding behaves like an ID of each word.

* Seq2Seq

* WaveNet

---

##Basic concepts:

* **tf-idf**: The product of two statistics, term frequency and inverse document frequency, is a importance weight given to a word in a set of document. They can be defined in various ways, but basically term frequency describes how often it appears, and inverse document frequency describes how many documents contain the word. The intuition is that if every document contains the word, it might be so common that it does not provide much specific information.