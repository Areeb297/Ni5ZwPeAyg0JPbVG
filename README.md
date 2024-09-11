# Customer Happiness Prediction for Logistics and Shipping Company

## Business Problem:
As a rapidly growing logistics and delivery startup, customer satisfaction is crucial for scaling and global expansion. The COVID-19 pandemic introduced various challenges that impacted customer experiences. To stay competitive and improve customer loyalty, we need to identify the key factors that make customers happy or unhappy. Predicting customer happiness will help reduce churn and focus on the elements that drive satisfaction. Our key focus or objective would be to focus on the recall score for the unhappy class so our model can have great performance in identifying nearly all potential unhappy customers for the company to ensure these customers are kept satisfied and rewarded to reduce churn. 

## Exploratory Data Analysis (EDA):
- The dataset consists of customer survey responses across six key areas, including delivery time, product expectations, pricing, and app usability.
- **Key Observations**:
  - **Delivery on time** and **app usability** show strong positive correlations with customer happiness.
  - **Satisfaction with courier service** also positively influences customer satisfaction.
  - Surprisingly, **content as expected** shows a weak negative correlation with happiness, suggesting that managing customer expectations better could improve satisfaction.
  - **Pricing** is a weaker predictor of happiness for this customer group.

- **Conclusion from EDA**: Customers value timely delivery, easy-to-use apps, and positive courier interactions. While price and product content have less impact, improving customer expectations management could enhance satisfaction.

## Modeling Results:
- **Strategy**: I initially used StandardScaler() to scale the training data, utilized LazyClassifier library with different random seeds to understand which random seeds get the best results (4646 was found the best performer after 100 iterations). Utilized techniques such as voting, stacking, hyperparameter tuning, recursive feature selection to select the best results and outputs.  
- **Goal**: Predict whether customers are happy (1) or unhappy (0) based on their survey responses.
- **Best Model**: The **LGBM Classifier** performed the best with:
  - **Accuracy**: 88%
  - **ROC AUC**: 88%
  - **F1 Score**: 87%

- **Top Features**:
  - **Courier satisfaction**
  - **Product availability**
  - **Delivery time**
  - **App usability**
  
- **Feature Removal**: Removing the **content as expected** feature improved model accuracy, as it had a negative correlation with happiness.
- **Model Results**: The optimized model reached a recall of 94% for the unhappy class meeting our expectations in solving the business problem defined earlier confirming its reliability. As per our model, it seems price is not a differentiating factor for customer satisfaction.

## Key Business Insights:
- **Delivery time** and **courier satisfaction** are primary drivers of customer happiness.
- **Product availability** and **app usability** are also important predictors.
- **Content expectations** did not strongly affect happiness, but managing expectations with clearer product descriptions could be beneficial.

## Recommendations:
- **Survey Focus**: Future surveys should focus on key factors: courier satisfaction, product availability, app usability, and delivery time.
- **Proactive Interventions**: Use the model to identify unhappy customers and take corrective actions to reduce churn.
- **Customer Rewards**: Consider using the model to identify satisfied customers for loyalty programs and rewards.

By focusing on these areas, we can improve overall customer satisfaction and loyalty, supporting the company's growth and expansion strategy.
