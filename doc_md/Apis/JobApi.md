# JobApi

All URIs are relative to *https://api.cielo24.com/api*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**addMediaFile**](JobApi.md#addMediaFile) | **POST** /job/add_media |  |
| [**addMediaUrl**](JobApi.md#addMediaUrl) | **GET** /job/add_media |  |
| [**authorizeJob**](JobApi.md#authorizeJob) | **POST** /job/authorize |  |
| [**getCaption**](JobApi.md#getCaption) | **GET** /job/get_caption |  |
| [**newJob**](JobApi.md#newJob) | **POST** /job/new |  |
| [**performTranscription**](JobApi.md#performTranscription) | **POST** /job/perform_transcription |  |
| [**performTranslation**](JobApi.md#performTranslation) | **POST** /job/perform_translation |  |


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

<a name="getCaption"></a>
# **getCaption**
> String getCaption(v, job\_id, caption\_format, build\_url, caption\_words\_min, caption\_by\_sentence, characters\_per\_caption\_line, dfxp\_header, disallow\_dangling, display\_effects\_speaker\_as, display\_speaker\_id, iwp\_name, elementlist\_version, emit\_speaker\_change\_tokens\_as, force\_case, include\_dfxp\_metadata, layout\_target\_caption\_length\_ms, line\_break\_on\_sentence, line\_ending\_format, lines\_per\_caption, mask\_profanity, maximum\_caption\_duration, merge\_gap\_interval, minimum\_caption\_length\_ms, minimum\_gap\_between\_captions\_ms, qt\_seamless, remove\_disfluencies, remove\_sounds\_list, remove\_sound\_references, replace\_slang, silence\_max\_ms, single\_speaker\_per\_caption, sound\_boundaries, sound\_threshold, sound\_tokens\_by\_caption, sound\_tokens\_by\_line, sound\_tokens\_by\_caption\_list, sound\_tokens\_by\_line\_list, speaker\_on\_new\_line, srt\_format, strip\_square\_brackets, utf8\_mark, replace\_english\_spelling)



    Get the caption file for a job. The job must have completed transcription before a caption can be downloaded.

### Parameters

|Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **v** | **Integer**|  | [default to 1] |
| **job\_id** | **String**|  | [default to null] |
| **caption\_format** | **String**|  | [default to null] [enum: DFXP, ECHO, QT, SAMI, SBV, SCC, SRT, TPM, TRANSCRIPT, TWX, WEB_VTT] |
| **build\_url** | **String**| Rather than returning the file, return a permanent URL to the file. | [optional] [default to false] [enum: true, false] |
| **caption\_words\_min** | **Integer**| Minimum number of words allowed in a caption. | [optional] [default to 1] |
| **caption\_by\_sentence** | **String**| When true, puts each sentence into its own caption. When false, more than one sentence may appear in a single caption. | [optional] [default to true] [enum: true, false] |
| **characters\_per\_caption\_line** | **Integer**| Maximum number of characters to be displayed on each caption line. | [optional] [default to 42] |
| **dfxp\_header** | **String**| Allows you to specify a custom header for your DFXP caption file. The header should be the entire contents of the header including the opening and closing tags. Ignored if caption_format does not equal DFXP. | [optional] [default to ] |
| **disallow\_dangling** | **String**| Will prevent captions from having the last word in a sentence start a new line. Last words will ALWAYS be kept on the same line, even if it breaks the characters_per_caption_line option. | [optional] [default to false] [enum: true, false] |
| **display\_effects\_speaker\_as** | **String**| Determines what speaker name should used for sound effects. | [optional] [default to Effects] |
| **display\_speaker\_id** | **String**| Determines the way speakers are identified in the captions. Choose \&quot;no\&quot; to not display speaker identities at all: \&quot;&gt;&gt; example\&quot; Choose \&quot;number\&quot; to display only the speaker number: \&quot;&gt;&gt; Speaker 1: example\&quot; Choose \&quot;name\&quot; to display the speaker name: \&quot;&gt;&gt; John Doe: example\&quot;. If you choose \&quot;name\&quot;, the speaker number will be displayed if the name is not available. | [optional] [default to name] [enum: no, number, name] |
| **iwp\_name** | **String**| The named version of element list to generate the transcript from. If not specified, the transcript will be generated from the latest version. | [optional] [default to ] [enum: PREMIUM, INTERIM_PROFESSIONAL, PROFESSIONAL, SPEAKER_ID, FINAL, MECHANICAL, CUSTOMER_APPROVED_RETURN, CUSTOMER_APPROVED_TRANSLATION] |
| **elementlist\_version** | **String**| The version of element list to generate the captions from. If not specified, the caption will be generated from the latest version. (ISO 8601 Date String) | [optional] [default to ] |
| **emit\_speaker\_change\_tokens\_as** | **String**| Determine what characters to use to denote speaker changes. | [optional] [default to &gt;&gt;] |
| **force\_case** | **String**| Force the contents of the captions to be all UPPER or lower case. If blank, the case of the captions is not changed. | [optional] [default to ] [enum: , lower, upper] |
| **include\_dfxp\_metadata** | **String**| When true, and the caption format requested is DFXP, the jobs name, ID and language will be added to the DFXP metadata header. When false, these data are omitted from the header. Ignored if caption_format does not equal DFXP. | [optional] [default to true] [enum: true, false] |
| **layout\_target\_caption\_length\_ms** | **Integer**| Captions generated will, on average, be this duration. However, they may vary significantly based on other parameters you set. | [optional] [default to 5000] |
| **line\_break\_on\_sentence** | **String**| Inserts a line break in between sentences that are in the same caption. | [optional] [default to false] [enum: true, false] |
| **line\_ending\_format** | **String**| Determine the end of line (EOL) character to use for the captions. | [optional] [default to UNIX] [enum: UNIX, OSX, WINDOWS] |
| **lines\_per\_caption** | **Integer**| Number of lines to be displayed for each caption. | [optional] [default to 2] |
| **mask\_profanity** | **String**| Replace profanity with asterisks. | [optional] [default to false] [enum: true, false] |
| **maximum\_caption\_duration** | **Integer**| No captions longer than this (in milliseconds) will be produced. If not specified, there is no maximum. | [optional] [default to null] |
| **merge\_gap\_interval** | **Integer**| Captions with a gap between them that is smaller than this (in milliseconds) will have their start and/or end times changed so there is no time gap between the captions. | [optional] [default to 1000] |
| **minimum\_caption\_length\_ms** | **Integer**| Extends the duration of short captions to the this minimum length. Additional time is taken from later caption blocks to meet this minimum time. | [optional] [default to null] |
| **minimum\_gap\_between\_captions\_ms** | **Integer**| Adds a minimum time between captions such as there will always be some time between captions where no text is displayed. When captions are very close together, time will be removed from the caption duration to make the gap. | [optional] [default to null] |
| **qt\_seamless** | **String**| Does not put time gaps of any kind between caption blocks. Ignored if caption_format does not equal QT. | [optional] [default to false] [enum: true, false] |
| **remove\_disfluencies** | **String**| Remove verbal disfluencies from the generated transcript. Common disfluencies such as \&quot;um\&quot; and \&quot;ah\&quot; are removed while maintaining appropriate punctuation. | [optional] [default to true] [enum: true, false] |
| **remove\_sounds\_list** | [**List**](../Models/String.md)| A list of sounds to not show in the caption. This is a JSON style list, and should look like [\&quot;MUSIC\&quot;, \&quot;LAUGH\&quot;]. Ignored if remove_sound_references is true. | [optional] [default to []] [enum: UNKNOWN, INAUDIBLE, CROSSTALK, MUSIC, NOISE, LAUGH, COUGH, FOREIGN, BLANK_AUDIO, APPLAUSE, BLEEP, ENDS_SENTENCE] |
| **remove\_sound\_references** | **String**| Remove ALL non-verbal sound and noise references from the generated transcript. Sounds and unidentified noises are depicted in the caption as [SOUND], [COUGH] and [NOISE]. If this parameter is set, these identifiers are omitted from the caption. | [optional] [default to true] [enum: true, false] |
| **replace\_slang** | **String**| Replace common slang terms from the generated transcript. Common replacements are \&quot;want to\&quot; for \&quot;wanna\&quot;, \&quot;going to\&quot; for \&quot;gonna\&quot;, etc. | [optional] [default to false] [enum: true, false] |
| **silence\_max\_ms** | **Integer**| If there is a interval of silence in the middle of a sentence longer than this, then the caption will be split. | [optional] [default to 2000] |
| **single\_speaker\_per\_caption** | **String**| When true, puts each speaker into its own caption. When false, more than one speaker may appear in a single caption. | [optional] [default to true] [enum: true, false] |
| **sound\_boundaries** | [**List**](../Models/String.md)| Specifies the characters to surround sound references with. The default will generate sound references that look like this: [MUSIC]. | [optional] [default to [&quot;[&quot;,&quot;]&quot;]] |
| **sound\_threshold** | **Integer**| Sound references that are longer than this threshold will be made their own caption entirely, and will not have any text included with them. If not set, Sound references will be included back to back with text no matter the duration of the sound. | [optional] [default to null] |
| **sound\_tokens\_by\_caption** | **String**| If true, all sound references will always be in their own caption. If false, more than one sound reference may appear in a single caption. | [optional] [default to false] [enum: true, false] |
| **sound\_tokens\_by\_line** | **String**| If true, all sound references will always be in their own line. If false, more than one sound reference may appear in a single line. | [optional] [default to false] [enum: true, false] |
| **sound\_tokens\_by\_caption\_list** | [**List**](../Models/String.md)| If non-empty, the specified sound references will always be in their own caption. If empty, more than one sound reference may appear in a single caption. Ignored if sound_tokens_by_caption is true. | [optional] [default to [&quot;BLANK_AUDIO&quot;,&quot;MUSIC&quot;]] [enum: UNKNOWN, INAUDIBLE, CROSSTALK, MUSIC, NOISE, LAUGH, COUGH, FOREIGN, BLANK_AUDIO, APPLAUSE, BLEEP, ENDS_SENTENCE] |
| **sound\_tokens\_by\_line\_list** | [**List**](../Models/String.md)| If non-empty, the specified sound references will always be in their own line. If empty, more than one sound reference may appear in a single line. Ignored if sound_tokens_by_line is true. | [optional] [default to [&quot;BLANK_AUDIO&quot;,&quot;MUSIC&quot;]] [enum: UNKNOWN, INAUDIBLE, CROSSTALK, MUSIC, NOISE, LAUGH, COUGH, FOREIGN, BLANK_AUDIO, APPLAUSE, BLEEP, ENDS_SENTENCE] |
| **speaker\_on\_new\_line** | **String**| If true, a speaker change will cause a new caption to be made. If false, multiple speakers may appear in a single caption. | [optional] [default to true] [enum: true, false] |
| **srt\_format** | **String**| If the caption format is SRT, determines what the caption blocks will look like. The default, prints caption blocks that look like this:    1:   00:00:06,060 --&gt; 00:00:16,060   This is the caption text.  You can alter the caption block by re-arranging or removing the substitution string values, shown enclosed in braces \&quot;{}\&quot; in the default value below. Substitution strings may used more than once if desired. Any text that is not a substitution string will be displayed as written. To add new lines, include a \\n. Note, you may need to escape the \\n with an extra backslash when encoding the request.  | [optional] [default to {caption_number:d}\n{start_hour:02d}:{start_minute:02d}:{start_second:02d},{start_millisecond:03d} --&gt;{end_hour:02d}:{end_minute:02d}:{end_second:02d},{end_millisecond:03d}\n{caption_text}\n\n] |
| **strip\_square\_brackets** | **String**| Removes all square brackets like &#39;[&#39; or &#39;]&#39; from captions. By default square brackets surround sound references like &#39;[MUSIC]&#39;, but they may exist as part of the caption text as well. | [optional] [default to false] [enum: true, false] |
| **utf8\_mark** | **String**| Adds a utf8 bytemark to the beginning of the caption. This should only be used if the system you are loading the caption files into needs a byte marker. The vast majority of systems do not. | [optional] [default to false] [enum: true, false] |
| **replace\_english\_spelling** | **String**| Replaces English spelling with location accurate spelling. i.e. Color --&gt; Colour  A: American  B: British  Z: British ize  U: Australian  C: Canadian  | [optional] [default to A] [enum: A, B, Z, U, C] |

### Return type

**String**

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: text/plain, application/json

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

<a name="performTranslation"></a>
# **performTranslation**
> PerformTranslationResponse performTranslation(v, job\_id, target\_languages, approve\_uplevel)



    Request that orders a new Translation language for a video that has been previously Transcribed and/or Translated. The New Job ID and job target language will be returned upon completion.

### Parameters

|Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **v** | **Integer**|  | [default to 1] |
| **job\_id** | **String**|  | [default to null] |
| **target\_languages** | **String**| The language(s) being ordered (Any RFC 5646 language code) separated by comma (,) | [default to null] |
| **approve\_uplevel** | **String**|  | [optional] [default to null] [enum: true, false, t, f, true, false] |

### Return type

[**PerformTranslationResponse**](../Models/PerformTranslationResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

