
# 1st MLSecOps Project (C2) - High Level Overview

This is a Machine Learning 'operationalization' project [showcasing the know-how by determining deployments targets, enabling foresights, baselining performance metrics, scaning logs and benchmarking], as part of the ML Engineer for Microsoft Azure Nanodegree Program [ND00333-AZMLND-C2] from Udacit (in order to prepare for Microsoft [Designing and Implementing a Data Science Solution on Azure] Exam DP-100).


### The Problem Statement:
The business goal/objective was binary classification inferencing [for decision intel foresights] on product sales (predicting if the product (term deposit) could be subscribed to (or not), when a bank client is contacted?). [... more on the Bank [Direct] Marketing dataset whitepaper](https://core.ac.uk/download/pdf/55631291.pdf)


### The Solution:
Rather than the usual "VotingEnsemble", the best performing model was an Azure AutoML [MaxAbsScaler & LightGBM] algorithm having had scored a %95.09 AUC weighted (in contrast to the other run type which was a pipeline same algorithm's best model having scored a %94.5 AUC weighted); using such AutoML to train the best ML model before its OpenAPI endpoint gets deployed for production-ready consumption by the other ecosystem microservices (including azure automation and/or logic apps) for optimal 'Decision Intelligence MLSecOps' synergy.



## Architectural Diagram

Below is the formal diagram related to the visualization of the project's main steps (as listed in the next section):

![Project-key-steps](images/Project-key-steps.png?raw=true)


## Key Steps

### MLSecOps Prepping & Authentication:
Mainly creating a Service Principal account and associating it with a specific workspace.

### Automating an ML Experiment:
Creating an experiment using Automated ML, configuring a compute cluster, and using it to run an experiment.


### Deploying the Best Model:
Deploying the AutoML run's Best Model for interacting with the HTTP API service and or the model [over POST requests].


### Logs Enabling:
Retrieving logs by enabling Application Insights at deploy time [with a check-box, or later by runing a code].


### Documenting Swagger:
Consuming the deployed model using the [OpenAPI] Swagger JSON file to interact with the trained model.


### Consuming Model Endpoints:
Consuming the deployed model using the endpoint's scoring_uri and its key that was generated post deployment.



### Pipeline Creating and Publishing:
Updating a Jupyter Notebook with already created [same AutoMl's] keys, URI, dataset, cluster, and model names.



## Areas of Improvement

Potential future improvements could be identified as:

- Retraining Hyperparameter Tuning with HyperDrive using Bayesian and/or 'Entire Grid' sampling.
- Extending AutoML config to include more parameters.
- Documenting XAI and [operationalizing] model [explanation] as a web service, using the [interpretability package] to explain ML models & predictions.
- Exporting Models with ONNX to be deployed to a DLT connected Dapp device.
- Integrating App Insights with Sentinel and/or CASB.



## [Optional] Standout Suggestions

Pending standout suggestions that were attempted include:

- Completing the optional items about load-testing the endpoint.
- Using a [Parallel Run Step](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-use-parallel-run-step) in a pipeline. - Testing a [local container](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-deploy-package-models) with a downloaded model.
- Exporting the model for [supportting ONNX](https://docs.microsoft.com/en-us/azure/machine-learning/concept-onnx).


# 1st MLSecOps Project (C2) - Low Level Specification


## Screencast Recording Documentation

  * **1st MLSecOps Project (C2) Screencast Demo in 5 mins: https://vimeo.com/510089284**
  * 1st MLSecOps Project (C2) Screencast Demo in 10 mins: https://vimeo.com/510089644

Above recordings' links were for the MLSecOps demo of the entire process of the actionable [production ready] project; , including showcasing of:
1. Working deployed ML model endpoint.
2. Deployed Pipeline.
3. Available AutoML Model.
4. Successful API requests to the endpoint with a JSON payload.


## Required Screenshots' Documentation
Below are breif describtions along with the required screenshots to demonstrate the completed project [overall end-to-end workflow's] critical stages criteria meeting its various main steps's specifications:


## Part I: Machine Learning Ops Principles


###### Role Owner - NO ERROR OR TRACEBACK
 !az ml workspace share -w workspace1st -g dsvm1st --user --- --role owner
###### Udacity no authorization to perform roleAssignmentswrite over scope
1st-AutoML-001 Role Owner - NO ERROR OR TRACEBACK
 

 
 
 


##### A link to the screencast video on YouTube (or a similar alternative streaming service):
In case you are unable to provide an audio file, you can include a written description of your script instead of audio, if you prefer. Please include it in your README file.

### Create a professional, portfolio-ready demo of deploying a ML model.
#### The screencast should meet the following criteria:
##### Screencast is 1-5 minutes in length, Audio is clear and understandable, Video is 1080P or higher with 16:9 aspect ratio, and text is readable)
#### The screencast shows the entire process of the working ML application, including a demonstration of:
##### Working deployed ML model endpoint.
##### Deployed Pipeline.
##### Available AutoML Model.
##### Successful API requests to the endpoint with a JSON payload.


## Part II: Deploy model in Azure ML Studio


### Create a new AutoML run


#### The submission includes screenshots of:

##### “Registered Datasets” in ML Studio shows "Bankmarketing" dataset available:
1st-AutoML-002 Registered Datasets in ML Studio shows [Bankmarketing] dataset available
 

 
##### The Auto ML experiment is shown as completed:

###### Auto ML experiment is shown as completed
 


#### Screeshot of the Auto ML Best Model after experiment completes:

###### Auto ML Best Model after experiment completes



### Deploy a model and consume a model endpoint via an HTTP API


#### The submission includes screenshots of:

##### Endpoints section in Azure ML Studio, showing that “Application Insights enabled” says “true”:
1st-AutoML-003b Endpoints section in Azure ML Studio, showing that 'Application Insights enabled' says 'true'
 
 

##### Logging is enabled by running the provided logs.py script:
1st-AutoML-004a Logging is enabled by running the provided logs.py script
 

1st-AutoML-004b endpoint and benchmark
 


##### Swagger runs on localhost showing the HTTP API methods and responses for the model:
1st-AutoML-005x Swagger runs on localhost showing the HTTP API methods and responses for the model
 


##### endpoint.py script runs against the API producing JSON output from the model:

###### AutoML - endpoint.py script runs against the API producing JSON output from the model



##### [OPTIONAL] Apache Benchmark (ab) runs against the HTTP API using authentication keys to retrieve performance results:
N/A




## Part III: Publish an ML Pipeline


### Create and publish a pipeline


#### The submission includes screenshots of:


##### The pipeline section of Azure ML studio, showing that the pipeline has been created:

###### Udacity - pipeline section of Azure ML studio, showing that the pipeline has been created



##### The Bankmarketing dataset with the AutoML module:

###### Udacity Registered Datasets in ML Studio shows Bankmarketing dataset available
 


##### The “Published Pipeline overview”, showing a REST endpoint and a status of ACTIVE:

###### Udacity - Published Pipeline overview, showing a REST endpoint and a status of ACTIVE
 




### Configure a pipeline with the Python SDK


#### A screenshot of the Jupyter Notebook is included in the submission:


##### showing the “Use RunDetails Widget” with the step runs:

###### Udacity - Use RunDetails Widget with the step runs
 


### Use a REST endpoint to interact with a Pipeline


#### The submission includes screenshots of:

##### ML studio showing the pipeline endpoint as Active:
 

##### ML studio showing the scheduled run:

###### Udacity - ML studio showing the scheduled run








### Machine Learning Ops Principles

###### Role Owner authorization to perform roleAssignmentswrite over scope - NO ERROR OR TRACEBACK
 !az ml workspace share -w workspace1st -g dsvm1st --user --- --role owner
![Udacity no authorization to perform roleAssignmentswrite over scope](images/101.png?raw=true)
![1st-AutoML-001 Role Owner - NO ERROR OR TRACEBACK - local](images/101.png?raw=true)
![1st-AutoML-001 Role Owner - NO ERROR OR TRACEBACK @ already exists](images/102.png?raw=true)



### Deploy model in Azure ML Studio



#### Create a new AutoML run


##### The submission includes screenshots of:

####### “Registered Datasets” in ML Studio shows "Bankmarketing" dataset available:

![1st-AutoML-002 Registered Datasets in ML Studio shows [Bankmarketing] dataset available](images/201.png?raw=true)
 

 
####### The Auto ML experiment is shown as completed:

![Auto ML experiment is shown as completed](images/203.png?raw=true)



##### Screeshot of the Auto ML Best Model after experiment completes:

![Auto ML Best Model after experiment completes](images/Auto ML Best Model after experiment completes.png?raw=true)
 


#### Deploy a model and consume a model endpoint via an HTTP API


##### The submission includes screenshots of:


####### Endpoints section in Azure ML Studio, showing that “Application Insights enabled” says “true”:

![1st-AutoML-003b Endpoints section in Azure ML Studio, showing that 'Application Insights enabled' says 'true'](images/301.png?raw=true)
 

####### Logging is enabled by running the provided logs.py script:

![1st-AutoML-004a Logging is enabled by running the provided logs.py script](images/303.png?raw=true)


![1st-AutoML-004b endpoint and benchmark](images/305.png?raw=true)
 


####### Swagger runs on localhost showing the HTTP API methods and responses for the model:

![1st-AutoML-005x Swagger runs on localhost showing the HTTP API methods and responses for the model](images/401.png?raw=true)
 


####### endpoint.py script runs against the API producing JSON output from the model:

![AutoML - endpoint.py script runs against the API producing JSON output from the model](images/405.png?raw=true)
 


####### [OPTIONAL] Apache Benchmark (ab) runs against the HTTP API using authentication keys to retrieve performance results:

N/A




### Publish an ML Pipeline


#### Create and publish a pipeline


##### The submission includes screenshots of:


####### The pipeline section of Azure ML studio, showing that the pipeline has been created:

![Udacity - pipeline section of Azure ML studio, showing that the pipeline has been created](images/Udacity - pipeline section of Azure ML studio, showing that the pipeline has been created.png?raw=true)



####### The Bankmarketing dataset with the AutoML module:

![Udacity Registered Datasets in ML Studio shows Bankmarketing dataset available](images/Udacity Registered Datasets in ML Studio shows Bankmarketing dataset available.png?raw=true)
 



####### The “Published Pipeline overview”, showing a REST endpoint and a status of ACTIVE:

![Udacity - Published Pipeline overview, showing a REST endpoint and a status of ACTIVE](images/Udacity - Published Pipeline overview, showing a REST endpoint and a status of ACTIVE.png?raw=true)
 




#### Configure a pipeline with the Python SDK



##### A screenshot of the Jupyter Notebook is included in the submission:


####### showing the “Use RunDetails Widget” with the step runs:

![Udacity - Use RunDetails Widget with the step runs](images/Udacity - Use RunDetails Widget with the step runs.png?raw=true)
 


#### Use a REST endpoint to interact with a Pipeline


##### The submission includes screenshots of:


####### ML studio showing the pipeline endpoint as Active:
 

####### ML studio showing the scheduled run:

![Udacity - ML studio showing the scheduled run](images/Udacity - ML studio showing the scheduled run.png?raw=true)
 








