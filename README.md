# lung-cancer-prediction-and-explainable-analysis
# A Hybrid Learning Framework Balancing Prediction Accuracy and Interpretability
### Project Introduction
#### This project proposes a hybrid learning framework that balances prediction accuracy and interpretability. It aims to achieve high-performance prediction tasks by integrating various classical machine learning models and provides in-depth interpretability analysis to help users understand the model's decision-making process.
### Dataset
#### For our study, we used two datasets, one is RNA-seq dataset from TCGA program, which is comprehensive, open-access, and integrates multidimensional data, supporting in-depth analysis and personalized medicine development, and the other one is our own constructed clinical specimen testing data. 
### Framework Design
### （1）Model Selection
#### The framework integrates several classical machine learning models, including decision trees, random forests, AdaBoost, XGBoost, and Gaussian Naive Bayes. Each model has its strengths in different datasets and tasks. By combining them, the framework can leverage their respective advantages to enhance overall performance.
##### (a) Decision Trees: Intuitive and easy to interpret but prone to overfitting.
##### (b) Random Forests: Reduce overfitting risk by constructing multiple decision trees and voting.
##### (c) AdaBoost: Optimizes model performance by combining multiple weak learners with weighted sums.
##### (d) XGBoost: Builds on gradient boosting with various optimizations for outstanding performance.
##### (e) Gaussian Naive Bayes: Suitable for data with clear probability distributions.
### （2）Hyperparameter Optimization
#### For each individual learner, grid search is employed to find the optimal hyperparameter combination. Grid search evaluates model performance across all predefined hyperparameter combinations, identifying the best configuration for subsequent model training.
### （3）Feature Selection
#### After determining the hyperparameters, Sequential Forward Feature Selection (SFFS) is used to extract key features. SFFS starts from an empty set and incrementally adds features that most improve model performance until a preset condition is met. This effectively reduces feature dimensionality, enhancing training efficiency and generalization ability.
### （4）Ensemble Model
#### Once the individual learners are optimized and feature selection is complete, these models are combined into a powerful ensemble model. By designing appropriate integration strategies such as voting or weighted averaging, the framework maximizes the strengths of each model to improve overall prediction performance.
### Model Analysis and Interpretation
### （1）Sample-Level Analysis
#### Histograms and density plots are drawn at the sample level to intuitively display data distribution. Histograms clearly show the frequency distribution of feature values, helping to understand the overall data distribution shape. Density plots further smooth the histogram curves, more intuitively reflecting the probability density distribution of the data, providing a basis for subsequent analysis.
### （2）Overall-Level Analysis
#### At the overall level of the ensemble model, feature importance ranking, Partial Dependence Plots (PDP), and heatmaps are used for analysis.
##### (a) Feature Importance Ranking: By calculating the contribution of each feature to the model's prediction results, features are ranked. This helps identify the most critical features for model prediction, guiding feature engineering and model optimization.
##### (b) Partial Dependence Plots (PDP): Show the relationship between features and model prediction results. PDPs intuitively display the impact trend of a feature on model predictions at different values, helping to understand the model's dependence on features.
##### (c) Heatmaps: Visualize the correlation between features and the relationship between features and model outputs. Heatmaps use color intensity to represent numerical values, intuitively presenting the degree of association between features and their impact on model outputs, helping to discover potential feature interactions.
### （3）Local-Level Analysis
#### At the local level of the ensemble model, various methods are used to interpret individual learners.
##### (a) Decision Tree Decision Path Visualization: For decision tree models, visualizing their decision paths shows the decision-making process of the decision tree on the overall sample. This allows users to clearly see how each sample is classified or predicted along the decision tree's path, enhancing the interpretability of the decision tree model.
##### (b) SHAP Analysis: Using SHAP values to analyze key features of each individual learner on the overall sample. SHAP values measure the contribution of features to model predictions, assigning a contribution value to each feature to reveal its importance to the model output. Additionally, force_plot is used for visualization to intuitively display the feature contributions of a single sample, helping users understand the model's prediction basis for that sample.
##### (c) LIME Analysis: Using LIME (Local Interpretable Model-agnostic Explanations) to interpret the predictions of each individual learner on a single sample. LIME approximates the behavior of complex models with local linear models, providing interpretable explanations for single-sample predictions. It generates the impact weights of each feature on the prediction result, helping users understand the model's decision logic for a single sample and further enhancing the model's transparency and credibility.
### Project Advantages
#### Efficiency: By integrating multiple classical models and combining hyperparameter optimization and feature selection techniques, the framework can efficiently handle large-scale datasets while ensuring model training speed and prediction performance.
#### Interpretability: Provides a rich set of interpretability analysis tools at the sample, overall, local, and single-sample levels, enabling users to deeply understand the model's decision-making process and enhance trust in the model.
#### Flexibility: Supports various model combinations and integration strategies, allowing users to flexibly adjust the framework's configuration according to specific task requirements.
