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

# Understanding a JSON profile
{: #output}

{{site.data.keyword.personalityinsightsfull}} is discontinued. Existing instances are supported until 1 December 2021, but as of 1 December 2020, you cannot create new instances. Any instance that exists on 1 December 2021 will be deleted.<br/><br/>No direct replacement exists for {{site.data.keyword.personalityinsightsshort}}. However, you can consider using [{{site.data.keyword.nlufull}}](/docs/natural-language-understanding?topic=natural-language-understanding-about) on {{site.data.keyword.cloud}} as part of a replacement analytic workflow for your {{site.data.keyword.personalityinsightsshort}} use cases. You can use {{site.data.keyword.nlushort}} to extract data and insights from text, such as keywords, categories, sentiment, emotion, and syntax. For more information about the personality models in Personality Insights, see [The science behind the service](/docs/personality-insights?topic=personality-insights-science).
{: deprecated}

When you use the `POST /v3/profile` method to analyze content, the service returns the results of its analysis as a JSON `Profile` object when you specify `application/json` with the `Accept` header of a request. The scope of the JSON output depends on the parameters you specify with the request. It also depends on whether the input text represents timestamped data, such as the text associated with a Twitter feed.
{: shortdesc}

The following sections describe the contents of a response in JSON format. All example output is produced by the sample JSON file [profile.json](https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json){: external}. For information about CSV output, see [Understanding a CSV profile](/docs/personality-insights?topic=personality-insights-outputCSV).

## The Profile object
{: #outputJSON}

The `Profile` object is the top-level JSON object that is returned by the service. The object has the following fields:

-   `word_count` (integer) provides the number of words from the input content that were used to generate the profile. This figure can be less than the number of words in the input if the request submitted a large amount of content. If the number of words fails to meet a minimum threshold, the output includes a `word_count_message` field that provides further guidance.
-   `processed language` (string) describes the language model that the service used to process the input: `ar` (Arabic), `en` (English), `es` (Spanish), `ja` (Japanese), or `ko` (Korean).
-   `personality` is a recursive array of `Trait` objects that describes the Big Five dimensions and facets that are inferred from the input text.
-   `needs` is an array of `Trait` objects that describes the Needs that are inferred from the input text.
-   `values` is an array of `Trait` objects that describes the Values that are inferred from the input text.
-   `behavior` is an array of `Behavior` objects that describes the distribution of the content over the days of the week and the hours of the day. The service returns the field only for JSON input that is timestamped.
-   `consumption_preferences` is an array of `ConsumptionPreferencesCategory` objects that provides results for each category of consumption preferences. The elements of the array provide information for the individual preferences of that category. The service returns the field only if the `consumption_preferences` query parameter of the request is set to `true`.
-   `warnings` is an array of `Warning` objects that provides messages about the input text. The array is empty if the input generated no warnings.

### Example response
{: #JSONExample}

The following example output shows the high-level structure of a `Profile` object. The output always includes the `personality`, `needs`, and `values` fields. If the input is timestamped JSON, the response includes the `behavior` field. And if the request also asks for consumption preferences, the response includes the `consumption_preferences` field. In this example, the input generates no warnings.

```javascript
{
  "word_count": 15223,
  "processed_language": "en",
  "personality": [
     . . .
  ],
  "needs": [
     . . .
  ],
  "values": [
     . . .
  ],
  "behavior": [
     . . .
  ],
  "consumption_preferences": [
     . . .
   ],
  "warnings": []
}
```
{: codeblock}

## Personality characteristics output
{: #traitJSON}

The `Profile` object always includes `personality`, `needs`, and `values` fields for all types of input. Each of these fields contains an array of `Trait` objects that describes the personality characteristics for the attributes of that type of characteristic. For Needs and Values characteristics, the array has a single level that describes the characteristics. For Big Five characteristics, a top-level array describes the dimensions, and second-level arrays describe the facets of each dimension.

-   `trait_id` (string) is the unique ID of the characteristic to which the results pertain:
    -   `big5_{characteristic}` for Big Five personality dimensions
    -   `facet_{characteristic}` for Big Five personality facets
    -   `need_{characteristic}` for Needs
    -   `value_{characteristic}` for Values
-   `name` (string) is the user-visible name of the characteristic.
-   `category` (string) is the category of the characteristic:
    -   `personality` for Big Five personality characteristics
    -   `needs` for Needs
    -   `values` for Values
-   `percentile` (double) is the normalized percentile score for the characteristic. For more information, see [Percentiles for personality characteristics](/docs/personality-insights?topic=personality-insights-numeric#percentiles).
-   `raw_score` (double) is the raw score for the characteristic. The field is returned only if you request raw scores by setting the `raw_scores` query parameter to `true`. For more information, see [Raw scores for personality characteristics](/docs/personality-insights?topic=personality-insights-numeric#rawScores-numeric).
-   `significant` (boolean) indicates whether the characteristic is meaningful for the input language. The field is always `true` for all characteristics of English, Spanish, and Japanese input. The field is `false` for the subset of characteristics of Arabic and Korean input for which the service's models are unable to generate meaningful results. For more information, see [Limitations for Arabic and Korean input](/docs/personality-insights?topic=personality-insights-numeric#limitations).
-   `children` is an array of `Trait` objects that provides more detailed results for the facets of each Big Five dimension as inferred from the input text. The array is returned only for Big Five dimensions.

### Example response
{: #traitExample}

The following example output shows snippets of the output for the Big Five, Needs, and Values characteristics. As described, only the Big Five characteristics have an array of `children` for their respective facets.

```javascript
{
  . . .
  "personality": [
    {
      "trait_id": "big5_openness",
      "name": "Openness",
      "category": "personality",
      "percentile": 0.8011555009553,
      "raw_score": 0.77565404255038,
      "significant": true,
      "children": [
        {
          "trait_id": "facet_adventurousness",
          "name": "Adventurousness",
          "category": "personality",
          "percentile": 0.89755869047319,
          "raw_score": 0.54990704031219,
          "significant": true
        },
        . . .
      ]
    },
    {
      "trait_id": "big5_conscientiousness",
      "name": "Conscientiousness",
      "category": "personality",
      "percentile": 0.81001753184176,
      "raw_score": 0.66899984888815,
      "significant": true,
      "children": [
        {
          "trait_id": "facet_achievement_striving",
          "name": "Achievement striving",
          "category": "personality",
          "percentile": 0.84613299226628,
          "raw_score": 0.74240118454888,
          "significant": true
        },
        . . .
      ]
    },
    {
      "trait_id": "big5_extraversion",
      "name": "Extraversion",
      "category": "personality",
      "percentile": 0.64980796071382,
      "raw_score": 0.56817738781166,
      "significant": true,
      "children": [
        {
          "trait_id": "facet_activity_level",
          "name": "Activity level",
          "category": "personality",
          "percentile": 0.88220584913965,
          "raw_score": 0.60106995926143,
          "significant": true
        },
      ]
    },
    {
      "trait_id": "big5_agreeableness",
      "name": "Agreeableness",
      "category": "personality",
      "percentile": 0.94786124793821,
      "raw_score": 0.80677815631809,
      "significant": true,
      "children": [
        {
          "trait_id": "facet_altruism",
          "name": "Altruism",
          "category": "personality",
          "percentile": 0.99241983824205,
          "raw_score": 0.79028406290747,
          "significant": true
        },
        . . .
      ]
    },
    {
      "trait_id": "big5_neuroticism",
      "name": "Emotional range",
      "category": "personality",
      "percentile": 0.5008224041628,
      "raw_score": 0.46748200007024,
      "significant": true,
      "children": [
        {
          "trait_id": "facet_anger",
          "name": "Fiery",
          "category": "personality",
          "percentile": 0.17640022058508,
          "raw_score": 0.48490315691802,
          "significant": true
        },
        . . .
      ]
    }
  ],
  "needs": [
    {
      "trait_id": "need_challenge",
      "name": "Challenge",
      "category": "needs",
      "percentile": 0.67362332054511,
      "raw_score": 0.75196348037675,
      "significant": true
    },
    . . .
  ],
  "values": [
    {
      "trait_id": "value_conservation",
      "name": "Conservation",
      "category": "values",
      "percentile": 0.89268222856139,
      "raw_score": 0.72135308187423,
      "significant": true
    },
    . . .
  ],
  . . .
}
```
{: codeblock}

## Behavioral output
{: #behaviorJSON}

If the input to the service is JSON that has timestamps for the individual content items, the `Profile` object includes a `behavior` field. The field includes a `Behavior` object for each day of the week and hour of the day.

-   `trait_id` (string) is the unique ID of the characteristic to which the results pertain:
    -   `behavior_{day}` for days of the week (for example, `behavior_sunday`).
    -   `behavior_{hour}` for hours of the day (for example, `behavior_0000`).
-   `name` (string) is the user-visible name of the characteristic.
-   `category` (string) is the category of the characteristic, which is always `behavior`.
-   `percentage` (double) is the percentage of content items that occurred during that day of the week or hour of the day. For more information, see [Percentages for behavioral characteristics](/docs/personality-insights?topic=personality-insights-numeric#percentages).

### Example response
{: #behaviorExample}

The following output shows snippets of the behavioral output for temporal characteristics.

```javascript
{
  . . .
  "behavior": [
    {
      "trait_id": "behavior_sunday",
      "name": "Sunday",
      "category": "behavior",
      "percentage": 0.21392532795156
    },
    {
      "trait_id": "behavior_monday",
      "name": "Monday",
      "category": "behavior",
      "percentage": 0.42583249243189
    },
    . . .
    {
      "trait_id": "behavior_saturday",
      "name": "Saturday",
      "category": "behavior",
      "percentage": 0.077699293642785
    },
    {
      "trait_id": "behavior_0000",
      "name": "0:00 am",
      "category": "behavior",
      "percentage": 0.4561049445005
    },
    {
      "trait_id": "behavior_0100",
      "name": "1:00 am",
      "category": "behavior",
      "percentage": 0.12209889001009
    },
    . . .
    {
      "trait_id": "behavior_2300",
      "name": "11:00 pm",
      "category": "behavior",
      "percentage": 0.12310797174571
    }
  ],
  . . .
}
```
{: codeblock}

## Consumption preferences output
{: #preferenceJSON}

If the `consumption_preferences` query parameter is set to `true`, the `Profile` object includes a `consumption_preferences` field. The field includes a `ConsumptionPreferencesCategory` object for each category of preferences.

-   `consumption_preference_category_id` (string) is the unique ID of the consumption preferences category to which the results pertain in the form `consumption_preferences_{category}`.
-   `name` (string) is the user-visible name of the consumption preferences category.
-   `consumption_preferences` is an array of `ConsumptionPreferences` objects that provides results for the individual preferences of the category.

Each individual preference for a category is described via a `ConsumptionPreferences` object. Some categories have only a single preference; other categories have many more.

-   `consumption_preference_id` (string) is the unique ID of the consumption preference to which the results pertain in the form `consumption_preferences_{preference}`.
-   `name` (string) is the user-visible name of the consumption preference.
-   `score` (double) is a score that indicates the author's likelihood of preferring the item. For more information, see [Scores for consumption preferences](/docs/personality-insights?topic=personality-insights-numeric#scores).

### Example response
{: #preferenceExample}

The following output shows snippets of the output for consumption preferences.

```javascript
{
  . . .
  "consumption_preferences": [
    {
      "consumption_preference_category_id": "consumption_preferences_shopping",
      "name": "Purchasing Preferences",
      "consumption_preferences": [
        {
          "consumption_preference_id": "consumption_preferences_automobile_ownership_cost",
          "name": "Likely to be sensitive to ownership cost when buying automobiles",
          "score": 0
        },
        . . .
      ]
    },
    {
      "consumption_preference_category_id": "consumption_preferences_health_and_activity",
      "name": "Health & Activity Preferences",
      "consumption_preferences": [
        {
          "consumption_preference_id": "consumption_preferences_eat_out",
          "name": "Likely to eat out frequently",
          "score": 1
        },
        . . .
      ]
    },
    . . .
    {
      "consumption_preference_category_id": "consumption_preferences_volunteering",
      "name": "Volunteering Preferences",
      "consumption_preferences": [
        {
          "consumption_preference_id": "consumption_preferences_volunteer",
          "name": "Likely to volunteer for social causes",
          "score": 0
        }
      ]
    }
  ],
  . . .
}
```
{: codeblock}
