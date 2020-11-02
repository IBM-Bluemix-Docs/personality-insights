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

# Personality models
{: #models}

{{site.data.keyword.IBM}} will begin sunsetting {{site.data.keyword.personalityinsightsfull}} on 1 December 2020. For a period of one year from this date, you will still be able to use {{site.data.keyword.personalityinsightsshort}}. However, as of 1 December 2021, the offering will no longer be available.<br/><br/>As an alternative, we encourage you to consider migrating to {{site.data.keyword.nlufull}}, a service on {{site.data.keyword.cloud}} that uses deep learning to extract data and insights from text such as keywords, categories, sentiment, emotion, and syntax to provide insights for your business or industry. For more information, see [About {{site.data.keyword.nlushort}}](https://cloud.ibm.com/docs/natural-language-understanding?topic=natural-language-understanding-about).
{: deprecated}

The {{site.data.keyword.personalityinsightsshort}} service is based on the psychology of language in combination with data analytics algorithms. The service analyzes the content that you send and returns a personality profile for the author of the input. The service infers personality characteristics based on three models:
{: shortdesc}

-   *Big Five* personality characteristics represent the most widely used model for generally describing how a person engages with the world. The model includes five primary dimensions:
    -   [*Agreeableness*](/docs/personality-insights?topic=personality-insights-agreeableness) is a person's tendency to be compassionate and cooperative toward others.
    -   [*Conscientiousness*](/docs/personality-insights?topic=personality-insights-conscientiousness) is a person's tendency to act in an organized or thoughtful way.
    -   [*Extraversion*](/docs/personality-insights?topic=personality-insights-extraversion) is a person's tendency to seek stimulation in the company of others.
    -   [*Emotional range*](/docs/personality-insights?topic=personality-insights-emotionalRange), also referred to as *Neuroticism* or *Natural reactions*, is the extent to which a person's emotions are sensitive to the person's environment.
    -   [*Openness*](/docs/personality-insights?topic=personality-insights-openness) is the extent to which a person is open to experiencing different activities.

    Each of these top-level dimensions has six facets that further characterize an individual according to the dimension.
-   [Needs](/docs/personality-insights?topic=personality-insights-needs) describe which aspects of a product resonate with a person. The model includes twelve characteristic needs.
-   [Values](/docs/personality-insights?topic=personality-insights-values) describe motivating factors that influence a person's decision making. The model includes five values.

For more information about how the models were developed and how the service uses them, see [The science behind the service](/docs/personality-insights?topic=personality-insights-science).

## Descriptions of Big Five personality characteristics
{: #bigFive}

Each Big Five dimension is described by three tables:

-   The *Facets* table introduces the dimension's facets and describes individuals who score high on each facet.
-   The *Range of characteristics* table presents general descriptions that might apply to individuals whose scores evidence more or less of each facet of the dimension, along with terms that might describe such individuals. For a convenient single-page table that summarizes the *Range of characteristics* tables for the facets of all five dimensions, see [Personality-Insights-Facet-Characteristics.pdf](https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Personality-Insights-Facet-Characteristics.pdf){: external}.
-   The *Primary and secondary dimensions* table presents information that relates the dimension to other dimensions, describing combinations of personality characteristics. The table provides interesting insight into how primary and secondary characteristics might interrelate to represent an individual's composite personality. For a convenient single-page table that summarizes the *Primary and secondary characteristics* tables for all five dimensions, see [Personality-Insights-Dimension-Characteristics.pdf](https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Personality-Insights-Dimension-Characteristics.pdf){: external}.
