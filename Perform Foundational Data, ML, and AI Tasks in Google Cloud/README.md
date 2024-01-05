# Perform Foundational Data, ML, and AI Tasks in Google Cloud


As a junior data engineer in Jooli Inc. and recently trained with Google Cloud and a number of data services you have been asked to demonstrate your newly learned skills. The team has asked you to complete the following tasks.

You are expected to have the skills and knowledge for these tasks so don’t expect step-by-step guides.

## Task 1: Run a simple Dataflow job

You have used Dataflow in the quest to load data into BigQuery from Pub/Sub, now use the Dataflow batch template Text Files on Cloud Storage to BigQuery under "Process Data in Bulk (batch)" to transfer data from a Cloud Storage bucket (gs://cloud-training/gsp323/lab.csv). The following table has the values you need to correctly configure the Dataflow job.

You will need to make sure you have:

- Create a BigQuery dataset called BigQuery Dataset Name.
- Create a Cloud Storage Bucket called Cloud Storage Bucket Name

![image](https://github.com/moniquecardoso25/Google-Cloud/assets/140358716/bc8c9a2d-3c04-4405-96d6-14be33f1ec39)

Answer:


###  Create table in BigQuery

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/b3d988e6-f770-45b0-8aa4-cc4a10986b35)

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/4d987428-0d96-449f-a414-06f659ae1cb3)


#### Creating a table in BigQuery 

gsutil cp gs://cloud-training/gsp323/lab.csv .
gsutil cp gs://cloud-training/gsp323/lab.schema .
cat lab.schema


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/3561c305-fb83-4fd9-926d-4dbc2b41017b)



[
{"type":"STRING","name":"guid"},
{"type":"BOOLEAN","name":"isActive"},
{"type":"STRING","name":"firstname"},
{"type":"STRING","name":"surname"},
{"type":"STRING","name":"company"},
{"type":"STRING","name":"email"},
{"type":"STRING","name":"phone"},
{"type":"STRING","name":"address"},
{"type":"STRING","name":"about"},
{"type":"TIMESTAMP","name":"registered"},
{"type":"FLOAT","name":"latitude"},
{"type":"FLOAT","name":"longitude"}
]



![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/1307cb6c-28f4-4d20-b34c-0316276fb6a9)



![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/12635762-a8f4-4900-9e9f-ddb1adcf5dfb)



![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/6bb62ad2-da66-41c4-85e8-a5522665e003)

#### Cloud storage Bucket

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/b9a3b5ea-411d-484e-b3a5-90ee6a6d0755)


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/315051f1-70bb-47cd-aa95-acaf05302160)



### Create a Job in DataFlow

#### Template

Text Files on Google Cloud Storage to Bigquery

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/48119144-7521-4789-9c89-822aa9c3b4e4)


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/34709b94-e1af-4a98-ad54-245aa9b00f4d)


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/4f0af2de-acb9-43d6-9300-fb00f1aacd60)



#### Machine Type

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/e3eb3d87-3b61-437c-948c-40e0f51f46da)


#### Job Created



### Task 2: Run a simple Dataproc job
You have used Dataproc in the quest, now you must run another example Spark job using Dataproc.

Before you run the job, log into one of the cluster nodes and copy the /data.txt file into hdfs (use the command hdfs dfs -cp gs://cloud-training/gsp323/data.txt /data.txt).

![image](https://github.com/moniquecardoso25/Google-Cloud/assets/140358716/d8b99a01-1767-4881-aa27-6046bfc50969)

#### Create a cluster on Compute Engine

Region

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/d8f1e5d9-260c-4e6f-b995-18f08cf0903e)


Nodes

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/df1dad9c-c6ff-423f-b5e9-46905de596ed)


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/aaf4892c-efab-4772-9011-63d2a46f7006)


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/4e211880-4455-44c0-ac79-e86179531b94)

#### Cluster created

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/118aeab5-0cab-4d24-95ad-42a3e79dddc1)


#### SSH VM instance

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/ffad2902-a8b7-4799-9002-da5d6df65aec)



![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/38ac4d49-61bc-47e7-80da-73df63c80b1f)


#### Dataproc Job

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/72035eb1-280a-475e-9397-83922d5e357e)


#### Job created

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/207ebdcc-5190-4eb5-949b-a1cea2a5f303)


### Task 3: Use the Google Cloud Speech API

Use Google Cloud Speech API to analyze the audio file gs://cloud-training/gsp323/task3.flac. Once you have analyzed the file, upload the resulting file to: Cloud Speech Location


#### API key

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/1118a04f-3c82-44c9-9b67-302e58d0446d)


AIzaSyAs_n-sv_DqVrXLeQpjDhDAnaRhM8xUIyY


export API_KEY=AIzaSyAs_n-sv_DqVrXLeQpjDhDAnaRhM8xUIyY
nano request.json
{

        "config": {
                "encoding":"FLAC"
                "languageCode":"en-US"
        },
        "audio": {
                "uri":"gs://cloud-training/gsp323/task3.flac"
        }
}



cat request.json

export API_KEY=AIzaSyAs_n-sv_DqVrXLeQpjDhDAnaRhM8xUIyY
curl -s -X POST -H "Content-Type: application/js on" --data-binary @request.json "https://speech.googleapis.com/v1/speech:recognize?key=${API_KEY}"> result.json


gsutil cp result.json gs://qwiklabs-gcp-01-ab6f7c136f0e-marking/task3-gcs-849.result




### Task 4: Use the Cloud Natural Language API
Use the Cloud Natural Language API to analyze the sentence from text about Odin. The text you need to analyze is "Old Norse texts portray Odin as one-eyed and long-bearded, frequently wielding a spear named Gungnir and wearing a cloak and a broad hat." Once you have analyzed the text, upload the resulting file to: Cloud Natural Language Location

#### Cloud Shell
gcloud iam service-accounts create my-natlang-sa \
gcloud iam service-accounts keys create ~/key.json \> --iam-account my-natlang-sa@{GOOGLE:_CLOUD_PROJECT}.iam.gserviceaccount.com
export GOOGLE_APPLICATION_CREDENTIALS="/home/USER/key.json"
gcloud ml language analyze-entities --content="Old Norse texts portray Odin as one-eyed and long-bearded, frequently wielding a spear named Gungnir and wearing a cloak and a broad hat." > result.json
cat result.json
gsutil cp result.json gs://

insert gs



