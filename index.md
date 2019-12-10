---

copyright:
  years: 2015, 2019
lastupdated: "2019-12-10"

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

# About
{: #about}

**Service update:** *The {{site.data.keyword.personalityinsightsshort}} service was updated on December 12, 2019. The service now supports the full implementation of token-based Identity and Access Management (IAM) authentication, and private network endpoints for Premium plans. For more information, see the [12 December 2019 service update](/docs/services/personality-insights?topic=personality-insights-release-notes#December2019) in the release notes.*

The {{site.data.keyword.personalityinsightsfull}} service provides an application programming interface (API) for deriving insights from social media, enterprise data, or other digital communications. The service uses linguistic analytics to infer individuals' intrinsic personality characteristics from digital communications such as email, text messages, tweets, and forum posts.
{: shortdesc}

The service infers, from potentially noisy social media, portraits of individuals that reflect their personality characteristics. It can also determine individuals' consumption preferences, which indicate their likelihood to prefer various products, services, and activities.

## Personality characteristics
{: #models-index}

The {{site.data.keyword.personalityinsightsshort}} service infers personality characteristics based on three primary models:

-   **Big Five** personality characteristics represent the most widely used model for generally describing how a person engages with the world. The model includes five primary dimensions: *Agreeableness*, *Conscientiousness*, *Extraversion*, *Emotional range*, and *Openness*. Each dimension has six facets that further characterize an individual according to the dimension.
-   **Needs** describe which aspects of a product are likely to resonate with a person. The model includes twelve characteristic needs: *Excitement*, *Harmony*, *Curiosity*, *Ideal*, *Closeness*, *Self-expression*, *Liberty*, *Love*, *Practicality*, *Stability*, *Challenge*, and *Structure*.
-   **Values** describe motivating factors that influence a person's decision making. The model includes five values: *Self-transcendence / Helping others*, *Conservation / Tradition*, *Hedonism / Taking pleasure in life*, *Self-enhancement / Achieving success*, and *Open to change / Excitement*.

For more information, see [Personality models](/docs/services/personality-insights?topic=personality-insights-models).

## Consumption preferences
{: #preferences-index}

Based on the personality characteristics that are inferred from the input text, the service can also return an indication of the author's consumption preferences. Consumption preferences indicate the author's likelihood to pursue different products, services, and activities. The service groups the individual preferences into eight categories: *Shopping*, *Music*, *Movies*, *Reading and learning*, *Health and activity*, *Volunteering*, *Environmental concern*, and *Entrepreneurship*. Each category contains from one to as many as a dozen individual preferences.

For more information, see [Consumption preferences](/docs/services/personality-insights?topic=personality-insights-preferences).

## Benefits of the service
{: #benefits}

As a core service of the {{site.data.keyword.ibmwatson}} platform, the {{site.data.keyword.personalityinsightsshort}} service can provide insights that help businesses

-   Understand their customers at a deeper level by learning their clients' preferences, improving customer satisfaction, and strengthening client relations.
-   Improve client acquisition, retention, and engagement.
-   Guide highly personalized engagements and interactions to better tailor their products, services, campaigns, and communications for individual clients.

For more information about how you can benefit from the service, see [Use cases](/docs/services/personality-insights?topic=personality-insights-usecases).

## Language support
{: #languages-index}

The service supports the following languages. You can use any combination of supported languages for the request and response, but all input text must be in the same language. For more information, see [Specifying request and response languages](/docs/services/personality-insights?topic=personality-insights-input#languages-input).

<table style="width:75%">
  <caption>Table 1. Supported languages</caption>
  <tr>
    <th style="width:50%; text-align:center">
      Request languages
    </th>
    <th style="width:50%; text-align:center">
      Response languages
    </th>
  </tr>
  <tr>
    <td style="text-align:center; vertical-align:top">
      Arabic<br/>
      English<br/>
      Japanese<br/>
      Korean<br/>
      Spanish
    </td>
    <td style="text-align:center; vertical-align:top">
      Arabic<br/>
      English<br/>
      Japanese<br/>
      Korean<br/>
      Spanish<br/>
      Brazilian Portuguese<br/>
      French<br/>
      German<br/>
      Italian<br/>
      Simplified Chinese<br/>
      Traditional Chinese
    </td>
  </tr>
</table>

## HIPAA
{: hipaa}

US Health Insurance Portability and Accountability Act (HIPAA) support does not apply to the {{site.data.keyword.personalityinsightsshort}} service. The service is stateless. It stores no user data on {{site.data.keyword.cloud_notm}}.

## Learn more about the service
{: #learn-index}

-   A [quick demo](https://personality-insights-demo.ng.bluemix.net/){: external} of the {{site.data.keyword.personalityinsightsshort}} service analyzes input text to develop a personality portrait that includes consumption preferences for the author.
-   Applications in {{site.data.keyword.watson}} [Starter Kits](https://cloud.ibm.com/developer/watson/starter-kits){: external} demonstrate the service.
-   [The service in action](/docs/services/personality-insights?topic=personality-insights-applied) and [The science behind the service](/docs/services/personality-insights?topic=personality-insights-science) provide information about the research that underlies the service.
-   The {{site.data.keyword.personalityinsightsshort}} service in the [{{site.data.keyword.cloud_notm}} Catalog](https://{DomainName}/catalog/services/personality-insights/){: external} describes the pricing plans that are available for the service.
