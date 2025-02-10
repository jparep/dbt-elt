# End-to-End ELT Pipeline with dbt, Airflow, S3, and Python

## Introduction
This project demonstrates how to create an end-to-end ELT (Extract, Load, Transform) pipeline using dbt, Airflow, S3, and Python. The pipeline extracts data from a source, loads it into an S3 bucket, and then transforms it using dbt.

## Prerequisites
- Python 3.8+
- dbt
- Apache Airflow
- AWS CLI configured with access to S3

## Project Structure
```
/home/jparep/proj/dbt-elt/
├── dags/
│   └── elt_pipeline.py
├── models/
│   └── example_model.sql
├── data/
│   └── source_data.csv
├── README.md
└── requirements.txt
```

## Setup

### 1. Clone the Repository
```sh
git clone git@github.com:jparep/dbt-elt.git
cd dbt-elt
```

### 2. Install Dependencies
```sh
pip install -r requirements.txt
```

### 3. Configure dbt
Update the `dbt_project.yml` and `profiles.yml` files with your database connection details.

### 4. Configure Airflow
Set up Airflow and create a new DAG for the ELT pipeline. Place the DAG file (`elt_pipeline.py`) in the `dags/` directory.

### 5. Configure AWS S3
Ensure your AWS CLI is configured and you have access to the S3 bucket where the data will be stored.

## Running the Pipeline

1. **Start Airflow**: 
    ```sh
    airflow webserver -p 8080
    airflow scheduler
    ```

2. **Trigger the DAG**: 
    Trigger the `elt_pipeline` DAG from the Airflow UI.

3. **Monitor the Pipeline**: 
    Monitor the progress and logs from the Airflow UI.

## Conclusion
This project sets up a basic ELT pipeline using dbt, Airflow, S3, and Python. You can extend this pipeline by adding more complex transformations, additional data sources, and more sophisticated error handling.

## License
This project is licensed under the MIT License.

## Acknowledgements
- [dbt](https://www.getdbt.com/)
- [Apache Airflow](https://airflow.apache.org/)
- [AWS S3](https://aws.amazon.com/s3/)
- [Python](https://www.python.org/)
