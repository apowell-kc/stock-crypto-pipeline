# Stock & Crypto Market Data Pipeline (In Progress)
Building a pipeline using Alpaca's API market data to process historical crypto/stock data in an ELT pattern. 

The aim of this project is to write a pipeline that processes cryptocurrency and stock market data using Alpaca's API. 

## Scope
The beauty of this project is it can evolve to handle greater complexity over time. In the end state I would like this to be a pipeline that handles both streaming and batch data. 

For now, the MVP scope is to take BTC bar data from the Alpaca API and follow an ELT design pattern.

#### Extract:
- BTC data requested via API
- BTC data is sent to Kafka via a kafka producer
- BTC data is consumed via a kafka consumer


#### Load:
- Spark processes the data and loads it to a Snowflake data warehouse

#### Transform:
- dbt runs transformations to enrich the data or add additional insight.
- Dashboard is built with the finished data from Snowflake.


## Tech Stack:
For this project the following tools will be used:

__Python:__ 

All the code will be written in python using the python API libraries such as kafka-python and pyspark

__Apache Kafka:__

Use to accept the data in the API and act as a message queue. Using this so I can add in streaming functionality later.

__Apache Spark:__ 

Use to process the data and take it from kafka to Snowflake.

__Apache Airflow:__

Use to perform the different pipeline operations on a schedule. I might use Airflow to porcess daily historical data so the pipeline can be perpetually running.

__Snowflake:__ 

Cloud data warehouse. 

__dbt:__

Use this to perform transformations on the data in the data warehouse. I'm very impressed with dbt and want to see more of what it can do.

__Viz tool: TBD__

I want to use something new. I'm considering Apache Superset, Looker, or Grafana


## Pipeline Diagram
This image provides a general overview of the flow of the current scope of the project.
This will be updated as the project evolves.

![pipeline_diagram](https://github.com/apowell-kc/stock-crypto-pipeline/assets/124818210/ff0fb9ad-a997-4cc6-aa6a-99f198ec06e9)

