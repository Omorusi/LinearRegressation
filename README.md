
## Machine Learning Project Overview
This project focuses on analysing basketball statistics, specifically the three-point shooting performance across various seasons. The main goal is to compute total three-point field goals made (3P) and attempted (3PA), and to analyse trends over seasons using linear regression.

## My Google Colab file
[Google Colab Notebook](https://colab.research.google.com/drive/123rW-SODe6pG0OVNj94U65Y41_V2htZn#scrollTo=_5-6eLLLxAOO)

### Technologies Used
- **Python**: The primary programming language for data processing.
- **Pandas**: For data manipulation and handling CSV files.
- **Numpy**: For performing numerical operations.
- **Matplotlib**: For visualising data through plots.
- **Scikit-learn**: To implement linear regression analysis to identify trends in shooting performance.

## Project Summary
This project utilises data collected from Basketball Reference, covering the last 24 seasons of professional basketball. The analysis focuses on three-point field goals (3P) made and attempted (3PA), aiming to identify trends in shooting performance and the increasing significance of three-point shooting in basketball. Preliminary findings suggest a substantial growth in three-point attempts and makes, indicating a shift in offensive strategy. By employing data processing techniques and linear regression, this project aims to contribute valuable insights into how the game of basketball has evolved over the years.

## Data Collected
The dataset for this project comes from Basketball Reference [Basketball Reference](https://www.basketball-reference.com/), covering 24 seasons of basketball statistics focused on three-point field goals (3P and 3PA). This extensive timeframe allows for analysis of trends in the growing importance of three-point shooting in influencing game strategies.

## Data Pre-Processing
Critical data pre-processing steps were undertaken, including cleaning missing data, formatting columns to numeric types, removing invalid records, and potentially normalising data ranges. These steps ensure the dataset is accurate and reliable for analysis.

## Data Analysis Insights
The analysis reveals a clear trend of increasing three-point attempts and makes, reflecting a shift in basketball strategies where teams prioritise three-point shooting. This trend illustrates the competitive advantage of effective long-range shooting, reinforcing its role as a cornerstone of modern basketball.

## Algorithms
A Linear Regression model was used to analyse the relationship between seasons and total three-point field goals made. This algorithm effectively identifies trends over time, with the slope indicating the rate of increase in three-point shots made per season. Visualisation tools like Matplotlib were employed to create plots for better interpretation of the data.
## Visualitasion of the one of the dataset (20-21)

![image](https://github.com/user-attachments/assets/96bd0d58-0670-4761-aa23-6e5ef17e329a)

This a representaion of one of the dataset which shows the 3 points made and 3 points attemps from all the nba player during that season

## Visualisation of the last 24 years 3 Point Attemps growing in the NBA

![progression during the year 3 p](https://github.com/user-attachments/assets/6c2cda38-1229-4e75-97a9-9d45b2be2f4b)

This graph shows the growing from the last 24 years that 3 points have made a good impact on teams as they play more to shots more shoots as they value of 3 points is greater than 2 points.

### Challenges Encountered
Throughout this project, several challenges have emerged, including:

- **Data Quality Issues**: Encountering missing or inconsistent data entries has required meticulous cleaning to ensure the accuracy of the analysis.
- **Complexity in Data Manipulation**: Handling various data formats and ensuring all entries were properly normalized posed a challenge during pre-processing.
- **Algorithm Selection**: Deciding on the most appropriate machine learning algorithm required a deeper understanding of their respective advantages and limitations, leading to some trial and error.
- **Ordering the Dates**: On the Y-axis of the graph, the values are not ordered from smallest to largest, as I am using the names of the files to represent them on the Y-axis.
For the Ordering the Dates I used :
## Problem with the seasons 

![image](https://github.com/user-attachments/assets/a920e10b-bc6c-467a-bff5-818c690ac964)

 # Extract the season number from the filename (assuming it is of the format "0-1.csv")
    season = file.split('/')[-1].split('.')[0]  # Get the filename without path and extension
    csv_data['Season'] = season  # Add the season column

### Additional Resources
- [Scikit-learn Documentation](https://scikit-learn.org/stable/documentation.html) - Comprehensive guide for implementing machine learning algorithms.
- [Pandas Documentation](https://pandas.pydata.org/pandas-docs/stable/) - Official documentation for data manipulation with Pandas.
- [Matplotlib Documentation](https://matplotlib.org/stable/contents.html) - Documentation for data visualization with Matplotlib.

## Prediction Model

Mean Absolute Error (MAE): 10398.16
Root Mean Squared Error (RMSE): 22423.59
R² Score: 0.41

The model's predictions are off by an average of about 10,398 attempts (MAE), with typical errors around 22,423 attempts (RMSE). It explains only 41% of the variance (R²), meaning it doesn't fully capture the relationship between seasons and three-point attempts. This suggests room for improvement with more features or a better model.

### Python Code for Linear Regression
```python
# Prepare the data for linear regression
X = totals_df['Season_Num'].values.reshape(-1, 1)  # Predictor variable (Seasons as 0-1, 1-2, etc.)
y = totals_df['Total 3P'].values  # Response variable (Total 3P)

# Create a linear regression model
X = totals_df['Season_Num'].values.reshape(-1, 1)  # Predictor variable (Seasons as 0-1, 1-2, etc.)
y = totals_df['Total 3P'].values  # Response variable (Total 3P)

# Create a linear regression model
model = LinearRegression()
model.fit(X, y)

# Predict values
y_pred = model.predict(X)

# Print the linear regression coefficients
print(f'Linear Regression Coefficient (slope): {model.coef_[0]}')
print(f'Linear Regression Intercept: {model.intercept_}')



