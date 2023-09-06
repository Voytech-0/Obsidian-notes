# Cross Validation
22:12:0110:53
Status:  #MachineLearning
Tags: 

---
Introduction to Machine Learning (for AI)
Cross Validation and hyperparameter Tuning
Dr. Matias Valdenegro & Dr. Andreea Sburlea
November 30, 2022

---
# Questions
- What is over- and under-fitting?
	- Overfitted model matches the training data but is not generalised enough for different sets
	- Under-fitted model does not predict the target variable even for the training set
- How to detect overfitting?
	- Check whether the model works significantly better for the training set than for the test set
	- Use cross-validation methods
- What is cross-validation?
	- It is the concept of evaluating a model on an independent dataset in order to evaluate its performance and assess the level of generalisation
- How can we split data for cross-validation?
	- We could use chronological or random sampling
- What is a leakage of data?
	- It occurs when the training set leaks and is a part of the validation or testing datasets. It results in a production of incorrect evaluation metrics.
- How can a leakage be prevented?
	- User data: Assign people to train and test sets
	- Time series: Whole time series has to be assigned to one of the sets. It cannot be divided.
	- Objects: 
- What is **K-Fold Cross Validation**?
	- A dataset is split into k folds (equally sized). Then each fold is used once for testing, and all folds minus that one participate in training the model. This way, k models are trained.
	- After optimising the hyperparameters  on the validation sets, the model is retrained with all the training data and tested on the hold-out test set.
- What is **Leave One Out CV**?
	- It is a k-fold CV in which K = N, so we train the model on all but one sample.
- What are the challenges and opportunities of hyperparameter tuning?
	- *Performance*: Some hyperparameters can affect the amount of computation that a model requires
	- *Objective function*: Fitting a model to a dataset requires not only training the model but also adjust the hyperparameters in order to obtain the lowest possible training loss
	- *Train set*: The model is trained at each optimization step in this dataset
	- *Validation set*: The optimisation process evaluates the model on this dataset and using validation metrics decides which are the best hyperparameters. 
	- *Test set*: Final evaluation should be done only once on the test set. 
- What are different types of hyperparameters?
	- Continuous: Continuous numerical values such as learning rate
	- Discrete: Integer numerical values such as number of layers, neurons etc.
	- Categorical: Discrete, but not numerical. For example, optimizers or the choice of a particular value in the set.
- How to tune hyperparameters using **Grid search**?
	- We are brute-forcing the search
	- Define a set of values for each hyperparameter, discretizing continuous values
	- Take the cross-product of each set of hyperparameters, producing a grid that specifies a value of each hyperparameter.
	- Train a model for each point in the grid, and evaluate on a validation set. Use the hyperparameter set with the best validation performance.
	- Good performance at the *edges* of the grid might suggest increasing the range / value of some hyperparameters K-Fold CV is preferred.
- How is **Random Search** performed?
	- Random Search replaces hyper-parameter sets with distributions over hyper-parameters. 
	- Instead of producing a grid, a set of hyper-parameters is obtained by sampling each of the distributions over hyper-parameters. 
	- Then the same evaluation process as Grid Search is used. 
	- This method is better than Grid Search as it provides more evaluations of the important hyper-parameters. 
	![[5 Cross Validation Grid and Random search.png]]
- What are the issues with Grid and Random Search?
	- These methods work okay, but require a large computational budget for experiments. 
	- They do not learn anything about the hyper-parameter space as search is performed. 
	- Performance is always limited by the choices made during hyper-parameter design, for example, by the ranges used in Grid Search. 
	- Only a single metric is used (predictive performance). Other metrics could be added such as maximizing computational performance, or minimizing the number of parameters. 
- What is **Bayesian Optimization**?
	- It is a method that combines learning and hyper-parameter optimization. 
	- Some initial hyper-parameters are evaluated, and then a Gaussian Process is fit to this data, in hyper-parameter space. 
	- The Gaussian Process is used to predict new promising hyper-parameters, by analysing regions of expected improvement with an *acquisition function*. 
	- New hyper-parameters are evaluated and this information is merged into the Gaussian Process, repeating in a loop until a computational budget is consumed. 
	- ![[5 Cross Validation Bayesian Optimisation.png|500]]
- What are **acquisition functions** in Bayesian Optimization?
	- Probability of Improvement 
	- Expected Improvement. 
	- Maximum Improvement. 
- What is **AutoML**?
	- The name stands for *Automatic Machine Learning* and it aims to provide a general solution to the hyper-parameter optimization problem.
	- Some software implementation of these algorithms are:
		- Hyperopt
		- Hyperas
		- auto-sklearn
- What is **data augmentation**?
	- a set of techniques to artificially create variations of data in the training set, as a way to increment the number of data points, and to introduce some partial invariances to the model. This usually improves model performance.
	- They have to be manually designed by a human and are ideally label-invariant; the label of original data points are the same
	- It can only be applied to the training set!!!
- What is **synthetic data**?
	- It is a data generated using a computer program like a simulator or a renderer.
	- Labels can be automatically generated using code, since all the information is known by the simulator.
	- For example self driving cars can be trained in photorealistic games
	- A model can be pre-trained on simulated data to learn basic information from it. This is called *domain randomization*
- What are some *invariances* added to augmented data?
	- Introducing noise
	- Changing brightness, contrast, crop, shifts, flips, quality re-compression, Gaussian blur
- How many augmented images should be added to a model?
	- Fixed number: All images are augmented N times in one run, resulting in N+1 times the data size. This value is selected as a trade-off between training time and available computational resources.
	- On the fly augmentation: The whole dataset is augmented once without saving the training set. Therefore, due to randomization, each training set has data augmented differently. 

#### Questions to Think About 
1. What are the differences between cross validation, k-fold cross-validation, and leave one out cross-validation? 
2. What is the major difference between a validation and test sets? 
3. Give an example (not ones from the lecture) of leakage between train and test set. 
4. What should you considering when selecting data augmentation methods for your problem? 
5. 
---
#### Take Home Messages 
- Proper training/validation/testing methodology is extremely importantto obtain realistic measures of model performance. 
- Leakage is a major problem that can happen without noticing. Papers are rejected due to this. 
- Hyper-parameter tuning is also a major headache, as there is a trade-off between compute budget and finding the ”right” hyper-parameters for your problem. 
- Data augmentation is a good way to (virtually) increase the size of your training set, but also needs to be designed by a human. 


---
# References