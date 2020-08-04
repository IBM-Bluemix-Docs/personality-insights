---

copyright:
  years: 2015, 2020
lastupdated: "2020-08-04"

subcollection: personality-insights

---

{:troubleshoot: data-hd-content-type='troubleshoot'}
{:support: data-reuse='support'}
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

# Requesting a profile
{: #input}

To analyze content, you use the HTTP `POST` request method to call the `/v3/profile` method of the {{site.data.keyword.personalityinsightsshort}} service. You can pass the service a maximum of 20 MB of content to be analyzed via the body of the request. However, the service requires far less input to produce an accurate personality profile. For more information, see [Providing sufficient input](#sufficient).
{: shortdesc}

The `/v3/profile` method includes parameters that specify the type of content to be passed to and returned by the service, as well as the language of each type of content. The service always returns a profile that provides insight into the personality characteristics of the author of the input text. You can also request raw scores and consumption preferences.

The following sections describe the parameters of the `/v3/profile` method. For information about the results of a request, see [Understanding a JSON profile](/docs/personality-insights?topic=personality-insights-output) and [Understanding a CSV profile](/docs/personality-insights?topic=personality-insights-outputCSV). For detailed information about the `/v3/profile` method, see the [API reference](https://{DomainName}/apidocs/personality-insights){: external}.

Request logging is disabled for the {{site.data.keyword.personalityinsightsshort}} service. Regardless of whether you set the `X-Watson-Learning-Opt-Out` request header, the service does not log or retain data from requests and responses.
{: note}

## Specifying request and response formats
{: #formats}

You use the `Content-Type` and `Accept` header parameters to indicate the format of the content that you are passing to the method and the format of the service's response. You can use any combination of supported formats for the request and response.

<table>
  <caption>Table 1. Specifying request and response formats</caption>
  <tr>
    <th style="width:10%; text-align:left; vertical-align:bottom">
      Format
    </th>
    <th style="width:26%; text-align:center; vertical-align:bottom">
      Argument
    </th>
    <th style="width:32%; text-align:center; vertical-align:bottom">
      Supported by<br/>
      <code>Content-Type</code>
    </th>
    <th style="width:32%; text-align:center; vertical-align:bottom">
      Supported by<br/>
      <code>Accept</code>
    </th>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      Plain text
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/plain</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      Yes (default)<br/><br/>
      The service processes plain text without modification.
    </td>
    <td style="text-align:center; vertical-align:top">
      No
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      HTML
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/html</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      Yes<br/><br/>
      The service strips tags from the content before it processes the text.
    </td>
    <td style="text-align:center; vertical-align:top">
      No
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      JSON
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>application/json</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      Yes<br/><br/>
      Content must conform to the model defined by the
      <code>Content</code> object, which is an array
      of <code>ContentItem</code> objects.
    </td>
    <td style="text-align:center; vertical-align:top">
      Yes<br/><br/>
      The service returns its results as a <code>Profile</code>
      object.
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      CSV
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/csv</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      No
    </td>
    <td style="text-align:center; vertical-align:top">
      Yes<br/><br/>
      By default, the service returns a single row of numeric results.
      Set the optional <code>csv_headers</code> query parameter to
      <code>true</code> to request headers for each column of the output.
    </td>
  </tr>
</table>

### Specifying the character set
{: #charset}
{: troubleshoot}
{: support}

By default, the service uses the following character sets for input content:

-   *For plain text and HTML content,* the service uses the International Standards Organization (ISO)-8859-1 character set (effectively the ASCII character set) per the HTTP version 1.1 specification.
-   *For JSON content,* the service effectively always uses the Unicode Transformation Format (UTF)-8 character set per Section 8.1 of the International Engineering Task Force (IETF) [Request for Comment (RFC) 7159](https://tools.ietf.org/html/rfc7159#section-8.1){: external}.

When submitting plain text or HTML content, include the `charset` parameter with the `Content-Type` header to indicate the character encoding of the input text. The following example specifies UTF-8 character encoding for plain text input:

```
Content-Type: text/plain;charset=utf-8
```
{: codeblock}

By using the `charset` parameter, you can avoid potential problems that are associated with non-ASCII or non-printable characters. If you pass UTF-8 data without specifying the character set, special characters can result in incorrect results or in HTTP 400- or 500-level errors.

### Using the curl command
{: #charsetCurl}

To prevent errors when using the `curl` command, always pass the content via the `--data-binary` option of the `curl` command to preserve any UTF-8 encoding of the content. If you use the `--data` option to pass the content as ASCII, the command can process the input, which can cause problems for data encoded in UTF-8.

For example, the following `curl` command correctly uses the `--data-binary` option to post the contents of the specified file with no additional processing. The command specifies the `charset` parameter with the `Content-Type` header, and it requests the JSON response format with the `Accept` header. Replace `{apikey}`, `{filename}`, and `{url}` with your API key, the name of your input file, and the URL of your service instance.

```bash
curl -X POST -u "apikey:{apikey}" \
--header "Content-Type: text/plain;charset=utf-8" \
--header "Accept: application/json" \
--data-binary @{filename} \
"{url}/v3/profile?version=2017-10-13"
```
{: pre}

For more examples of calling the service with different request and response formats, see the [Getting started tutorial](/docs/personality-insights?topic=personality-insights-gettingStarted).

## Specifying JSON input
{: #json}

To pass JSON input, you use the `Content` object. The object includes an array of `ContentItem` objects, each of which contains an element of the content. The only required field of the object is `content`, which provides the text to be analyzed. Other optional fields are

-   `id` (string) is a unique ID for the content item.
-   `created` (integer) is a UNIX timestamp that indicates when the content item was created.
-   `updated` (integer) is a UNIX timestamp that indicates when the content item was last updated.
-   `contenttype` (string) indicates the type of the content item: `text/plain` or `text/html`.
-   `language` (string) indicates the language of the content item: `ar` (Arabic), `en` (English), `es` (Spanish), `ja` (Japanese), or `ko` (Korean). See [Specifying request and response languages](#languages-input).
-   `parentid` (string) is the `id` of the content item's parent item.
-   `reply` (boolean) indicates whether the content item is a reply to another item.
-   `forward` (boolean) indicates whether the content item is a forward or copy of another item.

JSON input is well suited for content from Twitter or other social networks that consist of multiple conversations or posts. Instead of concatenating all of the author's text into a single string, you can use JSON to submit the data as it exists. This approach has the further advantage of letting the service know which pieces of text are related.

### Example JSON input
{: jsonExample}

Examples in the [Getting started tutorial](/docs/personality-insights?topic=personality-insights-gettingStarted) use the sample JSON file <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../icons/launch-glyph.svg" alt="External link icon" title="External link icon"></a>. The file includes a series of Twitter messages. The following example shows the first few tweets from the file.

```javascript
{
  "contentItems": [
    {
      "content": "Wow, I liked @TheRock before, now I really SEE how special he is. The daughter story was IT for me. So great! #MasterClass",
      "contenttype": "text/plain",
      "created": 1447639154000,
      "id": "666073008692314113",
      "language": "en"
    },
    {
      "content": ".@TheRock how did you Know to listen to your gut and Not go back to football? #MasterClass",
      "contenttype": "text/plain",
      "created": 1447638226000,
      "id": "666069114889179136",
      "language": "en"
    },
    . . .
  ]
}
```
{: codeblock}

## Specifying request and response languages
{: #languages-input}

You can use the `Content-Language` and `Accept-Language` header parameters to indicate the language of the input content and the language of the service's response. You can use any combination of supported languages for the request and response. If you do not indicate a language, the service uses its English-trained models for its analysis and English for its results. The following table lists the supported input and output languages and identifies the arguments that you use with the language-related parameters.

<table style="width:90%">
  <caption>Table 2. Specifying request and response languages</caption>
  <tr>
    <th style="width:28%; text-align:left; vertical-align:bottom">
      Language
    </th>
    <th style="width:12%; text-align:center; vertical-align:bottom">
      Argument
    </th>
    <th style="width:30%; text-align:center; vertical-align:bottom">
      Supported by<br/>
      <code>Content-Language</code>
    </th>
    <th style="width:30%; text-align:center; vertical-align:bottom">
      Supported by<br/>
      <code>Accept-Language</code>
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      Arabic
    </td>
    <td style="text-align:center">
      <code>ar</code>
    </td>
    <td style="text-align:center">
      Yes
    </td>
    <td style="text-align:center">
      Yes
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Brazilian Portuguese
    </td>
    <td style="text-align:center">
      <code>pt-br</code>
    </td>
    <td style="text-align:center">
      No
    </td>
    <td style="text-align:center">
      Yes
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      English
    </td>
    <td style="text-align:center">
      <code>en</code>
    </td>
    <td style="text-align:center">
      Yes
    </td>
    <td style="text-align:center">
      Yes
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      French
    </td>
    <td style="text-align:center">
      <code>fr</code>
    </td>
    <td style="text-align:center">
      No
    </td>
    <td style="text-align:center">
      Yes
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      German
    </td>
    <td style="text-align:center">
      <code>de</code>
    </td>
    <td style="text-align:center">
      No
    </td>
    <td style="text-align:center">
      Yes
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Italian
    </td>
    <td style="text-align:center">
      <code>it</code>
    </td>
    <td style="text-align:center">
      No
    </td>
    <td style="text-align:center">
      Yes
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Japanese
    </td>
    <td style="text-align:center">
      <code>ja</code>
    </td>
    <td style="text-align:center">
      Yes
    </td>
    <td style="text-align:center">
      Yes
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Korean
    </td>
    <td style="text-align:center">
      <code>ko</code>
    </td>
    <td style="text-align:center">
      Yes
    </td>
    <td style="text-align:center">
      Yes
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Simplified Chinese
    </td>
    <td style="text-align:center">
      <code>zh-cn</code>
    </td>
    <td style="text-align:center">
      No
    </td>
    <td style="text-align:center">
      Yes
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Spanish
    </td>
    <td style="text-align:center">
      <code>es</code>
    </td>
    <td style="text-align:center">
      Yes
    </td>
    <td style="text-align:center">
      Yes
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Traditional Chinese
    </td>
    <td style="text-align:center">
      <code>zh-tw</code>
    </td>
    <td style="text-align:center">
      No
    </td>
    <td style="text-align:center">
      Yes
    </td>
  </tr>
</table>

Be aware of the following usage note:

-   Submit all input text in the same language. Do not mix multiple languages in the same input text for a request.
-   For two-character language arguments, the service treats regional variants as their parent language; for example, it interprets `en-US` as `en`.

### Examples of language specification
{: languageExamples}

The following example uses the `Content-Language` and `Accept-Language` headers to both send input and request output in Spanish:

```bash
curl -X POST -u "apikey:{apikey}" \
--header "Content-Type: text/plain;charset=utf-8" \
--header "Accept: application/json" \
--header "Content-Language: es" \
--header "Accept-Language: es" \
--data-binary @{filename} \
"{url}/v3/profile?version=2017-10-13"
```
{: pre}

The following example omits the `Content-Language` header to pass input content in English (the default). It uses the `Accept-Language` header to request a response in Spanish:

```bash
curl -X POST -u "apikey:{apikey}" \
--header "Content-Type: text/plain;charset=utf-8" \
--header "Accept: application/json" \
--header "Accept-Language: es" \
--data-binary @{filename} \
"{url}/v3/profile?version=2017-10-13"
```
{: pre}

### Specifying a language for JSON content
{: #languageJSON}

For plain text and HTML input, the `Content-Language` header is the only way to specify the language. For JSON input, you can also specify the language of each individual content item by using the `language` parameter of the `ContentItem` object. For JSON, a language specified with the `Content-Language` header overrides a language that is specified for a content item; the service ignores content items that specify a different language.

Omit the `Content-Type` header to base the language solely on the specification of the content items. The service uses the most prevalent language from among the content items, which yields the best possible results. It counts the number of content items for each language and selects the language with the highest frequency. If multiple languages have the same maximum frequency, the service uses the language that reaches that value first. Again, the service ignores content items that specify a different language.

### Language considerations
{: #languageNotes}
{: troubleshoot}
{: support}

Consider the following details when you submit input text:

-   *For English,* the service bases results on US cultural norms. If you analyze English text from a different culture, you might need to adjust the results.
-   *For Arabic,* the service can trim the amount of input text for performance reasons. At a certain threshold, the accuracy of Arabic results does not improve with more words. If the service trims Arabic input, it returns a warning message to inform you that it reduced the amount of input text that it used for the profile.
-   *For Arabic and Korean,* the service is unable to return meaningful results for a subset of characteristics. For more information, see [Limitations for Arabic and Korean input](/docs/personality-insights?topic=personality-insights-numeric#limitations).

For general information about using translated text, see [Inferring personality from translated text](/docs/personality-insights?topic=personality-insights-guidance#translation).

## Providing sufficient input
{: #sufficient}

A meaningful personality profile can be created only where sufficient data of suitable quantity and quality is provided. Because language use varies naturally from document to document and from time to time, a small sample of text might not be representative of an individual's overall language patterns. Moreover, different characteristics and different media converge at different rates.

You can send the service up to 20 MB of input content. Up to a point, more words are likely to produce better results, improving the service's precision by reducing the deviation between the predicted results and the author's actual score. But accuracy levels off at around 3000 words of input, and more content does not contribute to the accuracy of the profile. Therefore, the service extracts and uses only the first 250 KB of content, not counting any HTML or JSON markup, from large requests.

This figure does not map to an exact number of words, which varies based on the language and nature of the text. In English, for example, average word length is between four and five characters, so this figure provides around 50,000 words. This number is at least 15 times more words than the service needs to produce an accurate profile. By truncating long input, the service improves response time without sacrificing precision. The `word_count` field of the response JSON indicates the number of words that the service uses for a request, which can be less than the number of words submitted.

The service validates only the number of words that you submit. If you submit enough words, the service produces a profile. The service does not check for duplicate words or sentences. Such validation is subjective and better left to the user, who might have valid reasons to submit such input. Therefore, it is possible to obtain a profile by submitting the same word or sentence many times, but the resulting profile is not necessarily meaningful.
{: note}

### Guidelines and recommendations
{: #sufficientGuidelines}
{: troubleshoot}
{: support}

The following table reports two values for different quantities of input text:

-   The *Average Mean Absolute Error (MAE)* across all characteristics based on the number of words that are provided as input. The smaller the MAE, the closer the service's results are to the scores the author would receive by taking a personality test.
-   The *Average correlation* between inferred and actual scores across all characteristics. The closer the correlation is to 1, the better the predictions. Correlations greater than 0.2 are considered acceptable; correlation higher than 0.4 are rare.

The information is based on English-language data, but the general guidelines apply to all languages. For more information about average MAE and correlation, including language-specific statistics, see [How precise is the service](/docs/personality-insights?topic=personality-insights-science#researchPrecise).

<table style="width:80%">
  <caption>Table 3. Average MAE and correlation</caption>
  <tr>
    <th style="text-align:center; vertical-align:bottom; width:24%">Number of words</th>
    <th style="text-align:center; width:38%">Average MAE<br/>across all
      characteristics</th>
    <th style="text-align:center; width:38%">Average correlation<br/>across
      all characteristics</th>
  </tr>
  <tr>
    <td style="text-align:center">3000</td>
    <td style="text-align:center">12.1%</td>
    <td style="text-align:center">0.257</td>
  </tr>
  <tr>
    <td style="text-align:center">1200</td>
    <td style="text-align:center">12.2%</td>
    <td style="text-align:center">0.237</td>
  </tr>
  <tr>
    <td style="text-align:center">600</td>
    <td style="text-align:center">12.3%</td>
    <td style="text-align:center">0.212</td>
  </tr>
  <tr>
    <td style="text-align:center">300</td>
    <td style="text-align:center">12.5%</td>
    <td style="text-align:center">0.175</td>
  </tr>
  <tr>
    <td style="text-align:center">100</td>
    <td style="text-align:center">12.7%</td>
    <td style="text-align:center">0.095</td>
  </tr>
</table>

As the following guidelines indicate, {{site.data.keyword.IBM_notm}} recommends that you provide at least 1200 words, but providing at least 600 words produces acceptable results:

-   3000 words are sufficient to achieve the service's maximum precision.
-   At least 1200 words result in an MAE that is within two percent of the best MAE that the service can return.
-   Between 600 and 1200 words result in an MAE that is within three percent of the best MAE that the service can return.
-   Fewer than 600 words generate a warning, but the service still analyzes the input.
-   Fewer than 100 words generate an error.

These guidelines can help you accommodate the reliability of the results to your application. For example, for a casual application that recommends movies, you might be comfortable with less precision. For an application that makes more critical recommendations, you likely require more precise results. For more information about how the service infers personality characteristics, see [How personality characteristics are inferred](/docs/personality-insights?topic=personality-insights-science#researchInfer).

## Requesting raw scores
{: #rawScores-input}

The service always returns normalized scores for each personality characteristic (Big Five dimension and facet, Need, and Value) as part of its response. The service can also report a `raw_score` for each characteristic if you set the `raw_scores` query parameter to `true`. Raw scores represent results for the characteristics that are based solely on the author's text and the model for that characteristic, without comparing the results to a sample population. For more information about using raw scores, see [Raw scores for personality characteristics](/docs/personality-insights?topic=personality-insights-numeric#rawScores-numeric).

## Requesting consumption preferences
{: #preferences-input}

The service always returns results for the personality models. When you set the `consumption_preferences` query parameter to `true`, the service also returns `scores` for various consumption preferences. The service bases the preferences on the personality characteristics that it infers from the input text. These results indicate the author's tendency to prefer different products, services, and activities. Businesses can use the results to better understand the author's inclinations and to personalize communications and offers for the author.

For more information about the different consumption preferences, see [Consumption preferences](/docs/personality-insights?topic=personality-insights-preferences). For information about interpreting the numeric results for a preference, see [Scores for consumption preferences](/docs/personality-insights?topic=personality-insights-numeric#scores).

## Specifying the interface version
{: #version}

All calls to the `/v3/profile` method must include the `version` query parameter to indicate the version of the service's API and response format that you want to use. You specify the version as a date in the format `YYYY-MM-DD`; for example, specify `2017-10-13` for October 13, 2017. The parameter allows the service to update its API and response format for new versions without breaking existing clients. For information about all available versions, see the [Release notes](/docs/personality-insights?topic=personality-insights-release-notes).

The date that you specify does not need to match a version of the service exactly; the service uses the version that is no later than the date you provide. If you specify a date that is earlier than the initial release of version 3 (`2016-10-19`), the service uses that version of the API. If you specify a date that is in the future or otherwise later than the most recent version, the service uses the latest version.
