# PerformTranscriptionBody
## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **job\_id** | **String** | The ID of the job | [default to null] |
| **transcription\_fidelity** | **String** | The desired fidelity of the transcription | [default to null] |
| **priority** | **String** | The desired priority of the transcription | [default to null] |
| **callback\_url** | **String** | A URL with query string which will be called on completion. If submitting the callback_url as a query string parameter, rather than a value in the POST data, the callback_url should be URL encoded. The callback URL can contain tags that will be replaced with job specific data when the callback is called. Below is the list of tags that are supported: {job_id}, {job_name}, {elementlist_version}, {iwp_name} (The Interim Work Product name associated with this ElementList version) | [optional] [default to null] |
| **options** | **String** | A job options json. See JobOptions object for details. | [optional] [default to null] |
| **target\_language** | **String** | An RFC 5646 language code to translate this job into. If not specified, then no translation will be performed. If specified, but the language code specified matches the language code on the job request, then no translation will be performed. | [optional] [default to null] |
| **turnaround\_hours** | **Integer** | The number of hours after submission that the job will be returned. If not specified, it will be set to a default based on the value of the priority parameter. The defaults are 24 and 48 for the PRIORITY and STANDARD priorities respectively. If you request a smaller number of hours than the default for the priority you have selected, the priority will be automatically changed. For example if you request a turnaround_hours of 16 with a priority of STANDARD, the priority will be automatically, and silently, changed to PRIORITY. | [optional] [default to null] |

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

