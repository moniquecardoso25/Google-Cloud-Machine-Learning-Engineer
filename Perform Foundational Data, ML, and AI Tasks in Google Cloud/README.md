# Perform Foundational Data, ML, and AI Tasks in Google Cloud

- Credits: Google Skills Boost
-  ML Path
-  Challenge Lab: Perform Foundational Data, ML, and AI Tasks in Google Cloud


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

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/6000885d-1572-4cb0-978e-0575fbc44c71)


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/049b06fb-001f-4c44-a910-c279b20788d4)



### Cloud storage Bucket

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/31fae0a0-58da-4315-b212-25680afcdda2)



![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/71f84934-e3ed-492e-9046-4013c3d2d518)



### Creating a table in BigQuery 

- gsutil cp gs://cloud-training/gsp323/lab.csv .
- gsutil cp gs://cloud-training/gsp323/lab.schema .
- cat lab.schema



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



![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/f1d6e99d-76a2-407c-b092-c829bb5eea95)



![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/aa1e9c05-240e-4260-aa48-cbd6cc0c8ee7)



![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/12b27a9d-0b21-49da-8922-71b29af96e20)




### Create a Job in DataFlow

### Template

Text Files on Google Cloud Storage to Bigquery

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/48119144-7521-4789-9c89-822aa9c3b4e4)


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/616f0dfb-420b-40b5-8c62-7161ea66b95c)



![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/753c3f36-06e8-4692-af6b-fd87485f564d)



### Machine Type

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/69a1c2d1-3c0b-4573-800d-d98f46dbf955)


### Job Created

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/e6d8be9b-6e80-4c56-bdbf-d7ded90cb1b9)


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/cbee849f-7a50-4106-8ade-05c45316a61e)



## Task 2: Run a simple Dataproc job
You have used Dataproc in the quest, now you must run another example Spark job using Dataproc.

Before you run the job, log into one of the cluster nodes and copy the /data.txt file into hdfs (use the command hdfs dfs -cp gs://cloud-training/gsp323/data.txt /data.txt).



### Create a cluster on Compute Engine

### Region

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/7f6b20d2-c4b6-458b-9c24-b8f61a7071ca)



### Nodes

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/65477cfd-935f-4ca3-8aa9-a77263060ed3)


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/7bcc0e6b-3030-41fc-9c3e-ade855df9ea7)



### Cluster created

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/cc1e0d83-56f2-49cb-95c9-c4ae4b14413a)



### SSH VM instance

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/d32091ac-96f7-4704-98ee-ccf48a963163)


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/c6ada96a-e18f-45ed-9b18-afab77fdb16a)



### Dataproc Job

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/760439a8-9805-4f66-bd12-7d42428b65c7)



### Job created

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/2c938aa1-e0af-4676-8fe7-41176d1e0167)


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/17e2fb0d-6ea9-4fb3-8eb5-ad4823662dbf)



## Task 3: Use the Google Cloud Speech API

Use Google Cloud Speech API to analyze the audio file gs://cloud-training/gsp323/task3.flac. Once you have analyzed the file, upload the resulting file to: gs://qwiklabs-gcp-01-57487449610c-marking/task3-gcs-230.result


### API key

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/bc660d89-d841-43e9-990f-359c46ad4145)



### Dataproc again. VM Instance 

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/c0651629-f3b1-49e7-a1ed-4597343b9261)



- export API_KEY=AIzaSyBWs9eVNOHkyVpOugesIbWqD97iK1KGudQ
- nano request.json

{
        "config": {
                "encoding":"FLAC",
                "languageCode":"en-US"
        },
        "audio": {
                "uri":"gs://cloud-training/gsp323/task3.flac"
        }
}


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/8366393c-d327-480f-9f59-0f2b7064512d)



- cat request.json

- export API_KEY=AIzaSyBWs9eVNOHkyVpOugesIbWqD97iK1KGudQ
- curl -s -X POST -H "Content-Type: application/js on" --data-binary @request.json "https://speech.googleapis.com/v1/speech:recognize?key=${API_KEY}" > result.json
- cat result.json
- gsutil cp result.json gs://qwiklabs-gcp-01-57487449610c-marking/task3-gcs-230.result


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/148f88b7-376a-498d-a67f-c6fc2f3876a1)



## Task 4: Use the Cloud Natural Language API

Use the Cloud Natural Language API to analyze the sentence from text about Odin. The text you need to analyze is "Old Norse texts portray Odin as one-eyed and long-bearded, frequently wielding a spear named Gungnir and wearing a cloak and a broad hat." Once you have analyzed the text, upload the resulting file to: gs://qwiklabs-gcp-01-57487449610c-marking/task4-cnl-743.result

### Cloud Shell

- gcloud iam service-accounts create my-natlang-sa \
Autorize Cloud Shell and continue: 
- > --display-name "my natural language service account"
- glcoud iam service-accounts keys create ~/keys.json \> --iam-account my-natlang-sa@${GOOGLE_CLOUD_PROJECT}.iam.gserviceaccount.com
- export GOOGLE_APPLICATION_CREDENTIALS="/home/USER/key.json"
- gcloud ml language analyze-entities --content="Old Norse texts portray Odin as one-eyed and long-bearded, frequently wielding a spear named Gungnir and wearing a cloak and a broad hat." > result.json
- cat result.json
- gsutil cp result.json gs://qwiklabs-gcp-01-57487449610c-marking/task4-cnl-743.result


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/8d04463c-241c-4338-b4d3-cfabb67c41c6)


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/a7a96bda-08b6-40ee-a2ee-8c5e51d1f8c4)


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/da218e4c-fa8f-4ca7-9bfa-2b459fed79ac)


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/42a34b5d-d1b8-4aac-837b-0f595b2dd2e7)

