# OpenAPI\Client\BusinessApi

All URIs are relative to https://gate.whapi.cloud, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createProduct()**](BusinessApi.md#createProduct) | **POST** /business/products | Create product |
| [**deleteProduct()**](BusinessApi.md#deleteProduct) | **DELETE** /business/products/{ProductID} | Delete product |
| [**getContactProducts()**](BusinessApi.md#getContactProducts) | **GET** /business/{ContactID}/products | Get products by Contact ID |
| [**getOrderItems()**](BusinessApi.md#getOrderItems) | **GET** /business/orders/{OrderID} | Get order items |
| [**getProduct()**](BusinessApi.md#getProduct) | **GET** /business/products/{ProductID} | Get product |
| [**getProducts()**](BusinessApi.md#getProducts) | **GET** /business/products | Get products |
| [**sendCatalog()**](BusinessApi.md#sendCatalog) | **POST** /business/catalogs/{ContactID} | Send catalog by Contact ID (phone number) |
| [**sendProduct()**](BusinessApi.md#sendProduct) | **POST** /business/products/{ProductID} | Send product |
| [**updateProduct()**](BusinessApi.md#updateProduct) | **PATCH** /business/products/{ProductID} | Update product |


## `createProduct()`

```php
createProduct($product_create): \OpenAPI\Client\Model\Product
```

Create product

In this method you will be able to register a product in your catalog

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


$apiInstance = new OpenAPI\Client\Api\BusinessApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$product_create = new \OpenAPI\Client\Model\ProductCreate(); // \OpenAPI\Client\Model\ProductCreate | Request body

try {
    $result = $apiInstance->createProduct($product_create);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BusinessApi->createProduct: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **product_create** | [**\OpenAPI\Client\Model\ProductCreate**](../Model/ProductCreate.md)| Request body | [optional] |

### Return type

[**\OpenAPI\Client\Model\Product**](../Model/Product.md)

### Authorization

[tokenAuth](../../README.md#tokenAuth), [bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteProduct()`

```php
deleteProduct($product_id): \OpenAPI\Client\Model\ResponseSuccess
```

Delete product

In this method you will be able to delete a product by its ID

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


$apiInstance = new OpenAPI\Client\Api\BusinessApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$product_id = 'product_id_example'; // string | Product ID

try {
    $result = $apiInstance->deleteProduct($product_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BusinessApi->deleteProduct: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **product_id** | **string**| Product ID | |

### Return type

[**\OpenAPI\Client\Model\ResponseSuccess**](../Model/ResponseSuccess.md)

### Authorization

[tokenAuth](../../README.md#tokenAuth), [bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getContactProducts()`

```php
getContactProducts($contact_id, $count, $offset): \OpenAPI\Client\Model\ProductsList
```

Get products by Contact ID

This method allows you to get the catalog and products by [Chat ID](https://support.whapi.cloud/help-desk/faq/chat-id.-what-is-it-and-how-to-get-it), even if it is not in your contact list

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


$apiInstance = new OpenAPI\Client\Api\BusinessApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$contact_id = 'contact_id_example'; // string | Contact ID
$count = 100; // float | Count of objects to return
$offset = 3.4; // float | Offset of objects to return

try {
    $result = $apiInstance->getContactProducts($contact_id, $count, $offset);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BusinessApi->getContactProducts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **contact_id** | **string**| Contact ID | |
| **count** | **float**| Count of objects to return | [optional] [default to 100] |
| **offset** | **float**| Offset of objects to return | [optional] |

### Return type

[**\OpenAPI\Client\Model\ProductsList**](../Model/ProductsList.md)

### Authorization

[tokenAuth](../../README.md#tokenAuth), [bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getOrderItems()`

```php
getOrderItems($order_id, $order_token): \OpenAPI\Client\Model\OrderItems
```

Get order items

The method allows you to get information about the items in the shopping cart sent to you in messages

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


$apiInstance = new OpenAPI\Client\Api\BusinessApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$order_id = 'order_id_example'; // string | Order ID
$order_token = 'order_token_example'; // string | Base64 token from order for receiving information

try {
    $result = $apiInstance->getOrderItems($order_id, $order_token);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BusinessApi->getOrderItems: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **order_id** | **string**| Order ID | |
| **order_token** | **string**| Base64 token from order for receiving information | [optional] |

### Return type

[**\OpenAPI\Client\Model\OrderItems**](../Model/OrderItems.md)

### Authorization

[tokenAuth](../../README.md#tokenAuth), [bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getProduct()`

```php
getProduct($product_id): \OpenAPI\Client\Model\Product
```

Get product

In this method you will be able to get your product by its ID

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


$apiInstance = new OpenAPI\Client\Api\BusinessApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$product_id = 'product_id_example'; // string | Product ID

try {
    $result = $apiInstance->getProduct($product_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BusinessApi->getProduct: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **product_id** | **string**| Product ID | |

### Return type

[**\OpenAPI\Client\Model\Product**](../Model/Product.md)

### Authorization

[tokenAuth](../../README.md#tokenAuth), [bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getProducts()`

```php
getProducts($count, $offset): \OpenAPI\Client\Model\ProductsList
```

Get products

With this method you will be able to get the products from a Whatsapp Business catalog

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


$apiInstance = new OpenAPI\Client\Api\BusinessApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$count = 100; // float | Count of objects to return
$offset = 3.4; // float | Offset of objects to return

try {
    $result = $apiInstance->getProducts($count, $offset);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BusinessApi->getProducts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **count** | **float**| Count of objects to return | [optional] [default to 100] |
| **offset** | **float**| Offset of objects to return | [optional] |

### Return type

[**\OpenAPI\Client\Model\ProductsList**](../Model/ProductsList.md)

### Authorization

[tokenAuth](../../README.md#tokenAuth), [bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `sendCatalog()`

```php
sendCatalog($contact_id, $sender_catalog_by_id): \OpenAPI\Client\Model\SentMessage
```

Send catalog by Contact ID (phone number)

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


$apiInstance = new OpenAPI\Client\Api\BusinessApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$contact_id = 'contact_id_example'; // string | Contact ID
$sender_catalog_by_id = new \OpenAPI\Client\Model\SenderCatalogByID(); // \OpenAPI\Client\Model\SenderCatalogByID | Message catalog

try {
    $result = $apiInstance->sendCatalog($contact_id, $sender_catalog_by_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BusinessApi->sendCatalog: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **contact_id** | **string**| Contact ID | |
| **sender_catalog_by_id** | [**\OpenAPI\Client\Model\SenderCatalogByID**](../Model/SenderCatalogByID.md)| Message catalog | |

### Return type

[**\OpenAPI\Client\Model\SentMessage**](../Model/SentMessage.md)

### Authorization

[tokenAuth](../../README.md#tokenAuth), [bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`, `multipart/form-data`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `sendProduct()`

```php
sendProduct($product_id, $sender_product_from_catalog): \OpenAPI\Client\Model\SentMessage
```

Send product

The method is for sending an item from your catalog

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


$apiInstance = new OpenAPI\Client\Api\BusinessApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$product_id = 'product_id_example'; // string | Product ID
$sender_product_from_catalog = new \OpenAPI\Client\Model\SenderProductFromCatalog(); // \OpenAPI\Client\Model\SenderProductFromCatalog | Message product

try {
    $result = $apiInstance->sendProduct($product_id, $sender_product_from_catalog);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BusinessApi->sendProduct: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **product_id** | **string**| Product ID | |
| **sender_product_from_catalog** | [**\OpenAPI\Client\Model\SenderProductFromCatalog**](../Model/SenderProductFromCatalog.md)| Message product | |

### Return type

[**\OpenAPI\Client\Model\SentMessage**](../Model/SentMessage.md)

### Authorization

[tokenAuth](../../README.md#tokenAuth), [bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`, `multipart/form-data`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateProduct()`

```php
updateProduct($product_id, $product_edit): \OpenAPI\Client\Model\Product
```

Update product

The *images* field is required and must contain all images

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


$apiInstance = new OpenAPI\Client\Api\BusinessApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$product_id = 'product_id_example'; // string | Product ID
$product_edit = new \OpenAPI\Client\Model\ProductEdit(); // \OpenAPI\Client\Model\ProductEdit | Message product

try {
    $result = $apiInstance->updateProduct($product_id, $product_edit);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BusinessApi->updateProduct: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **product_id** | **string**| Product ID | |
| **product_edit** | [**\OpenAPI\Client\Model\ProductEdit**](../Model/ProductEdit.md)| Message product | |

### Return type

[**\OpenAPI\Client\Model\Product**](../Model/Product.md)

### Authorization

[tokenAuth](../../README.md#tokenAuth), [bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`, `multipart/form-data`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
