<br/>
<p align="center">
  <a href="https://github.com/erkutkoral/Titanic">
    <img src="https://www.rmg.co.uk/sites/default/files/styles/large/public/Atlantic%20liner%20%27Titanic%27%20%28Br%2C%201912%29%20sinking%2C%20bow%20first%2C%201912%2C%20with%20eight%20full%20lifeboats%20nearby%20and%20an%20iceberg%20in%20the%20distance_banner.jpg?itok=yNsuSDzG" alt="Logo" width="600" height="400">
  </a>

  <h3 align="center">Titanic Survial Prediction</h3>

  <p align="center">
    Performed EDA, Data Preprocessing, Machine Learning, Model Evaluation and Validation steps in Kaggle's Titanic Data Set.
    - Let's get started.
    <br/>
    <br/>
    <a href="https://github.com/erkutkoral/Titanic"><strong>Explore the docs »</strong></a>
    <br/>
    <br/>
    <a href="https://github.com/erkutkoral/Titanic/issues">Report Bug</a>
    .
    <a href="https://github.com/erkutkoral/Titanic/issues">Request Feature</a>
  </p>
</p>

![Contributors](https://img.shields.io/github/contributors/erkutkoral/Titanic?color=dark-green) ![Issues](https://img.shields.io/github/issues/erkutkoral/Titanic) 

## Table Of Contents

* [About the Project](#about-the-project)
* [Technologies-Libraries-Frameworks](#technologies-libraries-frameworks)
* [Roadmap](#roadmap)
* [Conclusion](#conclusion)
* [Authors](#authors)

## About The Project

The sinking of the Titanic is one of the most infamous shipwrecks in history. On April 15, 1912, during her maiden voyage, the widely considered “unsinkable” RMS Titanic sank after colliding with an iceberg. Unfortunately, there weren’t enough lifeboats for everyone onboard, resulting in the death of 1502 out of 2224 passengers and crew. While there was some element of luck involved in surviving, it seems some groups of people were more likely to survive than others.

## Technologies-Libraries-Frameworks

Python Libraries: Numpy, Pandas, Matplotlib, Seaborn, Scikit-Learn.

## Roadmap

1. Exploratory Data Analysis
2. Feature Extraction
3. Handling Outliers
4. Handling Missing Values
5. Machine Learning
6. Model Evaluation

## Conclusion
- **Exploratory Data Analysis Insights:**
  - More than half of the passengers on the ship did not survive.
  - There are some people who did not pay anything to travel with ship. Its suspicious but maybe they are crew members.
  - Females tend to survive more than men.
  - Boarding from port C halfed the survival rate.
  - Travel class affected survival. We could also understand this information intuitively. We confirmed it.
  - 1 to 3 close relatives changed the survival rate to tending to survive more.

- **Preprocessing Insights**:
  - Cabin variable has the most missing values among others and having cabin number impacts survival rate drastically so created a variable about having cabin number.
  - The name letter count variable is a variable that specifies the number of letters in the name. It is derived from the relationship between name length and reputation.
  - Thought the same thing about word count.
  - In Name variable there are some patterns about titles. Created title variable, also created a doctor controller variable to see who is doctor in the ship.
  - Saw that survival rate is affecting by family size so created 2 variables about defining whether passenger is alone or not and how many relatives does passenger have.
  - Classifying Age variable may affect some level in model so created a categorical variable from age defining passengers "young", "mature", "senior" positions.
  - Created new Age x passenger class variable to get more sensetive classes.

  - Age and Fare variables have outliers, cutted from their edges with %5 and %95 quartile ratios.
  - Used Robust Scaler to reduce affecting ratio from outliers.
  - Performed One-Hot Encoding.
  - Performed Rare Encoding to reduce classes which are nearly zero affect in target variable.
 
  - Used Light GBM for modeling part.
  - Evaluated Learning Curve, Area Under Curve, Feature Importances.
    - **Learning Curve Insights:**
      - Increasing the training set size did not affect so much in train set and it was setted in higher scores.
      -  In the same time, the score of test set is increasing but its not enough to see the ending.
      -  With this view, it seems like model is overfitted. It has higher score in train set so it learnt everything in train set but when it tried to predict unseen data it did not do it proper but with increasing sample size it can meet in the middle with train set.
      -  Adding some data can show us more clean view if its not possible we can go through the hyperparameter optimization.
      -  Also, we can check learning_rate, n_estimators and colsample_bytree hyperparameters. They are directly affecting overfitting situations with optimizing gradient descent and tree structure.
    - **Area Under Curve Insights:**
        - There were fluctuations in the estimates for different threshold values.
        - Our curve did not fully cover the area. This means there is a better model
    - **Feature Importances Insights:**
        - Letter count and word count features are in top 5 features.
        - Age x Pclass variable in top features.
        - There are variables that affect the model with literally 0. All of them are classes of new variables so we can drop these useless classes and we can create new model without them.


## Authors

* **Erkut Koral** - [LınkedIn](https://www.linkedin.com/in/erkutkoral/)
