# JobApi

All URIs are relative to *https://api.cielo24.com/api*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**addMediaFile**](JobApi.md#addMediaFile) | **POST** /job/add_media |  |
| [**addMediaUrl**](JobApi.md#addMediaUrl) | **GET** /job/add_media |  |
| [**authorizeJob**](JobApi.md#authorizeJob) | **POST** /job/authorize |  |
| [**newJob**](JobApi.md#newJob) | **POST** /job/new |  |
| [**performTranscription**](JobApi.md#performTranscription) | **POST** /job/perform_transcription |  |


<a name="addMediaFile"></a>
# **addMediaFile**
> AddMediaResponse addMediaFile(v, job\_id, Content-Length, body, is\_duplicate)



    Add a piece of media to an existing job using a local file. No content-type should be included in the HTTP header. The media should be uploaded as raw binary, no encoding (base64, hex, etc) is required. Chunk-transfer encoding is NOT supported. File size is limited to 10 gb

### Parameters

|Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **v** | **Integer**|  | [default to 1] |
| **job\_id** | **String**|  | [default to null] |
| **Content-Length** | **Integer**|  | [default to null] |
| **body** | **File**|  | |
| **is\_duplicate** | **String**|  | [optional] [default to false] [enum: true, false] |

### Return type

[**AddMediaResponse**](../Models/AddMediaResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: video/mp4
- **Accept**: application/json

<a name="addMediaUrl"></a>
# **addMediaUrl**
> AddMediaResponse addMediaUrl(v, job\_id, media\_url, is\_duplicate)



    Add a piece of media to an existing job using a public media url. A job may only have a single piece of media associated with it, attempting to add additional media will return an error code.

### Parameters

|Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **v** | **Integer**|  | [default to 1] |
| **job\_id** | **String**|  | [default to null] |
| **media\_url** | **String**|  | [default to null] |
| **is\_duplicate** | **String**|  | [optional] [default to false] [enum: true, false] |

### Return type

[**AddMediaResponse**](../Models/AddMediaResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

<a name="authorizeJob"></a>
# **authorizeJob**
> authorizeJob(v, job\_id)



    Authorize an existing job. If your account has the \&quot;customer authorization\&quot; feature enabled (it is not enabled by default) jobs you create will be held in the \&quot;Authorizing\&quot; state until you call this method. Calling this method on a job that is not the \&quot;Authorizing\&quot; state has no effect and will return success. Please contact support@cielo24.com to enable the \&quot;customer authorization\&quot; feature.

### Parameters

|Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **v** | **Integer**|  | [default to 1] |
| **job\_id** | **String**|  | [default to null] |

### Return type

null (empty response body)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

<a name="newJob"></a>
# **newJob**
> NewJobResponse newJob(v, NewJobBody)



    Create a new job. A job is a container into which you can upload media and request that transcription be performed. Creating a job is prerequisite for virtually all other methods.

### Parameters

|Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **v** | **Integer**|  | [default to 1] |
| **NewJobBody** | [**NewJobBody**](../Models/NewJobBody.md)|  | |

### Return type

[**NewJobResponse**](../Models/NewJobResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

<a name="performTranscription"></a>
# **performTranscription**
> PerformTranscriptionResponse performTranscription(v, PerformTranscriptionBody)



    Request that transcription be performed on the specified job. A callback URL, if specified, will be called when the transcription is complete. See [callback documentation](https://cielo24.readthedocs.io/en/latest/basics.html#callbacks-label) for details.

### Parameters

|Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **v** | **Integer**|  | [default to 1] |
| **PerformTranscriptionBody** | [**PerformTranscriptionBody**](../Models/PerformTranscriptionBody.md)|  | |

### Return type

[**PerformTranscriptionResponse**](../Models/PerformTranscriptionResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

