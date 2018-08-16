# Table of Contents
* [Types of Artificial Intelligence Learning Models](#aimodels)
  * [Knowledge-Based Classification](#kbc)
  * [Feedback-Based Classification](#fbc)
* [Data Mining Vs Machine Learning](#mlvsdm)
* [Workflow of Machine Learning Project](#workflow)
* [Parametric vs Nonparametric](#tric)
* [Discriminative vs Generative Learning Algorithm](#dam)
* [Cross Validation](#cv)
* [Overfitting](#of)
* [Regularization](#reg)
* [Loss Functions for Regression and Classification](#lossfun)
* [Handle missing or Corrupted data](#missing)
* [Imbalanced Datasets](#imb)
* [Outliers](#out)

## Types of Artificial Intelligence Learning Models  <a name="aimodels"> </br>

### AI Learning Models: Knowledge-Based Classification  <a name="kbc"> </br>
- **Inductive Learning**: This type of AI learning model is based on inferring a general rule from datasets of input-output pairs. Algorithms SVM, ANN, kNN - are all inductive learners.
- **Deductive Learning**:  This type of AI learning technique starts with a series of rules and infers new rules that are more efficient in the context of a specific AI algorithm.
 - **Summary**: A deductive approach to teaching language starts by giving learners rules, then examples, then practice. It is a teacher-centred approach to presenting new content. This is compared with an inductive approach, which starts with examples and asks learners to find rules, and hence is more learner-centred.

### AI Learning Models: Feedback-Based Classification <a name="fbc"> </br>

Based on the feedback characteristics, AI learning models can be classified as supervised, unsupervised, semi-supervised or reinforced.

—  **Unsupervised Learning**: Unsupervised models focus on learning a pattern in the input data without any external feedback. Clustering is a classic example of unsupervised learning models.

—  **Supervised Learning**: Supervised learning models use external feedback to learning functions that map inputs to output observations. In those models the external environment acts as a “teacher” of the AI algorithms.

—  **Semi-supervised Learning**: Semi-supervised learning is a class of supervised learning tasks and techniques that also make use of unlabeled data for training – typically a small amount of labeled data with a large amount of unlabeled data.
The goal of a semi-supervised model is to classify some of the unlabeled data using the labeled information set.

—  **Reinforcement Learning**: Reinforcement learning models use opposite dynamics such as rewards and punishment to “reinforce” different types of knowledge. This type of learning technique is becoming really popular in modern AI solutions.

## Data Mining Vs Machine Learning <a name="mlvsdm"></br>

**Machine learning** focuses on prediction, based on known properties learned from the training data.</br>
**Data mining** focuses on the discovery of (previously) unknown properties in the data. This is the analysis step of Knowledge Discovery in Databases.

**Note** : If you have a better explanation a pull request would be helpful.

## Workflow of Data Science Project <a name="workflow"></br>

Given a data science / machine learning project, what steps should we follow? Here's how we should tackle it:

* **Specify business objective.** Are we trying to win more customers, achieve higher satisfaction, or gain more revenues?
* **Define problem.** What is the specific gap in your ideal world and the real one that requires machine learning to fill? Ask questions that can be addressed using your data and predictive modeling (ML algorithms).
* **Create a common sense baseline.** But before you resort to ML, set up a baseline to solve the problem as if you know zero data science. You may be amazed at how effective this baseline is. It can be as simple as recommending the top N popular items or other rule-based logic. This baseline can also server as a good benchmark for ML algorithms.
* **Review ML literatures.** To avoid reinventing the wheel and get inspired on what techniques / algorithms are good at addressing the questions using our data.
* **Set up a single-number metric.** What it means to be successful - high accuracy, lower error, or bigger AUC - and how do you measure it? The metric has to align with high-level goals, most often the success of your business. Set up a single-number against which all models are measured.
* **Do exploratory data analysis (EDA).** Play with the data to get a general idea of data type, distribution, variable correlation, facets etc. This step would involve a lot of plotting.
* **Partition data.** Validation set should be large enough to detect differences between the models you are training; test set should be large enough to indicate the overall performance of the final model; training set, needless to say, the larger the merrier.
* **Preprocess.** This would include data integration, cleaning, transformation, reduction, discretization and more.
* **Engineer features.** Coming up with features is difficult, time-consuming, requires expert knowledge. Applied machine learning is basically feature engineering. This step usually involves feature selection and creation, using domain knowledge. Can be minimal for deep learning projects.
* **Develop models.** Choose which algorithm to use, what hyperparameters to tune, which architecture to use etc.
* **Ensemble.** Ensemble can usually boost performance, depending on the correlations of the models/features. So it’s always a good idea to try out. But be open-minded about making tradeoff - some ensemble are too complex/slow to put into production.
* **Deploy model.** Deploy models into production for inference.
* **Monitor model.** Monitor model performance, and collect feedbacks.
* **Iterate.** Iterate the previous steps. Data science tends to be an iterative process, with new and improved models being developed over time.

![](https://github.com/theainerd/MLInterview/blob/master/images/workflow.png)

## Parametric vs Nonparametric ?</br> <a name="tric"></br>
A learning model that summarizes data with a set of parameters of fixed size (independent of the number of training examples) is called a **parametric model**.</br>
A learning model where the number of parameters is not determined prior to training. On the contrary, nonparametric models (can) become more and more complex with an increasing amount of data.

## Discriminative vs Generative Learning Algorithm ?</br> <a name="dam"></br>
- **Discriminative algorithms model p(y|x; w)**, that is, given the dataset and learned parameter, what is the probability of y belonging to a specific class. A discriminative algorithm doesn't care about how the data was generated, it simply categorizes a given example</br>
 Ex: Linear Regression, Logistic Regression, Support Vector Machines etc.
 Given a training set, an algorithm like logistic regression or the perceptron algorithm (basically) tries to find a straight line—that is, a decision boundary—that separates the elephants and dogs. Then, to classify a new animal as either an elephant or a dog, it checks on which side of the decision boundary it falls, and makes its prediction accordingly.</br>

- **Generative algorithms model p(x|y)**, that is, the distribution of features given that it belongs to a certain class. A generative algorithm models how the data was generated.</br>
 Ex: Naive Bayes, Hidden Markov Models etc.
 First, looking at elephants, we can build a model of what elephants look like. Then, looking at dogs, we can build a separate model of what dogs look like. Finally, to classify a new animal, we can match the new animal against the elephant model, and match it against the dog model, to see whether the new animal looks more like the elephants or more like the dogs we had seen in the training set.

## What is cross validation ?</br> <a name="cv"></br>

Cross Validation is a technique to evaluate predictive models by partitioning the original sample into a training set to train the model, and a validation set to evaluate it. For ex: K fold CV divides the data into k folds, train on each k-1 folds and evaluate it on remaining 1 fold. The result of k models can be averaged to get a overall model performance.

Time - Series Cross Validation :  Use forward chaining strategy
![](https://github.com/theainerd/MLInterview/blob/master/images/10_fold_cv.png)

## What is overfitting? <a name="of"></br>

Overfitting or High Variance is a modeling error which is caused by a hypothesis function that fits the training data too close but does not generalise well to predict new data.
![](https://github.com/theainerd/MLInterview/blob/master/images/partitions-underfitting-vs-overfitting-regression-via-polynomial-degree.png)

## What is regularization? <a name="reg"></br>

Regulariztion is a technique to prevent overfitting by penalizing the coefficients of the cost function.

  ### Ridge Regression
  It performs ‘L2 regularization’, i.e. adds penalty equivalent to square of the magnitude of coefficients. Thus, it optimises the following:

    Objective = RSS + α * (sum of square of coefficients)

  ### Lasso Regression
  LASSO stands for Least Absolute Shrinkage and Selection Operator.Lasso regression performs L1 regularization, i.e. it adds a factor of sum of absolute value of coefficients in the optimisation objective.

      Objective = RSS + α * (sum of square of coefficients)

  ### Elastic nets
  A technique known as Elastic Nets, which is a combination of Lasso
  and Ridge regression is used to tackle the limitations of both Ridge and
  Lasso Regression.
  
  
## Loss Functions for Regression and Classification? <a name="lossfun"></br>

* **Regression Loss Function**
    * Square or l2 loss (not robust)
    * Absolute or Laplace loss (not differentiable)
    * Huber Loss (robust and differentiable) - In statistics, the Huber loss is a loss function used in robust regression, that is less sensitive to outliers in data than the squared error loss. 
    
    ![](https://upload.wikimedia.org/wikipedia/commons/thumb/c/cc/Huber_loss.svg/1080px-Huber_loss.svg.png)
      
    ![](https://wikimedia.org/api/rest_v1/media/math/render/svg/e384efc4ae2632cb0bd714462b7c38c272098cf5)
    
* **Classification Loss Function**
    * SVM/Hinge loss - The hinge loss is used for "maximum-margin" classification, most notably for support vector machines (SVMs).
    * log loss (Logarithmic Loss) - measures the performance of a classification model where the prediction input is a probability value between 0 and 1. The goal of our machine learning models is to minimize this value. A perfect model would have a log loss of 0. Log loss increases as the predicted probability diverges from the actual label. **Accuracy vs Log LOSS**::
    
    ** **Accuracy** is the count of predictions where your predicted value equals the actual value. Accuracy is not always a good indicator because of its yes or no nature.
    
    ** **Log Loss** takes into account the uncertainty of your prediction based on **how much it varies** from the actual label. This gives us a **more nuanced view** into the performance of our model
    
    
## How do you handle missing or corrupted data in a dataset? <a name="missing"></br>
Before jumping to the methods of data imputation, we have to understand the reason why data goes missing.

  - **Missing at Random (MAR)**: Missing at random means that the propensity for a data point to be missing is not related to the missing data, but it is related to some of the observed data.
  -- Mean, Median and Mode Imputation
  
  - **Missing Completely at Random (MCAR)**: The fact that a certain value is missing has nothing to do with its hypothetical         value and with the values of other variables.
  -- Multiple Imputation
  
  - **Missing not at Random (MNAR)**: Two possible reasons are that the missing value depends on the hypothetical value (e.g.         People with high salaries generally do not want to reveal their incomes in surveys) or missing value is dependent on some other variable’s value (e.g. Let’s assume that females generally don’t want to reveal their ages! Here the missing value in age variable is impacted by gender variable).
  -- KNN (K Nearest Neighbors)

## How would you handle an imbalanced dataset? <a name="imb"></br>
* Using a better metrics like AUROC, Precision, Recall etc.
* Cost-sensitive Learning
* Over sampling of the minority class or Under sampling of the majority class.
* SMOTE (Synthetic Minority Over-sampling Technique.)
* Anomaly Detection

## how do you detect outliers? <a name="out"></br>

Outliers are extreme values that deviate from other observations on data , they may indicate a variability in a measurement, experimental errors or a novelty.

Most common causes of outliers on a data set:

* Data entry errors (human errors)
* Measurement errors (instrument errors)
* Experimental errors (data extraction or experiment planning/executing errors)
* Intentional (dummy outliers made to test detection methods)
* Data processing errors (data manipulation or data set unintended mutations)
* Sampling errors (extracting or mixing data from wrong or various sources)

Some of the most popular methods for outlier detection are:

* **Extreme Value Analysis**: Determine the statistical tails of the underlying distribution of the data. For example, statistical methods like the z-scores on univariate data.
* **Probabilistic and Statistical Models**: Determine unlikely instances from a probabilistic model of the data. For example, gaussian mixture models optimized using expectation-maximization.
* **Linear Models**: Projection methods that model the data into lower dimensions using linear correlations. For example, principle component analysis and data with large residual errors may be outliers.
* **Proximity-based Models**: Data instances that are isolated from the mass of the data as determined by cluster, density or nearest neighbor analysis.
* **Information Theoretic Models**: Outliers are detected as data instances that increase the complexity (minimum code length) of the dataset.
* **High-Dimensional Outlier Detection**: Methods that search subspaces for outliers give the breakdown of distance based measures in higher dimensions (curse of dimensionality).
