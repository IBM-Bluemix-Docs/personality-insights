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

# Consumption preferences
{: #preferences}

{{site.data.keyword.personalityinsightsfull}} is discontinued. Existing instances are supported until 1 December 2021, but as of 1 December 2020, you cannot create new instances. Any instance that exists on 1 December 2021 will be deleted.<br/><br/>No direct replacement exists for {{site.data.keyword.personalityinsightsshort}}. However, you can consider using [{{site.data.keyword.nlufull}}](/docs/natural-language-understanding?topic=natural-language-understanding-about) on {{site.data.keyword.cloud}} as part of a replacement analytic workflow for your {{site.data.keyword.personalityinsightsshort}} use cases. You can use {{site.data.keyword.nlushort}} to extract data and insights from text, such as keywords, categories, sentiment, emotion, and syntax. For more information about the personality models in Personality Insights, see [The science behind the service](/docs/personality-insights?topic=personality-insights-science).
{: deprecated}

The {{site.data.keyword.personalityinsightsshort}} service infers an author's personality characteristics for three models: Big Five, Needs, and Values. Based on its results for these models, the service can also produce consumption preferences for the author of the input text. Set the `consumption_preferences` query parameter to `true` for a request to obtain consumption preferences.
{: shortdesc}

The service groups the more than 40 consumption preferences into eight high-level categories. The preferences indicate the author's likelihood to prefer different products, services, and activities. For instance, the service can identify

-   The author's inclinations for clothing (comfort versus fashion) and automobiles (cost versus safety).
-   The author's leanings toward different genres of music, movies, and reading.
-   The author's attitudes about the environment and volunteering.

Businesses use the service's personality models to better understand their customers and to design and develop more personalized and targeted campaigns, products, and services. Consumption preferences make it even easier to act on the service's results. Businesses can easily obtain and respond to a list of preferences that are associated with an individual's dominant characteristics. For more information about possible applications of the consumption preferences, see [Use cases](/docs/personality-insights?topic=personality-insights-usecases) and [The service in action](/docs/personality-insights?topic=personality-insights-applied).

The following sections list and describe the consumption preferences that the service can return. For more information about interpreting the numeric preferences, see [Scores for consumption preferences](/docs/personality-insights?topic=personality-insights-numeric#scores). For information about how {{site.data.keyword.IBM_notm}} developed the preferences, see [The science behind the service](/docs/personality-insights?topic=personality-insights-science).

## Shopping preferences
{: #shopping}

Shopping preferences indicate the author's interest in different types of purchases, the extent to which the author's purchasing habits are influenced by different external sources, and the author's spending habits. The category ID and name are `consumption_preferences_shopping` and `Purchasing Preferences`. The category has 12 preferences.

| Consumption preference ID | Name | Scores |
|---------------------------|------|:------:|
| `consumption_preferences_automobile_ownership_cost` | Likely to be sensitive to ownership cost when buying automobiles | `0.0` (unlikely)<br/>`0.5` (neutral)<br/>`1.0` (likely) |
| `consumption_preferences_automobile_safety` | Likely to prefer safety when buying automobiles | `0.0` (unlikely)<br/>`0.5` (neutral)<br/>`1.0` (likely) |
| `consumption_preferences_clothes_quality` | Likely to prefer quality when buying clothes | `0.0` (unlikely)<br/>`1.0` (likely) |
| `consumption_preferences_clothes_style` | Likely to prefer style when buying clothes | `0.0` (unlikely)<br/>`1.0` (likely) |
| `consumption_preferences_clothes_comfort` | Likely to prefer comfort when buying clothes | `0.0` (unlikely)<br/>`1.0` (likely) |
| `consumption_preferences_influence_brand_name` | Likely to be influenced by brand name when making product purchases | `0.0` (unlikely)<br/>`0.5` (neutral)<br/>`1.0` (likely) |
| `consumption_preferences_influence_utility` | Likely to be influenced by product utility when making product purchases | `0.0` (unlikely)<br/>`0.5` (neutral)<br/>`1.0` (likely) |
| `consumption_preferences_influence_online_ads` | Likely to be influenced by online ads when making product purchases | `0.0` (unlikely)<br/>`1.0` (likely) |
| `consumption_preferences_influence_social_media` | Likely to be influenced by social media when making product purchases | `0.0` (unlikely)<br/>`1.0` (likely) |
| `consumption_preferences_influence_family_members` | Likely to be influenced by family when making product purchases | `0.0` (unlikely)<br/>`1.0` (likely) |
| `consumption_preferences_spur_of_moment` | Likely to indulge in spur of the moment purchases | `0.0` (unlikely)<br/>`0.5` (neutral)<br/>`1.0` (likely) |
| `consumption_preferences_credit_card_payment` | Likely to prefer using credit cards for shopping | `0.0` (unlikely)<br/>`1.0` (likely) |
{: caption="Table 1. Shopping preferences"}

## Movie preferences
{: #movie}

Movie preferences indicate the author's interest in different types of movies. The category ID and name are `consumption_preferences_movie` and `Movie Preferences`. The category has 10 preferences.

| Consumption preference ID | Name | Scores |
|---------------------------|------|:------:|
| `consumption_preferences_movie_romance` | Likely to like romance movies | `0.0` (unlikely)<br/>`1.0` (likely) |
| `consumption_preferences_movie_adventure` | Likely to like adventure movies | `0.0` (unlikely)<br/>`1.0` (likely) |
| `consumption_preferences_movie_horror` | Likely to like horror movies | `0.0` (unlikely)<br/>`1.0` (likely) |
| `consumption_preferences_movie_musical` | Likely to like musical movies | `0.0` (unlikely)<br/>`1.0` (likely) |
| `consumption_preferences_movie_historical` | Likely to like historical movies | `0.0` (unlikely)<br/>`1.0` (likely) |
| `consumption_preferences_movie_science_fiction` | Likely to like science-fiction movies | `0.0` (unlikely)<br/>`1.0` (likely) |
| `consumption_preferences_movie_war` | Likely to like war movies | `0.0` (unlikely)<br/>`1.0` (likely) |
| `consumption_preferences_movie_drama` | Likely to like drama movies | `0.0` (unlikely)<br/>`1.0` (likely) |
| `consumption_preferences_movie_action` | Likely to like action movies | `0.0` (unlikely)<br/>`1.0` (likely) |
| `consumption_preferences_movie_documentary` | Likely to like documentary movies | `0.0` (unlikely)<br/>`1.0` (likely) |
{: caption="Table 2. Movie preferences"}

## Music preferences
{: #music}

Music preferences indicate the author's interest in different types of music and whether the author enjoys playing music. The category ID and name are `consumption_preferences_music` and `Music Preferences`. The category has nine preferences.

| Consumption preference ID | Name | Scores |
|---------------------------|------|:------:|
| `consumption_preferences_music_rap` | Likely to like rap music | `0.0` (unlikely)<br/>`0.5` (neutral)<br/>`1.0` (likely) |
| `consumption_preferences_music_country` | Likely to like country music | `0.0` (unlikely)<br/>`0.5` (neutral)<br/>`1.0` (likely) |
| `consumption_preferences_music_r_b` | Likely to like R&amp;B music | `0.0` (unlikely)<br/>`0.5` (neutral)<br/>`1.0` (likely) |
| `consumption_preferences_music_hip_hop` | Likely to like hip hop music | `0.0` (unlikely)<br/>`0.5` (neutral)<br/>`1.0` (likely) |
| `consumption_preferences_music_live_event` | Likely to attend live musical events | `0.0` (unlikely)<br/>`1.0` (likely) |
| `consumption_preferences_music_playing` | Likely to have experience playing music | `0.0` (unlikely)<br/>`1.0` (likely) |
| `consumption_preferences_music_latin` | Likely to like Latin music | `0.0` (unlikely)<br/>`0.5` (neutral)<br/>`1.0` (likely) |
| `consumption_preferences_music_rock` | Likely to like rock music | `0.0` (unlikely)<br/>`0.5` (neutral)<br/>`1.0` (likely) |
| `consumption_preferences_music_classical` | Likely to like classical music | `0.0` (unlikely)<br/>`0.5` (neutral)<br/>`1.0` (likely) |
{: caption="Table 3. Music preferences"}

## Reading and learning preferences
{: #reading}

Reading and learning preferences indicate the author's likelihood to read, the author's motivation for reading, and the types of content the author enjoys reading. The category ID and name are `consumption_preferences_reading` and `Reading Preferences`. The category has five preferences.

| Consumption preference ID | Name | Scores |
|---------------------------|------|:------:|
| `consumption_preferences_read_frequency` | Likely to read often | `0.0` (unlikely)<br/>`0.5` (neutral)<br/>`1.0` (likely) |
| `consumption_preferences_books_entertainment_magazines` | Likely to read entertainment magazines | `0.0` (unlikely)<br/>`1.0` (likely) |
| `consumption_preferences_books_non_fiction` | Likely to read non-fiction books | `0.0` (unlikely)<br/>`1.0` (likely) |
| `consumption_preferences_books_financial_investing` | Likely to read financial investment books | `0.0` (unlikely)<br/>`1.0` (likely) |
| `consumption_preferences_books_autobiographies` | Likely to read autobiographical books | `0.0` (unlikely)<br/>`1.0` (likely) |
{: caption="Table 4. Reading and learning preferences"}

## Health and activity preferences
{: #health}

Health and activity preferences indicate the author's interest in healthy foods and physical activity. The category ID and name are `consumption_preferences_health_and_activity` and `Health & Activity Preferences`. The category has three preferences.

| Consumption preference ID | Name | Scores |
|---------------------------|------|:------:|
| `consumption_preferences_eat_out` | Likely to eat out frequently | `0.0` (unlikely)<br/>`0.5` (neutral)<br/>`1.0` (likely) |
| `consumption_preferences_gym_membership` | Likely to have a gym membership | `0.0` (unlikely)<br/>`1.0` (likely) |
| `consumption_preferences_outdoor` | Likely to like outdoor activities | `0.0` (unlikely)<br/>`0.5` (neutral)<br/>`1.0` (likely) |
{: caption="Table 5. Health and activity preferences"}

## Entrepreneurship preferences
{: #entrepreneur}

Entrepreneurship preferences indicate the author's interest in starting a business. The category ID and name are `consumption_preferences_entrepreneurship` and `Entrepreneurship Preferences`. The category has one preference.

| Consumption preference ID | Name | Scores |
|---------------------------|------|:------:|
| `consumption_preferences_start_business` | Likely to consider starting a business in next few years | `0.0` (unlikely)<br/>`0.5` (neutral)<br/>`1.0` (likely) |
{: caption="Table 6. Entrepreneurship preferences"}

## Environmental concern preferences
{: #environment}

Environmental concern preferences indicate the author's interest in the environment. The category ID and name are `consumption_preferences_environmental_concern` and `Environmental Concern Preferences`. The category has one preference.

| Consumption preference ID | Name | Scores |
|---------------------------|------|:------:|
| `consumption_preferences_concerned_environment` | Likely to be concerned about the environment | `0.0` (unlikely)<br/>`0.5` (neutral)<br/>`1.0` (likely) |
{: caption="Table 7. Environmental concern preferences"}

## Volunteering preferences
{: #volunteer}

Volunteering preferences indicate the author's interest in volunteering for social causes. The category ID and name are `consumption_preferences_volunteering` and `Volunteering Preferences`. The category has one preference.

| Consumption preference ID | Name | Scores |
|---------------------------|------|:------:|
| `consumption_preferences_volunteer` | Likely to volunteer for social causes | `0.0` (unlikely)<br/>`1.0` (likely) |
{: caption="Table 8. Volunteering preferences"}
