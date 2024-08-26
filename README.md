# Data Lakehouse

This project integrating different open-source technologies in order to create a working **open data lakehouse** solution based on **Apache Iceberg**. 

Core technologies used are:

| Component | Description | Version |
| --------- | ----------- | ------- |
| Trino     | Federated query engine | v443 |
| MinIO     | Object store   |  v2023.08.23  | 
| Hive MestaStore (HMS) | Metadata respository |    v.3.1.3
| Apache Spark | Distributed computation engine | v3.4.1 | 
| Apache Iceberg | Analytics table open format | v1.6
| Jupyter notebook | Web-based computational documents | v1.0.0 |

### Code structure

All software **components are distributed based on docker images**. There is a docker-compose file that automates the deployment of all components easily. All components' configuration files are inside [docker directory](docker).

In the [notebooks folder](notebooks), there is a **Jupyter notebook showing a simplified Spark-based ETL batch job** that generates data products stored in MinIO object storage. All data products are registered into the Hive MetaStore (HMS) service as Apache Iceberg tables. 

Both Spark (for data creation) and Trino (for interactive data exposition) use the lakehouse capabilities through Hive metastore (HMS), creating a seamless integration of ETL workloads and interactive querying.

Inside [datasets folder](datasets) are a small-sized files with samples of the datasets used.


