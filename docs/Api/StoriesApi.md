# OpenAPI\Client\StoriesApi

All URIs are relative to https://gate.whapi.cloud, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createStory()**](StoriesApi.md#createStory) | **POST** /stories | Create &amp; publish story |
| [**getStories()**](StoriesApi.md#getStories) | **GET** /stories | Get list of stories |


## `createStory()`

```php
createStory($sender_stories): \OpenAPI\Client\Model\SentMessage
```

Create & publish story

The method responsible for sending images or texts to your status. Remember that statuses disappear after 24 hours. The requirements for [sending all media types are identical](https://support.whapi.cloud/help-desk/sending/send-video-audio-image-document)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: tokenAuth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('token', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('token', 'Bearer');

// Configure Bearer (token) authorization: bearerAuth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new OpenAPI\Client\Api\StoriesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$sender_stories = new \OpenAPI\Client\Model\SenderStories(); // \OpenAPI\Client\Model\SenderStories | Stories post parameters

try {
    $result = $apiInstance->createStory($sender_stories);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StoriesApi->createStory: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **sender_stories** | [**\OpenAPI\Client\Model\SenderStories**](../Model/SenderStories.md)| Stories post parameters | |

### Return type

[**\OpenAPI\Client\Model\SentMessage**](../Model/SentMessage.md)

### Authorization

[tokenAuth](../../README.md#tokenAuth), [bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getStories()`

```php
getStories($count, $offset, $time_from, $time_to, $normal_types, $author, $from_me): \OpenAPI\Client\Model\MessagesList
```

Get list of stories

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: tokenAuth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('token', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('token', 'Bearer');

// Configure Bearer (token) authorization: bearerAuth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new OpenAPI\Client\Api\StoriesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$count = 100; // float | Count of objects to return
$offset = 3.4; // float | Offset of objects to return
$time_from = 3.4; // float | Timestamp from which to get objects
$time_to = 3.4; // float | Timestamp up to which to get objects
$normal_types = True; // bool | If false, include system messages
$author = 'author_example'; // string | To filter by author (Contact ID)
$from_me = True; // bool | If true, only return messages sent by the authenticated user. If false, only return messages sent by other users.

try {
    $result = $apiInstance->getStories($count, $offset, $time_from, $time_to, $normal_types, $author, $from_me);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StoriesApi->getStories: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **count** | **float**| Count of objects to return | [optional] [default to 100] |
| **offset** | **float**| Offset of objects to return | [optional] |
| **time_from** | **float**| Timestamp from which to get objects | [optional] |
| **time_to** | **float**| Timestamp up to which to get objects | [optional] |
| **normal_types** | **bool**| If false, include system messages | [optional] |
| **author** | **string**| To filter by author (Contact ID) | [optional] |
| **from_me** | **bool**| If true, only return messages sent by the authenticated user. If false, only return messages sent by other users. | [optional] |

### Return type

[**\OpenAPI\Client\Model\MessagesList**](../Model/MessagesList.md)

### Authorization

[tokenAuth](../../README.md#tokenAuth), [bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
