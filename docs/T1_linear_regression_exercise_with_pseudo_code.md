## Exercise with pseudo-code for Linear Regression

Consider the following pseudo-code to train a simple Linear Regression model. It is designed to minimize the $L=(y-\hat{y})^2$ *loss* function.
Explain the following:
- What is the strategy to reduce the *loss* in each iteration?
- How many observations are used for each update of the model weights?
- Is there a risk of overfitting at each step of the algorithm?
  
  ---
  Pseudo code for SGD (stochastic gradient descent) to fit a linear regression:
  
  - Dataset:  $D = {(x_1^{(i)}, ..., x_k^{(i)}, y^{(i)})}\_{i=1}\^N$  `N observations, k features`
  - Learning rate:  $\eta$ `Small positive value`
  - Max iterations: max_iter `Number of epochs`
  - Initial weights $w$ := $(w_0, w_1, ..., w_n)$ `Typically, all zero, or random`
  - For iter := 1 to max_iter 
    - For each  $(x_1, ..., x_k, y) \in D$  `Update weights after each example`
      - $\hat{y}$ := $w_0 + w_1 x_1 + w_2 x_2 + \dots + w_k x_k$ `Predict response with current weights`
      - error := $y-\hat{y}$
      - $w_0$ := $w_0 + \eta \cdot$ error # `Update weight (bias)`
      - For $j$ := 1 to $n$
        - $w_j$ := $w_j + \eta \cdot$ error $\cdot x_j$ # `Update weight (for each feature)`
          
  ---
