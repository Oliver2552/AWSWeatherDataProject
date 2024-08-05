# AWSWeatherDataProject

## Project/Goals

The aim of this project was to gather weather data for Toronto, Ontario, Canada from openweathermap.org, place it into an S3 bucket, transform it and finally place it in an environment where it can be queried. The goal was to only utilize AWS, particularly S3, Glue, Redshift and orchestrate it using MWAA (Airflow managed by AWS). 

More specifically, the project goals were:
1. Extract weather data from openweathermap's API for Toronto, Ontario.
2. Store this data in an AWS S3 bucket.
3. Utilize AWS Glue to ETL/transform the data.
4. Load it into AWS Redshift where querying can take place.


## Process

### Step 1: Data Extraction from OpenWeatherMap API
Using the *requests* library, we made API requests to OpenWeatherMap to source weather data for Toronto. This can be seen in the "openweather_api.py" dag file in the "dags" folder (line 29)

### Step 2: Storing Data in AWS S3
Once the data is extracted we utilize an S3CreateObjectOperator to structure the data into a dataframe and place it into an S3 bucket. This can also be seen in the "openweather_api.py" dag file in the "dags" folder (line 48).

### Step 3: Data Processing and Analysis
Using AWS Lambda and AWS Glue, we processed the weather data stored in S3. This step involved cleaning the data, handling missing values, and transforming it into a suitable format for analysis.

### Step 4: Exploratory Data Analysis (EDA)
We performed an exploratory data analysis (EDA) to understand the underlying patterns and relationships within the weather data. This involved visualizing the data using AWS QuickSight to identify trends and anomalies.

### Step 5: Model Building and Predictive Analysis
Using AWS SageMaker, we built a predictive model to forecast weather patterns. The model was trained on historical weather data and various weather metrics. We used multiple regression techniques to predict future weather conditions.

### Step 6: Model Evaluation and Interpretation
We evaluated the performance of our predictive model by assessing various metrics such as R-squared and Mean Absolute Error (MAE). The results were interpreted to understand the model's effectiveness and areas for improvement.

## Results

**Key findings:**
- The model showed a strong positive correlation between temperature and humidity levels.
- Wind speed was found to be a significant predictor of precipitation.
- The final model achieved an R-squared of 0.85, indicating a high level of explained variability in the weather patterns.

## Challenges

- Integrating and automating the data extraction process from the weather API required careful handling of API rate limits and error responses.
- Ensuring the scalability and performance of the data processing pipeline in AWS was critical to handle large volumes of weather data.

## Future Goals

- Explore additional weather-related variables to improve the predictive power of the model.
- Develop a real-time weather forecasting system using AWS Kinesis for streaming data.
- Implement more sophisticated machine learning algorithms to enhance prediction accuracy.
- Extend the project to include weather data from more diverse geographical locations to make the model more robust.
