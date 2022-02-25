# Written Description

## Abstract
I created a classifier model that predicts the success or failure of an attempted terror attack anywhere in the world with an ROC-AUC score of 97% on unseen data. I also created a model using U.S. data only that performed almost as well, with an ROC-AUC score of 96%. The three features most important to the U.S. model were property, longitude, and the nationality of the victim(s). Attacks on the West Coast have a very high success rate, and attacks on non-US victims in the US (at places like embassies) have a lower success rate than attacks on U.S. citizens. Attacks intended to cause destruction to property, such as firebombing (but not actual bombings) are very likely to succeed.

## Components
### Design

My client is the U.S. government. They are interested in preventing terrorist attacks at the local level, and they want to know if it's possible to predict the success or failure of terrorist attacks based on certain features. I built a gradient boost classification model to predict success or failure of a terror attack attempt, learned which features were important to the model, and performed EDA to draw my conclusions.

#### Success Metrics
Since 2005, terror attacks in the U.S. succeed at a rate of 87%, while the average success rate for G7 countries (as well as Western Europe and North America together) during that time is 73%. Any policy developed as a result of these findings should lower the US percentage and hopefully fall below the G7 mean percentage.

I used ROC-AUC as my guiding metric, in order to make sure my model predicts failed attacks (the much smaller class) successfully.

#### Risks and Assumptions
* My results don't involve intelligence efforts to stop terror before it's attempted
* It could possibly be the case that improved intelligence efforts would *raise* the terror success rate, if the attacks that do escape detection tend to be better planned
* My results don't involve lowering the number of attacks, only stopping attempted attacks

### Data
I used data from the Global Terrorism Database from the University of Maryland, which logs all terror attacks recorded since the 1970s globally (hundreds of thousands of rows). I also used global data on police numbers, GDP, and population. There are over a hundred features, including location data, attack type, and data on the victims and perpetrators. The target is binary - success/failure of an attempted attack.

### Tools
* XGBoost Classifier from sklearn for predictive model
* Python, pandas, and numpy for exploratory data analysis
* Visualizations using matplotlib

### Communication
* 5 minute slide presentation to client (US government) with recommendations
* This description / abstract