---

copyright:
  years: 2015, 2021
lastupdated: "2021-03-10"

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

# The science behind the service
{: #science}

{{site.data.keyword.personalityinsightsfull}} is discontinued. Existing instances are supported until 1 December 2021, but as of 1 December 2020, you cannot create new instances. Any instance that exists on 1 December 2021 will be deleted.<br/><br/>No direct replacement exists for {{site.data.keyword.personalityinsightsshort}}. However, you can consider using [{{site.data.keyword.nlufull}}](/docs/natural-language-understanding?topic=natural-language-understanding-about) on {{site.data.keyword.cloud}} as part of a replacement analytic workflow for your {{site.data.keyword.personalityinsightsshort}} use cases. You can use {{site.data.keyword.nlushort}} to extract data and insights from text, such as keywords, categories, sentiment, emotion, and syntax. For more information about the personality models in Personality Insights, see [The science behind the service](/docs/personality-insights?topic=personality-insights-science).
{: deprecated}

A well-accepted theory of psychology, marketing, and other fields is that human language reflects personality, thinking style, social connections, and emotional states. The frequency with which people use certain categories of words can provide clues to these characteristics. Several researchers found that variations in word usage in writings such as blogs, essays, and tweets can predict aspects of personality ([Fast and Funder, 2008](/docs/personality-insights?topic=personality-insights-references#fast2008); [Gill and others, 2009](/docs/personality-insights?topic=personality-insights-references#gill2009); [Golbeck and others, 2011](/docs/personality-insights?topic=personality-insights-references#golbeck2011); [Hirsh and Peterson, 2009](/docs/personality-insights?topic=personality-insights-references#hirsh2009); and [Yarkoni, 2010](/docs/personality-insights?topic=personality-insights-references#yarkoni2010)).
{: shortdesc}

{{site.data.keyword.IBM_notm}} conducted a set of studies to understand whether personality characteristics that are inferred from social media data can predict people's behavior and preferences. {{site.data.keyword.IBM_notm}} found that people with specific personality characteristics responded and retweeted in higher numbers in information-collection and -spreading tasks. For example, people who score high on excitement-seeking are more likely to respond, while people who score high on cautiousness are less likely to do so ([Mahmud and others, 2013](/docs/personality-insights?topic=personality-insights-references#mahmud2013)). Similarly, people who score high on modesty, openness, and friendliness are more likely to spread information ([Lee and others, 2014](/docs/personality-insights?topic=personality-insights-references#lee2014)).

{{site.data.keyword.IBM_notm}} also found that people with high openness and low emotional range (neuroticism) as inferred from social media language responded more favorably (for example, by clicking an advertisement link or following an account). These results are corroborated by survey-based, ground-truth checking. For example, targeting the 10 percent of users in terms of highest openness and lowest emotional range resulted in increases in click rate from 6.8 percent to 11.3 percent and in follow rate from 4.7 percent to 8.8 percent.

Multiple recent studies disclosed similar results for characteristics that were computed from social media data. One recent study with retail store data found that people who score high in orderliness, self-discipline, and cautiousness and low in immoderation are 40 percent more likely than the random population to respond to coupons. A second study found that people with specific values showed specific reading interests ([Hsieh and others 2014](/docs/personality-insights?topic=personality-insights-references#hsieh2014)). For example, people with a higher self-transcendence value demonstrated an interest in reading articles about the environment, and people with a higher self-enhancement value showed an interest in reading articles about work. A third study of more than 600 Twitter users found that a person's personality characteristics can predict their brand preference with 65 percent accuracy.

The following sections expand upon these high-level findings to describe the research and development behind the {{site.data.keyword.personalityinsightsshort}} service. For more information about studies that apply the service to tangible scenarios, see [The service in action](/docs/personality-insights?topic=personality-insights-applied).

## Understanding the personality models
{: #researchModels}
{: help}
{: support}

For the {{site.data.keyword.personalityinsightsshort}} service, {{site.data.keyword.IBM_notm}} developed models to infer scores for Big Five dimensions and facets, Needs, and Values from textual information. The models reported by the service are based on research in the fields of psychology, psycholinguistics, and marketing:

-   [Big Five](/docs/personality-insights?topic=personality-insights-models) is one of the most studied of the personality models that were developed by psychologists ([Costa and McCrae, 1992](/docs/personality-insights?topic=personality-insights-references#costa1992), and [Norman, 1963](/docs/personality-insights?topic=personality-insights-references#norman1963)). It is the most widely used personality model to describe how a person generally engages with the world. The service computes the five dimensions and thirty facets of the model. The dimensions are often referred to by the mnemonic *OCEAN*, where *O* stands for Openness, *C* for Conscientiousness, *E* for Extraversion, *A* for Agreeableness, and *N* for Neuroticism. (Because the term Neuroticism can have a specific clinical meaning, the service presents such insights under the more generally applicable heading Emotional range.)
-   [Needs](/docs/personality-insights?topic=personality-insights-needs) are an important aspect of human behavior. Research literature suggests that several types of human needs are universal and directly influence consumer behavior ([Kotler and Armstrong, 2013](/docs/personality-insights?topic=personality-insights-references#kotler2013), and [Ford, 2005](/docs/personality-insights?topic=personality-insights-references#ford2005)). The twelve categories of needs that are reported by the service are described in marketing literature as desires that people hope to fulfill when they consider a product or service.
-   [Values](/docs/personality-insights?topic=personality-insights-values) convey what is most important to an individual. They are "desirable, trans-situational goals, varying in importance, that serve as guiding principles in people's lives" ([Schwartz, 2006](/docs/personality-insights?topic=personality-insights-references#schwartz2006)). Schwartz summarizes five features that are common to all values:

    1.  Values are beliefs.
    1.  Values are a motivational construct.
    1.  Values transcend specific actions and situations.
    1.  Values guide the selection or evaluation of actions, policies, people, and events.
    1.  Values vary by relative importance and can be ranked by importance.

    The service computes the five basic human values that were proposed by Schwartz and that were validated in more than twenty countries ([Schwartz, 1992](/docs/personality-insights?topic=personality-insights-references#schwartz1992)).

## How personality characteristics are inferred
{: #researchInfer}

The {{site.data.keyword.personalityinsightsshort}} service infers personality characteristics from textual information based on an open-vocabulary approach. This method reflects the latest trend in the research about personality inference ([Arnoux and others, 2017](/docs/personality-insights?topic=personality-insights-references#arnoux2017), [Schwartz and others, 2013](/docs/personality-insights?topic=personality-insights-references#schwartz2013), and [Plank and Hovy, 2015](/docs/personality-insights?topic=personality-insights-references#plank2015)).

The service first tokenizes the input text to develop a representation in an *n*-dimensional space. The service uses an open-source word-embedding technique, [GloVe](https://nlp.stanford.edu/projects/glove/){: external}, to obtain a vector representation for the words in the input text ([Pennington and others, 2014](/docs/personality-insights?topic=personality-insights-references#pennington2014)). It then feeds this representation to a machine-learning algorithm that infers a personality profile with Big Five, Needs, and Values characteristics. To train the algorithm, the service uses scores from surveys that were conducted among thousands of users along with data from their Twitter feeds.

{{site.data.keyword.IBM_notm}} developed the models for all supported languages in an identical way. The models were developed independent of user demographics such as age, gender, or culture. In the future, {{site.data.keyword.IBM_notm}} might develop models that are specific to different demographic categories.

Earlier versions of the service used the Linguistic Inquiry and Word Count (LIWC) psycholinguistic dictionary with its machine-learning model. However, the open-vocabulary approach outperforms the LIWC-based model. For more information about the service's precision for each language in terms of average Mean Absolute Error (MAE) and correlation, see [How precise is the service](#researchPrecise). For guidance about providing input text to achieve the most accurate results, see [Providing sufficient input](/docs/personality-insights?topic=personality-insights-input#sufficient).

## How precise is the service
{: #researchPrecise}

{{site.data.keyword.IBM_notm}} conducted a validation study to understand the accuracy of the service's approach to inferring a personality profile. {{site.data.keyword.IBM_notm}} collected survey responses and Twitter feeds from between 1500 and 2000 participants for all characteristics and languages. To establish *ground truth*, participants took four sets of standard psychometric tests:

-   A 50-item Big Five derived from the International Personality Item Pool (IPIP)
-   A 120-item Facet derived from the IPIP Neuroticism, Extraversion &amp; Openness (IPIP-NEO)
-   A 52-item fundamental Needs developed by {{site.data.keyword.IBM_notm}}
-   A 26-item basic Values developed by Schwartz

{{site.data.keyword.IBM_notm}} then compared the scores that were derived by its models with the survey-based scores for the Twitter users. Based on these results, {{site.data.keyword.IBM_notm}} determined the [average Mean Absolute Error](#preciseMAE) and [average correlation](#preciseCorrelation) between the inferred and actual scores for the different categories of personality characteristics. [Per-language average MAE and correlation](#precisePerLanguage) provide the statistical values for each supported language.

### Average Mean Absolute Error
{: #preciseMAE}

*Mean Absolute Error (MAE)* is a metric that is used to measure the difference between actual and predicted values. For the {{site.data.keyword.personalityinsightsshort}} service, the actual value, or ground truth, is the personality score that was obtained by administering a personality survey. The predicted value is the score that the service's models produce.

{{site.data.keyword.IBM_notm}} computed the MAE by taking the average of the absolute value of the difference between the actual and predicted scores. {{site.data.keyword.IBM_notm}} used the absolute value because predicting more or less of the actual value is irrelevant. As long as a difference exists, the model is penalized by the magnitude of the error. The lower the MAE, the better the performance of the model. {{site.data.keyword.IBM_notm}} uses a scale of 0 to 1 for MAE, where 0 means no error (the predicted value is the exact same as the actual value), and 1 means maximum error.

### Average correlation
{: #preciseCorrelation}

*Average correlation* is a statistical term that measures the interdependence of two variables. With this metric, {{site.data.keyword.IBM_notm}} measured the correlation between inferred and actual scores for the different categories of personality characteristics. If the predicted score closely tracks the actual results, the correlation score is high; otherwise, the score is low.

{{site.data.keyword.IBM_notm}} measures correlation on a scale of -1 to 1:

-   1 indicates a perfect direct (increasing) linear relationship.
-   -1 indicates a perfect inverse (decreasing) linear relationship.

In all other cases, the value lies between these extremes. If the variables are independent (they have no relationship at all), the correlation is 0.

{{site.data.keyword.IBM_notm}} looks for numbers closer to 1 for best predictions. But personalities are difficult to predict based solely on text, and it is rare to see correlations that exceed 0.4 for these types of psychological models. In research literature for this domain, correlations greater than 0.2 are considered acceptable.

### Per-language average MAE and correlation
{: #precisePerLanguage}

The following table shows per-language average MAE and correlation results for the {{site.data.keyword.personalityinsightsshort}} service. The results place the service at the forefront of personality inference from textual data as indicated by [Schwartz and others (2013)](/docs/personality-insights?topic=personality-insights-references#schwartz2013) and [Plank and Hovy (2015)](/docs/personality-insights?topic=personality-insights-references#plank2015).

<table summary="For each row that identifies a language in the first column, the following two rows provide the average MAE and the average correlation for the Big Five dimensions, the Big Five facets, the Needs, and the Values.">
  <caption>Table 1. Average MAE and correlation by language</caption>
  <tr>
    <th id="language" style="text-align:left; vertical-align:bottom">
      Language
    </th>
    <th id="dimensions" style="text-align:center; vertical-align:bottom">
      Big Five dimensions
    </th>
    <th id="facets" style="text-align:center; vertical-align:bottom">
      Big Five facets
    </th>
    <th id="needs" style="text-align:center; vertical-align:bottom">
      Needs
    </th>
    <th id="values" style="text-align:center; vertical-align:bottom">
      Values
    </th>
  </tr>
  <tr>
    <th id="arabic" headers="language" colspan="5" style="text-align:left">
      **Arabic**
    </th>
  </tr>
  <tr>
    <td headers="language arabic" style="text-align:left">
      Average MAE
    </td>
    <td headers="dimensions arabic" style="text-align:center">
      0.09
    </td>
    <td headers="facets arabic" style="text-align:center">
      0.12
    </td>
    <td headers="needs arabic" style="text-align:center">
      0.11
    </td>
    <td headers="values arabic" style="text-align:center">
      0.10
    </td>
  </tr>
  <tr>
    <td headers="language arabic" style="text-align:left">
      Average correlation
    </td>
    <td headers="dimensions arabic" style="text-align:center">
      0.16
    </td>
    <td headers="facets arabic" style="text-align:center">
      0.14
    </td>
    <td headers="needs arabic" style="text-align:center">
      0.13
    </td>
    <td headers="values arabic" style="text-align:center">
      0.14
    </td>
  </tr>
  <tr>
    <th id="english" headers="language" colspan="5" style="text-align:left">
      **English**
    </th>
  </tr>
  <tr>
    <td headers="language english" style="text-align:left">
      Average MAE
    </td>
    <td headers="dimensions english" style="text-align:center">
      0.12
    </td>
    <td headers="facets english" style="text-align:center">
      0.12
    </td>
    <td headers="needs english" style="text-align:center">
      0.11
    </td>
    <td headers="values english" style="text-align:center">
      0.11
    </td>
  </tr>
  <tr>
    <td headers="language english" style="text-align:left">
      Average correlation
    </td>
    <td headers="dimensions english" style="text-align:center">
      0.31
    </td>
    <td headers="facets english" style="text-align:center">
      0.28
    </td>
    <td headers="needs english" style="text-align:center">
      0.22
    </td>
    <td headers="values english" style="text-align:center">
      0.24
    </td>
  </tr>
  <tr>
    <th id="japanese" headers="language" colspan="5" style="text-align:left">
      **Japanese**
    </th>
  </tr>
  <tr>
    <td headers="language japanese" style="text-align:left">
      Average MAE
    </td>
    <td headers="dimensions japanese" style="text-align:center">
      0.10
    </td>
    <td headers="facets japanese" style="text-align:center">
      0.12
    </td>
    <td headers="needs japanese" style="text-align:center">
      0.11
    </td>
    <td headers="values japanese" style="text-align:center">
      0.11
    </td>
  </tr>
  <tr>
    <td headers="language japanese" style="text-align:left">
      Average correlation
    </td>
    <td headers="dimensions japanese" style="text-align:center">
      0.30
    </td>
    <td headers="facets japanese" style="text-align:center">
      0.22
    </td>
    <td headers="needs japanese" style="text-align:center">
      0.25
    </td>
    <td headers="values japanese" style="text-align:center">
      0.19
    </td>
  </tr>
  <tr>
    <th id="korean" headers="language" colspan="5" style="text-align:left">
      **Korean**
    </th>
  </tr>
  <tr>
    <td headers="language korean" style="text-align:left">
      Average MAE
    </td>
    <td headers="dimensions korean" style="text-align:center">
      0.09
    </td>
    <td headers="facets korean" style="text-align:center">
      0.12
    </td>
    <td headers="needs korean" style="text-align:center">
      0.11
    </td>
    <td headers="values korean" style="text-align:center">
      0.11
    </td>
  </tr>
  <tr>
    <td headers="language korean" style="text-align:left">
      Average correlation
    </td>
    <td headers="dimensions korean" style="text-align:center">
      0.25
    </td>
    <td headers="facets korean" style="text-align:center">
      0.21
    </td>
    <td headers="needs korean" style="text-align:center">
      0.13
    </td>
    <td headers="values korean" style="text-align:center">
      0.12
    </td>
  </tr>
  <tr>
    <th id="spanish" headers="language" colspan="5" style="text-align:left">
      **Spanish**
    </th>
  </tr>
  <tr>
    <td headers="language spanish" style="text-align:left">
      Average MAE
    </td>
    <td headers="dimensions spanish" style="text-align:center">
      0.10
    </td>
    <td headers="facets spanish" style="text-align:center">
      0.12
    </td>
    <td headers="needs spanish" style="text-align:center">
      0.12
    </td>
    <td headers="values spanish" style="text-align:center">
      0.11
    </td>
  </tr>
  <tr>
    <td headers="language spanish" style="text-align:left">
      Average correlation
    </td>
    <td headers="dimensions spanish" style="text-align:center">
      0.35
    </td>
    <td headers="facets spanish" style="text-align:center">
      0.21
    </td>
    <td headers="needs spanish" style="text-align:center">
      0.24
    </td>
    <td headers="values spanish" style="text-align:center">
      0.19
    </td>
  </tr>
</table>

To compute the percentile scores, {{site.data.keyword.IBM_notm}} collected a very large data set of Twitter users and computed their personality portraits:

-   One million users for English
-   Two-hundred thousand users for Korean
-   One-hundred thousand users for each of Arabic and Japanese
-   Eighty thousand users for Spanish

{{site.data.keyword.IBM_notm}} then compared the raw scores of each computed profile to the distribution of profiles from the data sets to determine the percentiles.

For Arabic and Korean input, the service is unable to produce meaningful percentiles and raw scores for some personality characteristics. For more information, see [Limitations for Arabic and Korean input](/docs/personality-insights?topic=personality-insights-numeric#limitations).
{: note}

## Understanding consumption preferences
{: #researchPrefs}

The relationship between personality and purchasing behavior was studied across various products and services:

-   [Chen (2007)](/docs/personality-insights?topic=personality-insights-references#chen2007), while testing preferences for organic foods, indicated that an individual's personality characteristics play an important role in establishing personal food-choice criteria.
-   [Schlegelmilch and others (1996)](/docs/personality-insights?topic=personality-insights-references#schlegelmilch1996) explored the relationship between personality variables and pro-environmental purchasing behavior. The authors showed that consumers' overall environmental consciousness has a positive impact on green purchasing decisions.
-   [Hymbaugh and Garrett (2007)](/docs/personality-insights?topic=personality-insights-references#hymbaugh1974) investigated the relationship between personality and skydiving and found that people who score high in adventurousness and excitement-seeking generally indulge in skydiving. (For more information, see [Risk profiles](/docs/personality-insights?topic=personality-insights-applied#otherRisk).)

Applying these known relations between consumption behaviors and personality is challenging. Most of the works used personality data derived from surveys, and their models are not publicly available. Therefore, {{site.data.keyword.IBM_notm}} decided to learn these consumption preference models directly. When it was training the models, {{site.data.keyword.IBM_notm}} used personality scores that were returned from the {{site.data.keyword.personalityinsightsshort}} service as features. As a result, when you apply these models to calculate a user's personality characteristics with the service, the predictions are likely to be more accurate.

## How consumption preferences are inferred
{: #researchInferPrefs}

The {{site.data.keyword.personalityinsightsshort}} service infers consumption preferences based on the results of its personality profile for the author of the input text. From existing literature, {{site.data.keyword.IBM_notm}} identified 104 consumption preferences that have proved to be correlated with personality. These include preferences that are related to shopping, movies, music, and other categories. {{site.data.keyword.IBM_notm}} then created a psychometric survey to assess an individual's inclination for each consumption behavior.

{{site.data.keyword.IBM_notm}} obtained responses to its survey from about 600 individuals for whom it also had Twitter data (more than 200 self-authored tweets for each user). {{site.data.keyword.IBM_notm}} submitted the tweets to the service to gather a personality profile for each individual. It then built a classifier for each consumption preference, where the input feature set was the personality information.

For inclusion with the service, {{site.data.keyword.IBM_notm}} selected only those consumption preferences for which personality-based classification performed at least 9 percent better than random classification. Of the original 104 preferences, 42 satisfied this criterion and are exposed as consumption preferences by the service.

<!--
COMMENTED FOR REMOVAL OF LIWC AND SAMPLING ERROR 08/10/2016

## How media influence inferred characteristics

{{site.data.keyword.IBM_notm}} conducted a validation study to understand the effect of media on inferred characteristics. To determine the accuracy of the service's approach to estimating characteristics, {{site.data.keyword.IBM_notm}} compared scores that were derived by its models with survey-based scores for Twitter users (for instance, approximately 500 users for English and more than 600 for Spanish).

To establish ground truth, participants took three sets of standard psychometric tests: 50-item Big Five (derived from the International Personality Item Pool, or IPIP), 52-item fundamental Needs (developed by {{site.data.keyword.IBM_notm}}), and 26-item basic Values (developed by Schwartz). {{site.data.keyword.IBM_notm}} conducted the study in two phases:

-   For the first study, conducted in 2013, {{site.data.keyword.IBM_notm}} recruited 256 Twitter users ([Gou and others, 2014](/docs/personality-insights?topic=personality-insights-references#gou2014)). Although the models were learned from different sources, {{site.data.keyword.IBM_notm}} found that for more than 80 percent of the Twitter users, scores for characteristics that were inferred for all three models correlated significantly with survey-based scores (p-value &lt; 0.05 and correlation coefficient between 0.05 and 0.80). Specifically, scores that were derived by the service correlated with survey-based scores as follows:
    -   For 80.8 percent of participants' Big Five scores (p-value &lt; 0.05 and correlation coefficients between 0.05 and 0.75)
    -   For 86.6 percent of participants' Needs scores (p-value &lt; 0.05 and correlation coefficient between 0.05 and 0.80)
    -   For 98.21 percent of participants' Values scores (p-value &lt; 0.05 and correlation coefficients between 0.05 and 0.55)
-   For the second study, conducted in 2015, {{site.data.keyword.IBM_notm}} recruited another set of 237 Twitter users. The study found that for Big Five and Values, scores for inferred characteristics correlated significantly with survey-based scores (p-value &lt; 0.05 and correlation coefficient between 0.07 and 0.21) for every Twitter user. For needs, such significant correlation was observed for 90 percent of the users (p value &lt; 0.05 and correlation coefficient between 0.01 and 0.20).

In both studies, participants also rated on a five-point scale how well each derived characteristic matched their perceptions of themselves. Their ratings suggest that the inferred characteristics largely matched their self-perceptions. Specifically, means of all ratings were above 3 ("somewhat") out of 5 ("perfect").

-   For the 256 Twitter users of the first study, means were 3.4 (with a standard deviation of 1.14) for Big Five, 3.39 (with a standard deviation of 1.34) for Needs, and 3.13 (with a standard deviation of 1.17) for Values.
-   For the 237 Twitter users of the second study, means were 3.31 (with a standard deviation of 1.18) for Big Five, 3.37 (with a standard deviation of 1.22) for Needs, and 3.36 (with a standard deviation of 1.18) for Values.

COMMENTED FOR REMOVAL OF LIWC AND SAMPLING ERROR 08/10/2016
-->

## Notes about personality surveys
{: #researchSurveys}

When it developed the {{site.data.keyword.personalityinsightsshort}} service, {{site.data.keyword.IBM_notm}} relied on personality surveys to establish ground-truth data for personality inference. Ground truth refers to the factual data obtained through direct observation rather than through inference. A typical measure of accuracy for any machine-learning model is to compare the scores that are inferred by the model with ground-truth data. The previous sections describe how {{site.data.keyword.IBM_notm}} used surveys to validate the accuracy of the service.

The following notes clarify the use of personality surveys and survey-based personality estimation:

-   Personality surveys are long and time-consuming to complete. Survey results are constrained by the number of Twitter users who were willing and available to participate in {{site.data.keyword.IBM_notm}}'s study. {{site.data.keyword.IBM_notm}} plans to conduct validation studies with more users, as well as with users of other online media such as email, blogs, and forums.
-   Survey-based personality estimation is based on self-reporting, which might not always be a true reflection of one's personality: Some users might give noisy answers to such surveys. To reduce the noise, {{site.data.keyword.IBM_notm}} filtered survey responses by including attention-checking questions and by discarding surveys that were completed too quickly.
-   While the correlation between inferred and survey-based scores is both positive and significant, the results imply that inferred scores might not always correlate with survey-based results. Researchers from outside of {{site.data.keyword.IBM_notm}} also conducted experiments to compare how well inferred scores match scores obtained from surveys, and none reported a fully consistent match:
    -   [Golbeck and others (2011)](/docs/personality-insights?topic=personality-insights-references#golbeck2011) reported an error rate of 10 to 18 percent for inferred scores matched with survey-based scores.
    -   [Sumner and others (2012)](/docs/personality-insights?topic=personality-insights-references#sumner2012) reported approximately 65-percent accuracy for personality prediction.
    -   [Mairesse and Walker (2006)](/docs/personality-insights?topic=personality-insights-references#mairesse2006) reported 60- to 70-percent accuracy for Big Five personality prediction.

In general, it is widely accepted in research literature that self-reported scores from personality surveys do not always fully match scores that are inferred from text. What is more important, however, is that {{site.data.keyword.IBM_notm}} found that characteristics that are inferred from text can often reliably predict real-world behavior.
