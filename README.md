# Kidney_Disease_Classification
End to End Kidney Disease Classification model using MLFlow, DVC, DagsHub, AWS, Github Actions, Docker

## Kidney-Disease-Classification-MLflow-DVC

## Workflows

1. Update config.yaml
2. Update secrets.yaml [Optional]
3. Update params.yaml
4. Update the entity
5. Update the configuration manager in src config
6. Update the components
7. Update the pipeline 
8. Update the main.py
9. Update the dvc.yaml
10. app.py

# How to run?
### STEPS:

Clone the repository

```bash
https://github.com/Jkanishkha0305/Kidney_Disease_Classification
```
### STEP 01 - Create a conda environment after opening the repository

```bash
conda create -n kidney python=3.8 -y
```

```bash
conda activate kidney
```


### STEP 02 - install the requirements
```bash
pip install -r requirements.txt
```

### STEP 03 - collect dataset
Dataset : Kaggel [CT KIDNEY DATASET: Normal-Cyst-Tumor and Stone]    
Dataset Link : https://www.kaggle.com/datasets/nazmul0087/ct-kidney-dataset-normal-cyst-tumor-and-stone  
Size : 1.66 GB   
Files : 12.4k Files


### Step 04 - prepare base model 
Keras API link : https://keras.io/api/applications/  
Model Chosen : VGG16   
Model link : https://keras.io/api/applications/vgg/#vgg16-function   
Image size : 244x244x3


## MLflow

- [Documentation](https://mlflow.org/docs/latest/index.html)

- [MLflow tutorial](https://youtu.be/qdcHHrsXA48?si=bD5vDS60akNphkem)

- [MLflow Model Registry Docs](https://mlflow.org/docs/latest/model-registry.html#api-workflow)

##### cmd
- mlflow ui


### dagshub
[dagshub](https://dagshub.com/)

```bash
import dagshub
dagshub.init(repo_owner='Jkanishkha0305', repo_name='Kidney_Disease_Classification', mlflow=True)

import mlflow
with mlflow.start_run():
  mlflow.log_param('parameter name', 'value')
  mlflow.log_metric('metric name', 1)
```  


MLFLOW_TRACKING_URI=https://dagshub.com/Jkanishkha0305/Kidney_Disease_Classification.mlflow \
MLFLOW_TRACKING_USERNAME=entbappy \  
MLFLOW_TRACKING_PASSWORD=6bd16d7f5ee713eba8329fb353c637dc8de93b55 \  
python script.py

Run this to export as env variables:

```bash

export MLFLOW_TRACKING_URI=https://dagshub.com/Jkanishkha0305/Kidney_Disease_Classification.mlflow

export MLFLOW_TRACKING_USERNAME=Jkanishkha0305

export MLFLOW_TRACKING_PASSWORD=6bd16d7f5ee713eba8329fb353c637dc8de93b55

```


### DVC cmd

1. dvc init
2. dvc repro
3. dvc dag


## About MLflow & DVC

MLflow

 - Its Production Grade
 - Trace all of your expriements
 - Logging & taging your model


DVC 

 - Its very lite weight for POC only
 - lite weight expriements tracker
 - It can perform Orchestration (Creating Pipelines)

