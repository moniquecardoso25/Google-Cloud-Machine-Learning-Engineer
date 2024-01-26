# Vertex AI: Predicting Loan Risk with AutoML

- Credits: Google Skill Boost
- Introduction to AI and Machine Learning on Google Cloud

## Objective

- Use AutoMl to predict loan risk through building a Ml model
- The dataset is related to loans from financial institution with 2.500 data points (AutoML requires at least 100 data points)
- Practice the learning of the course about ML workflow:
   1. Data Preparation
   2. Model Development
   3. Model Serving
- Evaluate the model performance.
- Deploy the model to an endpoint.
- Get predictions
  
 
    ![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/f26297d3-b3c5-4726-a8b3-317aef9fcc8c)



    ![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/cc988545-3a56-42a4-bb12-0b0acf8917b5)


# Task 1. Prepare the training data

The initial Vertex AI dashboard illustrates the major stages to train and deploy a ML model: prepare the training data, train the model, and get predictions. Later, the dashboard displays your recent activities, such as the recent datasets, models, predictions, endpoints, and notebook instances.

Create a dataset

1. In the Google Cloud console, on the Navigation menu, click Vertex AI > Datasets.
2. Click Create dataset.
3. Give dataset a name LoanRisk.
4. For the data type and objective, click Tabular, and then select Regression/classification.
5. Click Create.


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/91ac681f-20d7-4569-a015-50fd2a4f984f)
   

### Upload data

There are three options to import data in Vertex AI:

- Upload a local file from your computer.
- Select files from Cloud Storage.
- Select data from BigQuery.
- For convenience, the dataset is already uploaded to Cloud Storage


1. For the data source, select Select CSV files from Cloud Storage.

2. For Import file path, enter:

```spls/cbl455/loan_risk.csv```

3. Click Continue


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/9f59a8d3-e5b4-46fb-a3e3-c44d1e507516)



## Task 2. Train your model

With a dataset uploaded, you're ready to train a model to predict whether a customer will repay the loan.

- Click Train new model and select Other .
Training method

1. The dataset is already named LoanRisk.

2. For Objective, select Classification.

You select classification instead of regression because you are predicting a distinct number (whether a customer will repay a loan: 0 for repay, 1 for default/not repay) instead of a continuous number.

3. Click Continue.
   

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/beab389a-3ba0-4cc5-a990-01ebb3f0bb84)



### Model details

Specify the name of the model and the target column.

1. Give the model a name, such as LoanRisk.

2. For Target column, select Default .

3. (Optional) Explore Advanced options to determine how to assign the training vs. testing data and specify the encryption.

4. Click Continue.

5. For Add features, click Continue.

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/8d62fd77-6f45-4600-a8cd-5f415419f55d)

Advanced Options

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/31bf1c3b-a181-4878-9f70-6f2ed8945cb6)


### Training options

Specify which columns you want to include in the training model. For example, ClientID might be irrelevant to predict loan risk.

1. Click the minus sign on the ClientID row to exclude it from the training model.

3. (Optional) Explore Advanced options to select different optimization objectives.
For more information about optimization objectives for tabular AutoML models, refer to the Optimization objectives for tabular AutoML models guide.

4. Click Continue.


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/15947766-376f-4d3b-ba11-cabba533330e)

Advanced Options


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/30f2368a-d050-4e7a-9495-c0b3a08cdff9)


### Compute and pricing

1. For Budget, which represents the number of node hours for training, enter 1.
Training your AutoML model for 1 compute hour is typically a good start for understanding whether there is a relationship between the features and label you've selected. From there, you can modify your features and train for more time to improve model performance.

2. Leave early stopping Enabled.

3. Click Start training.

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/337ef85b-c0c5-41f8-971d-6b695a907693)


Depending on the data size and the training method, the training can take from a few minutes to a couple of hours. Normally you would receive an email from Google Cloud when the training job is complete. However, in the Qwiklabs environment, you will not receive an email.

To save the waiting for the model training, you download a pre-trained model in Task 5 to get predictions in Task 6. This pre-trained model is the training result following the same steps from Task 1 to Task 2.

## Task 3. Evaluate the model performance (demonstration only)

Vertex AI provides many metrics to evaluate the model performance. You focus on three:

- Precision/Recall curve
- Confusion Matrix
- Feature Importance

The confidence threshold determines how a ML model counts the positive cases. A higher threshold increases the precision, but decreases recall. A lower threshold decreases the precision, but increases recall.

You can manually adjust the threshold to observe its impact on precision and recall and find the best tradeoff point between the two to meet your business needs.

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/a367d3a8-c138-40cc-9c29-98730da78bad)


## Task 4. Deploy the model (demonstration only)

Create and define an endpoint

1. On your model page, click Deploy & test, and then click Deploy to Endpoint.

2. For Endpoint name, type LoanRisk

3. Click Continue.


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/1fc6f734-0da4-46cd-bb71-4a5dec85e81e)


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/83cc68db-7342-4d55-838c-c09ca69c15c8)


### Model settings and monitoring

1. Leave the traffic splitting settings as-is.

2. For Machine type, select e2-standard-8, 8 vCPUs, 30 GiB memory.

3. For Explainability Options, click Feature attribution.

4. Click Done.

5. Click Continue.

6. In Model monitoring, click Continue.

7. In Model objectives > Training data source, select Vertex AI dataset.

8. Select your dataset from the drop down menu.

9. In Target column, type Default

10. Leave the remaining settings as-is and click Deploy

## Task 5. SML Bearer Token

1. Log in to gsp-auth-kjyo252taq-uc.a.run.app.

2. When logging in, use your student email address and password.

3. Click the Copy button. This will copy a very long token to your clipboard.


## Task 6. Get predictions

In this section, use the Shared Machine Learning (SML) service to work with an existing trained model.

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/8b64da27-f69a-4043-9caf-ab2424d7f7eb)


To use the trained model, you will need to create some environment variables.

1. Open a Cloud Shell window.

2. Replace INSERT_SML_BEARER_TOKEN with the bearer token value from the previous section:

```export AUTH_TOKEN="INSERT_SML_BEARER_TOKEN"```

3 Download the lab assets:
```gcloud storage cp gs://spls/cbl455/cbl455.tar.gz .```

4. Extract the lab assets:
```tar -xvf cbl455.tar.gz```

5. Create an ENDPOINT environment variable:
```export ENDPOINT="https://sml-api-vertex-kjyo252taq-uc.a.run.app/vertex/predict/tabular_classification"```

6. Create a INPUT_DATA_FILE environment variable:
```export INPUT_DATA_FILE="INPUT-JSON" ```


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/ed67952f-fdcb-4831-8ce1-d0e6672b1842)


The file INPUT-JSON is composed of the following values:

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/45df6b00-0551-4bda-adb5-20419ffc19a6)

7. Test the SML Service by passing the parameters specified in the environment variables.
8. Perform a request to the SML service:
```
./smlproxy tabular \
  -a $AUTH_TOKEN \
  -e $ENDPOINT \
  -d $INPUT_DATA_FILE
```

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/e61ebbd1-e51a-4be6-a0ac-8daaa5c38a15)


9. Alter the INPUT-JSON file to test a new scenario:

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/0d386294-deaa-4939-8c27-6684d141913b)
    

11. Test the SML Service by passing the parameters specified in the environment variables.

12. Edit the file INPUT-JSON and replace the original values.

13. Perform a request to the SML service:
```
./smlproxy tabular \
  -a $AUTH_TOKEN \
  -e $ENDPOINT \
  -d $INPUT_DATA_FILE
```

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/7e7d3fdc-1dd8-4f8a-b2c4-bfc529e24218)


- In this case, assuming that the person's income is 50,000, age 30, and loan 20,000, the model predicts that this person will repay the loan.

It can be made in Google Cloud Console

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/32d5bc42-77c5-4fca-8db7-eee120263913)

