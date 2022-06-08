# AccountApi

All URIs are relative to *https://api.cielo24.com/api*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getSettings**](AccountApi.md#getSettings) | **GET** /account/get_settings |  |
| [**login**](AccountApi.md#login) | **POST** /account/login |  |
| [**logout**](AccountApi.md#logout) | **POST** /account/logout |  |
| [**verifyKey**](AccountApi.md#verifyKey) | **GET** /account/verify_key |  |


<a name="getSettings"></a>
# **getSettings**
> getSettings(v)



    Get Account Settings

### Parameters

|Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **v** | **Integer**|  | [default to 1] |

### Return type

null (empty response body)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

<a name="login"></a>
# **login**
> LoginResponse login(v, LoginBody)



    Login to the cielo24 API to obtain an API access token for use when calling other methods. Optional arguments may be passed either as HTTP headers or query string parameters. Required arguments must be passed as query string parameters.

### Parameters

|Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **v** | **Integer**|  | [default to 1] |
| **LoginBody** | [**LoginBody**](../Models/LoginBody.md)|  | |

### Return type

[**LoginResponse**](../Models/LoginResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

<a name="logout"></a>
# **logout**
> logout(v)



    Logout of the current session, invalidating the API token.

### Parameters

|Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **v** | **Integer**|  | [default to 1] |

### Return type

null (empty response body)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

<a name="verifyKey"></a>
# **verifyKey**
> VerifyKeyResponse verifyKey(v)



    Test Auth

### Parameters

|Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **v** | **Integer**|  | [default to 1] |

### Return type

[**VerifyKeyResponse**](../Models/VerifyKeyResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

