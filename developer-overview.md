---

copyright:
  years: 2015, 2021
lastupdated: "2021-03-10"

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

# Overview for developers
{: #overviewDevelopers}

{{site.data.keyword.personalityinsightsfull}} is discontinued. Existing instances are supported until 1 December 2021, but as of 1 December 2020, you cannot create new instances. Any instance that exists on 1 December 2021 will be deleted.<br/><br/>No direct replacement exists for {{site.data.keyword.personalityinsightsshort}}. However, you can consider using [{{site.data.keyword.nlufull}}](/docs/natural-language-understanding?topic=natural-language-understanding-about) on {{site.data.keyword.cloud}} as part of a replacement analytic workflow for your {{site.data.keyword.personalityinsightsshort}} use cases. You can use {{site.data.keyword.nlushort}} to extract data and insights from text, such as keywords, categories, sentiment, emotion, and syntax. For more information about the personality models in Personality Insights, see [The science behind the service](/docs/personality-insights?topic=personality-insights-science).
{: deprecated}

You can use the {{site.data.keyword.personalityinsightsshort}} service via an HTTP Representational State Transfer (REST) API. Several Software Development Kits (SDKs) are also available to simplify application development in various languages.
{: shortdesc}

## Programming with the service
{: #programming}

To produce a personality profile, you send text to the service's HTTP `POST /v3/profile` method. You can submit plain text, HTML, or JSON content. The service can return its analysis in JSON or CSV format

For each personality characteristic, the service reports a *percentile*. The percentile is a normalized score that describes the extent to which the author's writing exhibits a characteristic within a sample population. If requested, the service also returns a *raw score*, which is an absolute value that is not normalized for a sample population. If the input is timestamped, the service provides a summary of the author's writing habits by day of week and time of day. And if requested, the service also returns a likelihood score for each of its available consumption preferences.

For more information about using the service, see

-   [Requesting a profile](/docs/personality-insights?topic=personality-insights-input)
-   [Understanding a JSON profile](/docs/personality-insights?topic=personality-insights-output)
-   [Understanding a CSV profile](/docs/personality-insights?topic=personality-insights-outputCSV)

### Visualizing a profile
{: #visualize}

The service provides a collection of JavaScript files that enable graphic visualization of a profile. The scripts facilitate use of the service with caching and content distribution networks. They rely on JavaScript, jQuery, HTML, and SVG with the Data-Driven Documents (`D3.js`) library to depict the results. For more information about `D3.js`, see [d3js.org](https://d3js.org/){: external}.

### CORS support
{: #CORS}

The service supports Cross-Origin Resource Sharing (CORS). CORS allows browser-based clients to make asynchronous requests directly to the service from front-end scripts. CORS circumvents the same-origin security policy, which otherwise prevents such requests.

By using CORS, web pages can request resources from a foreign domain, one that is outside the domain from which the request originated. For more information, see [enable-cors.org](https://enable-cors.org/){: external}.

## Using Software Development Kits
{: #sdks}

SDKs are available for the {{site.data.keyword.personalityinsightsshort}} service to simplify application development. {{site.data.keyword.ibmwatson}} SDKs are available for many popular programming languages and platforms.

-   For a complete list of SDKs and links to the SDKs on GitHub, see [Using SDKs](/docs/personality-insights?topic=watson-using-sdks).
-   For detailed information about all methods of the Node, Java, Python, Ruby, and Go SDKs for the {{site.data.keyword.personalityinsightsshort}} service, see the [API & SDK reference](https://{DomainName}/apidocs/personality-insights){: external}.

## Learning more about application development
{: #learn-overview}

For more information about working with {{site.data.keyword.watson}} services and {{site.data.keyword.cloud}}, see the following sections:

-   For an introduction to working with {{site.data.keyword.watson}} services and {{site.data.keyword.cloud_notm}}, see [Getting started with {{site.data.keyword.watson}} and {{site.data.keyword.cloud_notm}}](/docs/watson?topic=watson-about).
-   All service instances use {{site.data.keyword.cloud_notm}} Identity and Access Management (IAM) for authentication. For more information, see [Authenticating to Watson services](/docs/watson?topic=watson-iam).
-   Request logging is disabled for the {{site.data.keyword.personalityinsightsshort}} service. The service does not log or retain data from requests and responses, regardless of whether the `X-Watson-Learning-Opt-Out` request header is set.
