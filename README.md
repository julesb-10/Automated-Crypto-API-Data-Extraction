# Automated Cryptocurrency API Pull

This project automates the retrieval of cryptocurrency market data from the CoinMarketCap API using Python.  
Each run of the script fetches the latest listings and appends the newly collected data to a CSV file, allowing the dataset to grow continuously over time.

The output structure is designed so that it could easily be directed to a database or data warehouse (e.g., Snowflake, BigQuery, PostgreSQL, Redshift) instead of a CSV.

---

## Features

- Automated recurring API requests using Python and time-based iteration  
- Appends each new data pull to an existing CSV for cumulative historical storage  
- Includes a timestamp for each batch to support time-series or trend analysis  
- Easily extendable to load the data into cloud data warehouses or analytics pipelines  

---

## Technologies Used

- **Python**  
- **Requests** for API communication  
- **Pandas** for data handling and CSV writing  
- **Jupyter Notebook** for development and execution  

---

## How It Works

1. A session is created using the Requests library, and authentication headers are applied.  
2. The script performs a GET request to fetch the latest cryptocurrency listings.  
3. JSON data is transformed into a Pandas DataFrame.  
4. A timestamp column is added to record when each pull occurred.  
5. The new data is appended to a CSV file, preserving all previously collected records.  
6. The loop sleeps for a predetermined amount of time before executing the next pull.  

This process can be scheduled for many iterations depending on API rate limits, allowing fully automated growth of a historical dataset.

---

## Use Cases

- Building time-series datasets for cryptocurrency analysis  
- Feeding BI dashboards or analytics tools with refreshed data  
- Automating ETL/ELT ingestion workflows  
- Eliminating manual data collection tasks in financial or any other data-driven environments

