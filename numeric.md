---

copyright:
  years: 2015, 2018
lastupdated: "2018-11-15"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
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

# Interpreting the numeric results
{: #numeric}

The {{site.data.keyword.personalityinsightsshort}} service returns numeric results for each of the personality and behavioral characteristics and for each consumption preference. The values differ in the information they provide.
{: shortdesc}

For Arabic and Korean input, the service is unable to produce meaningful percentiles and raw scores for a number of personality characteristics. For more information, see [Limitations for Arabic and Korean input](#limitations).
{: note}

## Percentiles for personality characteristics
{: #percentiles}

For each request, the service always reports a normalized score as a `percentile` for each Big Five, Values, and Needs personality characteristic. Normalized scores represent a percentile ranking for each characteristic that is based on qualities that the service infers from the input text. The service computes normalized scores by comparing the raw score for the author's text with results from a sample population. The service reports each percentile as a double in the range of 0 to 1.

For example, a percentile of `0.64980796071382` for the personality characteristic `big5_extraversion` indicates that the author's score for that characteristic is in the 65th percentile. The author's writing exhibits the tendency to an extent that is greater than 64 percent and less than 34 percent of the sample population. The precision of the percentile depends on the number of words that were submitted as input with the request. For more information, see [Providing sufficient input](/docs/services/personality-insights/input.html#sufficient).

No mathematical relationship exists between the percentiles that are reported for Big Five dimensions and facets. The service calculates the normalized percentile for each dimension and facet independently based on correlations between survey participants' scores for that dimension or facet and the words that they use. Therefore, even though facets provide finer-grained descriptions of dimensions, adding the scores for the six facets of a dimension does not necessarily yield the percentile for that dimension. The same is true of raw scores.
{: note}

## Raw scores for personality characteristics
{: #rawScores}

If you specify `true` for the `raw_scores` query parameter of the request, the service reports a `raw_score` for each personality characteristic. Raw scores represent the score for a characteristic that is based solely on the author's text and the model for that characteristic. When it generates raw scores, the service does not compare the results to a sample population. Raw scores can be interpreted as the scores the author would receive from taking a personality test.

The service reports each raw score as a double in the range of 0 to 1. A higher score generally indicates a greater likelihood that the author has that characteristic. However, raw scores must be considered in aggregate: The range of values in practice might be much smaller than 0 to 1, so an individual score must be considered in the context of the overall scores and their range. But in general, a raw score, for instance, of `0.56817738781166` for the personality characteristic `big5_extraversion` indicates that the author would likely have achieved this score on a personality test. Compare this raw score with the normalized percentile reported for the same author and characteristic in the previous section.

The service makes raw scores available for users who want to apply a custom normalization for a specific scenario or who do not require a comparison with a sample population. Users who want to know how the author's characteristics compare with a large sample population can use the normalized scores. Users who want to derive their own normalized percentile scores from the raw data can compare the raw scores against a different sample population and apply a different approach to normalization.

To normalize a raw score to a percentile for a specific characteristic, compare the raw score with a sample population for which the mean and the standard deviation for the characteristic are known. For example, {{site.data.keyword.IBM_notm}} conducted studies to gather data from a large sample population of Twitter users. {{site.data.keyword.IBM_notm}} computed the users' scores for each of the personality characteristics and then established the mean and standard deviation for each characteristic. To compute the percentile score for a raw score that it infers from its analysis of input text, the service uses the mean and standard deviation that it derived from its sample Twitter population for that characteristic.

## Percentages for behavioral characteristics
{: #percentages}

If you submit JSON data whose content items have timestamps, the service reports a `percentage` for each behavioral characteristic. Behavioral characteristics identify the temporal distribution of the input. The percentage indicates how many of the content items occurred during each day of the week and time of day. For example, a percentage of `0.4561049445005` for the behavioral characteristic `behavior_0000` means that roughly 46 percent of the content items were created between the hours of midnight and 1:00 a.m.

## Scores for consumption preferences
{: #scores}

If you specify `true` for the `consumption_preferences` query parameter of the request, the service reports consumption preferences that include a `score` for each preference. The service derives the score from the personality characteristics that it infers from the input text. The score is a double that indicates how likely the author of the text is to prefer the item. It is an indication of preference, not a normalized percentage.

For some preferences, the score is one of three values:

-   `0.0`: The author is very unlikely to prefer the item. For some preferences, you can interpret the value as meaning that the author has a low level of interest.
-   `0.5`: The author is neutral about the item. For some preferences, the value can mean that the author has a medium level of interest.
-   `1.0`: The author is very likely to prefer the item. For some preferences, the value indicates a high level of interest.

For other preferences, the score represents a binary value. The author of the input text is either unlikely (`0.0`) or likely (`1.0`) to have an interest in the item, or the author has either a low or high level of interest. In some cases, the score can represent a simple yes or no response (for instance, is the author likely to have experience volunteering for social causes).

For a complete list of all preferences by category and the range of their results, see [Consumption preferences](/docs/services/personality-insights/preferences.html).

## Limitations for Arabic and Korean input
{: #limitations}

For Arabic and Korean input, the service's models are unable to produce meaningful results for a subset of personality characteristics. For the following characteristics, normalized percentile scores are always `0.5` and raw scores are always the mean of the original distribution. The `significant` field for each of these characteristics is always `false`. Do *not* rely on the results for these characteristics as part of the personality profile of the author.

<table>
  <caption>Table 1. Characteristics whose results are not significant</caption>
  <tr>
    <th style="text-align:left; vertical-align:bottom">
      Characteristics
    </th>
    <th style="text-align:left; vertical-align:bottom; width:40%">
      Arabic results that<br/>are not meaningful
    </th>
    <th style="text-align:left; vertical-align:bottom; width:40%">
      Korean results that<br/>are not meaningful
    </th>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      Big Five dimensions
    </td>
    <td style="text-align:left; vertical-align:top">
      Emotional range
    </td>
    <td style="text-align:left; vertical-align:top">
      None
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      Big Five facets
    </td>
    <td style="text-align:left; vertical-align:top">
      <ul style="margin:0px 0px 0px 15px; padding:0px">
        <li style="margin:0px; line-height:110%; padding:0px">
          *Agreeableness*: Altruism, Cooperation, Modesty, and Trust
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *Conscientiousness*: Achievement striving and Dutifulness
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *Extraversion*: Cheerfulness and Friendliness (Outgoing)
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *Emotional range*: Anger (Fiery), Prone to worry, Immoderation,
          and Self-consciousness
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *Openness*: Adventurousness, Imagination, and Intellect
        </li>
      </ul>
    </td>
    <td style="text-align:left; vertical-align:top">
      <ul style="margin:0px 0px 0px 15px; padding:0px">
        <li style="margin:0px; padding:0px">
          *Extraversion*: Excitement-seeking
        </li>
      </ul>
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      Needs
    </td>
    <td style="text-align:left; vertical-align:top">
      Ideal, Liberty, Love, Practicality, and Structure
    </td>
    <td style="text-align:left; vertical-align:top">
      Liberty and Stability
    </td>
  </tr>
  </tr>
    <td style="text-align:left; vertical-align:top">
      Values
    </td>
    <td style="text-align:left; vertical-align:top">
      Self-enhancement
    </td>
    <td style="text-align:left; vertical-align:top">
      Conservation
    </td>
  </tr>
</table>
