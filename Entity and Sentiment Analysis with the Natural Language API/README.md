# Entity and Sentiment Analysis with the Natural Language API

**Credits**
- Google Cloud Skills Boost
- Course: Introduction to AI and Machine Learning on Google Cloud
- [Lab AI Development Options](https://www.cloudskillsboost.google/course_sessions/4587336/labs/423387)

## Task 1. Create an API key
Since you use curl to send a request to the Natural Language API, you must generate an API key to pass in your request URL.

To create an API key, in the Cloud Console, select Navigation menu > APIs & Services > Credentials.

- Click Create credentials and select API key.

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/2ed47703-bcdf-43d8-bef3-7a4ae577e897)


- Copy the generated API key and click Close.


## Task 2. Make an entity analysis request

The first Natural Language API method you use is analyzeEntities. With this method, the API can extract entities (like people, places, and events) from text. To try it out the API's entity analysis, use the following sentence:

Joanne Rowling, who writes under the pen names J. K. Rowling and Robert Galbraith, is a British novelist and screenwriter who wrote the Harry Potter fantasy series.

You build your request to the Natural Language API in the file, request.json.

1. Use nano (a code editor) to create the file request.json:
`nano request.json`

2. Type or paste the following code into request.json:
```
{
  "document":{
    "type":"PLAIN_TEXT",
    "content":"Joanne Rowling, who writes under the pen names J. K. Rowling and Robert Galbraith, is a British novelist and screenwriter who wrote the Harry Potter fantasy series."
  },
  "encodingType":"UTF8"
}
```
3. Press CTRL+X to exit nano, then Y to save the file, then ENTER to confirm.

In the request, you're telling the Natural Language API about the text being sent. Supported type values are `PLAIN_TEXT` or `HTML`. In content, you pass the text to send to the Natural Language API for analysis.

The Natural Language API also supports sending files stored in Cloud Storage for text processing. If you wanted to send a file from Cloud Storage, you would replace `content` with `gcsContentUri` and give it a value of the text file's uri in Cloud Storage.

`encodingType` tells the API which type of text encoding to use when processing our text. The API will use this to calculate where specific entities appear in our text.


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/047198fb-0831-45bc-b5c4-1fe5e95db4e4)



## Task 3. Call the Natural Language API

1. You can now pass your request body, along with the API key environment variable you saved earlier, to the Natural Language API with the following curl command (all in one single command line):

```
curl "https://language.googleapis.com/v1/documents:analyzeEntities?key=${API_KEY}" \
  -s -X POST -H "Content-Type: application/json" --data-binary @request.json > result.json
```

2. In order to check the response run:
`cat result.json`

Result

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/beed08d7-2925-474e-b992-72c9e94a43a0)


Example

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/b9581fa4-303e-4322-a1c2-4776756605dd)



## Task 4. Sentiment analysis with the Natural Language API
In addition to extracting entities, the Natural Language API also lets you perform sentiment analysis on a block of text. This JSON request will include the same parameters as the request above, but this time change the text to include something with a stronger sentiment.

1. Use nano to replace the code in request.json with the following, and feel free to replace the content below with your own text:
```
 {
  "document":{
    "type":"PLAIN_TEXT",
    "content":"Harry Potter is the best book. I think everyone should read it."
  },
  "encodingType": "UTF8"
}
```

2. Press CTRL+X to exit nano, then Y to save the file, then ENTER to confirm.

3. Next you send the request to the API's analyzeSentiment endpoint:

```
curl "https://language.googleapis.com/v1/documents:analyzeSentiment?key=${API_KEY}" \
  -s -X POST -H "Content-Type: application/json" --data-binary @request.json
```
Result

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/8a888b12-c54e-49f3-993d-8a2ff342d248)


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/741bb7d5-2f34-43c4-9b3b-dae0b53e2e5c)


Example

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/b0bc2c04-0df7-4c0d-90c0-f84854aec257)

Notice that you get two types of sentiment values: sentiment for the document as a whole, and sentiment broken down by sentence. The sentiment method returns two values:

- `score` - is a number from -1.0 to 1.0 indicating how positive or negative the statement is.
- `magnitude` - is a number ranging from 0 to infinity that represents the weight of sentiment expressed in the statement, regardless of being positive or negative.
Longer blocks of text with heavily weighted statements have higher magnitude values. The score for the first sentence is positive (0.7), whereas the score for the second sentence is neutral (0.1).




## Task 5. Analyzing entity sentiment
In addition to providing sentiment details on the entire text document, the Natural Language API can also break down sentiment by the entities in the text. Use this sentence as an example:

- I liked the sushi but the service was terrible.

In this case, getting a sentiment score for the entire sentence as you did above might not be so useful. If this was a restaurant review and there were hundreds of reviews for the same restaurant, you'd want to know exactly which things people liked and didn't like in their reviews. Fortunately, the Natural Language API has a method that lets you get the sentiment for each entity in the text, called analyzeEntitySentiment. Let's see how it works!

1. Use nano to update request.json with the sentence below:

``` 
 {
  "document":{
    "type":"PLAIN_TEXT",
    "content":"I liked the sushi but the service was terrible."
  },
  "encodingType": "UTF8"
}
```
2. Press CTRL+X to exit nano, then Y to save the file, then ENTER to confirm.

3. Then call the `analyzeEntitySentiment` endpoint with the following curl command:

```
curl "https://language.googleapis.com/v1/documents:analyzeEntitySentiment?key=${API_KEY}" \
  -s -X POST -H "Content-Type: application/json" --data-binary @request.json
```


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/bca079ea-05eb-4065-9288-feceae12d33b)

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/037c9434-027b-4c6b-8655-cbd48f0405fb)


Example

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/082547d2-7e30-4975-9a0d-6cc8aaadf191)

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/4a33d9dd-e989-493b-8e5d-29a0b4f20921)

You can see that the score returned for "sushi" was a neutral score of 0, whereas "service" got a score of -0.7. Cool! You also may notice that there are two sentiment objects returned for each entity. If either of these terms were mentioned more than once, the API would return a different sentiment score and magnitude for each mention, along with an aggregate sentiment for the entity.



## Task 6. Analyzing syntax and parts of speech
Use syntactic analysis, another of the Natural Language API's methods, to dive deeper into the linguistic details of the text. analyzeSyntax extracts linguistic information, breaking up the given text into a series of sentences and tokens (generally, word boundaries), to provide further analysis on those tokens. For each word in the text, the API tells you the word's part of speech (noun, verb, adjective, etc.) and how it relates to other words in the sentence (Is it the root verb? A modifier?).

Try it out with a simple sentence. This JSON request will be similar to the ones above, with the addition of a features key. This tells the API to perform syntax annotation.

1. Use nano to replace the code in request.json with the following:

```
{
  "document":{
    "type":"PLAIN_TEXT",
    "content": "Joanne Rowling is a British novelist, screenwriter and film producer."
  },
  "encodingType": "UTF8"
}
```
2. Press CTRL+X to exit nano, then Y to save the file, then ENTER to confirm.

3. Then call the API's analyzeSyntax method:

```
curl "https://language.googleapis.com/v1/documents:analyzeSyntax?key=${API_KEY}" \
  -s -X POST -H "Content-Type: application/json" --data-binary @request.json
```


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/0cddbb32-61e0-4eb7-b922-7015442bb89a)


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/e19c388e-0fd3-404d-a0e1-a0a87c8481ba)

The response should return an object like the one below for each token in the sentence:

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/7a248b96-8b5e-4e0a-8d96-7bf7442f1561)


Break down the response:

- `partOfSpeech` tells you that "Joanne" is a noun.
- `dependencyEdge` includes data that you can use to create a dependency parse tree of the text. Essentially, this is a diagram showing how words in a sentence relate to each other. A dependency parse tree for the sentence above would look like this:

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/ddba77cb-6717-4c06-8220-dc680ba8b861)

- `headTokenIndex` is the index of the token that has an arc pointing at "Joanne". Think of each token in the sentence as a word in an array.
- `headTokenIndex` of 1 for "Joanne" refers to the word "Rowling", which it is connected to in the tree. The label `NN` (short for noun compound modifier) describes the word's role in the sentence. "Joanne" modifies "Rowling", the subject of the sentence.
- `lemma` is the canonical form of the word. For example, the words run, runs, ran, and running all have a lemma of run. The lemma value is useful for tracking occurrences of a word in a large piece of text over time.


## Task 7. Multilingual natural language processing

The Natural Language API also supports languages other than English (full list can be found in the Language Support Guide).

1. Modify the code in request.json with a sentence in Japanese:
```
{
  "document":{
    "type":"PLAIN_TEXT",
    "content":"日本のグーグルのオフィスは、東京の六本木ヒルズにあります"
  }
}
```
2. Press CTRL+X to exit nano, then Y to save the file, then ENTER to confirm.
Notice that you didn't tell the API which language the text is, it can automatically detect it!

3. Next, you send it to the analyzeEntities endpoint:
```
curl "https://language.googleapis.com/v1/documents:analyzeEntities?key=${API_KEY}" \
  -s -X POST -H "Content-Type: application/json" --data-binary @request.json
```

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/67b2482e-eaae-4424-8a44-4d22b3529dd8)


![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/e43ca253-2aa6-48d0-9391-0d4868a8d17d)


Example

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/ec465a39-5c8f-448e-a850-69e50529605c)

![image](https://github.com/moniquecardoso25/Google-Cloud-Machine-Learning-Engineer/assets/140358716/473da354-9e9e-4d4e-9177-098a428cba34)



