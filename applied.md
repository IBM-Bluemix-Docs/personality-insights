---

copyright:
  years: 2015, 2017
lastupdated: "2017-10-12"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}
{:pre: .pre}
{:codeblock: .codeblock}
{:screen: .screen}
{:javascript: .ph data-hd-programlang='javascript'}
{:java: .ph data-hd-programlang='java'}
{:python: .ph data-hd-programlang='python'}
{:swift: .ph data-hd-programlang='swift'}

# The service in action
{: #applied}

{{site.data.keyword.IBM_notm}} and other researchers have validated many hypotheses that are related to real-world applications of personality characteristics. These studies have helped to drive development of the {{site.data.keyword.personalityinsightsshort}} service. Their findings provide insight into some of the many ways that you can apply the service to your business and communications goals. For more information about the research that underlies the {{site.data.keyword.personalityinsightsshort}} service, see [The science behind the service](/docs/services/personality-insights/science.html).
{: shortdesc}

## Studies by IBM researchers
{: #appliedIBM}

The following studies conducted by {{site.data.keyword.IBM_notm}} researchers indicate that applying the results of the service can yield tangible results in multiple domains. The studies contributed directly to the development of the service. The table includes links to sections with more information about each study.

<table>
  <caption>Table 3. Studies by IBM</caption>
  <tr>
    <th style="text-align:left; width:25%">Study</th>
    <th style="text-align:center; width:25%">Subjects</th>
    <th style="text-align:left; width:50%">Effect of personality
    characteristics</th>
  </tr>
  <tr>
    <td>
      <a href="#IBMrespond"><strong>Responding to tweets</strong></a>
      <br/>(information collection)
    </td>
    <td style="text-align:center">2000 Twitter users</td>
    <td>
      <strong>More likely to respond:</strong> Score high on Big Five dimensions
      and facets excitement-seeking, friendliness, activity level,
      gregariousness, trust, morality, extraversion, and
      agreeableness<br/><br/>
      <strong>Less likely to respond:</strong> Score high on Big Five facets
      cautiousness and anxiety
    </td>
  </tr>
  <tr>
    <td>
      <a href="#IBMretweet"><strong>Re-tweeting</strong></a>
      <br/>(information spreading)
    </td>
    <td style="text-align:center">3500 Twitter users</td>
    <td>
      <strong>More likely to re-tweet:</strong> Score high on Big Five
      dimensions and facets modesty, openness, and friendliness
    </td>
  </tr>
  <tr>
    <td>
      <a href="#IBMtarget"><strong>Targeted advertising</strong></a>
      <br/>(unsolicited advertising)
    </td>
    <td style="text-align:center">More than 6000 Twitter users
    </td>
    <td>
      <strong>Respond more favorably:</strong> Score high on Big Five dimension
      openness, and score low on Big Five dimension emotional range
    </td>
  </tr>
  <tr>
    <td>
      <a href="#IBMcampaign"><strong>Marketing campaigns</strong></a>
      <br/>(coupon redemption)
    </td>
    <td style="text-align:center">Thousands of retail customers</td>
    <td>
      <strong>More likely to respond:</strong> Score high on Big Five facets
      orderliness, self-discipline, and cautiousness, and score low
      on Big Five facet immoderation
    </td>
  </tr>
  <tr>
    <td>
      <a href="#IBMbrand"><strong>Brand preference</strong></a>
      <br/>(brand affinity)
    </td>
    <td style="text-align:center">600 Twitter users</td>
    <td>
      <strong>Predictors of brand preference:</strong> Big Five dimensions
      and facets conscientiousness, conservation, self-enhancement,
      and agreeableness; Needs love and ideal; and Value hedonism
    </td>
  </tr>
  <tr>
    <td>
      <a href="#IBMmember"><strong>Member satisfaction</strong></a>
      <br/>(community fulfillment)
    </td>
    <td style="text-align:center">More than 3000 community members</td>
    <td>
      <strong>Predictors of member satisfaction:</strong> Characteristics such
      as anger, anxiety, work, leisure, inhibition, assent, and use of the
      first-person pronoun
    </td>
  </tr>
  <tr>
    <td>
      <a href="#IBMreading"><strong>Reading preference</strong></a>
      <br/>(content interest)
    </td>
    <td style="text-align:center">More than 200 participants</td>
    <td>
      <strong>Interest in environmental articles:</strong> Score high on Value
      self-transcendence<br/><br/>
      <strong>Interest in work-related articles:</strong> Score high on Value
      self-enhancement
    </td>
  </tr>
  <tr>
    <td>
      <a href="#IBMpreferences"><strong>Predicting consumption
      preferences</strong></a><br/>(consumer purchasing)
    </td>
    <td style="text-align:center">Hundreds of thousands of data records</td>
    <td>
      <strong>Predicting consumer preferences:</strong> Demographic data and
      personality characteristics
    </td>
  </tr>
</table>

### Responding to tweets
{: #IBMrespond}

{{site.data.keyword.IBM_notm}} found that people with specific personality characteristics respond more readily to information-collection tasks. {{site.data.keyword.IBM_notm}} recently conducted a study of more than 2000 Twitter users to understand the factors that influence the likelihood to respond to such tasks and to develop models to predict responses to questions ([Mahmud et al., 2013](/docs/services/personality-insights/references.html#mahmud2013), and [Mahmud et al., 2014](/docs/services/personality-insights/references.html#mahmud2014)).

{{site.data.keyword.IBM_notm}} trained the model that was used in the study from two question-and-answer data sets in which Twitter users were asked either location-based or product-related questions. The questions depended on whether the users reported being present at a location or owning a product. As features in the prediction model, {{site.data.keyword.IBM_notm}} included social behavior (for example, past response rate and tweeting activity), readiness (for example, how long the user is inactive), category features of the Linguistic Inquiry and Word Count (LIWC) psycholinguistics dictionary, and Big Five dimensions and facets.

{{site.data.keyword.IBM_notm}} found a set of Big Five personality characteristics that are significant in predicting the likelihood to respond. Specifically, {{site.data.keyword.IBM_notm}} found that people who score high on the dimensions and facets excitement-seeking, friendliness, activity level, gregariousness, trust, morality, extraversion, and agreeableness are more likely to respond to tweets. Alternatively, people who score high on the facets cautiousness and anxiety are less likely to respond. These results were found to be statistically significant (p-value &lt; 0.05).

### Re-tweeting
{: #IBMretweet}

Similarly, {{site.data.keyword.IBM_notm}} also found that people with specific personality characteristics respond in greater numbers to information-spreading tasks. {{site.data.keyword.IBM_notm}} recently conducted another study among more than 3500 Twitter users to understand the factors that increase the likelihood to re-tweet information and to develop models to predict re-tweeting behavior ([Lee et al., 2014](/docs/services/personality-insights/references.html#lee2014)).

As features in the model that was used in the study, {{site.data.keyword.IBM_notm}} included past social media activity, social media profile information, readiness, the LIWC dictionary, and Big Five dimensions and facets. The study found that a set of Big Five characteristics is significant in predicting the tendency to re-tweet. For example, the results indicate that people who score high on the dimensions and facets modesty, openness, and friendliness are more likely to spread information. The findings were statistically significant (p-value &lt; 0.05).

### Targeted advertising
{: #IBMtarget}

{{site.data.keyword.IBM_notm}} found that people with specific personality characteristics respond more favorably to targeted advertising. Recently, {{site.data.keyword.IBM_notm}} created a Twitter-based travel information service to test the hypothesis that certain Twitter users would respond more favorably to unsolicited advertisements from the service. The hypothesis predicted that such users would be more likely to click a link for an advertisement or to follow an account. {{site.data.keyword.IBM_notm}} conducted two studies based on this use case and the hypothesized effects of personality ([Chen et al., 2015](/docs/services/personality-insights/references.html#chen2015)).

In a survey study, {{site.data.keyword.IBM_notm}} asked 133 Twitter users to report their likely response to a tweet that advertises a travel information service. {{site.data.keyword.IBM_notm}} then used traditional questionnaires to measure the users personalities. In a field study, {{site.data.keyword.IBM_notm}} sent tweets advertising the service to more than 5900 traveling Twitter users. {{site.data.keyword.IBM_notm}} then used the {{site.data.keyword.personalityinsightsshort}} service to infer the users' personality characteristics from their past tweets.

The two studies yielded consistent results: People who score high on the dimension openness and low on the dimension emotional range (neuroticism) indeed respond more favorably to the advertisement. These findings are true despite the different approaches that were used by the studies to obtain the users' personality characteristics. Targeting the top 10 percent of users with high openness and low emotional range increased click rate from 6.8 to 11.3 percent and follow rate from 4.7 to 8.8 percent. The results were statistically significant (p-value &lt; 0.05).

### Marketing campaigns
{: #IBMcampaign}

{{site.data.keyword.IBM_notm}} recently worked with a large retailer to infer characteristics for thousands of its customers who are involved in marketing campaigns. The retailer sent coupons to its customers. A positive response was defined as redeeming any coupon. According to psychology theory, people who score high on the Big Five facets orderliness, self-discipline, and cautiousness and low on the facet immoderation are more likely to redeem coupons.

{{site.data.keyword.IBM_notm}} validated the hypothesis by using customer data and inferred personality characteristics. {{site.data.keyword.IBM_notm}} first segmented the customer population into quartiles based on individual personality characteristics. Using normalized percentile scores for the characteristics (with a scale of 1 to 100), {{site.data.keyword.IBM_notm}} used linear combination to compute a combined score for each customer:

*Orderliness + Self-Discipline + Cautiousness + (100 - Immoderation)*

{{site.data.keyword.IBM_notm}} then compared results for the customers in the highest quartile with those in the lowest quartile, ignoring the middle half of the population. The study found that people with the hypothesized characteristics are 40 percent more likely to respond to coupons than are people from the random population.

### Brand preference
{: #IBMbrand}

{{site.data.keyword.IBM_notm}} conducted a study of more than 600 Twitter users to understand whether Big Five, Values, and Needs personality characteristics can predict users' preferences for different brands (whether they like or dislike a brand). The study evaluated 22 brands from six categories: luxury cars, beverages, fast food, retail, shampoos, and smartphones. {{site.data.keyword.IBM_notm}} established ground truth for brand preference by conducting a survey among the users.

The study found that personality characteristics can predict brand preference with 65-percent accuracy. Specifically, the study found that the Big Five dimensions and facets conscientiousness, conservation, self-enhancement, and agreeableness, the Needs love and ideal, and the Value hedonism are among the characteristics most likely to predict brand preference.

### Member satisfaction
{: #IBMmember}

{{site.data.keyword.IBM_notm}} conducted a study among its employees who are members of online workplace communities to investigate whether the language they use in the communities is related to their level of satisfaction with the communities ([Matthews et al., 2015](/docs/services/personality-insights/references.html#matthews2015)). {{site.data.keyword.IBM_notm}} measured community satisfaction by self-reported surveys. {{site.data.keyword.IBM_notm}} examined 142 workplace communities; depending on community size, {{site.data.keyword.IBM_notm}} surveyed 20 to 26 members of each community.

The study found that language use in the communities, as measured by the LIWC dictionary, correlates with member satisfaction. Specifically, the study found that LIWC categories such as anger, anxiety, work, leisure, inhibition, assent, and first-person pronoun are good predictors of member satisfaction. {{site.data.keyword.IBM_notm}} expects characteristics that are computed from the text in a community to correlate well with member satisfaction for the community.

### Reading preference
{: #IBMreading}

{{site.data.keyword.IBM_notm}} conducted a study to understand the relationship between Values and reading interests ([Hsieh et al., 2014](/docs/services/personality-insights/references.html#hsieh2014)). {{site.data.keyword.IBM_notm}} hypothesized that

1.  People with a higher self-transcendence value will demonstrate an interest in reading articles about the environment.
1.  People with a higher self-enhancement value will show an interest in reading articles about work.
1.  People with a higher hedonism value will evince a stronger interest in content about leisure.

{{site.data.keyword.IBM_notm}} recruited more than 200 participants for the study from the Amazon Mechanical Turk marketplace. Participants completed a Values survey and answered questions about their level of interest in reading different articles.

The study validated the first two hypotheses: Participants with a higher score on the Value self-transcendence demonstrated an interest in reading articles about the environment, and participants with a higher score on the Value self-enhancement showed an interest in reading articles about work. These results were statistically significant (p-value &lt; 0.05).

However, the study observed a weak correlation between the Value hedonism and an interest in reading leisure articles. This weak link might indicate that people do not consider reading a hedonistic activity, no matter the topic of the article.

### Predicting consumption preferences
{: #IBMpreferences}

{{site.data.keyword.IBM_notm}} collaborated with [Acxiom ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://www.acxiom.com/){: new_window} to investigate whether an individual's personality portrait can improve the predictive accuracy of individuals' consumption preferences compared with predictions based solely on demographic attributes. The study examined 133 consumption preferences for about 785,000 individuals in the US. Adding personality insights characteristics to demographics improved the predictive accuracy for 115 preferences (86.5 percent), and for 23 of the preferences, using personality insights alone provides better accuracy than using demographics only.

The study was based on two technologies: The results of the {{site.data.keyword.IBM_notm}} {{site.data.keyword.personalityinsightsshort}} service and the Acxiom InfoBase product, specifically InfoBase Customer Enhancement&trade; data elements. Acxiom is an industry-leading provider of demographic data for clients' marketing needs. Acxiom's demographic data, such as age, gender, income, household size, income range, and so on, can help analyze and enhance customer data to identify selling and retention opportunities, fill gaps in customer contact information, assist in analyzing customer information, and identify prospects, among other things.

The study analyzed 133 behavioral consumption attributes based on 22 {{site.data.keyword.personalityinsightsshort}} characteristics and four demographics categories (gender, education, household income, and age). The results show that 115 of the 133 consumption preferences exhibited better predictive accuracy when demographics were augmented with personality characteristics. Moreover, the lack of improvement on the remaining 18 preferences might be due to the nature of the comparison and how the data were calculated. Future experiments will attempt more complex comparisons to see whether a different approach further improves accuracy.

The overall results reveal that {{site.data.keyword.personalityinsightsshort}} characteristics are useful in predicting various consumption preferences. Using demographics and personality characteristics together usually yields better predictive accuracy. But {{site.data.keyword.personalityinsightsshort}} alone is a good alternative when demographics are not available.

For more information about the study, see <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Improving-Consumption-Preferences-Accuracy.pdf" download="Improving-Consumption-Preferences-Accuracy.pdf">Improving-Consumption-Preferences-Accuracy.pdf <img src="../../icons/launch-glyph.svg" alt="External link icon" title="External link icon" class="style-scope doc-content"></a>. For more information about the consumption preferences model used in the study, see [Liu et al. (2016)](/docs/services/personality-insights/references.html#liu2016).

## Studies by other researchers
{: #appliedOthers}

Many studies conducted by researchers outside of {{site.data.keyword.IBM_notm}} indicate that personality correlates with and can predict various outcomes. The following sections describe these studies, which corroborate and augment the research described in the previous section.

### Consumer preferences
{: #otherConsumer}

-   [Hirsh et al. (2012)](/docs/services/personality-insights/references.html#hirsh2012) surveyed people about various marketing messages. They found that people respond more positively to messages tailored to their personality.
-   [Chen (2011)](/docs/services/personality-insights/references.html#chen2011) found that in the context of online marketing, people with high openness are more intellectually curious and open to new ideas. Such people are therefore more likely to try new things.
-   [Westfall (1962)](/docs/services/personality-insights/references.html#westfall1962) found that personality differences exist between the owners of convertible cars and the owners of standard or compact cars. Consumers who score high in the agreeableness dimension and in the orderliness facet of the conscientiousness dimension prefer traditional cars. Consumers who score high in the openness dimension, on the other hand, might make a convertible car their first choice.
-   [Choo and Mokhtarian (2002)](/docs/services/personality-insights/references.html#choo2002) examined the relationship between choice of vehicle type and factors such as personality, lifestyle, attitude, and demographics. They found that individuals who score high in the facets adventurousness, excitement-seeking, and authority-challenging might prefer powerful performance cars. People who score high in the agreeableness dimension, however, might not like powerful cars.
-   [Kassarjian (1971)](/docs/services/personality-insights/references.html#kassarjian1971) found that car owners typically tend to perceive the types of cars they purchase as extensions of their personality. [Environmental consciousness](#otherEnvironment) describes how an individual's personality can influence their preference for low-emission vehicles.
-   [Myszkowski and Storme (2012)](/docs/services/personality-insights/references.html#myszkowski2012) found that openness significantly predicts individuals' tendency to prefer and respond to well-designed products. Their study suggests that individuals with *low* openness tend to respond more intensely to the appearance of a product, amplifying design-driven product choices. Conversely, individuals with *high* openness tend to focus more on other product aspects, leading them to disregard aesthetic characteristics.
-   [Lin (2002)](/docs/services/personality-insights/references.html#lin2002) and [Sarli and Tat (2011)](/docs/services/personality-insights/references.html#sarli2011) reported that personality characteristics affect one's brand preferences.

### Personal preferences
{: #otherPersonal}

-   [Hu and Pu (2011)](/docs/services/personality-insights/references.html#hu2011) found that in the music domain, recommendations are more successful when they leverage the correlations between people's personality and their music preferences.
-   [Chamorro-Premuzic and Furnham (2007)](/docs/services/personality-insights/references.html#chamorro2007) also reported that individual differences in personality and cognitive ability might determine how people experience music. [Rentfrow and Gosling (2003)](/docs/services/personality-insights/references.html#rentfrow2003) reported similar findings in an earlier study.
-   [Golbeck and Norris (2013)](/docs/services/personality-insights/references.html#golbeck2013) found correlations between personality and movie preferences among Netflix&trade; users.

### Spending habits
{: #otherSpending}

-   [Pirog and Roberts (2007)](/docs/services/personality-insights/references.html#pirog2007) revealed the relationship between spending habits and personality. They focused on the "misuse" (or "abuse") of credit cards among college students. They found that students who score high in conscientiousness tend to use debit cards or cash and tend not to abuse credit cards. Conversely, high neuroticism (emotional range) is likely to be associated with excessive use of credit cards.

### Risk profiles
{: #otherRisk}

-   [Lauriola and Levin (2001)](/docs/services/personality-insights/references.html#lauriola2001) showed that personality influences individuals' risky decision-making in financial investments. They concluded that people who score high on openness to experiences tend to make risky investments. Meanwhile, neuroticism (emotional range) might make people less willing to take such risks.
-   [Nicholson et al. (2001)](/docs/services/personality-insights/references.html#nicholson2001) further developed the correlation between Big Five characteristics and risk profiles. Their findings reveal that agreeableness and conscientiousness lower people's willingness to take risks in general. In contrast, individuals who score high in extraversion are more likely to make risky decisions.
-   [Tok (2011)](/docs/services/personality-insights/references.html#tok2011) identified the relationship between Big Five personality characteristics and participation in risky adventure sports such as skiing, mountain biking, flying, gliding, parasailing, and scuba diving. Four of the Big Five characteristics directly influence participation in risky sports: High scores in extraversion, openness, and neuroticism (emotional range) increase the probability of participation in these sports; a high score in conscientious reduces the willingness to participate.
-   [Hymbaugh and Garrett (1974)](/docs/services/personality-insights/references.html#hymbaugh1974) studied skydivers' personality characteristics. They found that skydivers typically have higher excitement-seeking and adventurousness than the general population.

### Professional performance
{: #otherProfessional}

-  [Barrick and Mount (1991)](/docs/services/personality-insights/references.html#barrick1991) explored the relationship of Big Five personality dimensions to job performance. They found that personality dimensions such as conscientiousness are related to job performance for all job groups they studied (professional, managers, sales, police, skilled, and semi-skilled).
-   [Hurtz and Donovan (2000)](/docs/services/personality-insights/references.html#hurtz2000) reported that conscientiousness is the personality characteristic that is most predictive of job performance.
-   [Lim and Ployhart (2004)](/docs/services/personality-insights/references.html#lim2004) found that extraversion is positively correlated with leadership abilities.
-   [Judge et al. (2002)](/docs/services/personality-insights/references.html#judge2002) reported that extraverted individuals are more satisfied in the workplace; work gives them an opportunity to experience an optimal level of arousal. Conversely, introverted individuals are less satisfied in the workplace due to too much stimulation.
-   [van Vianen et al. (2012)](/docs/services/personality-insights/references.html#vanvianen2012) reported individual differences in adaptability and its causes, correlates, and consequences. They found that conscientiousness, extraversion, and openness correlate positively with career adaptability.

### Academic performance
{: #otherAcademic}

-   [Chamorro-Premuzic and Furnham (2003)](/docs/services/personality-insights/references.html#chamorro2003) reported a longitudinal study in which they found that personality characteristics impact academic performance. Specifically, they found that neuroticism (emotional range) might impair academic performance and that conscientiousness might lead to higher academic achievement.
-   [Komarraju and Karau (2005)](/docs/services/personality-insights/references.html#komarraju2005) found that some personality characteristics impact an individual's behavior with respect to self-improvement learning. The study reveals that high openness and conscientiousness often lead to a greater interest in self-improvement learning and that high neuroticism (emotional range) decreases the motivation for such learning.

### Professional relationships
{: #otherProRelations}

-   [Flynn and Smith (2007)](/docs/services/personality-insights/references.html#flynn2007) found that personality influences interaction preferences between professionals and customers. For example, patients with a high degree of conscientiousness and openness prefer to be actively involved in deciding the course of treatment. Patients with high levels of agreeableness or emotional range (neuroticism) prefer doctors to take the lead in making important health decisions.
-   [Duberstein et al. (2007)](/docs/services/personality-insights/references.html#duberstein2007) similarly reported that physician's personalities affected the satisfaction level of their patients. For example, patients reported being more satisfied with physicians who score relatively high in openness and average in conscientiousness.

### Personal relationships
{: #otherPerRelations}

-   [Botwin et al. (1997)](/docs/services/personality-insights/references.html#botwin1997) found that personality affects romantic relationships. The personality characteristics of one's partner significantly predict marital dissatisfaction, most notably when the partner scores lower on agreeableness, emotional range, and openness than desired.

### Health
{: #otherHealth}

-   [Turiano et al. (2012)](/docs/services/personality-insights/references.html#turiano2012) reported a longitudinal study over a 10-year time span in which they found that Big Five characteristics predicted health-related outcomes. For example, all of the characteristics except for openness predicted self-rated physical health, and all of the characteristics except for agreeableness predicted number of work days limited due to physical health.
-   [Masui et al. (2006)](/docs/services/personality-insights/references.html#masui2006) found that high scores in the specific personality characteristics conscientiousness, extraversion, and openness are associated with longevity. Other researchers have also uncovered a relationship between Big Five personality characteristics and life expectancy.
-   [Roberts et al. (2007)](/docs/services/personality-insights/references.html#roberts2007) reported that specific personality characteristics predict important life outcomes, such as mortality, divorce, and success at work.

### Diet and exercise
{: #otherDiet}

-   [Shepherd and Sparks (1994)](/docs/services/personality-insights/references.html#shepherd1994) developed the relationship between personality and food choice. Their study reveals that people with high scores in emotional range (neuroticism), especially in the facet immoderation, tend to consume high-fat food.
-   [Elfhag and Morey (2008)](/docs/services/personality-insights/references.html#elfhag2008) revealed that conscientiousness is positively related to a preference for low-fat food. Specifically, the self-discipline and dutifulness facets of the conscientiousness dimension positively influence the consumption of low-fat food and (because weight management is closely related to food choice) regular weight control.
-   [Heaven at al. (2001)](/docs/services/personality-insights/references.html#heaven2001) reported that consumption of health food is related to two Big Five dimensions. People with high neuroticism (emotional range) are usually less likely to choose healthy food, while people with high conscientiousness prefer healthy food. The paper also cites several facets that subtly relate to food choice: artistic interests (from the openness dimension) and self-discipline (from the conscientiousness dimension) correlate positively to greater consumption of health food; conversely, being susceptible to stress has a somewhat negative correlation with health-food consumption.
-   [Lusk (2012)](/docs/services/personality-insights/references.html#lusk2012) found that food lovers score high in openness to experience. Openness might motivate people to try different foods and help them to become food connoisseurs.
-   [Courneya and Hellsten (1998)](/docs/services/personality-insights/references.html#courneya1998) found that personality influences an individual's tendency to pursue habits associated with a healthy lifestyle, including physical exercise. Extraversion and conscientiousness correlate positively with more frequent physical exercise, while neuroticism (emotional range) might negatively influence the frequency of exercise.

### Dining out
{: #otherDining}

-   [Kim et al. (2010)](/docs/services/personality-insights/references.html#kim2010) proved that openness to experience correlates positively with more frequent dining out. People who score low in openness usually dine out less often.
-   [van Trijp and Steenkamp (1992)](/docs/services/personality-insights/references.html#vantrijp1992) found that dining out correlates with the excitement-seeking (sensation-seeking) facet of the extraversion dimension.

### Environmental consciousness
{: #otherEnvironment}

-   [Griskevicius et al. (2010)](/docs/services/personality-insights/references.html#griskevicius2010) found that a person's personality influences their interest in environmental concerns. They studied the relationship between personality and pro-environmental behavior such as using low-emission vehicles and pursuing green living, gardening, recycling, and so on. For most people, higher levels of agreeableness, openness, and conscientiousness are associated with a greater inclination for pro-environmental behavior.
-   [Fraj and Martinez (2006)](/docs/services/personality-insights/references.html#fraj2006) found that personality influences the decision to buy environmentally conscious products. People characterized by personality features such as extraversion, agreeableness, and conscientiousness are more likely to purchase such products.

### Community service
{: #otherCommunity}

-   [Penner et al. (2005)](/docs/services/personality-insights/references.html#penner2005) reported that an individual's personality affects their engagement in community service. In a review paper, the authors summarized several personality factors that influence prosocial behavior. They found that extraversion and agreeableness have positive influences on engaging in community service. In particular, the altruism and cooperation facets of the agreeableness dimension might have the most impact, while the gregariousness facet of the extraversion dimension has a more subtle positive correlation to community service.

### Religion and spirituality
{: #otherReligion}

-   [Adorno et al. (1950)](/docs/services/personality-insights/references.html#adorno1950), in their classic book *The Authoritarian Personality*, report a possible correlation between personality characteristics and religion. They suggest that people who score high in agreeableness are more religious, while those who score high in authority-challenging are less motivated to participate in religious and spiritual practices.
