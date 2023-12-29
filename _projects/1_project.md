---
layout: page
title: Machine Learning Project
description: unsupervised learning and reinforcement learning
img: assets/img/projects_img/ml/kmeans_digits_reduced.png
importance: 1
category: work
---

## Unsupervised Learning

Unsupervised learning is one category of techniques in machine learning that aims to find patterns of a dataset without explicit labeling required by supervised learning. Two main methods fall under unsupervised learning are clustering and dimensionality reduction. 

Dimensionality reduction is the method to find more important features and exclude features that are not important. With more features, the data can be sparse and for some models they can suffer from dimensionality curse. In this project, we use primary component analysis (PCA), independent component analysis (ICA) and locally linear embedding (LLE) to conduct dimensionality reduction for MNIST dataset.
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects_img/ml/PCA projection first 2 components Digits.png" title="PCA image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects_img/ml/ICA projection first 2 components Digits.png" title="ICA image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects_img/ml/LLE projection first 2 components Digits.png" title="LLE image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Embedding with PCA, ICA and LLE applied on MNIST dataset.
</div>

Another method dominates unsupervised learning is clustering, which is to find hidden pattern in a given dataset. Two popular clustering methods are k-Means and expectation maximization (EM). In this project, I show clustering with original dataset and dimensionality reduced dataset.
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects_img/ml/kmeans_digits_reduced.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects_img/ml/em_digits_reduced.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    K-Means and EM clustering using original, PCA processed and LLE processed MNIST data.
</div>

- Dimensionality Reduction:
    - The linearity of the dataset plays a crucial role in the performance of dimensionality reduction methods.
    - The chosen dataset exhibits a significant linear relationship, which may explain why the manifold approach, such as LLE, does not perform as well.
- Clustering Using Dimensionality-Reduced Data:
    - PCA and manifold LLE were applied for dimensionality reduction, and PCA yielded the best clustering results for the datasets.

## Reinforcement Learning
Reinforcement learning is a type of machine learning paradigm where an agent learns to make decisions by interacting with an environment. The agent takes actions, receives feedback in the form of rewards, and learns to maximize its cumulative reward over time.Reinforcement Learning algorithms, such as Q-learning, policy iteration and value iteration methods, use the MDP framework to model the environment and learn an optimal policy. These algorithms aim to find a strategy (policy) that guides the agent to take actions that lead to the highest expected long-term reward.

Policy iteration and value iteration are reinforcement learning methods developed from Bellman equation, which fully encodes the utility of a state in a markov decision process (MDP).

$$U\left(s\right) = R\left(s\right) + \gamma \max_{a\in A\left(s\right)}\sum_{s'} T\left(s,a,s'\right)U\left(s'\right)$$


### Frozen Lake Problem

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects_img/ml/Frozen Lake Policy Map Iteration 9 (Policy Iteration) Gamma 0.99.png" title="frozen lake pi image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects_img/ml/Frozen Lake Policy Map Iteration 9 (Value Iteration) Gamma 0.99.png" title="frozen lake vi" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects_img/ml/Frozen Lake Policy Map Iteration 0.1 (Q Learning) Epsilon 0.1.png" title="frozen lake ql image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Optimal policy map developed with policy iteration, value iteration and Q-learning for Frozen Lake problem.
</div>


### Blackjack Problem

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects_img/ml/Blackjack Policy Map Iteration 9 (Policy Iteration) Gamma 0.99.png" title="frozen lake pi image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects_img/ml/Blackjack Policy Map Iteration 9 (Value Iteration) Gamma 0.99.png" title="frozen lake vi" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects_img/ml/Blackjack Policy Map Iteration 0.1 (Q Learning) Epsilon 0.1.png" title="frozen lake ql image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Optimal policy map developed with policy iteration, value iteration and Q-learning for Blackjack problem.
</div>

- Policy Iteration and Value Iteration
    - PI and VI would reach to the same optimal policy when they are long-term planning enough to reach the goal.
    - PI and VI may show observable difference if the discount rate Gamma is small and they are favoring immediate rewards in different ways.
    - When changing Gamma, typically time cost for each iteration in PI would be similar if it is deterministic process, and can change drastically if it is stochastic process.
    - When changing Gamma, typically time cost for each iteration in VI would be less sensitive no matter it is stochastic or non-stochastic process.
    - PI/VI may not be very robust when solving stochastic problem like Blackjack.
- Q Learning
    - QL would generate very different optimal strategy compared to PI/VI because of the nature of action selection.
    - QL can be more robust when solving stochastic problems like Blackjack.
    - In complex problem like with large state space, QL convergence behavior can be very sensitive when tuning epsilon.

## References

[CS 7641: Machine Learning](https://omscs.gatech.edu/cs-7641-machine-learning)



