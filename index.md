---

copyright:
  years: 2015, 2020
lastupdated: "2020-11-02"

subcollection: personality-insights

---

{:help: data-hd-content-type='help'}
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

# About
{: #about}

{{site.data.keyword.IBM}} will begin sunsetting {{site.data.keyword.personalityinsightsfull}} on 1 December 2020. For a period of one year from this date, you will still be able to use {{site.data.keyword.personalityinsightsshort}}. However, as of 1 December 2021, the offering will no longer be available.<br/><br/>As an alternative, we encourage you to consider migrating to {{site.data.keyword.nlufull}}, a service on {{site.data.keyword.cloud}} that uses deep learning to extract data and insights from text such as keywords, categories, sentiment, emotion, and syntax to provide insights for your business or industry. For more information, see [About {{site.data.keyword.nlushort}}](https://cloud.ibm.com/docs/natural-language-understanding?topic=natural-language-understanding-about).
{: deprecated}

The {{site.data.keyword.personalityinsightsfull}} service provides an API for deriving insights from social media, enterprise data, or other digital communications. The service uses linguistic analytics to infer individuals' intrinsic personality characteristics from digital communications such as email, text messages, tweets, and forum posts.
{: shortdesc}

The service infers, from potentially noisy social media, portraits of individuals that reflect their personality characteristics. It can also determine individuals' consumption preferences, which indicate their likelihood to prefer various products, services, and activities.

## Personality characteristics
{: #models-index}
{: help}
{: support}

The {{site.data.keyword.personalityinsightsshort}} service infers personality characteristics based on three primary models:

-   **Big Five** personality characteristics represent the most widely used model for generally describing how a person engages with the world. The model includes five primary dimensions: *Agreeableness*, *Conscientiousness*, *Extraversion*, *Emotional range*, and *Openness*. Each dimension has six facets that further characterize an individual according to the dimension.
-   **Needs** describe which aspects of a product are likely to resonate with a person. The model includes twelve characteristic needs: *Excitement*, *Harmony*, *Curiosity*, *Ideal*, *Closeness*, *Self-expression*, *Liberty*, *Love*, *Practicality*, *Stability*, *Challenge*, and *Structure*.
-   **Values** describe motivating factors that influence a person's decision making. The model includes five values: *Self-transcendence / Helping others*, *Conservation / Tradition*, *Hedonism / Taking pleasure in life*, *Self-enhancement / Achieving success*, and *Open to change / Excitement*.

For more information, see [Personality models](/docs/personality-insights?topic=personality-insights-models).

## Consumption preferences
{: #preferences-index}
{: help}
{: support}

Based on the personality characteristics that are inferred from the input text, the service can also return an indication of the author's consumption preferences. Consumption preferences indicate the author's likelihood to pursue different products, services, and activities. The service groups the individual preferences into eight categories: *Shopping*, *Music*, *Movies*, *Reading and learning*, *Health and activity*, *Volunteering*, *Environmental concern*, and *Entrepreneurship*. Each category contains from one to as many as a dozen individual preferences.

For more information, see [Consumption preferences](/docs/personality-insights?topic=personality-insights-preferences).

## Benefits of the service
{: #benefits}

As a core service of the {{site.data.keyword.ibmwatson}} platform, the {{site.data.keyword.personalityinsightsshort}} service can provide insights that help businesses

-   Understand their customers at a deeper level by learning their clients' preferences, improving customer satisfaction, and strengthening client relations.
-   Improve client acquisition, retention, and engagement.
-   Guide highly personalized engagements and interactions to better tailor their products, services, campaigns, and communications for individual clients.

For more information about how you can benefit from the service, see [Use cases](/docs/personality-insights?topic=personality-insights-usecases).

## Language support
{: #languages-index}
{: help}
{: support}

The service supports the following languages. You can use any combination of supported languages for the request and response, but all input text must be in the same language. For more information, see [Specifying request and response languages](/docs/personality-insights?topic=personality-insights-input#languages-input).

| Request languages | Response languages |
|:-----------------:|:------------------:|
| Arabic<br/>English<br/>Japanese<br/>Korean<br/>Spanish | Arabic<br/>English<br/>Japanese<br/>Korean<br/>Spanish<br/>Brazilian Portuguese<br/>French<br/>German<br/>Italian<br/>Simplified Chinese<br/>Traditional Chinese |
{: caption="Table 1. Supported languages"}

## HIPAA
{: hipaa}

US Health Insurance Portability and Accountability Act (HIPAA) support does not apply to the {{site.data.keyword.personalityinsightsshort}} service. The service is stateless. It stores no user data on {{site.data.keyword.cloud_notm}}.

## Learn more about the service
{: #learn-index}

-   A [quick demo](https://personality-insights-demo.ng.bluemix.net/){: external} of the {{site.data.keyword.personalityinsightsshort}} service analyzes input text to develop a personality portrait that includes consumption preferences for the author.
-   [The service in action](/docs/personality-insights?topic=personality-insights-applied) and [The science behind the service](/docs/personality-insights?topic=personality-insights-science) provide information about the research that underlies the service.
-   The {{site.data.keyword.personalityinsightsshort}} service in the [{{site.data.keyword.cloud_notm}} Catalog](https://{DomainName}/catalog/services/personality-insights/){: external} describes the pricing plans that are available for the service.
