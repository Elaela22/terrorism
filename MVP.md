# MVP
## Predicting Failed Terrorist Attacks

### Background
My client is the US government. They are interested in preventing terrorist attacks at the local level, and they want to know if it's possible to predict the success or failure of terrorist attacks based on certain features.

I've built a gradient boost classification model to find out which features may cause an attempted attack to succeed or fail.

### Impact hypothesis
By creating a model that can predict the success or failure of different types of terror attacks, the U.S. government can prioritize which types of attacks (that make it past the execution stage) to devote the most resources towards thwarting.

### Success metrics
Currently, terror attacks in the U.S. succeed at a rate of 88.9%, while the average success rate for G7 countries (as well as Western Europe and North America together) is 77.5%. Any policy developed as a result of these findings should lower the US percentage and hopefully fall below the G7 mean percentage.

The classes in my dataset are imbalanced, since terror attacks (if they reach the point of execution) are so much more likely to succeed than fail. However, there is enough data that special class balancing techniques aren't necessary.

I'm using ROC-AUC as my guiding metric to make sure I don't ignore the importance of correctly identifying true negatives, which are harder to predict.

### Data
I'm using data from the Global Terrorism Database, as well as global data on police numbers, GDP, and population. There are hundreds of thousands of terrorist incidents logged here, and I'm using only those logged since 2009 due to a change in 2008 in how attacks were recorded.

### Exploratory findings
#### Predictive model metrics
The success or failure of terrorist attacks can be predicted with an ROC-AUC of 0.969.

Precision: 98%
Recall: 98%

Failed terrorist attacks are identified successfully 86% of the time.

#### Feature importance
The following features are the five most important to predictive success in the model (this does not necessarily give information on *why* each feature is important):

1. Country
2. Specificity (this involves the logged location - the chances of a failed attack are highest if the event did not occur in city/village/town)
3. Logged doubt as to whether it qualifies as a terror attack
4. Region
5. Number of police in the country per 100k population

Interestingly, the following are *not* very important to the model:

1. Type of attack
2. Group responsible for the attack
3. The target

#### Visualizations:

Feature importance:

![](https://raw.githubusercontent.com/Elaela22/terrorism/main/terror_feature_imptce.png)

Characteristics of failed terror attacks in U.S.:

![](https://raw.githubusercontent.com/Elaela22/terrorism/main/failed_terror_bar.png)

### Recommendation
My gradient boost model is very predictive, but not easily interpretable. I recommend the following:

1. No need to increase #s of police in the U.S. Globally, having a sufficient police force is very predictive for thwarting terror attacks, but the US is already past the threshold of sufficient numbers, and there's no evidence more would help us.
2. Use the created gradient boost model to look at different scenarios and prioritize different situations (i.e. feature interactions) accordingly
2. Most terror attacks in the U.S. are thwarted because someone noticed an explosive. Educate the public on suspicious things to look for, especially in these places:
 * Highly trafficked areas, like public transit in major cities
 * Churches, synagogues, temples, and mosques
 * Government buildings, like courthouses
 * Planned Parenthoods