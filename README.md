## Advanced Machine Learning
This place holds my projects and notes for advanced machine learning techniques.

[My Index page for all repositories.](https://github.com/zxfsheep/Index/blob/master/README.md)

## Projects

* [Solving BipedalWalker-v2 from the OpenAI gym using TensorFlow.](https://nbviewer.jupyter.org/github/zxfsheep/advanced-machine-learning/blob/master/BipedalWalker-v2/BipedalWalker.ipynb) The task was solved (100 consecutive 300+ points) using an Actor-Critic style model, with some personal improvisations. In particular, a rollout estimator with a random horizon length is used.

* [Classifying Lego bricks using TensorFlow.](https://nbviewer.jupyter.org/github/zxfsheep/advanced-machine-learning/blob/master/lego_bricks.ipynb) Many adjustments were made according to the lessons learned and mistakes found in the experiment below.

* [Classifying blood cell types using TensorFlow.](https://nbviewer.jupyter.org/github/zxfsheep/advanced-machine-learning/blob/master/blood_cell.ipynb)

---

## Notes
These actively updated notes are written with my own interpretation and thoughts, with links to original papers or references.

* [Learning with unlabeled data](https://nbviewer.jupyter.org/github/zxfsheep/advanced-machine-learning/blob/master/summaries/Learning_with_unlabeled_data.ipynb): What can we do with limited labeled data and a lot of unlabeled data? This happens all the time in real life, and labeling data has become a major bottleneck in practical machine learning. Depending on the task, this can involve semi-supervised learning, unsupervised learning, weakly-supervised learning, transfer learning, active learning, one-shot/zero-shot learning, reinforcement learning, apprenticeship learning, multi-task learning, data augmentation, etc.

* [Reinforcement Learning](https://github.com/zxfsheep/advanced-machine-learning/blob/master/summaries/RL.md): Tasks which require learning to improve performance in a random, new environment.

* [Computer Vision](https://nbviewer.jupyter.org/github/zxfsheep/advanced-machine-learning/blob/master/summaries/Vision.ipynb): Tasks such as objection detection, bounding box labeling, semantic segmentation, instance segmentation.

* [Natural Language Processing](https://nbviewer.jupyter.org/github/zxfsheep/advanced-machine-learning/blob/master/summaries/NLP.ipynb): This is a very wide field including part of text tagging, text classification, sentiment analysis, language translation, text-to-speech, speech-to-text, relation extraction, etc.

* [Recommendation System](https://github.com/zxfsheep/advanced-machine-learning/blob/master/summaries/Recommendation.md): Predict preferences of customers based on the past behaviors as well as data of other customers. The sparsity of available data is usually a big challenge.
