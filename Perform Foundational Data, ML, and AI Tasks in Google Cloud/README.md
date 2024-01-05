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


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/5e92e37b-b99e-436f-9624-d87f1f5e28ed)


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/0175ec63-219c-42cb-9f14-6f8822c3295d)

#### Creating a table in BigQuery 

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/3561c305-fb83-4fd9-926d-4dbc2b41017b)



- [
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


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/b221f858-dcc4-4bf0-9c54-ff1e6a1442de)


- gsutil cp gs://cloud-training/gsp323/lab.csv .
- gsutil cp gs://cloud-training/gsp323/lab.schema .
- cat lab.schema


### Create a Job in DataFlow

#### Template

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/0c39a6c2-685d-49c4-ab2f-77ec38ae8f33)

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/04e20a2f-83ac-4390-9132-e82284a890a2)


#### Machine Type

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/bdd7dcbd-a188-472d-98a8-707e3274d7ec)


#### Job Created

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/28b82a62-9590-49e6-b622-7dd99012db23)


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/8b35ca02-c22d-4f57-ab10-091592747483)



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



