# eazyml-client
A python client library wrapper for EazyML's REST API.

# Getting Started

## API URL
### Development
```
https://development.eazyml.com/
```

### Production
```
https://production.eazyml.com/
```

## Authentication
A user must authenticate and retrieve an authentication token to be used for all API calls. This API allows you to authenticate with EazyML and returns a token.
```
import eazyml

username = ‘api_demo’
password = ‘api_demo’

auth_token = eazyml.ez_auth(username, password)
```

## Training Data Upload
This API allows you to upload training data in a file. The accepted file formats are CSV and Microsoft Excel.
```
import eazyml
username = ‘api_demo’
password = ‘api_demo’

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
