# RBFN
Develop a Daily Temperature Monitoring System using RBF Network

Accurate forecasting of temperature is crucial for numerous sectors such as agriculture, energy management, and climate monitoring. Traditional linear models may fail to capture the complex patterns and non-linear dependencies present in time series climate data. As such, advanced non-linear models, like Radial Basis Function (RBF) networks, are better suited for modelling these intricate relationships.
This project aims to design and implement an RBF neural network model to predict daily temperatures based on historical climate data. The primary goal is to:
1.	Use the past 7 days of temperature data to predict the next day's temperature.
2.	Evaluate the performance of the RBF network by calculating metrics such as Mean Squared Error (MSE) and R-squared (R²) scores.
3.	Extend the model's predictive capacity to forecast the temperature for the next 30 days based on the historical dataset.
The dataset consists of historical daily temperature records for Delhi, India. The prediction model will be trained on this data to make short-term forecasts, and its performance will be evaluated against actual observations. Visualization of both the model's predictions and future forecasts will be provided to illustrate its accuracy and usability.

# Download the dataset from Kaggle 
# You need to have kaggle API set up on your machine 
!Kaggle datasets download -d sumanthvrao/daily-climate-time-series-data 
!unzip daily-climate-time-series-data.zip 
# Load the dataset df = pd. read_csv('DailyDelhiClimateTrain.csv')

Constraints:
• Dataset: Assumes Kaggle API is set up to download daily-climate-time-series-data. The 'date' column is converted to datetime, and meantemp is the target variable.
• RBF Network:
•	Centers (n_centers): 100 random centers are chosen from the data.
•	Gaussian Width (sigma): Fixed at 0.5 for the RBF units.
•	Weights: Computed using the pseudo-inverse of the RBF activations, including a bias term.
• Time Series Data Preparation:
•	Look-back Window: 7 days of past data are used to predict the next day's temperature.
• Data Handling:
•	Train-Test Split: 80% training, 20% testing.
•	Normalization: Input data is standardized using StandardScaler.
• Evaluation:
•	Metrics: Evaluated using Mean Squared Error (MSE) and R-squared (R²).
• Future Prediction:
•	Prediction Horizon: The model predicts the next 30 days, updating the input sequence after each prediction.


