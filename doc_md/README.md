# Documentation for Cielo24

<a name="documentation-for-api-endpoints"></a>
## Documentation for API Endpoints

All URIs are relative to *https://api.cielo24.com/api*

| Class | Method | HTTP request | Description |
|------------ | ------------- | ------------- | -------------|
| *AccountApi* | [**getSettings**](Apis/AccountApi.md#getsettings) | **GET** /account/get_settings | Get Account Settings |
*AccountApi* | [**login**](Apis/AccountApi.md#login) | **POST** /account/login | Login to the cielo24 API to obtain an API access token for use when calling other methods. Optional arguments may be passed either as HTTP headers or query string parameters. Required arguments must be passed as query string parameters. |
*AccountApi* | [**logout**](Apis/AccountApi.md#logout) | **POST** /account/logout | Logout of the current session, invalidating the API token. |
*AccountApi* | [**verifyKey**](Apis/AccountApi.md#verifykey) | **GET** /account/verify_key | Test Auth |
| *JobApi* | [**addMediaFile**](Apis/JobApi.md#addmediafile) | **POST** /job/add_media | Add a piece of media to an existing job using a local file. No content-type should be included in the HTTP header. The media should be uploaded as raw binary, no encoding (base64, hex, etc) is required. Chunk-transfer encoding is NOT supported. File size is limited to 10 gb |
*JobApi* | [**addMediaUrl**](Apis/JobApi.md#addmediaurl) | **GET** /job/add_media | Add a piece of media to an existing job using a public media url. A job may only have a single piece of media associated with it, attempting to add additional media will return an error code. |
*JobApi* | [**authorizeJob**](Apis/JobApi.md#authorizejob) | **POST** /job/authorize | Authorize an existing job. If your account has the \"customer authorization\" feature enabled (it is not enabled by default) jobs you create will be held in the \"Authorizing\" state until you call this method. Calling this method on a job that is not the \"Authorizing\" state has no effect and will return success. Please contact support@cielo24.com to enable the \"customer authorization\" feature. |
*JobApi* | [**newJob**](Apis/JobApi.md#newjob) | **POST** /job/new | Create a new job. A job is a container into which you can upload media and request that transcription be performed. Creating a job is prerequisite for virtually all other methods. |
*JobApi* | [**performTranscription**](Apis/JobApi.md#performtranscription) | **POST** /job/perform_transcription | Request that transcription be performed on the specified job. A callback URL, if specified, will be called when the transcription is complete. See [callback documentation](https://cielo24.readthedocs.io/en/latest/basics.html#callbacks-label) for details. |


<a name="documentation-for-models"></a>
## Documentation for Models

 - [AddMediaResponse](./Models/AddMediaResponse.md)
 - [ErrorResponse](./Models/ErrorResponse.md)
 - [IWPEnum](./Models/IWPEnum.md)
 - [JobOptions](./Models/JobOptions.md)
 - [LoginBody](./Models/LoginBody.md)
 - [LoginResponse](./Models/LoginResponse.md)
 - [NewJobBody](./Models/NewJobBody.md)
 - [NewJobResponse](./Models/NewJobResponse.md)
 - [PerformTranscriptionBody](./Models/PerformTranscriptionBody.md)
 - [PerformTranscriptionResponse](./Models/PerformTranscriptionResponse.md)
 - [VerifyKeyResponse](./Models/VerifyKeyResponse.md)


<a name="documentation-for-authorization"></a>
## Documentation for Authorization

<a name="ApiKeyAuth"></a>
### ApiKeyAuth

- **Type**: API key
- **API key parameter name**: api_token
- **Location**: URL query string

