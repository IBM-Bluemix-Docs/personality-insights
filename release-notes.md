---

copyright:
  years: 2015, 2020
lastupdated: "2020-11-02"

subcollection: personality-insights

---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}
{:tip: .tip}
{:important: .important}
{:note: .note}
{:deprecated: .deprecated}
{:pre: .pre}
{:codeblock: .codeblock}
{:screen: .screen}
{:javascript: .ph data-hd-programlang='javascript'}
{:java: .ph data-hd-programlang='java'}
{:python: .ph data-hd-programlang='python'}
{:swift: .ph data-hd-programlang='swift'}

# Release notes
{: #release-notes}

The following sections document the new features and changes that were included for each release of the {{site.data.keyword.personalityinsightsfull}} service. Unless otherwise noted, all changes are compatible with earlier releases and are automatically and transparently available to all new and existing applications.
{: shortdesc}

The release notes document the *service version* and *interface version* for all recent updates. You specify the *interface version* with the `version` query parameter to use new features and functionality made available with that update. The service returns both versions with the `X-Service-Api-Version` response header.
{: note}

## 1 November 2020
{: #November2020}

{{site.data.keyword.IBM}} will begin sunsetting {{site.data.keyword.personalityinsightsfull}} on 1 December 2020. For a period of one year from this date, you will still be able to use {{site.data.keyword.personalityinsightsshort}}. However, as of 1 December 2021, the offering will no longer be available.<br/><br/>As an alternative, we encourage you to consider migrating to {{site.data.keyword.nlufull}}, a service on {{site.data.keyword.cloud}} that uses deep learning to extract data and insights from text such as keywords, categories, sentiment, emotion, and syntax to provide insights for your business or industry. For more information, see [About {{site.data.keyword.nlushort}}](https://cloud.ibm.com/docs/natural-language-understanding?topic=natural-language-understanding-about).
{: deprecated}

{{site.data.keyword.nlushort}} offers several features and capabilities that make it an attractive alternative to {{site.data.keyword.personalityinsightsshort}}. By default, {{site.data.keyword.nlushort}} provides the following features:

-   Understand emotions by detecting anger, disgust, fear, joy, or sadness that is conveyed in the content or by the context around target phrases specified in the target parameter.
-   Understand the general sentiment of your content or the sentiment toward specific target phrases.

Clients who want to continue their use cases currently supported by {{site.data.keyword.personalityinsightsshort}} can re-create the capabilities by leveraging {{site.data.keyword.nlushort}} and {{site.data.keyword.nlclassifierfull}} to build their own custom text classification models.

For more information about how clients are using {{site.data.keyword.nlushort}}, see these case studies:

-   [www.ibm.com/case-studies/centiment](https://www.ibm.com/case-studies/centiment){: external}
-   [www.ibm.com/case-studies/havas](https://www.ibm.com/case-studies/havas){: external}
-   [www.ibm.com/case-studies/buzz-radar-cloud-marketing-performance-optimization](https://www.ibm.com/case-studies/buzz-radar-cloud-marketing-performance-optimization){: external}
-   [www.ibm.com/case-studies/guardio-cloud-bullying-detection-application](https://www.ibm.com/case-studies/guardio-cloud-bullying-detection-application){: external}
-   [www.ibm.com/case-studies/opentopic-inc](https://www.ibm.com/case-studies/opentopic-inc){: external}

## 12 December 2019
{: #December2019}

**Service version** - `3.6.1`<br/> **Interface version** - `2017-10-13`

- **Full support for IBM Cloud IAM**

    - {{site.data.keyword.personalityinsightsshort}} now supports the full implementation of {{site.data.keyword.cloud_notm}} Identity and Access Management (IAM). API keys for Watson services are no longer limited to a single service instance. You can create access policies and API keys that apply to more than one service, and you can grant access between services.
    - To support this change, the API service endpoints use a different domain and include the service instance ID. The pattern is `api.{location}.{offering}.watson.cloud.ibm.com/instances/{instance_id}`.

        Example URL for an instance hosted in the Dallas location: `api.us-south.personality-insights.watson.cloud.ibm.com/instances/6bbda3b3-d572-45e1-8c54-22d6ed9e52c2`

        The previous public endpoint domain was `watsonplatform.net`.

        For more information about the URLs, see the [API & SDK reference](https://{DomainName}/apidocs/personality-insights#service-endpoint){: external}.

        These URLs do not introduce a breaking change. The new URLs work both for your existing service instances and for new instances. The original URLs continue to work on your existing service instances for at least one year (until December 2020).
    - For more information about IAM, see [Authenticating to Watson services](/docs/watson?topic=watson-iam).

- **New network and data security features**

    **Support for private network endpoints**

   Users of Premium plans can create private network endpoints to connect to {{site.data.keyword.personalityinsightsshort}} over a private network. Connections to private network endpoints do not require public internet access. For more information, see [Public and private network endpoints](/docs/personality-insights?topic=watson-public-private-endpoints).

## 15 November 2019
{: #November2019}

**Service version** - `3.6.1`<br/> **Interface version** - `2017-10-13`

**New South Korea location**

You can now create {{site.data.keyword.personalityinsightsshort}} instances in the Seoul location. As with other locations, the {{site.data.keyword.cloud_notm}} Seoul location uses token-based Identity and Access Management (IAM) authentication.

## Older releases
{: #older}

-   [30 July 2019](#July2019)
-   [18 June 2019](#June2019)
-   [9 January 2019](#January2019)
-   [21 December 2018](#December2018)
-   [18 November 2018](#November2018b)
-   [7 November 2018](#November2018a)
-   [30 October 2018](#October2018)
-   [11 June 2018](#June2018b)
-   [4 June 2018](#June2018a)
-   [23 March 2018](#March2018)
-   [13 October 2017](#October2017)
-   [18 September 2017](#September2017)
-   [10 April 2017](#April2017)
-   [1 March 2017](#March2017)
-   [20 February 2017](#February2017b)
-   [13 February 2017](#February2017)
-   [13 January 2017](#January2017)
-   [15 December 2016](#December2016)
-   [15 November 2016](#November2016)
-   [20 October 2016](#October2016b)
-   [12 October 2016](#October2016a)
-   [31 August 2016](#August2016)
-   [14 July 2016](#July2016b)
-   [1 July 2016](#July2016a)
-   [7 June 2016](#June2016b)
-   [1 June 2016](#June2016a)
-   [17 May 2016](#May2016)
-   [18 March 2016](#March2016)
-   [9 July 2015](#July2015)
-   [23 February 2015](#February2015)

### 30 July 2019
{: #July2019}

**Service version** - `3.6.1`<br/> **Interface version** - `2017-10-13`

- Overall, accuracy of [emotional range (neuroticism)](/docs/personality-insights?topic=personality-insights-emotionalRange) improved. For details about the accuracy of the service, see [Per-language average MAE and correlation](/docs/personality-insights?topic=personality-insights-science#precisePerLanguage). Because the emotional range dimension is part of the *Big Five* personality characteristics, the accuracy of that dimension is included in the value of the *Big Five dimensions* column.
- For Arabic, the emotional range is now statistically significant. The limitation that existed previously was removed from the table in [Limitations for Arabic and Korean input](/docs/personality-insights?topic=personality-insights-numeric#limitations).

### 18 June 2019
{: #June2019}

**Service version** - `3.6.0`<br/> **Interface version** - `2017-10-13`

The service was updated to maintain compatibility with {{site.data.keyword.cloud_notm}}.

### 9 January 2019
{: #January2019}

**Service version** - `3.5.0`<br/> **Interface version** - `2017-10-13`

The service was updated for small defect fixes.

### 21 December 2018
{: #December2018}

**Service version** - `3.4.5`<br/> **Interface version** - `2017-10-13`

Version 2 of the {{site.data.keyword.personalityinsightsshort}} API has been removed from service. Version 3 of the service was released on 19 October 2016. At that time, users were strongly encouraged to migrate from version 2 as soon as possible.

### 18 November 2018
{: #November2018b}

**Service version** - `3.4.5`<br/> **Interface version** - `2017-10-13`

The {{site.data.keyword.personalityinsightsshort}} service is now available in the {{site.data.keyword.cloud}} London location (**eu-gb**). Like all locations, London uses token-based Identity and Access Management (IAM) authentication. All new services instances that you create in this location use IAM authentication.

### 7 November 2018
{: #November2018a}

**Service version** - `3.4.5`<br/> **Interface version** - `2017-10-13`

The {{site.data.keyword.personalityinsightsshort}} service is now available in the {{site.data.keyword.cloud_notm}} Tokyo location (**jp-tok**). Like all locations, Tokyo uses token-based Identity and Access Management (IAM) authentication. All new services instances that you create in this location use IAM authentication.

### 30 October 2018
{: #October2018}

**Service version** - `3.4.5`<br/> **Interface version** - `2017-10-13`

The {{site.data.keyword.personalityinsightsshort}} service has migrated to token-based Identity and Access Management (IAM) authentication for all locations. All {{site.data.keyword.cloud_notm}} services now use IAM authentication. The {{site.data.keyword.personalityinsightsshort}} service migrated in each location on the following dates:

-   Dallas (**us-south**): October 30, 2018
-   Frankfurt (**eu-de**): October 30, 2018
-   Washington, DC (**us-east**): June 11, 2018
-   Sydney (**au-syd**): June 4, 2018

The migration to IAM authentication affects new and existing service instances differently:

-   *All new service instances that you create in any location* now use IAM authentication to access the service. You can pass either a bearer token or an API key: Tokens support authenticated requests without embedding service credentials in every call; API keys use HTTP basic authentication. When you use any of the {{site.data.keyword.watson}} SDKs, you can pass the API key and let the SDK manage the lifecycle of the tokens.
-   *Existing service instances that you created in a location before the indicated migration date* continue to use the `{username}` and `{password}` from their previous Cloud Foundry service credentials for authentication until you update them to use IAM authentication. Because the {{site.data.keyword.personalityinsightsshort}} service is stateless, you can perform the following steps to convert an existing service instance to use IAM authentication:

    1.  Delete and re-create the service instance.
    1.  Modify your application code to use IAM authentication.

For more information, see the following documentation:

-   To learn which authentication mechanism your service instance uses, view your service credentials by clicking the instance on the [{{site.data.keyword.cloud_notm}} dashboard](https://{DomainName}/resources){: external}.
-   For more information about using IAM API keys and tokens with Watson services, see [Authenticating to Watson services](/docs/watson?topic=watson-iam).
-   For examples that use IAM authentication, see the [API & SDK reference](https://{DomainName}/apidocs/personality-insights){: external}.

### 11 June 2018
{: #June2018b}

**Service version** - `3.4.5`<br/> **Interface version** - `2017-10-13`

For service instances and applications that are hosted in Washington, DC (**us-east**), the service now supports a new API authentication process. For more information, see the [30 October 2018 service update](#October2018).

### 4 June 2018
{: #June2018a}

**Service version** - `3.4.5`<br/> **Interface version** - `2017-10-13`

For service instances and applications that are hosted in Sydney (**au-syd**), the service now supports a new API authentication process. For more information, see the [30 October 2018 service update](#October2018).

### 23 March 2018
{: #March2018}

**Service version** - `3.4.4`<br/> **Interface version** - `2017-10-13`

-   The service was updated with small defect fixes. The changes were specific to the Arabic, Japanese, and Korean languages.
-   The `Accept` request header is now required with the `POST /v3/profile` method. You must specify either `application/json` or `text/csv`.

### 13 October 2017
{: #October2017}

**Service version** - `3.4.0`<br/> **Interface version** - `2017-10-13`

-   The `Trait` object of a personality profile now includes a `significant` field. A separate `Trait` object reports the results for each Big Five dimension, Big Five facet, Need, and Value. The `significant` field of each instance of the object identifies whether the results for the characteristic are meaningful for the input language (`Content-Language`) of the request:

    -   For English, Spanish, and Japanese, the field is always `true` for all personality characteristics.
    -   For Arabic and Korean, the field is `true` for most personality characteristics but is `false` for characteristics for which the service's models are unable to produce meaningful results. The field is `false` for a constant set of characteristics. For a complete list, see [Limitations for Arabic and Korean input](/docs/personality-insights?topic=personality-insights-numeric#limitations). Do not rely on the results for any characteristic for which the field is `false`.

    For more information about the service's JSON response content, see [Understanding a JSON profile](/docs/personality-insights?topic=personality-insights-output).
-   CSV output also now includes columns whose headings are named `*_significant`. Each column provides a boolean value to indicate whether a characteristic is meaningful. For more information about the service's CSV response content, see [Understanding a CSV profile](/docs/personality-insights?topic=personality-insights-outputCSV).
-   To use this latest version of the interface, specify the interface version `2017-10-13` with the `version` parameter.

### 18 September 2017
{: #September2017}

**Service version** - `3.3.0`<br/> **Interface version** - `2016-10-19`

The service now supports input content in Korean (`ko`). For more information about the average Mean Absolute Error (MAE) and average correlation for Korean input, see [Per-language average MAE and correlation](/docs/personality-insights?topic=personality-insights-science#precisePerLanguage).

The service's models are unable to produce meaningful percentiles and raw scores for a few personality characteristics of Korean input. For more information about the results for these characteristics, see [Limitations for Arabic and Korean input](/docs/personality-insights?topic=personality-insights-numeric#limitations).

### 10 April 2017
{: #April2017}

**Service version** - `3.1.7`<br/> **Interface version** - `2016-10-19`

-   The service changed how it handles requests with large amounts of input content. The service accepts a maximum of 20 MB of content. However, for the models that are based on *GloVe*, accuracy levels off at around 3000 words of input. This behavior is different from the older models, where more text produced greater accuracy. In general, the service no longer needs as much content to produce an accurate profile. But more content requires more processing time, which can cause a request to time out before it completes.

    Therefore, the service now extracts and uses only the first 250 KB of content, not counting any HTML or JSON markup, from large requests. This figure does not map to an exact number of words, which varies based on the language and nature of the text. In English, for example, average word length is between four and five characters, so this figure provides around 50,000 words, which is at least 15 times more words than the service needs. The `word_count` field of the response JSON indicates the number of words that the service uses for a request, which can be less than the number of words in the input.

    Because it still bases a profile on many more words than it strictly needs for maximum accuracy, the service produces a profile that is as accurate as in the past. However, the service responds much faster than before. For requests for which it uses only a portion of the input content, the service returns the following `CONTENT_TRUNCATED` warning message to make the user aware of the fact:

    `For maximum accuracy while also optimizing processing time, only the first 250KB of input text (excluding markup) was analyzed. Accuracy levels off at approximately 3K words so this did not affect the accuracy of the profile.`

    For more information, see [Providing sufficient input](/docs/personality-insights?topic=personality-insights-input#sufficient).
-   The service was updated with small security fixes.

### 1 March 2017
{: #March2017}

**Service version** - `3.1.6`<br/> **Interface version** - `2016-10-19`

The service was updated with small enhancements to logging.

### 20 February 2017
{: #February2017b}

**Service version** - `3.1.5.1`<br/> **Interface version** - `2016-10-19`

The service was updated with small security and defect fixes, and to improve metering of API calls.

### 13 February 2017
{: #February2017}

**Service version** - `3.1.4`<br/> **Interface version** - `2016-10-19`

-   The list of consumption preferences was refined. The list now includes only those preferences that are most important to understanding an individual's dominant lifestyle habits and consumer characteristics. The list of consumption preferences was shortened from 51 to 42. The remaining preferences more concisely express the author's likelihood to prefer different products, services, and activities, making it even easier to act on the results.

    The service no longer returns the following nine consumption preferences:

    -   The `consumption_preferences_shopping` category no longer includes
        -   `consumption_preferences_automobile_resale_value`
    -   The `consumption_preferences_reading` category no longer includes
        -   `consumption_preferences_read_motive_enjoyment`<br/>
        -   `consumption_preferences_read_motive_information`<br/>
        -   `consumption_preferences_read_motive_mandatory`<br/>
        -   `consumption_preferences_read_motive_relaxation`
    -   The `consumption_preferences_health_and_activity` category no longer includes
        -   `consumption_preferences_adventurous_sports`
        -   `consumption_preferences_fast_food_frequency`
    -   The `consumption_preferences_volunteering` category no longer includes
        -   `consumption_preferences_volunteering_time`
        -   `consumption_preferences_volunteer_learning`

    For more information about the remaining preferences, see [Consumption preferences](/docs/personality-insights?topic=personality-insights-preferences).
-   *For Arabic input*, information about the average Mean Absolute Error (MAE) and average correlation is now available in [Per-language average MAE and correlation](/docs/personality-insights?topic=personality-insights-science#precisePerLanguage). In addition, the service's models are unable to produce meaningful percentiles and raw scores for a collection of personality characteristics. For more information about the results for these characteristics, see [Limitations for Arabic and Korean input](/docs/personality-insights?topic=personality-insights-numeric#limitations).

### 13 January 2017
{: #January2017}

**Service version** - `3.1.2.1`<br/> **Interface version** - `2016-10-19`

The Personality insights service was updated with a few small defect fixes.

### 15 December 2016
{: #December2016}

**Service version** - `3.1.1`<br/> **Interface version** - `2016-10-19`

For Arabic input text, the {{site.data.keyword.personalityinsightsshort}} service now uses *GloVe* to develop a personality profile. The service no longer uses the Linguistic Inquiry and Word Count (LIWC) psycholinguistics dictionary for any language. For more information about how the service develops a personality portrait, see [How personality characteristics are inferred](/docs/personality-insights?topic=personality-insights-science#researchInfer).

### 15 November 2016
{: #November2016}

**Service version** - `3.1.0`<br/> **Interface version** - `2016-10-19`

-   For Japanese input text, the {{site.data.keyword.personalityinsightsshort}} service now uses *GloVe* to develop a personality profile. The service no longer uses the Linguistic Inquiry and Word Count (LIWC) psycholinguistics dictionary for Japanese input. For more information, see [How personality characteristics are inferred](/docs/personality-insights?topic=personality-insights-science#researchInfer).
-   The `name` fields of the `ConsumptionPreferencesCategory` and `ConsumptionPreferences` objects are now returned with localized strings in the language that is specified with the `Accept-Language` request header.
-   The update includes a few small defect fixes.

### 20 October 2016
{: #October2016b}

**Service version** - `3.0.0`<br/> **Interface version** - `2016-10-19`

The {{site.data.keyword.personalityinsightsshort}} service and its API were updated significantly. The API was incremented from version 2 to version 3 and offers new features. The remaining sections of this release note describe the changes in detail.

Version 3 is not compatible with version 2. You are encouraged to migrate to version 3 to take advantage of the new features and changes. Migration to version 3 consists only of updating and redeploying your applications to use the changes that are described in these release notes for the new version. You do not need to create a new instance of the service in {{site.data.keyword.cloud_notm}}; you only need to call the `v3` API.

Version 2 of the {{site.data.keyword.personalityinsightsshort}} API is to be removed from service soon. You are strongly encouraged to migrate to version 3 as soon as possible.
{: note}

#### More information about version 3

This documentation now describes version 3 of the {{site.data.keyword.personalityinsightsshort}} API. The following sections summarize the changes for the new version of the interface:

-   For more information about calling the `/v3/profile` method, see [Requesting a profile](/docs/personality-insights?topic=personality-insights-input).
-   For more information about the `/v3/profile` method's response, see [Understanding a JSON profile](/docs/personality-insights?topic=personality-insights-output) and [Understanding a CSV profile](/docs/personality-insights?topic=personality-insights-outputCSV).
-   For more information about the version 3 interface, see the [API & SDK reference](https://{DomainName}/apidocs/personality-insights){: external}.

#### Changes to parameters of the `/v3/profile` method

Parameters of the `/v3/profile` method changed:

-   The API now offers an optional query parameter named `consumption_preferences`. The parameter accepts a boolean value that indicates whether information that is inferred about consumption preferences is to be returned with the results. By default, the information is not included in the response. For more information, see [New consumption preferences feature](#cp).
-   The API now includes a required `version` query parameter. The parameter accepts a string that identifies the requested version of the API and the response format as a date in the form `YYYY-MM-DD`; for example, specify `2016-10-19` for October 19, 2016. This parameter allows the service to update its API or response format for new versions without breaking existing clients. The initial string for version 3 of the API is `2016-10-19`.

    The date that you specify does not need to match a version of the service exactly. The service uses the version that is no later than the date you provide. If you specify a date that is earlier than the release date of version 3, the service uses version 3 of the API. If you specify a date that is in the future or otherwise later than the most recent version, the service uses the latest version.
-   The name of the `include_raw` query parameter is now `raw_scores`.
-   The name of the `headers` query parameter is now `csv_headers`.

#### New consumption preferences feature
{: #cp}

The consumption preferences feature provides an indication of the author's tendency to exhibit different consumer tendencies. When you pass the `consumption_preferences` query parameter with a value of `true` to the `/v3/profile` method, the service returns extra results with the `Profile` object:

-   A `consumption_preferences` field that provides an array of `ConsumptionPreferencesCategory` objects.
-   Each `ConsumptionPreferencesCategory` object includes the following fields:
    -   `consumption_preference_category_id`: The ID of one of the consumption preferences categories
    -   `name`: The user-visible name of the category.
    -   `consumption_preferences`: An array of `ConsumptionPreferences` objects that provides results that are inferred from the input text for the individual preferences of the category
-   Each `ConsumptionPreferences` object includes the following fields:
    -   `consumption_preference_id`: The ID of one of the consumption preferences.
    -   `name`: The user-visible name of the consumption preference.
    -   `score`: The score for the consumption preference:

        -   `0.0` indicates unlikely
        -   `0.5` indicates neutrality
        -   `1.0` indicates likely

        The scores for some preferences are binary and do not allow a neutral value. The score is an indication of preference based on the results that are inferred from the input text, not a normalized percentile.

For more information about the consumption preferences, see [Consumption preferences](/docs/personality-insights?topic=personality-insights-preferences).

The `name` field for both consumption preferences objects is always returned in English, regardless of the language specified with the `Accept-Language` request header.
{: note}

#### Changes to JSON objects and fields

JSON input and output objects and their fields were simplified and clarified:

-   The following fields were removed from JSON `ContentItem` objects that you can pass to the `/v3/profile` method with a request:
    -   `userid`
    -   `sourceid`
    -   `charset` (previously deprecated)

    You pass these objects in the body of a JSON request as elements of the `contentItems` array of the `Content` object.
-   The following fields of the JSON `Profile` object that is returned by the `/v3/profile` method changed:
    -   The following fields were removed:
        -   `id`
        -   `source`
    -   The `tree` field was removed. It is replaced by four new fields:
        -   `personality` for Big Five personality characteristics.
        -   `needs` for Needs characteristics.
        -   `values` for Values characteristics.
        -   `behavior` for temporal results about the distribution of the content over the days of the week and the hours of the day. This field is returned only for JSON input that is timestamped.

        This change effectively moves the results one level higher in the JSON `Profile` object, eliminating a level of recursion.
    -   The name of the `processed_lang` field is now `processed_language`.
-   The following fields of JSON `Trait` objects that are returned by the `/v3/profile` method were renamed:
    -   The name of the `id` field of the JSON `Trait` object is now `trait_id`.
    -   The name of the `percentage` field of the JSON `Trait` object is now `percentile`.
-   The following fields of JSON `Trait` objects that are returned by the `/v3/profile` method were removed:
    -   `sampling_error`
    -   `raw_sampling_error`

    The service now reports an average Mean Absolute Error (MAE) that qualifies the precision of its results. For more information about the MAE for different amounts of input text, see [Providing sufficient input](/docs/personality-insights?topic=personality-insights-input#sufficient).
-   JSON `Trait` objects are still returned for the `personality`, `needs`, and `values` fields of the `Profile` object. But the `behavior` field returns an array of JSON objects named `Behavior` that has the following fields:
    -   `trait_id`
    -   `name`
    -   `category`
    -   `percentage`

    In addition, behavioral information is no longer returned as a tree of values. The output consists of a single array that lists all temporal characteristics (day of week and time of day).
-   The name of the `id` field of the JSON `Warnings` object that can be returned by the `/v3/profile` method is now `warnings_id`.

#### Changes to JSON IDs
{: #ids}

The JSON IDs that the service returns for the `trait_id` (formerly `id`) field of the `Trait` and the new `Behavior` object changed:

-   The IDs for Big Five dimensions now begin with the string `big5_`.
-   The IDs for Big Five facets now begin with the string `facet_`.
-   The IDs for Needs now begin with the string `need_`.
-   The IDs for Values now begin with the string `value_`.
-   The IDs for all temporal characteristics now begin with the string `behavior_`.
-   The IDs for temporal characteristics that are related to time of day now use four-digit 24-hour time (for example, `behavior_0000`) rather than 12-hour time (for example, `0:00 am`).
-   All characters are now lowercase.
-   Spaces and hyphens are now underscores.

#### Changes to CSV headers
{: #headers}

The optional column headers that the service can return for CSV output changed:

-   All of the changes that are described for the `trait_id` of the JSON output also apply to the CSV headers.
-   The headers for raw scores for Big Five dimensions now begin with the string `big5_`.
-   The headers for raw scores for Big Five facets now begin with the string `facet_`.
-   The headers for raw scores for Needs now begin with the string `need_`.
-   The headers for raw scores for Values now begin with the string `value_`.
-   The header for the processed language column is now `processed_language` rather than `processed_lang`.
-   The `user` and `source_id` columns are no longer returned.
-   All characters are now lowercase.
-   Spaces and hyphens are now underscores.

#### Removal of the `visualize` method

Version 2 of the service's API included a deprecated `visualize` method that was used in an earlier release to visualize the results of a call to the `/v3/profile` method. The `visualize` method has been removed from the service's API. The service continues to provide a collection of JavaScript files that enable graphic visualization of a profile. For more information, see [Visualizing a profile](/docs/personality-insights?topic=personality-insights-overviewDevelopers#visualize).

### 12 October 2016
{: #October2016a}

For Spanish input text, the {{site.data.keyword.personalityinsightsshort}} service now uses *GloVe* to develop a personality profile. The service no longer uses the Linguistic Inquiry and Word Count (LIWC) psycholinguistics dictionary for Spanish input. The service began to use the new model for English input text on August 31. It plans to apply the new model to the remaining input languages soon. For more information about the new model, see [How personality characteristics are inferred](/docs/personality-insights?topic=personality-insights-science#researchInfer).

### 31 August 2016
{: #August2016}

The service now uses *GloVe* to develop a personality profile. *GloVe* is an open-source word-embedding technique. For more information, see [How personality characteristics are inferred](/docs/personality-insights?topic=personality-insights-science#researchInfer). The service uses the new approach only for English input text. For other languages, the service continues to use the Linguistic Inquiry and Word Count (LIWC) psycholinguistics dictionary. The service plans to use the open-vocabulary approach for all languages in the future.

For the new model used for English input, the service reports the average Mean Absolute Error (MAE) of the results for its trained model. For more information about how the MAE changes with different amounts of input text, see [Providing sufficient input](/docs/personality-insights?topic=personality-insights-input#sufficient).

{{site.data.keyword.IBM_notm}} plans to report the MAE for non-English models in the future. {{site.data.keyword.IBM_notm}} plans to use the MAE instead of sampling errors to determine how the precision of the service changes based on the amount of input text that you provide.

### 14 July 2016
{: #July2016b}

-   For Arabic input, the service can now trim the amount of input text for performance reasons. At a certain threshold, the accuracy of the results for Arabic does not improve with more words. If the service trims Arabic input text, it returns a `PARTIAL_TEXT_USED` warning with the following message:

    `The text provided to compute the profile was trimmed for performance reasons. This action does not affect the accuracy of the output, as not all of the input text was required.`
-   The update includes defect fixes and internal improvements.

### 1 July 2016
{: #July2016a}

-   The pricing plans for the service now offer lower prices for {{site.data.keyword.personalityinsightsshort}} users. For more information, see the {{site.data.keyword.personalityinsightsshort}} service in the [{{site.data.keyword.cloud_notm}} Catalog](https://{DomainName}/catalog/services/personality-insights/){: external}.
-   The list of supported response languages that you can specify with the `Accept-Language` header now includes
    -   `ar` (Arabic)
    -   `de` (German)
    -   `en` (English, the default)
    -   `es` (Spanish)
    -   `fr` (French)
    -   `it` (Italian)
    -   `ja` (Japanese)
    -   `ko` (Korean)
    -   `pt-br` (Brazilian Portuguese)
    -   `zh-cn` (Simplified Chinese)
    -   `zh-tw` (Traditional Chinese)

    For more information, see [Specifying request and response languages](/docs/personality-insights?topic=personality-insights-input#languages-input).
-   The `/v2/profile` method can now return the following HTTP status codes:
    -   429 *Too Many Requests*: The service is processing too many requests for the content language. Wait a short time and try the request again. If you are submitting many requests for the language, consider throttling the rate at which you submit requests.
    -   504 *Gateway Timeout*: The request timed out or took too long to process. Wait a short time and try the request again. If the input contained too many words (for example, more than 20,000), consider reducing the number of words but maintain the guidelines for meaningful input.

    The method no longer returns 503 *Service Unavailable*. For more information about possible response codes, see the [API & SDK reference](https://{DomainName}/apidocs/personality-insights){: external}.
-   The update includes defect fixes and internal improvements.

### 7 June 2016
{: #June2016b}

-   The service now supports Cross-Origin Resource Sharing (CORS) to allow browser-based clients to call the service directly. For more information, see [CORS support](/docs/personality-insights?topic=personality-insights-overviewDevelopers#CORS).
-   The service's performance for Japanese text improved significantly.
-   The update includes defect fixes and internal improvements.

### 1 June 2016
{: #June2016a}

The service was updated for defect fixes and internal improvements. A new top-level field, `warnings`, was also added to the JSON results that are returned by the service. For more information, see the [API & SDK reference](https://{DomainName}/apidocs/personality-insights){: external}.

### 17 May 2016
{: #May2016}

The service was updated for defect fixes and internal improvements.

### 18 March 2016
{: #March2016}

The service now supports the following languages:

-   The service supports four languages for its input text: Arabic (`ar`), English (`en`), Spanish (`es`), and Japanese (`ja`). To specify the language, use the HTTP `Content-Language` header for plain text and HTML input or the `language` property of the `ContentItem` object for JSON input.
-   The service supports the same four languages for its response. To specify the language of the response, use the `Accept-Language` header.

You can use any combination of languages for the input and response. If you do not indicate a language, the service defaults to English. For more information, see [Specifying request and response languages](/docs/personality-insights?topic=personality-insights-input#languages-input). You can also refer to the blog post [Arabic and Japanese support is now available for {{site.data.keyword.IBM_notm}} {{site.data.keyword.watson}} {{site.data.keyword.personalityinsightsshort}}](https://www.ibm.com/blogs/watson/2016/04/arabic-japanese-support-now-available-ibm-watson-personality-insights/){: external}.

Because it requires significantly more computing cycles to analyze than other languages, Arabic content takes markedly longer to process. Although the service supports the same 20 MB restriction on the amount of input text for all languages, the practical limit for Arabic content might be lower to avoid timeouts. Japanese content also takes longer to process, but the delays are of less meaningful significance than they are for Arabic.
{: note}

### 9 July 2015
{: #July2015}

-   *Language support.* You can analyze both English and Spanish content. You indicate the language of the input text with the `Content-Language` header of the `/v2/profile` method. For more information about specifying a language, see [Specifying request and response languages](/docs/personality-insights?topic=personality-insights-input#languages-input).
-   *Raw scores.* You can request raw scores and raw sampling errors that are computed from the input text and the service's models. The values are not normalized or compared with a sample population. Raw scores are useful for customers who want to apply a custom normalization for a specific scenario or who do not require a comparison with a sample population. You request raw scores by setting the `include_raw` query parameter of the `/v2/profile` method to `true`. For more information, see [Interpreting the numeric results](/docs/personality-insights?topic=personality-insights-numeric).
-   *Model enhancements.* Based on its latest studies, {{site.data.keyword.IBM_notm}} further improved some of its approaches to inferring personality characteristics. The changes are transparent to the service's users; they do not invalidate any previous results that were obtained from the service. For more information about the studies and the service's approach to inference, see [How personality characteristics are inferred](/docs/personality-insights?topic=personality-insights-science#researchInfer).

### 23 February 2015
{: #February2015}

As of February 23, 2015, the {{site.data.keyword.personalityinsightsshort}} service is the generally available (GA) version of the former User Modeling service, which was available as a beta release. The GA release requires that users migrate to an instance of the new service. The following differences exist between the beta and GA versions of the service.

-   The {{site.data.keyword.personalityinsightsshort}} service is compatible with the User Modeling service. The differences that are described provide more flexibility and improved results without affecting current applications.
-   The parameters with which you create the service in {{site.data.keyword.cloud_notm}} changed. You now use a service name of `personality_insights` instead of `user_modeling` and a service plan of `"IBM Watson Personality Insights Monthly Plan"` instead of `user_modeling_free_plan`.
-   The `/v2/profile` method accepts two new input formats. The `Content-Type` header now accepts the input formats plain text (`text/plain`), which is the default, and HTML (`text/html`), in addition to JSON (`application/json`).
-   The `/v2/profile` method now returns a new output format. The `Accept` header now accepts the output format CSV (`text/csv`) in addition to JSON (`application/json`), which is the default.
-   The `/v2/profile` method now includes a new output element, `sampling_error`, for each characteristic for which it reports a percentage value. The sampling error is returned as a double value that indicates the service's level of confidence in the author's percentile based on the input text.
-   The Needs model employs improved tokenization and processing to better normalize the distribution of values for its characteristics. You are advised to recompute any results that were generated by the User Modeling API.
-   The `visualize` method is now deprecated and will be removed entirely in a future release. You can use the `personality.js` JavaScript file that is provided with the sample application to achieve similar results from the client. The `textsummary.js` JavaScript file provides extra formatting for the results of the service.
