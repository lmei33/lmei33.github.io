---
layout: post
title:  "Attrition Analysis"
date:   2019-02-20
excerpt: "A project to predict employee attrition and identify influtial factors to reduce employee attrition."
project: true
tag:
- python 
- colabnotebook
- attrition
- machinelearning
comments: true
---

[CLICK HERE: Check out My Colab Notebook in Github Repo](https://github.com/lmei33/trial/blob/master/Employee_Attrition_Analysis.ipynb)

![0](https://mk0at44uvaxh7f73.kinstacdn.com/wp-content/uploads/2017/12/Topic-1.png)    


      
## Overview
Attrition, in Human Resource terminology, refers to the phenomenon of the employees leaving the company. Employee attrition is always the focus of Human Resource Management. This project aims to  predict employee attrition and identify influtial factors to reduce employee attrition. 

The original data is from IBM HR Analytics Employee Attrition & Performance:
[Link to The Data set](https://www.kaggle.com/pavansubhasht/ibm-hr-analytics-attrition-dataset)


## Process  

### Data Ingest

### EDA 
* Attrition Proportion
![1](https://raw.githubusercontent.com/lmei33/lmei33.github.io/master/assets/img/1.png)    

* Attrition Factors Heatmap
![2](https://raw.githubusercontent.com/lmei33/lmei33.github.io/master/assets/img/2.png) 

* Take a look at the objective factors
![3](https://raw.githubusercontent.com/lmei33/lmei33.github.io/master/assets/img/3.png) 

* Analysis on Monthly Income
![4](https://raw.githubusercontent.com/lmei33/lmei33.github.io/master/assets/img/4.png) 
  Break the result by Job Involvement
![5](https://raw.githubusercontent.com/lmei33/lmei33.github.io/master/assets/img/5.png) 

* Satisfaction
![6](https://raw.githubusercontent.com/lmei33/lmei33.github.io/master/assets/img/6.png)


### Model
After several trials, I chose Logistic Regression

---

{% highlight yaml %}
from sklearn.model_selection import train_test_split

predictors = IBM_Attrition_Nu.drop(['Attrition'], axis=1)
target = IBM_Attrition_Nu["Attrition"]
x_train, x_val, y_train, y_val = train_test_split(predictors, target, test_size = 0.22, random_state = 0)

from sklearn.metrics import accuracy_score
from sklearn.linear_model import LogisticRegression

logreg = LogisticRegression()
logreg.fit(x_train, y_train)
y_pred = logreg.predict(x_val)
acc_logreg = round(accuracy_score(y_pred, y_val) * 100, 2)
print(acc_logreg)
>> 87.35
{% endhighlight %}

---

* Confusion Matrix
![7](https://raw.githubusercontent.com/lmei33/lmei33.github.io/master/assets/img/7.png)

* Top 6 Influential Factors
![8](https://raw.githubusercontent.com/lmei33/lmei33.github.io/master/assets/img/8.png)

