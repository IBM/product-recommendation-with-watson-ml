# Build a product recommendation engine with Watson Machine Learning and PixieApps

In this code pattern historical shopping data is used to build a recommendation engine with Spark and Watson Machine Learning. The model is then used in an interactive PixieApp in which a shopping basket is simulated and used to create a list of recommendations. 

When you have completed this code patterns, you will understand how to:

* Use [Jupyter Notebooks](http://jupyter.org/) in [IBM Watson Studio](https://dataplatform.ibm.com/)
* Build a recommendation model with SparkML and Watson Machine Learning to provide product recommendations for customers based on their purchase history
* Build an interactive dashboard using [PixieApps](https://ibm-watson-data-lab.github.io/pixiedust/pixieapps.html)

The intended audience is data scientists and developers interested in building, deploying and testing machine learning models from a Jupyter notebook with Watson Machine Learning.

## Flow

[](flow.png)

1. Load the provided notebook into Watson Studio
1. Load and transform the customer data in the notebook
1. Build a k-means clustering model with SparkML 
1. Deploy the model to Watson Machine Learning 
1. Test and compare the models build in the notebook and through the Watson Machine Learning API
1. Use the API to build an interactive PixieApp 

## Included Components

* [IBM Watson Studio](https://console.bluemix.net/catalog/services/watson-studio): a suite of tools and a collaborative environment for data scientists, developers and domain experts
* [IBM Apache Spark](https://console.ng.bluemix.net/catalog/services/apache-spark): an open source cluster computing framework optimized for extremely fast and large scale data processing
* [IBM Watson Machine Learning](https://console.bluemix.net/catalog/services/machine-learning): a set of REST APIs to develop applications that make smarter decisions, solve tough problems, and improve user outcomes

## Featured Technologies

* [Jupyter notebooks](http://jupyter.org/): an open-source web application that allows you to create and share documents that contain live code, equations, visualizations and explanatory text
* [PixieDust](https://github.com/ibm-cds-labs/pixiedust): Python helper library for Jupyter notebooks
* [PixieApps](https://ibm-cds-labs.github.io/pixiedust/pixieapps.html): Python library to write and run UI elements for analytics directly in a Jupyter notebook

# Watch the video


# Steps

Follow these steps to setup and run this code pattern. The steps are described in detail below.

1. [Sign up for Watson Studio](#1-sign-up-for-watson-studio)
2. [Create a Project](#2-create-a-project)
1. [Create IBM Cloud services](#3-create-ibm-cloud-services)
1. [Create the notebook](#4-create-the-notebook)
1. [Update the notebook with service credentials](#5-update-the-notebook-with-service-credentials)
1. [Run the notebook](#6-run-the-notebook)
1. [Build and run the recommendation PixieApp](#7-build-the-pixieapp)

## 1. Sign up for Watson Studio

Sign up for IBM's [Watson Studio](https://dataplatform.ibm.com). By creating a project in Watson Studio a free tier ``Object Storage`` service will be created in your IBM Cloud account. Take note of your service names as you will need to select them in the following steps.

> Note: When creating your Object Storage service, select the ``Free`` storage type in order to avoid having to pay an upgrade fee.

## 2. Create a project

In Watson Studio create a new project which will contain the notebook and connections to the IBM Cloud services.

## 3. Create IBM Cloud services

Create the following IBM Cloud services:

* [**Watson Machine Learning**](https://console.bluemix.net/catalog/services/natural-language-understanding)
* [**Spark**](https://console.bluemix.net/catalog/services/natural-language-understanding)
* https://github.com/IBM/pixiedust-traffic-analysis/blob/master/doc/source/images/createSparkService.png

## 4. Create the notebook

* In [Watson Studio](https://dataplatform.ibm.com), click on `Create notebook` to create a notebook.
* Create a project if necessary, provisioning an object storage service if required.
* In the `Assets` tab, select the `Create notebook` option.
* Select the `From URL` tab.
* Enter a name for the notebook.
* Optionally, enter a description for the notebook.
* Enter this Notebook URL: https://github.com/IBM/watson-document-co-relation/blob/master/notebooks/watson_correlate_documents.ipynb
* Select the **Spark** runtime.
* Click the `Create` button.

## 5. Update the notebook with service credentials

#### Add the Watson Machine Learning credentials to the notebook
Select the cell below `2.1 Add your service credentials from IBM Cloud for the Watson services` section in the notebook to update the credentials for Watson Natural Language Understanding. 

Open the Watson Natural Language Understanding service in your [IBM Cloud Dashboard](https://console.bluemix.net/dashboard/services) and click on your service, which you should have named `wdc-NLU-service`.

Once the service is open click the `Service Credentials` menu on the left.

![](doc/source/images/service_credentials.png)

In the `Service Credentials` that opens up in the UI, select whichever `Credentials` you would like to use in the notebook from the `KEY NAME` column. Click `View credentials` and copy `username` and `password` key values that appear on the UI in JSON format.

![](doc/source/images/copy_credentials.png)

Update the `username` and `password` key values in the cell below `2.1 Add your service credentials from IBM Cloud for the Watson services` section.

![](doc/source/images/watson_nlu_credentials.png)

## 6. Run the notebook

When a notebook is executed, what is actually happening is that each code cell in
the notebook is executed, in order, from top to bottom.

> IMPORTANT: The first time you run your notebook, you will need to install the necessary
packages in section 1.1 and then `Restart the kernel`.

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
* At a scheduled time.
  * Press the `Schedule` button located in the top right section of your notebook
    panel. Here you can schedule your notebook to be executed once at some future
    time, or repeatedly at your specified interval.

## 7. Build and run the recommendation PixieApp


# Other scenarios and use cases for which a solution can be built using the above methodology

[See USECASES.md.](USECASES.md)

# Related links

[Mine insights from software development artifacts](https://developer.ibm.com/code/patterns/mine-insights-from-software-development-artifacts/)

[Get insights on personal finance data](https://developer.ibm.com/code/?p=29292&preview=true)

# Troubleshooting

[See DEBUGGING.md.](DEBUGGING.md)

# License

[Apache 2.0](LICENSE)


