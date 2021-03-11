---

copyright:
  years: 2019. 2021
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

# High availability and disaster recovery
{: #ha-dr}

{{site.data.keyword.personalityinsightsfull}} is discontinued. Existing instances are supported until 1 December 2021, but as of 1 December 2020, you cannot create new instances. Any instance that exists on 1 December 2021 will be deleted.<br/><br/>No direct replacement exists for {{site.data.keyword.personalityinsightsshort}}. However, you can consider using [{{site.data.keyword.nlufull}}](/docs/natural-language-understanding?topic=natural-language-understanding-about) on {{site.data.keyword.cloud}} as part of a replacement analytic workflow for your {{site.data.keyword.personalityinsightsshort}} use cases. You can use {{site.data.keyword.nlushort}} to extract data and insights from text, such as keywords, categories, sentiment, emotion, and syntax. For more information about the personality models in Personality Insights, see [The science behind the service](/docs/personality-insights?topic=personality-insights-science).
{: deprecated}

The {{site.data.keyword.personalityinsightsfull}} service is highly available within any {{site.data.keyword.cloud_notm}} location. It has no backup and restore requirements for disaster recovery.
{: shortdesc}

## High availability
{: #high-availability}

The {{site.data.keyword.personalityinsightsshort}} service is highly available with no single point of failure within any {{site.data.keyword.cloud_notm}} location (for example, Dallas or Washington, DC). The service achieves high availability automatically and transparently by means of the multi-zone region (MZR) feature provided by {{site.data.keyword.cloud_notm}}.

{{site.data.keyword.cloud_notm}} enables multiple zones that do not share a single point of failure within a single location. It also provides automatic load balancing across the zones within a region.

## Disaster recovery
{: #disaster-recovery}

The {{site.data.keyword.personalityinsightsshort}} service is stateless. It stores no user data on {{site.data.keyword.cloud_notm}}. In the event of a catastrophic failure in a region, complete the following steps:

1.  Create a new instance of the {{site.data.keyword.personalityinsightsshort}} service in a different region.
1.  Modify your application to use the URL and credentials for the new service instance.
