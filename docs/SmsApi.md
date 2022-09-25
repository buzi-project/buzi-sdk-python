# buziv2.SmsApi

All URIs are relative to *https://petstore3.swagger.io*

Method | HTTP request | Description
------------- | ------------- | -------------
[**cancel_message**](SmsApi.md#cancel_message) | **POST** /v1/sms/messages/{messageId}/cancel | Cancel a message
[**create_message**](SmsApi.md#create_message) | **POST** /v1/sms/messages | Create Message
[**create_pricing**](SmsApi.md#create_pricing) | **PUT** /v1/sms/networks/{networkId}/pricing | Create network price
[**delete_message**](SmsApi.md#delete_message) | **DELETE** /v1/sms/messages/{messageId} | Deletes a message
[**get_message**](SmsApi.md#get_message) | **GET** /v1/sms/messages/{messageId} | Get message
[**get_network**](SmsApi.md#get_network) | **GET** /v1/sms/networks/{networkId} | Get network
[**get_pricing**](SmsApi.md#get_pricing) | **GET** /v1/sms/networks/{networkId}/pricing | List network rates
[**list_messages**](SmsApi.md#list_messages) | **GET** /v1/sms/messages | List messages
[**list_networks**](SmsApi.md#list_networks) | **GET** /v1/sms/networks | List networks
[**send_message**](SmsApi.md#send_message) | **POST** /v1/sms/messages/{messageId}/send | Sends a message


# **cancel_message**
> Message cancel_message(message_id)

Cancel a message

Returns a single pet

### Example

* Api Key Authentication (ApiKeyAuth):
* Basic Authentication (BasicAuth):
* Bearer Authentication (BearerAuth):

```python
import time
import buziv2
from buziv2.api import sms_api
from buziv2.model.error import Error
from buziv2.model.message import Message
from pprint import pprint
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

    # example passing only required values which don't have defaults set
    try:
        # Cancel a message
        api_response = api_instance.cancel_message(message_id)
        pprint(api_response)
    except buziv2.ApiException as e:
        print("Exception when calling SmsApi->cancel_message: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **message_id** | **int**| ID of pet to return |

### Return type

[**Message**](Message.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [BasicAuth](../README.md#BasicAuth), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | successful operation |  -  |
**400** | Invalid ID supplied |  -  |
**404** | Pet not found |  -  |
**0** | Unexpected Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_message**
> Message create_message(create_message_input)

Create Message

Update an existing pet by Id

### Example

* Api Key Authentication (ApiKeyAuth):
* Basic Authentication (BasicAuth):
* Bearer Authentication (BearerAuth):

```python
import time
import buziv2
from buziv2.api import sms_api
from buziv2.model.error import Error
from buziv2.model.message import Message
from buziv2.model.create_message_input import CreateMessageInput
from pprint import pprint
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
    create_message_input = CreateMessageInput(
        to=[
            "to_example",
        ],
        _from="_from_example",
        network_id=1,
        callback_url="callback_url_example",
    ) # CreateMessageInput | Update an existent pet in the store

    # example passing only required values which don't have defaults set
    try:
        # Create Message
        api_response = api_instance.create_message(create_message_input)
        pprint(api_response)
    except buziv2.ApiException as e:
        print("Exception when calling SmsApi->create_message: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **create_message_input** | [**CreateMessageInput**](CreateMessageInput.md)| Update an existent pet in the store |

### Return type

[**Message**](Message.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [BasicAuth](../README.md#BasicAuth), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Invalid ID supplied |  -  |
**404** | Pet not found |  -  |
**405** | Validation exception |  -  |
**0** | Unexpected Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_pricing**
> Message create_pricing(network_id)

Create network price

Returns a single pet

### Example

* Api Key Authentication (ApiKeyAuth):
* Basic Authentication (BasicAuth):
* Bearer Authentication (BearerAuth):

```python
import time
import buziv2
from buziv2.api import sms_api
from buziv2.model.error import Error
from buziv2.model.message import Message
from pprint import pprint
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
    network_id = 1 # int | 

    # example passing only required values which don't have defaults set
    try:
        # Create network price
        api_response = api_instance.create_pricing(network_id)
        pprint(api_response)
    except buziv2.ApiException as e:
        print("Exception when calling SmsApi->create_pricing: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **network_id** | **int**|  |

### Return type

[**Message**](Message.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [BasicAuth](../README.md#BasicAuth), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | successful operation |  -  |
**400** | Invalid ID supplied |  -  |
**404** | Pet not found |  -  |
**0** | Unexpected Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_message**
> Error delete_message(message_id)

Deletes a message

delete a message

### Example

* Api Key Authentication (ApiKeyAuth):
* Basic Authentication (BasicAuth):
* Bearer Authentication (BearerAuth):

```python
import time
import buziv2
from buziv2.api import sms_api
from buziv2.model.error import Error
from pprint import pprint
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
    message_id = 1 # int | Pet id to delete
    api_key = "api_key_example" # str |  (optional)

    # example passing only required values which don't have defaults set
    try:
        # Deletes a message
        api_response = api_instance.delete_message(message_id)
        pprint(api_response)
    except buziv2.ApiException as e:
        print("Exception when calling SmsApi->delete_message: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Deletes a message
        api_response = api_instance.delete_message(message_id, api_key=api_key)
        pprint(api_response)
    except buziv2.ApiException as e:
        print("Exception when calling SmsApi->delete_message: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **message_id** | **int**| Pet id to delete |
 **api_key** | **str**|  | [optional]

### Return type

[**Error**](Error.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [BasicAuth](../README.md#BasicAuth), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**400** | Invalid pet value |  -  |
**0** | Unexpected Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_message**
> Message get_message(message_id)

Get message

Returns a single pet

### Example

* Api Key Authentication (ApiKeyAuth):
* Basic Authentication (BasicAuth):
* Bearer Authentication (BearerAuth):

```python
import time
import buziv2
from buziv2.api import sms_api
from buziv2.model.error import Error
from buziv2.model.message import Message
from pprint import pprint
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

    # example passing only required values which don't have defaults set
    try:
        # Get message
        api_response = api_instance.get_message(message_id)
        pprint(api_response)
    except buziv2.ApiException as e:
        print("Exception when calling SmsApi->get_message: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **message_id** | **int**| ID of pet to return |

### Return type

[**Message**](Message.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [BasicAuth](../README.md#BasicAuth), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | successful operation |  -  |
**400** | Invalid ID supplied |  -  |
**404** | Pet not found |  -  |
**0** | Unexpected Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_network**
> Network get_network(network_id)

Get network

Returns a single pet

### Example

* Api Key Authentication (ApiKeyAuth):
* Basic Authentication (BasicAuth):
* Bearer Authentication (BearerAuth):

```python
import time
import buziv2
from buziv2.api import sms_api
from buziv2.model.error import Error
from buziv2.model.network import Network
from pprint import pprint
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
    network_id = 1 # int | 
    country_code = 1 # int | ID of pet to return (optional)

    # example passing only required values which don't have defaults set
    try:
        # Get network
        api_response = api_instance.get_network(network_id)
        pprint(api_response)
    except buziv2.ApiException as e:
        print("Exception when calling SmsApi->get_network: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Get network
        api_response = api_instance.get_network(network_id, country_code=country_code)
        pprint(api_response)
    except buziv2.ApiException as e:
        print("Exception when calling SmsApi->get_network: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **network_id** | **int**|  |
 **country_code** | **int**| ID of pet to return | [optional]

### Return type

[**Network**](Network.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [BasicAuth](../README.md#BasicAuth), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | successful operation |  -  |
**400** | Invalid ID supplied |  -  |
**404** | Pet not found |  -  |
**0** | Unexpected Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_pricing**
> [Pricing] get_pricing(network_id)

List network rates

Returns a single pet

### Example

* Api Key Authentication (ApiKeyAuth):
* Basic Authentication (BasicAuth):
* Bearer Authentication (BearerAuth):

```python
import time
import buziv2
from buziv2.api import sms_api
from buziv2.model.error import Error
from buziv2.model.pricing import Pricing
from pprint import pprint
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
    network_id = 1 # int | 

    # example passing only required values which don't have defaults set
    try:
        # List network rates
        api_response = api_instance.get_pricing(network_id)
        pprint(api_response)
    except buziv2.ApiException as e:
        print("Exception when calling SmsApi->get_pricing: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **network_id** | **int**|  |

### Return type

[**[Pricing]**](Pricing.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [BasicAuth](../README.md#BasicAuth), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | successful operation |  -  |
**400** | Invalid ID supplied |  -  |
**404** | Pet not found |  -  |
**0** | Unexpected Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_messages**
> [Message] list_messages()

List messages

Update an existing pet by Id

### Example

* Api Key Authentication (ApiKeyAuth):
* Basic Authentication (BasicAuth):
* Bearer Authentication (BearerAuth):

```python
import time
import buziv2
from buziv2.api import sms_api
from buziv2.model.error import Error
from buziv2.model.message import Message
from pprint import pprint
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
    inbox = "inbox_example" # str |  (optional)
    status = "status_example" # str |  (optional)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # List messages
        api_response = api_instance.list_messages(inbox=inbox, status=status)
        pprint(api_response)
    except buziv2.ApiException as e:
        print("Exception when calling SmsApi->list_messages: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **inbox** | **str**|  | [optional]
 **status** | **str**|  | [optional]

### Return type

[**[Message]**](Message.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [BasicAuth](../README.md#BasicAuth), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Invalid ID supplied |  -  |
**404** | Pet not found |  -  |
**405** | Validation exception |  -  |
**0** | Unexpected Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_networks**
> [Network] list_networks()

List networks

Returns a single pet

### Example

* Api Key Authentication (ApiKeyAuth):
* Basic Authentication (BasicAuth):
* Bearer Authentication (BearerAuth):

```python
import time
import buziv2
from buziv2.api import sms_api
from buziv2.model.error import Error
from buziv2.model.network import Network
from pprint import pprint
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
    country_code = "country_code_example" # str | ID of pet to return (optional)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # List networks
        api_response = api_instance.list_networks(country_code=country_code)
        pprint(api_response)
    except buziv2.ApiException as e:
        print("Exception when calling SmsApi->list_networks: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **country_code** | **str**| ID of pet to return | [optional]

### Return type

[**[Network]**](Network.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [BasicAuth](../README.md#BasicAuth), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | successful operation |  -  |
**400** | Invalid ID supplied |  -  |
**404** | Pet not found |  -  |
**0** | Unexpected Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **send_message**
> Message send_message(message_id)

Sends a message

Returns a single pet

### Example

* Api Key Authentication (ApiKeyAuth):
* Basic Authentication (BasicAuth):
* Bearer Authentication (BearerAuth):

```python
import time
import buziv2
from buziv2.api import sms_api
from buziv2.model.error import Error
from buziv2.model.message import Message
from pprint import pprint
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

    # example passing only required values which don't have defaults set
    try:
        # Sends a message
        api_response = api_instance.send_message(message_id)
        pprint(api_response)
    except buziv2.ApiException as e:
        print("Exception when calling SmsApi->send_message: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **message_id** | **int**| ID of pet to return |

### Return type

[**Message**](Message.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [BasicAuth](../README.md#BasicAuth), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | successful operation |  -  |
**400** | Invalid ID supplied |  -  |
**404** | Pet not found |  -  |
**0** | Unexpected Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

