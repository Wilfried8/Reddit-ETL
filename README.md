## How this pipeline works

There is one DAG (pipeline) running which extracts Reddit data from its API using Python's PRAW API wrapper.

It is setup to extract data from the past 24 hours and store in a CSV with fields such as post ID, author name, and so forth.

This CSV is then loaded directly into an AWS S3 bucket (cloud storage) before being copied to AWS Redshift (cloud data warehouse).

This entire process is running with Apache Airflow (orchestration tool) running with Docker. This saves us having to manually setup Airflow.