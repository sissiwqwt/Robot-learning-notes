# Machine learning & Deep learning refresher

learning material:
- https://www.deeplearningbook.org/
- Patterns, Predictions, and Actions: Foundations of ML
- Pytorch tutorial: https://pytorch.org/tutorials/

## supervised learning basics
**machine learning foundations:**
- model/architecture
- training data
- loss
- learning objective
- generalization
- optimization
- overfitting
- underfitting

### optimization
#### GD v.s. SGD
**Learning objective:**
$$
\min_{w} L_N(w) = \sum_{i \in D_{\text{train}}} L(y_i, f(x_i \mid w))
$$
**Gradient Descent (GD):**
$$
w \leftarrow w - \eta \nabla_w L_N(w)
$$
Prohibitively expensive if the training dataset is large!
**Mini-batch Stochastic Gradient Descent (SGD):**
$$
w \leftarrow w - \eta \nabla_w \sum_{i \in \text{Batch}} L(y_i, f(x_i \mid w))
$$
- An online optimization algorithm (only needs access to one batch at a time)  
- Leverages fast vector operations (especially on GPU)  
- Can be parallelized (e.g., different cores compute gradients on different mini-batches)  
- Not just "DL": useful even for least-squares regression on large datasets!

#### learning rate
practical rules of thumb:
- divide the loss by the number of examples (**normalize**)
- start with a relatively large learning rate
- whenever the validation error stops going down,lower the step size
- stop when the validation error makes no further progress (**early stopping**)

#### optimization beyond SGD
Non-convex problems are hard to optimize. Good news: we don't really care about finding the global optimum, it's more important to find a good local optimum.
- Momentum, AdaGrad, RMSProp, Adam, ...
- many tradeoffs
- example: how momentum works
$$
\mathbf{w}_{t+1} = \mathbf{w}_t + \mathbf{v}_{t+1} \\
\mathbf{v}_{t+1} = \rho \mathbf{v}_t - \eta \nabla f(\mathbf{w}_t)
$$

#### regularization
$$\argmin_{w}\sum_{i\in D_{train}}L(y_i,f(x_i|w))+ \lambda \cdot R(w)$$
- ridge regression (L2 regularization): $R(w) = ||w||^2$
- lasso (L1 regularization): $R(w) = ||w||_1$

#### probabilistic approach
maximize  log likelihood of $w$ on the training data:
$$\sum_i \sum_{k=1}^{K}1_{y_i=k}log\:softmax(f(x_i|w))_k$$

## Deep learning
Problem: A linear model considers each feature independently and regresses the weight $w$ with which it contributes to the label.
BUt in images, pixels are correlated with their neighbors. 