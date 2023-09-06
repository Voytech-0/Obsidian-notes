# Regularisation
22:12:0313:55
Status:  #MachineLearning
Tags: 

---
- What is **regularization**?
	- Introducing additional information to the learning process in order to reduce overfitting and improve generalization
	- We usually need many more samples than there are features to learn a concept properly. 
- When is a problem called **ill-posed** or **ill-conditioned**?
	- When there are fewer samples than dimensional features, as not all possible feature values are defined. 
- What are some general patterns of regularization?
	- **Weight Constraints** - Put limitation into weight values, reducing the effective number of parameters.
	- **Output constraints** - Put limitations into intermediate or final output values, also reducing the effective number of parameters. 
	- **Introducing noise** - Add noise to features or weights to constraint undesirable interactions, like correlation between features.
- What is the relation of the strength parameter **R** and the complexity / capacity **P**?
	- *Large R* - Big regularization effect, model is very constrained, and effective P decreases significantly
	- *Middle R* - Balanced regularization effect, model is constrained but not too much. Potential improvement in generalization. Effective P is smaller than P.
	- *Small R* - Almost no regularization effect, model is not or little constrained, and effective P is almost the same as P.
- What is **Early stopping**?
	- It is the process of stopping training right before the validation loss starts to increase.
	- To do this we need a three-way split into train, validation and test set.
- What is $L^p$ regularization?
	- The most common regularization method. It introduces a penalty that considers the norm of the model parameters (weights).
	- The most common values of $p$ are 1 (LASSO) or 2 (weight decay)
- What is **L^1 Regularization (Lasso)**
	- There is a tendency to make some of the model parameters to be set to zero (sparse solution)
	- A model parameter will be non-zero only if it positively contributes to reduce the original loss of the model. 
- What is **L^2 Regularization (Weight Decay)**
	- Tends to make the model's parameters decay to small values, unless they are supported by the data and reduce the loss of the model.
- What is **Elastic Net Regularization?**
	- A method combining $L^1$ and $L^2$ regularization. 
- How is regularization coefficient $\lambda$ determined?
	- $\lambda=0$ is an equivalent of not using any regularization. Too high value may result in overfitting. 
	- The value should be tuned using cross validation in validation set (K-Fold is preferred). It is the regularization strength coefficient (R)
- What is *eavesdropping* in Multi-Task learning?
	- When a shared feature F is easier to learn in task A, B can eavesdrop into the shared layers which hopefully can learn F effectively. 

---
- Today we cover regularisation, a way to control model complexity in a way that improves learning. 
- Regularisation is the main tool we use to combat overfitting and improve generalisation. 
- There are many ways to do regularisation, in this lecture we cover the most common ones: weight penalisation in the loss function. 
- We also cover a little of multi-task learning 
---

---
# References