# Practice_Project_Sentiment_Analysis_Flask
With IBM course's initiative I developed a Python web app using Flask and integrate Embeddable Watson AI libraries to make the web app showcase AI-based abilities.

##Tasks and objectives that has been accomplished:
- Task 1: Clone the project repository
- Task 2: Create a sentiment analysis application using Watson NLP library
- Task 3: Format the output of the application
- Task 4: Package the application
- Task 5: Run Unit tests on your application
- Task 6: Deploy as web application using Flask
- Task 7: Incorporate Error handling
- Task 8: Run static code analysis

After cloning the corresponding repo you need to ensure libraries and Python:
```
python3.11 -V
pip3.11 show requests flask pylint
python3.11 -m pip install requests flask pylint
```
After creating the sentiment analysis, the execution is tried using Python shell.
```
$python3.11
>>> from sentiment_analysis import sentiment_analyzer
>>> sentiment_analyzer("I love this new technology")
'{"documentSentiment":{"score":0.996954, "label":"SENT_POSITIVE", "mixed":false, "sentimentMentions":[{"span":{"begin":0, "end":26, "text":"I love this new technology"}, "sentimentprob":{"positive":0.9941229, "neutral":0.0028645627, "negative":0.0030124863}}]}, "targetedSentiments":{"targetedSentiments":{}, "producerId":{"name":"Aggregated Sentiment Workflow", "version":"0.0.1"}}, "producerId":{"name":"Aggregated Sentiment Workflow", "version":"0.0.1"}}'
>>> import json
>>> from sentiment_analysis import sentiment_analyzer
>>> response = sentiment_analyzer("I love this new technology")
>>> formatted_response = json.loads(response)
>>> print(formatted_response)
{'documentSentiment': {'score': 0.996954, 'label': 'SENT_POSITIVE', 'mixed': False, 'sentimentMentions': [{'span': {'begin': 0, 'end': 26, 'text': 'I love this new technology'}, 'sentimentprob': {'positive': 0.9941229, 'neutral': 0.0028645627, 'negative': 0.0030124863}}]}, 'targetedSentiments': {'targetedSentiments': {}, 'producerId': {'name': 'Aggregated Sentiment Workflow', 'version': '0.0.1'}}, 'producerId': {'name': 'Aggregated Sentiment Workflow', 'version': '0.0.1'}}
>>> 
```
To exit the Python shell, type exit() or press Ctrl+Z

As the next step, the output is formatted as JSON. 
```
>>>from sentiment_analysis import sentiment_ascore = formatted_response['documentSentimlabel = formatted_response['documentSentimformatted_response = json.loads(response) response = sentiment_analyzer("I love thisfrom sentiment_analysis import sentiment_asentiment_analyzer("I love this new technology")
'{"documentSentiment":{"score":0.996954, "label":"SENT_POSITIVE", "mixed":false, "sentimentMentions":[{"span":{"begin":0, "end":26, "text":"I love this new technology"}, "sentimentprob":{"positive":0.9941229, "neutral":0.0028645627, "negative":0.0030124863}}]}, "targetedSentiments":{"targetedSentiments":{}, "producerId":{"name":"Aggregated Sentiment Workflow", "version":"0.0.1"}}, "producerId":{"name":"Aggregated Sentiment Workflow", "version":"0.0.1"}}'
```

Package the application by creating an __init__.py file to reference the module.
```
$python3.11
Python 3.11.14 (main, Oct 10 2025, 08:54:03) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from SentimentAnalysis.sentiment_analysis import sentiment_analyzer
>>> sentiment_analyzer("This is fun.")
{'label': 'SENT_POSITIVE', 'score': 0.997183}
```

Implemented a unittest using assertEqual and run the test
```
$ python3.11 test_sentiment_analysis.py
----------------------------------------------------------------------
Ran 1 test in 0.682s
```
Make sure the directory is in this structure:
directory structure:
practice_project/
├── SentimentAnalysis/
│   ├── __init__.py
│   ├── sentiment_analysis.py
├── templates/
│   ├── index.html
├── static/
│   ├── mywebscript.js
├── server.py



pylint server.py for static code analysis
