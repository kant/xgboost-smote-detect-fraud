# Fraud prediction using imbalanced data

Credit-card fraud is a growing problem worldwide which costs upwards of billions of dollars per year. It is a wide-ranging term for theft and fraud committed using or involving a payment card, such as a credit card or debit card, as a fraudulent source of funds in a transaction. The purpose may be to obtain goods without paying, or to obtain unauthorized funds from an account. According to 2016 data released by ACI Worldwide and financial industry consultant Aite Group, nearly 1 in 3 consumers globally have been victimized by card fraud in the past five years. The benchmark survey also reported that 14 of the 17 countries surveyed experienced an increase in card fraud between 2014 and 2016. A 2016 iovation/Aite Group study projected impact on financial fraud reports that credit card fraud losses may climb to as much as $10 billion in the United States alone by 2020. Therefore, it becomes the need of the hour to use technology and reduce these alarming numbers.

Predictive analytics uses historical data to predict future events. Typically, historical data is used to build a mathematical model that captures important trends. That predictive model is then used on current data to predict what will happen next, or to suggest actions to take for optimal outcomes. We use the same approach to draw a solution to the credit card fraud detection problem Fraudulent transactions are costly, but it is too expensive and inefficient to investigate every transaction for fraud. Even if possible, investigating innocent customers could prove to be a very poor customer experience, leading some clients to leave the business. Hence, using a predicative model we can automatically identify and prioritize likely fraudulent activity. Fraud units can then investigate only those incidents likely to require it. As compared to the other solutions present, this is an efficient, and an accurate solution devoid of human error. We aim to minimize instances where it is predicted as fraud but it is not actually fraud(False Positives) and those where it is fraud but is not predicted as one(False Negatives).

When the reader has completed this code pattern, they will understand how to:

* Build predictive models using Bagging & Boosting statistical techniques.
* Run different statistical models and evaluate the results.
* Sample the data to create a balance between the majority & minority populations to handle imbalanced data.
* Demonstrate how the sampling techniques can give a lift to the accuracy of the predictive model.

# Architecture Diagram

![](https://github.com/IBM/xgboost-smote-detect-fraud/blob/master/image/architecture.png)

1. User logs into Watson Studio, creates an instance which includes object storage.
2. User uploads the csv file to the object storage.
3. User imports a Jupyter Notebook from the URL.
4. User runs the statistical models and sampling techniques in the notebook.
5. User exports the predictive modelling results to the object storage.

## Included components

* [IBM Watson Studio](https://www.ibm.com/cloud/watson-studio): Analyze data using RStudio, Jupyter, and Python in a configured, collaborative environment that includes IBM value-adds, such as managed Spark.

* [IBM Cloud Object Storage](https://console.ng.bluemix.net/catalog/services/object-storage/?cm_sp=dw-bluemix-_-code-_-devcenter): An IBM Cloud service that provides an unstructured cloud data store to build and deliver cost effective apps and services with high reliability and fast speed to market. This code pattern uses Object Storage (Swift API).

* [Jupyter Notebooks](http://jupyter.org/): An open-source web application that allows you to create and share documents that contain live code, equations, visualizations and explanatory text.

## Featured technologies

* [Data Science](https://developer.ibm.com/code/technologies/data-science/): Systems and scientific methods to analyze structured and unstructured data in order to extract knowledge and insights.
* [Analytics](https://developer.ibm.com/code/technologies/analytics/): Analytics delivers the value of data for the enterprise.
* [Python](https://www.python.org/): Python is a programming language that lets you work more quickly and integrate your systems more effectively.
* [Jupyter Notebooks](http://jupyter.org/): An open-source web application that allows you to create and share documents that contain live code, equations, visualizations and explanatory text.

# Watch the Video

NA

# Steps

Follow these steps to setup and run this code pattern. The steps are
described in detail below.

1. [Sign up for IBM Cloud](#1-sign-up-for-ibm-cloud)
1. [Sign up for Watson Studio](#2-sign-up-for-watson-studio)
1. [Create the notebook](#3-create-the-notebook)
1. [Add the data](#4-add-the-data)
1. [Insert the dataframe](#5-insert-the-dataframe)
1. [Run the notebook](#6-run-the-notebook)
1. [Analyze the results](#7-analyze-the-results)

## 1. Sign up for IBM Cloud

Sign up for IBM [**Cloud**](https://console.bluemix.net/). By clicking on create a free account you will get 30 days trial account.

## 2. Sign up for Watson Studio

Sign up for IBM's [Watson Studio](http://dataplatform.ibm.com/). By creating a project in Watson Studio a free tier ``Object Storage`` service will be created in your IBM Cloud account. Choose the storage type as Object Storage (Swift API) for this code pattern.

## 3. Create the notebook

* Open [IBM Watson Studio](https://dataplatform.ibm.com).
* Click on `Create notebook` to create a notebook.
* Select the `From URL` tab.
* Enter a name for the notebook.
* Optionally, enter a description for the notebook.
* Enter this Notebook URL: https://github.com/IBM/xgboost-smote-detect-fraud/blob/master/notebook/Fraud_Detection.ipynb
* Select the free Anaconda runtime.
* Click the `Create` button.

![](https://github.com/IBM/xgboost-smote-detect-fraud/blob/master/image/create_notebook.PNG)

## 4. Add the data

Use `Find and Add Data` (look for the `10/01` icon)
and its `Files` tab. From there you can click
`browse` and add data files from your computer.

Note: The data file in the `data` directory - `creditcard.csv` has been downloaded from https://www.kaggle.com/mlg-ulb/creditcardfraud/data . The data file used in this pattern is the subset of the original data downloaded from Kaggle where random samples of 20% observations has been extracted from the original data. 

![](https://github.com/IBM/xgboost-smote-detect-fraud/blob/master/image/add_file.png)

Note: The data file is in the `data` directory

## 5. Insert the DataFrame

Select the cell below `2. Read the Data & convert it into Dataframe` section in the notebook.

Use `Find and Add Data` (look for the `10/01` icon) and its `Files` tab. You should see the file names uploaded earlier. Make sure your active cell is the empty one created earlier. Select `Insert to code` (below your file name). Click `Insert pandas DataFrame` from drop down menu.

![](https://github.com/IBM/xgboost-smote-detect-fraud/blob/master/image/insert%20df.PNG)

## 6. Run the notebook

When a notebook is executed, what is actually happening is that each code cell in
the notebook is executed, in order, from top to bottom.

Each code cell is selectable and is preceded by a tag in the left margin. The tag
format is `In [x]:`. Depending on the state of the notebook, the `x` can be:

* A blank, this indicates that the cell has never been executed.
* A number, this number represents the relative order this code step was executed.
* A `*`, this indicates that the cell is currently executing.

There are several ways to execute the code cells in your notebook:

* One cell at a time.
  * Select the cell, and then press the `Play` button in the toolbar.
* Batch mode, in sequential order.
  * From the `Cell` menu bar, there are several options available. For example, you
    can `Run All` cells in your notebook, or you can `Run All Below`, that will
    start executing from the first cell under the currently selected cell, and then
    continue executing all cells that follow.
    
## 7. Analyze the results

We can evaluate the statistical outputs in this section after each run of the model & play around with hyper parameters for better results. 

![](https://github.com/IBM/xgboost-smote-detect-fraud/blob/master/image/analyze_results.PNG)

###  The flow of the whole process could be summed up in the following diagram

![](https://github.com/IBM/xgboost-smote-detect-fraud/blob/master/image/flow.PNG)

When faced with imbalanced data sets there is no one stop solution to improve the accuracy of the prediction model. In most cases, synthetic techniques like SMOTE will outperform the conventional oversampling and undersampling methods. Bagging improves stability & accuracy of machine learning algorithms. Boosting is an ensemble technique to combine weak learners to create a strong learner that can make accurate predictions.
    
  
# Troubleshooting

[See DEBUGGING.md.](DEBUGGING.md)

# License

[Apache 2.0](LICENSE)

