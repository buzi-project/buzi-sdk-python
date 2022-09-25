# buzi-v1
This is a sample Pet Store Server based on the OpenAPI 3.0 specification.  You can find out more about
Swagger at [https://swagger.io](https://swagger.io). In the third iteration of the pet store, we've switched to the design first approach!
You can now help us improve the API whether it's by making changes to the definition itself or to the code.
That way, with time, we can improve the API in general, and expose some of the new features in OAS3.

_If you're looking for the Swagger 2.0/OAS 2.0 version of Petstore, then click [here](https://editor.swagger.io/?url=https://petstore.swagger.io/v2/swagger.yaml). Alternatively, you can load via the `Edit > Load Petstore OAS 2.0` menu option!_

Some useful links:
- [The Pet Store repository](https://github.com/swagger-api/swagger-petstore)
- [The source API definition for the Pet Store](https://github.com/swagger-api/swagger-petstore/blob/master/src/main/resources/openapi.yaml)

This Python package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: 1.0.0
- Package version: 0.202209251204.0
- Build package: org.openapitools.codegen.languages.PythonClientCodegen

## Requirements.

Python >=3.6

## Installation & Usage
### pip install

If the python package is hosted on a repository, you can install directly using:

```sh
pip install git+https://github.com/buzi-project/buzi-sdk-python.git
```
(you may need to run `pip` with root permission: `sudo pip install git+https://github.com/buzi-project/buzi-sdk-python.git`)

Then import the package:
```python
import buziv2
```

### Setuptools

Install via [Setuptools](http://pypi.python.org/pypi/setuptools).

```sh
python setup.py install --user
```
(or `sudo python setup.py install` to install the package for all users)

Then import the package:
```python
import buziv2
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```python

import time
import buziv2
from pprint import pprint
from buziv2.api import sms_api
from buziv2.model.create_message_input import CreateMessageInput
from buziv2.model.error import Error
from buziv2.model.message import Message
from buziv2.model.network import Network
from buziv2.model.pricing import Pricing
# Defining the host is optional and defaults to https://petstore3.swagger.io
# See configuration.py for a list of all supported configuration parameters.
configuration = buziv2.Configuration(
    host = "https://petstore3.swagger.io"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure API key authorization: ApiKeyAuth
configuration.api_key['ApiKeyAuth'] = 'YOUR_API_KEY'

# Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
# configuration.api_key_prefix['ApiKeyAuth'] = 'Bearer'

# Configure HTTP basic authorization: BasicAuth
configuration = buziv2.Configuration(
    username = 'YOUR_USERNAME',
    password = 'YOUR_PASSWORD'
)

# Configure Bearer authorization: BearerAuth
configuration = buziv2.Configuration(
    access_token = 'YOUR_BEARER_TOKEN'
)


# Enter a context with an instance of the API client
with buziv2.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = sms_api.SmsApi(api_client)
    message_id = 1 # int | ID of pet to return

    try:
        # Cancel a message
        api_response = api_instance.cancel_message(message_id)
        pprint(api_response)
    except buziv2.ApiException as e:
        print("Exception when calling SmsApi->cancel_message: %s\n" % e)
```

## Documentation for API Endpoints

All URIs are relative to *https://petstore3.swagger.io*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*SmsApi* | [**cancel_message**](docs/SmsApi.md#cancel_message) | **POST** /v1/sms/messages/{messageId}/cancel | Cancel a message
*SmsApi* | [**create_message**](docs/SmsApi.md#create_message) | **POST** /v1/sms/messages | Create Message
*SmsApi* | [**create_pricing**](docs/SmsApi.md#create_pricing) | **PUT** /v1/sms/networks/{networkId}/pricing | Create network price
*SmsApi* | [**delete_message**](docs/SmsApi.md#delete_message) | **DELETE** /v1/sms/messages/{messageId} | Deletes a message
*SmsApi* | [**get_message**](docs/SmsApi.md#get_message) | **GET** /v1/sms/messages/{messageId} | Get message
*SmsApi* | [**get_network**](docs/SmsApi.md#get_network) | **GET** /v1/sms/networks/{networkId} | Get network
*SmsApi* | [**get_pricing**](docs/SmsApi.md#get_pricing) | **GET** /v1/sms/networks/{networkId}/pricing | List network rates
*SmsApi* | [**list_messages**](docs/SmsApi.md#list_messages) | **GET** /v1/sms/messages | List messages
*SmsApi* | [**list_networks**](docs/SmsApi.md#list_networks) | **GET** /v1/sms/networks | List networks
*SmsApi* | [**send_message**](docs/SmsApi.md#send_message) | **POST** /v1/sms/messages/{messageId}/send | Sends a message


## Documentation For Models

 - [Cost](docs/Cost.md)
 - [CreateMessageInput](docs/CreateMessageInput.md)
 - [Error](docs/Error.md)
 - [Message](docs/Message.md)
 - [Network](docs/Network.md)
 - [Pricing](docs/Pricing.md)


## Documentation For Authorization


## ApiKeyAuth

- **Type**: API key
- **API key parameter name**: X-API-Key
- **Location**: HTTP header


## BasicAuth

- **Type**: HTTP basic authentication


## BearerAuth

- **Type**: Bearer authentication


## Author

edson@michaque.com


## Notes for Large OpenAPI documents
If the OpenAPI document is large, imports in buziv2.apis and buziv2.models may fail with a
RecursionError indicating the maximum recursion limit has been exceeded. In that case, there are a couple of solutions:

Solution 1:
Use specific imports for apis and models like:
- `from buziv2.api.default_api import DefaultApi`
- `from buziv2.model.pet import Pet`

Solution 2:
Before importing the package, adjust the maximum recursion limit as shown below:
```
import sys
sys.setrecursionlimit(1500)
import buziv2
from buziv2.apis import *
from buziv2.models import *
```

