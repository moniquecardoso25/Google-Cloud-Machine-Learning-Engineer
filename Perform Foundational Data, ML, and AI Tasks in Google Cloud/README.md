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

- bq mk lab_515
- gsutil mb gs://qwiklabs-gcp-04-a80d95a1806a-marking
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




###  Create table in BigQuery

#### Creating a table in BigQuery 

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/290b99db-e8a6-42ea-85c9-2c3945597f79)

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/f28babaf-b167-4ea5-a50f-60c646b360be)

#### Table Created
![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/fbcc9bcf-fa20-467e-b6e9-1086d26d6a01)


### Create a Job in DataFlow

#### Template
![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/d9185bff-0492-4b13-b943-bce52dd69f42)

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/b1753582-9f79-4696-baaf-17caa50af1e7)

#### Machine Type
![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/5ed62aef-7b9b-4c63-bf2f-a5f08b07583c)


#### Job Created



### Task 2: Run a simple Dataproc job
You have used Dataproc in the quest, now you must run another example Spark job using Dataproc.

Before you run the job, log into one of the cluster nodes and copy the /data.txt file into hdfs (use the command hdfs dfs -cp gs://cloud-training/gsp323/data.txt /data.txt).

![image](https://github.com/moniquecardoso25/Google-Cloud/assets/140358716/d8b99a01-1767-4881-aa27-6046bfc50969)

#### Create a cluster on Compute Engine

Region

![image](https://github.com/moniquecardoso25/Google-Cloud/assets/140358716/645bb195-90c4-4926-a76e-86dc2065391e)


Nodes

![image](https://github.com/moniquecardoso25/Google-Cloud/assets/140358716/084e09da-5369-4535-a60c-ce3097642005)






### Task 3: Use the Google Cloud Speech API

Use Google Cloud Speech API to analyze the audio file gs://cloud-training/gsp323/task3.flac. Once you have analyzed the file, upload the resulting file to: Cloud Speech Location






### Task 4: Use the Cloud Natural Language API
Use the Cloud Natural Language API to analyze the sentence from text about Odin. The text you need to analyze is "Old Norse texts portray Odin as one-eyed and long-bearded, frequently wielding a spear named Gungnir and wearing a cloak and a broad hat." Once you have analyzed the text, upload the resulting file to: Cloud Natural Language Location





