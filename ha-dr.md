---

copyright:
  years: 2019. 2020
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

# High availability and disaster recovery
{: #ha-dr}

{{site.data.keyword.IBM}} will begin sunsetting {{site.data.keyword.personalityinsightsfull}} on 1 December 2020. For a period of one year from this date, you will still be able to use {{site.data.keyword.personalityinsightsshort}}. However, as of 1 December 2021, the offering will no longer be available.<br/><br/>As an alternative, we encourage you to consider migrating to {{site.data.keyword.nlufull}}, a service on {{site.data.keyword.cloud}} that uses deep learning to extract data and insights from text such as keywords, categories, sentiment, emotion, and syntax to provide insights for your business or industry. For more information, see [About {{site.data.keyword.nlushort}}](https://cloud.ibm.com/docs/natural-language-understanding?topic=natural-language-understanding-about).
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
