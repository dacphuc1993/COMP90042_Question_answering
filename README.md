# COMP90042_Question_answering

This is a project of COMP90042 Web search and text analysis.

There are 3 JSON files: `QA_train.json`, `QA_dev.json` and `QA_test.json`. Each of datafiles is a json list, with each element of the list corresponding to a text whose "sentence" key provides an
ordered list of the sentences of a Wikipedia article, and whose "qa" key is a list of questions whose answers can be
found in the article. For the training and dev data, each "qa" dictionary consists of the "question" (a string) as well as the
"answer" (a string) and "answer_sentence" (an integer), which is the index of the sentence where the answer can be
found.

Output is a CSV file with following format:
```
id,answer
1,answer1
2,answer2
3,answer3
```
where the answer strings can be words or sequences of words, and the ids are increasing integers and denote the
question in the test dataset.

 Steps to answer question are:
 - Sentence retrieval: retrieve sentences that might contain answers. This process uses TF.IDF value
 (Term frequency - inverted document frequency) to determine such sentences.
 - Entity extraction: identify entities in sentences using Stanford NER (Named Entity Recognition). There are 4 categories 
 for entities namely PERSON, LOCATION, NUMBER, and OTHER.
 - Answer ranking: from entities in a sentence, choose the entities that suit question best.
 
