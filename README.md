# eazyml-client
A python client library wrapper for EazyML's REST API. 

Supports Python 2.x only. Python 3 support coming soon.

Full API documentation can be found at https://www.eazyml.com/docs

# Getting Started

## Prerequisites
Our eazyml client library requires the following python package dependencies.
```
pip install requests
pip install configparser
```

## API URL
### Development
The development environment supports users in Trial subscription.  
By default the client library uses the development endpoint.
```
https://development.eazyml.com/
```

### Production
The production environment supports users that have subscribed to Standard, Deluxe or Premium subscriptions.
```
https://production.eazyml.com/
```

## Authentication
A user must authenticate and retrieve an authentication token to be used for all API calls. This API allows you to authenticate with EazyML and returns a token.
```
import eazyml

username = <your username>
password = <your password>

auth_token = eazyml.ez_auth(username, password)
```

## Training Data Upload
This API allows you to upload training data in a file. The accepted file formats are CSV and Microsoft Excel.
```
import eazyml
username = <your username>
password = <your password>

auth_token = eazyml.ez_auth(username, password)["token"]
options = {
        "id": "null",
        "impute": "yes",
        "outlier": "yes",
        "discard": [<column_names>],        
        "accelerate": "yes",
        "outcome" : <outcome_column>
        }
dataset_id = eazyml.ez_load(auth_token, <train_file_path>, options)
```
