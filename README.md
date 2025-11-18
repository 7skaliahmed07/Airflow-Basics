# Basic Airflow Repository

This repository contains a collection of hands-on Apache Airflow practice exercises designed to build foundational skills in workflow orchestration, task dependency management, data processing, monitoring, and integration with external systems.  
Each DAG focuses on one key Airflow concept, gradually progressing from simple scheduling to more advanced data engineering patterns.

The exercises are intentionally small, focused, and practical—ideal for learning, experimentation, and onboarding new Airflow users.

---

## 🚀 Project Objectives

This practice repository was created to:

- Understand the fundamentals of Airflow DAGs, tasks, and scheduling.  
- Learn how to process data using Python operators.  
- Explore failure handling and retry logic.  
- Work with sensors for dependency checks.  
- Integrate Airflow with Postgres.  
- Run distributed computation using Apache Spark.  
- Build an organized, scalable Airflow project structure.

---

## 📂 Repository Structure

```

dags/
│
├── 01-average_page_visits.py
├── 02-average_page_visits_with_failures.py
├── 03-bookings_per_listing.py
├── 04-bookings_per_listing_with_sensor.py
├── 05-bookings_per_listing_with_postgres.py
└── bookings_per_listing_spark.py

````

Each DAG introduces a new Airflow capability or concept.

---

## 📘 DAG Descriptions

### **1. 01-average_page_visits.py**
A simple Airflow DAG that:

- Reads page visit data  
- Calculates the average number of visits  
- Demonstrates basic PythonOperator usage  
- Introduces pulling and pushing values using XCom  

This is the foundation DAG for the rest of the exercises.

---

### **2. 02-average_page_visits_with_failures.py**
An extended version of DAG 01 that introduces:

- Intentional task failure for learning  
- Retry logic  
- Error handling patterns  
- Email/on-failure notifications (if configured)

This DAG helps understand how Airflow reacts to failures.

---

### **3. 03-bookings_per_listing.py**
This DAG processes booking data and:

- Computes bookings grouped by listing  
- Introduces slightly more complex Python workflows  
- Demonstrates intermediate transformations  
- Produces structured results through XCom

It serves as a bridge into more realistic data pipelines.

---

### **4. 04-bookings_per_listing_with_sensor.py**
Adds a **sensor** to the previous DAG, covering:

- How Airflow sensors work  
- External dependency checks before DAG execution  
- File or table availability monitoring  
- Reducing pipeline failure by waiting for prerequisites

This introduces the idea of event-based orchestration.

---

### **5. 05-bookings_per_listing_with_postgres.py**
A more advanced DAG integrating **Postgres**:

- Queries data from a Postgres database  
- Uses Airflow’s Postgres provider  
- Writes results back into a target table  
- Demonstrates Airflow connections and hooks  

This is the first **end-to-end data engineering pipeline** in the repository.

---

### **6. bookings_per_listing_spark.py**
A distributed version of the bookings calculation using **Apache Spark**, demonstrating:

- Airflow integration with SparkSubmitOperator  
- Running large-scale/cluster-based processing  
- Separating orchestration (Airflow) from execution (Spark)  

This represents a real-world scalable data pipeline pattern.

---

## 🛠 Technologies Used

- **Apache Airflow 2.10.x**  
- **Python 3.12**  
- **Postgres (Airflow Provider)**  
- **Sensors (File/External)**  
- **Apache Spark (optional integration)**  
- **PythonOperator, PostgresOperator, SparkSubmitOperator**  

---

## ✅ Summary

This repository demonstrates:

* Basic Airflow DAG creation
* Error handling and retries
* Sensors for external dependencies
* Database integration using Postgres
* Running distributed jobs using Spark
* Best practices for organizing Airflow projects

It is intended as a complete beginner-to-intermediate learning path for mastering core Airflow concepts in a practical and incremental way.

