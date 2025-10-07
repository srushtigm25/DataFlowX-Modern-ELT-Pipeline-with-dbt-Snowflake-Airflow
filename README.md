
# DataFlowX-Modern-ELT-Pipeline-with-dbt-Snowflake-Airflow
DataFlowX is a hands-on, end-to-end ELT pipeline built using dbt, Snowflake, and Apache Airflow, showcasing the backbone of a modern data engineering stack.


Overview - 
DataFlowX demonstrates how to design and deploy a modern ELT (Extract → Load → Transform) data pipeline using cloud-native and open-source tools.

🧩 Key Features -

✅ End-to-end ELT Workflow – from raw ingestion to analytics-ready data marts

🧠 Data Modeling – staging, fact, and mart layers using dbt best practices

⚙️ Automated Orchestration – dbt transformations triggered via Airflow DAGs

🔐 Snowflake RBAC Setup – role-based access control for secure warehouse access

🧪 Data Quality Tests – generic and singular tests using dbt

🧰 Modular Architecture – easily extensible for real-world data sources

Architecture Diagram - 

          +-------------------+
          |   Source Data     |
          +-------------------+
                    |
                    ▼
        +----------------------+
        |   Snowflake Stage    |
        +----------------------+
                    |
                    ▼
        +----------------------+
        |     dbt Models       |
        | (Staging → Fact → Mart)
        +----------------------+
                    |
                    ▼
        +----------------------+
        | Airflow Orchestration|
        +----------------------+
                    |
                    ▼
        +----------------------+
        |   Analytics Layer    |
        +----------------------+
Tech Stack -

Layer	Tool	Purpose
🏭 Data Warehouse	Snowflake	Central data storage and compute

🧱 Transformation	dbt Core	SQL-based modular transformation and testing

⏰ Orchestration	Apache Airflow	Workflow scheduling and automation

🐳 Infrastructure	Docker (optional)	Containerized environment

📊 Visualization	dbt Docs / Airflow UI	Lineage & monitoring


🚀 Setup & Execution - 

1️⃣ Setup Snowflake & dbt

Create a Snowflake database, warehouse, and roles

Configure your dbt profile

pip install dbt-snowflake
dbt init dataflowx


Update your profiles.yml:

target: dev
outputs:
  dev:
    type: snowflake
    account: <account_id>
    user: <user_name>
    password: <password>
    role: TRANSFORMER
    database: DATAFLOWX
    warehouse: COMPUTE_WH
    schema: DBT_DEV

2️⃣ Configure dbt Project - 
Edit dbt_project.yml and install dependencies:

dbt deps


Run dbt models:

dbt run
dbt test

3️⃣ Orchestrate with Airflow - 
Deploy the DAG in your Airflow instance:

airflow dags list
airflow dags trigger dbt_dataflowx_dag


Optionally, run with Docker:

docker-compose up

📊 Results - 

🔄 Data successfully transformed from raw → staging → marts

✅ dbt models tested and validated

⏰ Airflow DAGs running daily on schedule

🔐 Snowflake RBAC implemented for secure data access

Credits & References -

Credit to the original video author for educational inspiration.

https://youtu.be/OLXkGB7krGo?si=2g7NTtzjFCzjDJZT


