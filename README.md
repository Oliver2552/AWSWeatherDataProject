# Weather Data Pipeline Project

## Overview

This project aims to create a weather data pipeline using AWS services S3, Glue, Redshift and is orchestrated by Airflow. The pipeline extracts weather data from the OpenWeather API, stores it in an S3 bucket, transforms the data using AWS Glue, and finally loads it into a Redshift cluster for analysis.

## Project Structure

- **DAGs**: Two Airflow DAGs are defined for the workflow.
  - `openweather_api.py`: Extracts weather data from the OpenWeather API and stores it in an S3 bucket.
  - `transform_redshift_load.py`: Transforms the weather data using AWS Glue and loads it into a Redshift cluster.

## Components

- **OpenWeather API**: Provides weather data for various locations.
- **AWS S3**: Storage for raw and processed data.
- **AWS Glue**: ETL service to transform the data.
- **AWS Redshift**: Data warehouse to store and analyze the transformed data.

## Airflow Setup

1. **Create connections in Airflow**:
   - **AWS Connection**: Add your AWS credentials in the Airflow UI.
   - **Redshift Connection**: Add your Redshift cluster connection details.

## AWS Setup

1. **S3 Bucket**: Create an S3 bucket to store the weather data.
2. **Glue Job**: Create an AWS Glue job to transform the weather data.
3. **Redshift Cluster**: Set up a Redshift cluster to store the transformed data.

## Running the Pipeline

1. **Trigger the Extraction DAG**: Run the `weather_data_extraction_dag` from the Airflow UI to extract data from the OpenWeather API and store it in S3.
2. **Trigger the Transformation DAG**: Run the `weather_data_transformation_dag` from the Airflow UI to transform the data using AWS Glue and load it into Redshift.

## Future Improvements

- **Data Quality Checks**: Implement data quality checks to ensure the accuracy and completeness of the data.
- **Error Handling**: Enhance error handling and logging to capture and address issues during the pipeline execution.
- **Scalability**: Optimize the pipeline to handle larger datasets and more complex transformations.

## Conclusion

This project demonstrates the integration of Airflow, AWS Glue, and Redshift to create a scalable and reliable weather data pipeline. It serves as a foundation for building more advanced data pipelines for various use cases.
