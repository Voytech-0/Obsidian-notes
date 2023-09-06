# 2 Introduction
22:11:1717:04
Status:  #MachineLearning
Tags: 

---
### Machine learning:
- Unsupervised
- Supervised
- Reinforcement

### Requirements of AI:
- Adaptivity or adaptability
- learning
- generalisation

### The qualification problem

### Data driven paradigm
To alleviate the Qualification problem we use big data

## Learning Paradigms
### Supervised Learning 
- Learning through supervision, that is, a teacher tells the agent what is the correct answer given some input or stimuli. The agent should learn mapping between input and desired output. 

### Unsupervised Learning
- Learn from data without supervision - not having a clear relation between input and desired output. 
- It is not limited by labels, so we cab out more data in it.
- The problem is generally algorithmic. It is difficult to extract patterns and properties of data without assumptions. 
- We typically learn features of data to classify it. 
- We can learn [[convolutional features]] that can be learned using unsupervised learning on images. 

### Reinforcement Learning 
- The agent operating in an environment receives a reward signal (positive or negative). 
- The agent learns policies maximising a specified criterion. For example, they may maximise the sum or reward over a whole interaction episode. 
- It is often used for sequential action. 

### Transfer Learning
- Combination of previous paradigms, where learned knowledge is used to learn or improve on new tasks. 
#### Self-Supervised
The agent / algorithm supervises itself by means of solving a pretext task. It can be automatically computed and solved, but generally it needs to be designed by humans. 
#### Semi-Supervised Learning
The agent / algorithm receives multiple kinds of supervision at the same time. Both unsupervised and supervised on different parts
#### Weak Supervision
The agent receives supervision, but it is *weak*. For example for object detection only class labels are provided instead of labels and boxes. 

### Generalisation
The model we train is supposed to generalise on the data provided during training. 

---
### Basic ML concepts
[[Model]]
[[Loss function]]
[[Training data]]
[[Classification]]
[[Regression]]
[[Multi-task learning]]

---
### Learning as Optimisation
- It is crucial to choose a correct loss function 

**Trainable parameters**: Parameters that are directly trained using an optimisation.
**Non-trainable parameter**

**Training set**: the Set used to train data, which usually is around 70% to 80% of the data available
**Test set**: The set that is used to evaluate the trained model. It should be an independent dataset with samples that have not been seen during training. It's the remaining 20 to 30% of data.

### Linear Separability 
- Basic classification concept used for separating hyperplanes 
- *definition slide 31*
- The role of Feature Engineering for Classification is to transform features to be linearly separable. 

## Feature Engineering
[[Feature]]

#### Feature vectors
- Vectors with elements corresponding to individual features. 

---
## Types of Features 

### Continuous 
 Real numbers. For example, distances, floating point numbers, convolutional feature maps, gradients, etc. 

### Discrete 
 Integer numbers that can be ordered and are countable. For example, number of shoes in your apartment, most currencies (€,$), number of persons living in a house, population of a country, etc. 

### Categorical 
 Categories, where no order can be established. For example, colors, nationality, course code, etc. 

---

## Obtaining Features 

 There is a whole field of Feature Engineering, to obtain high quality features for tasks. Specially in NLP and Computer Vision. 

 The quality of your features related to a specific task, defines the performance of your machine learning model. Better features means better performance, and viceversa. 

 Features can also be (non-linear) transformations of raw data (pixels, sound, text, etc). This is what Deep Learning does. 

---

## Feature Transformations 

 A simple way to ”improve” your features is to make aggregation or non-linear transformations of features. For example: Aggregation Mean, standard deviation, variance, skew, kurtosis, etc. Polynomials For a scalar feature x, use x,x^2 ,x^3 ,x^3 ,...,xp. The polynomial degreepis a hyper-parameter. Frequency Fourier transform of your data is commonly used as features, with a frequency cutoff. 

---

## Not Useful Features 
- Features that are linearly correlated with each other. 
- Features that do not change over the whole dataset (constant). 
- Features with many missing or unclear values. 
- Features that do not predict the target value of interest. 
- Random features. 

---

## Pre-Processing 

 In general data needs to be pre-processed and normalized before being used with any model. This is because when learning a model, it will only work with data that is similar to the training data distribution, so normalizing allows data to be more similar to this distribution, and not to vary too much. 
- Pre-processing can also discard invalid data, select which features will be used, and put data in a common format. 
- Train and test splits are also part of pre-processing. 
- Depending on the task (like regression), outputs can also be post-processed to produce ideal predictions. 

---

## Normalization 

 Normalization is the process where input features are standarized to a common range. 
- This is required as features might be at different scales (numerical range), and the model might assign importance to each feature according to the highest value. 
- In general training a model with normalized data is much easier, so it is a recommended first step. 
- Target values can also be normalized, for example, to make regression easier (by limiting the model output range). 
- We cover a set of normalization techniques. Avery importantpoint is that normalization generally captures some statistics from the training set, so any normalization should be applied in the training set, and then in the test set (using train statistics) and in any new data when making predictions. 
- Normalization allows all features to have similar ranges, which makes training smoother. Models trained on unnormalized data usually perform worse. 
- Sometimes it is difficult to normalize when the training and test sets vary considerably. 

### Min-Max 

 For each featurex, compute the following: 

 xnorm=maxx−xmin−minxx (2) 

 This transforms all values to range inside[ 0 , 1 ]. The minimum feature value is mapped to zero, and the maximum feature is mapped to one. Intermediate values are mapped to( 0 , 1 ). 

 There is also a transformation to the[a,b]range: 

 xnorm= (b−a)maxx−x−minminxx+a (3) 

### Standard or Mean-Std 

 For each featurex, compute the following: 

 z=x−stdmean(x)(x)=x−σμx x 

 (4) 

 This transforms all values to an approximate range, usually[− 3 , 3 ], depending on the distribution ofx. You might recognize that this is the same as the z-score used in a normal/gaussian distribution. The mean ofzis 0.0, and the standard deviation and variance is 1.0. 

### Unit Vector 

 For a feature vectorx, compute the following: 

 v=||xx||={||xxi||}i (5) 

 This makes the data lie on andimensional hyper-sphere. Where||x|| is a vector norm, for example the L2 norm||x||= 

 pP ixi^2 

---

## Normalization Whitening 

 Whitening is a more complex transformation of multi-dimensional dataX, with the purpose of de-correlating and setting the covariance matrixΣof the data to the identity matrix. 

 For zero-centered (mean substracted) data X, the basic transformation is: 
$$Z=WX$$
 The matrix W is called a **whitening matrix**, and should follow that $$W^TW={\Sigma}^{-1}$$
 Depending on the choice of W, there are different types of whitening: ZCA Whitening Select W= Σ−^12 PCA Whitening Compute W using Principal Component Analysis (PCA). Note that ZCA and PCA whitening produce different results but in both cases the data is normalized to identity covariance. 

## Normalization PCA Whitening 

 Here the matrixW is computed using the eigenvalue decomposition onΣ, which is a matrix decomposition in the form: Σ =UΛUT (7) WhereUcontains the eigenvectors ofΣas columns, and Λis a diagonal matrix containing the eigenvalues ofΣ. This can be computed using functions like np.linalg.eig. ThenWis computed as: 

 W= Λ− 

(^12) UT (8) This sets the covariance ofX to be a identity matrix. 

---

## Normalization Images 

 For specialized data types, there are specific normalization methods. For images we have: Histogram Equalization This adjust contrast in the image so the distribution (histogram) of gray levels is uniform. This makes sure that all gray levels are equally represented in the normalized image. It is useful for when the image has dominant shadows or highlights. 

---

## Normalization Images 

 Noise Removal Noise can be removed using a median or gaussian filter, with a careful design to not remove important image features. Resizing Images in a dataset can vary in size, and they are usually normalized to a standard size. Common values are 224×224 or 256×256. Normalized size must be carefully chosen to not lose image features. 

---

## Normalization Histogram Equalization 

 0 50 100 150 200 250 Figure: Original image and histogram (red). The black curve is the cumulative distribution. 

 0 50 100 150 200 250 Figure: Equalized image and histogram (red). The black curve is the cumulative distribution. 53 / 70 

---

## Normalization Audio 

 Resampling The sampling rate of the audio signal can also be normalized, common values at 44.1 kHz or 22.05 kHz. Audio Length The length (in time) of audio signals can also be normalized, in a similar way to image size normalization. 

---

## Normalization Audio 

 Amplitude Normalization The overall volume of audio can also be normalized, to make sure all samples in the dataset have similar volume. This is done in two ways: 

1. Peak Normalization. Normalizing to the maximum value across time samples. This is similar to min-max scaling. 

2. Loudness Normalization. Normalizing to a aggregate loudness of the whole audio signal across time. For example it can be the root mean square (RMS), or a value related to human perception of loudness. 

---

## Normalization Text 

 Text is the most difficult to normalize, since many factors can vary: 
- Stop words are usually removed. 
- Numbers, dates, acronyms and abbreviations can be standarized to common terms (like transforming 10 to Ten, dates to ISO formats, and acronyms removed or expanded. 
- Non alphanumeric characters are usually removed. 
- Specific words can be standardized, specially if they have multiple meanings, depending on the application. 
- Spelling across variations of the same language can also be normalized, for example British vs Australian vs American English. 

---

## Normalization Categorical Variables 

 Categorical variables are usually not numeric, for example, when a variable can take a value from a pre-defined set of values. A common mistake is to just assign numerical values to each of the categorical values, but this biases the model, as it thinks higher value means more importance. 

 So youcannotuse categorical variables by converting them to integers. This is acommonmistake. 

---

## Normalization Categorical Variables 

 An unbiased way to encode categorical variables is to use one-hot encoding. 

 If the variable hasN possible values and we encode category i, then a vector ofN elements is used to represent it, where all elements are 0.0, except for the i-th value which is set to 1.0. 

 An example: 
- Cat =[ 1. 0 , 0. 0 , 0. 0 ] 
- Dog =[ 0. 0 , 1. 0 , 0. 0 ] 
- Bunny =[ 0. 0 , 0. 0 , 1. 0 ] 

---

## Normalization Regression 

 One important detail, is that output values (labels) can also be normalized, particularly in the case of regression. 
- If your labels have a limited range, normalizing can teach the model what values are allowed. Models can also be configured to output in a normalized range. 
- One should also make sure to remove or clip output values that are outside of the expected ranges. 
- Correct normalization of the output and labels can the process of learning a model much easier. 

---

## Normalization Which to use? 

 We have covered a lot of normalization methods. Choosing them is difficult, usually we experiment during ML model development and choose what performs best. 
- In many cases it is trial and error. 
- Experience tells us what to try first. 
- Exploratory analysis of your data can reveal properties that should be normalized. Always look at your data before trying to learn models from it. 

---

## Challenges in Machine Learning 

### Quality of Data 

 The biggest bottleneck is obtaining high quality data (including features and labels) for the task of interest. Without data, a model cannot be learned. 

 Low quality data (incorrect labels, unclear or useless features, missing values, etc) hurts the performance of your model. 

 Well known saying, Garbage in, Garbage out. 

### Computation and Memory Capabilities 

 Large machine learning models, specially deep learning, convolutional nets, and transformers, require lots of compute capability for training and inference. 

 Large datasets also require proportional more computation and memory (RAM) to be processed. 

 This is why we use (multiple) GPUs, TPUs, etc. 

 Compute capability can be a bottleneck for Research and Development. 

### Model Misspecification 

 Model misspecification is using the wrong model for a given dataset. 

 In simple words, you have some features/data, a task and a target to predict. Wedo notknow what would be the best model for this task. 

 In general you do not know the mathematical model that generated the data. Specially for highly dimensional data. 

 So we usually do trial and error and research to find out this. 

---

## Generalization 

 Overall I think the biggest issue currently in AI is the lack of generalization, that means, solutions are given to specific problems, but general AI solutions (true AGI) does not exist yet. 
- Alpha Go and variations (Alpha Go Zero and Alpha Zero) only solved playing the game of Go, but these advances have not benefited other applications. 
- Deep Blue can play chess, but it has not served to solve some of humanities biggest issues (like peace, hunger, wealth distribution, etc). 
- All models overfit to some degree, but some are useful. 

---

## Explainability 

 Most AI methods overall areBlack Boxes, meaning it is difficult to interpret their decisions, or to get an explanation on how a decision is made. 
- Explanations and interpretability are required for AI to gain human trust, and it is even legally required in some countries (like in the EU with the GDPR). 
- Explaining black box method is very difficult, as computational concepts do not always map to human understandable concepts. The use of non-linear methods also makes it difficult. 
- Building methods that are easily interpretable (AKA white box methods) is also very difficult, and in many cases they work but are less accurate than black box models. 

---

## Safety and Trustworthiness 

 As AI is used for real world applications, specially ones involving humans, it is very important to ensure that it will not perform unexpected actions or behave abnormally. 
- Right now there are AI systems that are actively hurting people, for example: 
- In the US, poorly understood AI systems are being used to decide if a person will commit a crime, or how long their sentence should be. 
- AI systems being used for monitoring of populations, violating their human rights. 
- AI systems used by banks to review and recommend on decisions for loans, and by companies to decide who to interview for a job. 

---

## Questions to Think About 

1. What is a feature? 

2. Describe linear separability in your own words. 

3. What is the need for normalization and pre-processing of features? 

4. Can regression labels/targets be normalized? 

5. What factors can hurt the performance of a Machine Learning model? 

6. Your model does not learn, what is the most likely cause? 

---

## Take Home Messages 
- There are three paradigms in Machine Learning, Supervised, Unsupervised, and Reinforcement. 
- Generalization is the biggest issue/core idea of Machine Learning. 
- Two main tasks: Classification and Regression. 
- Learning is done through an optimization problem. 
- Normalization and pre-processing of features and labels is very important. 
- Machine Learning is not magic, there are many challenges. 

---

## Questions? 




---
# References