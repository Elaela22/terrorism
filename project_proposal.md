# Project Proposal
## Predicting Successful Terror Attacks
### Question/need:
* *What is the framing question of your analysis, or the purpose of the model/system you plan to build?*

My client is the US government. They are interested in preventing terrorist attacks at the local level, and they want to know more about the characteristics of successful and failed attempted attacks, using global data.

I propose building a classification model (currently, gradient boost performs best) to find out which features may cause an attempted attack to succeed or fail. The government can use this information to make policy changes and ultimately decrease the percentage of attacks that are successful (89% from 2008-2017).

* *Who benefits from exploring this question or building this model/system?*

The US government benefits from understanding what features most successfully predict a failed or successful attack, since one of the primary purposes of a federal government is homeland security. Ultimately, US citizens will benefit from fewer successful attacks, if policy changes are successful. 

-------

### Data description:
* *What dataset(s) do you plan to use, and how will you obtain the data?*

I have downloaded a dataset from the [Global Terrorism Database](https://www.start.umd.edu/gtd/):

> Managed by the National Consortium for the Study of Terrorism and Responses to Terrorism (START), the Global Terrorism Database™ includes more than 200,000 terrorist attacks dating back to 1970.

They have an explanatory pdf on their methods and feature descriptions [here](https://start.umd.edu/gtd/downloads/Codebook.pdf). They have comprehensive data on all attacks since 1970, but I plan to only use data after 2008 (or possibly even later) to keep my analysis relevant to current technology and procedures, especially since data collection methods changed noticeably in 2008.

I also plan to experiment with merging other data sources to better understand what factors play into successful protection against attacks, such as size of police force per capita, GDP, spending on public safety, etc.

* *What is an individual sample/unit of analysis in this project? What characteristics/features do you expect to work with?*

The unit of analysis is an attempted terror attack. I expect to work with the features included in my main dataset and possibly additional features from other datasets. Features will include location information, type of attack, weapons used, suicide/not suicide, the criteria that classified it as a terrorist attack in the first place, etc. I will investigate extra features involving each country's approach to law and order as well.

One key note is that this dataset doesn't have anything to do with attacks that were prevented from execution in advance through intelligence, so my findings will not have any relevance to the intelligence community - only on attacks that have made it to the *execution* stage. Attack failures may also be caused by the failure of the terrorists' methods themselves, like a bomb failing to go off, rather than anything the host country may or may not have done to prevent the attack.

This is also an imbalanced dataset, with most terrorist attacks succeeding (around 88%) so I'll need to make sure I account for that imbalance when evaluating models.

* *If modeling, what will you predict as your target?*

I will predict the success/failure of a terrorist attack. The dataset I'm using describes success in this way:

> *Success of a terrorist strike is defined according to the tangible effects of the attack. Success is
> not judged in terms of the larger goals of the perpetrators. For example, a bomb that exploded
> in a building would be counted as a success even if it did not succeed in bringing the building
> down or inducing government repression.*

-------

### Tools:
*How do you intend to meet the tools requirement of the project?*

* I'll use scikit-learn to build a classification model (have already tested knn, logistic regression, and gradient boost)
* Visualization tools may include matplotlib, seaborn, Plotly
* Python, pandas, numpy for data exploration and cleaning

*Are you planning in advance to need or use additional tools beyond those required?*

No, just potentially additional datasets.

-------

### MVP goal:
* *What would a minimum viable product (MVP) look like for this project?*

A minimum viable product would consist of an evaluation metric from a classification algorithm with a visualization of feature importance.
