# Keyword Extraction API

This api has two endpoints to allow you to extra unique keywords from a set of text, as described in this blogpost: https://towardsdatascience.com/build-a-keyword-extraction-api-with-spacy-flask-and-fuzzywuzzy-4909d7ffc105

Uses FuzzyWuzzy to correct for any human-errors in text

## Endpoints

- Endpoint 1: Keyword Extraction

Sample POSTMAN request:
```
import requests
import json

url = "http://127.0.0.1:5000/api/keywords"

payload = json.dumps({
  "query_string": "I am testing the API endpoint that finds the keywords in a set of text",
  "tags": []
})
headers = {
  'Content-Type': 'application/json'
}

response = requests.request("POST", url, headers=headers, data=payload)

print(response.text)
```

- Endpoint 2: Get Fuzzy Match

Sample POSTMAN request:
```
import requests
import json

url = "http://127.0.0.1:5000/api/fuzzy-matches"

payload = json.dumps({
  "token": "mediuam",
  "dictionary": [
    "medium",
    "twitter",
    "google",
    "linkedIn",
    "facebook"
  ]
})
headers = {
  'Content-Type': 'application/json'
}

response = requests.request("POST", url, headers=headers, data=payload)

print(response.text)
```

## Technologies

- spaCy
- FuzzyWuzzy
- Flask