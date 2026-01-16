# Cloudmersive.APIClient.NET.BotDetection.Api.CaptchaApi

All URIs are relative to *https://api.cloudmersive.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**BotCaptchaImageGeneratePost**](CaptchaApi.md#botcaptchaimagegeneratepost) | **POST** /bot/captcha/image/generate | Create an image CAPTCHA |
| [**BotCaptchaImageValidatePost**](CaptchaApi.md#botcaptchaimagevalidatepost) | **POST** /bot/captcha/image/validate | Validate a CAPTCHA response from the user |

<a id="botcaptchaimagegeneratepost"></a>
# **BotCaptchaImageGeneratePost**
> ImageCaptchaGenerateResult BotCaptchaImageGeneratePost (int? characters = null)

Create an image CAPTCHA

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Cloudmersive.APIClient.NET.BotDetection.Api;
using Cloudmersive.APIClient.NET.BotDetection.Client;
using Cloudmersive.APIClient.NET.BotDetection.Model;

namespace Example
{
    public class BotCaptchaImageGeneratePostExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.cloudmersive.com";
            // Configure API key authorization: Apikey
            config.AddApiKey("Apikey", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("Apikey", "Bearer");

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new CaptchaApi(httpClient, config, httpClientHandler);
            var characters = 56;  // int? | Number of characters to request that the user enter; must be 2 or more (optional) 

            try
            {
                // Create an image CAPTCHA
                ImageCaptchaGenerateResult result = apiInstance.BotCaptchaImageGeneratePost(characters);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CaptchaApi.BotCaptchaImageGeneratePost: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the BotCaptchaImageGeneratePostWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create an image CAPTCHA
    ApiResponse<ImageCaptchaGenerateResult> response = apiInstance.BotCaptchaImageGeneratePostWithHttpInfo(characters);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CaptchaApi.BotCaptchaImageGeneratePostWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **characters** | **int?** | Number of characters to request that the user enter; must be 2 or more | [optional]  |

### Return type

[**ImageCaptchaGenerateResult**](ImageCaptchaGenerateResult.md)

### Authorization

[Apikey](../README.md#Apikey)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: text/plain, application/json, text/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="botcaptchaimagevalidatepost"></a>
# **BotCaptchaImageValidatePost**
> ImageCaptchaValidateResult BotCaptchaImageValidatePost (string captchaID = null, string challengeResponse = null, int? userTimeoutMilliseconds = null)

Validate a CAPTCHA response from the user

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Cloudmersive.APIClient.NET.BotDetection.Api;
using Cloudmersive.APIClient.NET.BotDetection.Client;
using Cloudmersive.APIClient.NET.BotDetection.Model;

namespace Example
{
    public class BotCaptchaImageValidatePostExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.cloudmersive.com";
            // Configure API key authorization: Apikey
            config.AddApiKey("Apikey", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("Apikey", "Bearer");

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new CaptchaApi(httpClient, config, httpClientHandler);
            var captchaID = "captchaID_example";  // string | The ID of the CAPTCHA (this is returned from the CAPTCHA generate API) (optional) 
            var challengeResponse = "challengeResponse_example";  // string | The challenge response input text received from the user to validate if they are a person or bot (optional) 
            var userTimeoutMilliseconds = 56;  // int? | The amount of time in milliseconds to allow the user to respond; if the response occurs more than this amount of time, in milliseconds, after the CAPTCHA was created, the answer will be considered invalid even if it is correct (optional) 

            try
            {
                // Validate a CAPTCHA response from the user
                ImageCaptchaValidateResult result = apiInstance.BotCaptchaImageValidatePost(captchaID, challengeResponse, userTimeoutMilliseconds);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CaptchaApi.BotCaptchaImageValidatePost: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the BotCaptchaImageValidatePostWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Validate a CAPTCHA response from the user
    ApiResponse<ImageCaptchaValidateResult> response = apiInstance.BotCaptchaImageValidatePostWithHttpInfo(captchaID, challengeResponse, userTimeoutMilliseconds);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CaptchaApi.BotCaptchaImageValidatePostWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **captchaID** | **string** | The ID of the CAPTCHA (this is returned from the CAPTCHA generate API) | [optional]  |
| **challengeResponse** | **string** | The challenge response input text received from the user to validate if they are a person or bot | [optional]  |
| **userTimeoutMilliseconds** | **int?** | The amount of time in milliseconds to allow the user to respond; if the response occurs more than this amount of time, in milliseconds, after the CAPTCHA was created, the answer will be considered invalid even if it is correct | [optional]  |

### Return type

[**ImageCaptchaValidateResult**](ImageCaptchaValidateResult.md)

### Authorization

[Apikey](../README.md#Apikey)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: text/plain, application/json, text/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

