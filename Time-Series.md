# Time Series

## Introduction 

Time-Series databases are designed to store data that chages with time.This can be any kind of data wich was collected over time.

![What is Time Series?](https://365datascience.com/wp-content/uploads/2019/11/what-is-time-series-data-compressed-768x432.jpg)

Image extracted from:

## [What Is Time Series Data?](https://365datascience.com/time-series-data/)

Time series databases allow businesses to store time-stamped data.Time series databases are optimized for storing this data so that it can be easily 
pulled and analyzed. Time series data is often used when running predictive analytics or machine learning algorithms, enabling users to understand 
historical data to help predict future outcomes. Some big data processing and distribution software may provide time series storage functionality.

We can divide the Time Series Databases in 3 categories:

* Store data based on timestamps
* Consume data in real time
* Allow to easily pull the data for time series analysis

## Why use Time-Series?

**Predict future**: Make informed predictions about future events, observe real-time changes, and capture historical anomalies.

**Understand past**: Understand past data with a purpose-built database.

## Who uses Time Series?

**Database administrators**: Time series databases have grown in popularity since they are easier to implement, have greater flexibility, and tend to have 
faster data retrieval times. Database administrators use these tools to maintain and manage their time series data, ensuring it is properly stored.

**Data scientists**: As data science, including artificial intelligence, is fueled by data, it is key that this data is stored in the most effective and 
efficient manner. This ensures that the data can be queried and analyzed properly.

## Kinds of Time Series Database Software

**Relational databases**: Relational databases are traditional database tools used to align information into rows and columns. The structure allows for easy 
querying using SQL. Relational databases are used to store both simple information, such as identities and contact information, and complex information 
critical to business operations. They are highly scalable and can be stored on-premises, in the cloud, or through hybrid systems.

**NoSQL databases**: NoSQL databases such as graph databases are a great option for unstructured data. If the user needs to render a value that is easily found 
by its key, then a key-value store is the fastest and most scalable. The drawback is a much more limited querying ability, implying its limitations for 
analytic data. Conversely, rendering a user’s email address based on the username or caching web data is a simple and fast solution in a key-value store.

## Time Series Features

**Querying using time**: Time series databases allow users to query data using time, allowing them to search or analyze the data across a given time period, 
even by a fraction of a second.

**Data security**: Time series database solutions include data security features to protect the data stored by a business in its databases.

**Database creation and maintenance**: Time series databases software allows users to quickly create brand-new relational databases and modify them with ease.

**Scalability**: Times series database solutions grow with the data and is hence scalable, with the only pain point being physical or cloud storage capacity.

**Operating system (OS) compatibility**: Relational database solutions are compatible with numerous OS.

**Recovery**: Whether a database needs to be rolled back or outrightly recovered, some time series database solutions offer recovery features in the event any 
errors occur.

## Relationship to Big Data

Data has become the backbone of conducting business in the information age. As data drives business decisions and trends, it’s important that the data be 
digestible, easy to follow, and easy to reference. That’s why big data software mostly falls back on relational database solutions. Designed with strict organization, 
referencing, and referral in mind, relational databases absorb and store massive amounts of data to be later digested in the decision-making process.


All this information was extracted from [Best Time Series Databases Software](https://www.g2.com/categories/time-series-databases?utf8=%E2%9C%93&order=popular)


# Time-Series Databases

Comparation between 5 Time-Series databases:

Databases/Attributes | Amazon Timestream            | DataStax                      | InfluxDB                          | Prometheus                        | QuasarDB                          |
-------------------- | :--------------------------: | :---------------------------: | :-------------------------------: | :-------------------------------: | --------------------------------: |                         
**Market Segemnet**  | Mid-Market(56.3% of reviews) | Enterprise (61.5% of reviews) | Small-Business (52.4% of reviews) | Small-Business (47.4% of reviews) | Small-Business (33.3% of reviews) | 
**Unique Categories** | Amazon Timestream is categorized as Database as a Service (DBaaS) | DataStax is categorized as Data Replication, Database Monitoring, Database as a Service (DBaaS), Graph Databases, and Key-Value Stores | InfluxDB has no unique categories | Prometheus is categorized as Database Management Systems (DBMS) and Container Monitoring | QuasarDB has no unique categories |
**What is it?** | Amazon Timestream is a fast, scalable, fully managed time series database service for IoT and operational applications that makes it easy to store and analyze trillions of events per day at 1/10th the cost of relational databases. | DataStax helps companies compete in a rapidly changing world where expectations are high and new innovations happen daily. | InfluxDB is the open source time series database | An open-source service monitoring system and time series database. | QuasarDB is a high-performance, distributed time series database that seamlessly combines in-memory capabilities with reliable storage. It’s built on a vertical approach with a single software package that provides storage, distribution, standardization and analysis | 
**Pricing** | Free Trial Unavailable | Free Trial Unavailable | Free Trial Unavailable | Free Trial Unavailable | Free Trial Unavailable |
**Ease of Use** | 8.0 | 7.9 | 9.0 | 7.8 | 5.0 |
**Case of Use** | DevOps, Applications of IoT, Application Monitoring, Industrial Telemetry | Hybrid and Multi-cloud, Microservices, System Modernization, Streaming IoT, Analytics | Deep insights and analytics | Storage, visualizations, Integrations with Docker, HaProxy, StatsD and JMX metrics | import and export databases, Remote connectors with Grafana, Kafka, Spark, Excel and  Prometehus, APIs consults |
**Supoort** | Amazon web service | Apache Cassandra | Open Source | Open Source or Cloud Native | SQL |











