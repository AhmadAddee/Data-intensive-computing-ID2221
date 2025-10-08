# Setting up the environment

- First, make sure you have Docker Desktop installed.
- Open the command prompt, navigate to this folder, and run `docker compose -f .\spark-docker.yml up -d`
  > If you run into port-occupation issues, figre what service is occupying that port (e.g., `netstat -ano | findstr ":3306"`), get the name of the service (`Get-Process -Id <PID>`), and stop it (`Stop-Service "<name>"`).
- Check that the containers are running by typing `docker ps`.
- Install [MariaDB Connector/C](https://mariadb.com/downloads/connectors/connectors-data-access/c-connector/) for Windows.
- Make sure you have Java 17 JDK (`java --version`), and an environment variable pointed to it (`$ENV:JAVA_HOME`)
- Add a new Environment Variable with the name `PYSPARK_PYTHON` that points to your Python path (verify with `$ENV:PYSPARK_PYTHON`).
- Install [Anaconda Navigator](https://www.anaconda.com/download/success) by installing Anaconda Distribution.
- From Anaconda Navigator, create a new environment called `spark`, and install `Jupyter Notebook` in this environment.
- Open an `Anaconda Prompt` and navigate to this folder. From there, type `conda activate spark`, and then `jupyter notebook`, to open the project in Jupyter.
- From there, open the file [code_00_03_Spark_BDE_Setup_Prerequisites.ipynb](code_00_03_Spark_BDE_Setup_Prerequisites.ipynb) and install the required packages.

---
# Concepts
## Data Engineering
Designing and building systems that collect and analyze data to deliver insights and actions.

## Data Engineering vs. Data Analytics vs. Data Science
Data Engineering deals with the preparation of data for further analytics. It deals with integrating data sources
to extract data, build data pipelines for transport, processing, and transforming data to required formats, and
aggregation to finally store them. This data can also be used to build business actions downstream.

Business analytics, on the other hand, works on data that is already prepared by data engineering. It deals with
using the processed data to create dashboards and reports for doing exploratory data analytics and statistical modeling
of data. This includes generating recommendations for business actions.

Data science is a broad domain that encompasses data engineering and business analytics. It also includes machine
learning and generating predictions to drive business outcomes.

**Function** | **Data Engineering** | **Busines Analytics** | **Data Science**
--- |----------------------|-----------------------|-------------------
Integrate Data Sources | X                    |                       |   
Build Data Pipelines | X                    |                       |   
Process and Transform Data | X                    |                       |   
Store Data | X                    |                       |   
Dashboards and Reports |                      | X                     |   
Exploratory Analytics |                      | X                     |   
Statistical Modeling |                      | X                     |   
Machine Learning |                      |                       |   X
Business Recommendations |                      | X                     |   
Business Actions | X                    |                       |   

## Data Engineering Functions
Data engineering consists of five functions - namely **acquisition**, **transport**, **storage**, **processing**,
and **serving**.
Data pipelines are built by combining multiple such functions to deliver a given outcome.