# Airflow Local Setup (Beginner Friendly)

This guide walks you through installing and running Apache Airflow locally using a Python virtual environment.  
It is designed for beginners learning the basics of Airflow.

---

## 1. Create a Python Virtual Environment

```bash
python -m venv venv
# or specify a version:
python3.12 -m venv venv
````

---

## 2. Activate the Virtual Environment

```bash
source venv/bin/activate
```

---

## 3. Install Apache Airflow

Set Airflow and Python versions:

```bash
AIRFLOW_VERSION="2.10.4"
PYTHON_VERSION="3.12"

CONSTRAINT_URL="https://raw.githubusercontent.com/apache/airflow/constraints-${AIRFLOW_VERSION}/constraints-${PYTHON_VERSION}.txt"
```

Install Airflow:

```bash
pip install "apache-airflow==${AIRFLOW_VERSION}" --constraint "${CONSTRAINT_URL}"
```

---

## 4. Initialize Airflow Database

```bash
airflow db migrate
```

---

## 5. Create a DAGs Folder

This folder will contain your airflow DAG files:

```bash
mkdir dags
```

---

## 6. Update Airflow Configuration

Check the Airflow home directory:

```bash
airflow info
```

Then edit the configuration file:

```bash
vim <airflow-home-path>/airflow.cfg
```

Update:

* `dags_folder = /path/to/your/dags`
* `load_examples = False`

---

## 7. Create an Airflow User

```bash
airflow users create \
  --username admin \
  --firstname <your-name> \
  --lastname <your-surname> \
  --role Admin \
  --email admin@example.com \
  --password admin
```

---

## 8. Start the Airflow Webserver

```bash
airflow webserver --port 8080
```

---

## 9. Start the Airflow Scheduler

Open a new terminal, then:

```bash
source venv/bin/activate
airflow scheduler
```

---

## 10. Access the Airflow UI

Open:

```
http://localhost:8080
```

Login using the username and password created earlier.

---

## requirements.txt

Below are recommended packages for a basic Airflow environment.

```txt
# Core Airflow installation
apache-airflow==2.10.4

# Optional Airflow extras (common for beginners)
apache-airflow-providers-cncf-kubernetes
apache-airflow-providers-docker
apache-airflow-providers-google
apache-airflow-providers-amazon
apache-airflow-providers-sqlite

# Useful Python utilities for DAGs
pandas
requests
python-dotenv

# If using dbt or analytics
dbt-core
dbt-postgres
```

To install using constraints (recommended):

```bash
pip install -r requirements.txt \
  --constraint https://raw.githubusercontent.com/apache/airflow/constraints-2.10.4/constraints-3.12.txt
```

---

You now have everything needed to run Airflow locally and start building DAGs inside the `dags/` folder.

```

---
