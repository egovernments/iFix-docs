---
description: Tools used to create the OLAP system for the iFix
---

# Tools used

iFix dashboard is developed using the opensource tools that included the complete OLAP system that streams the data from various sources, transform and process data and visualize the data using dashboards

| Platform Tools | Latest Version | Used Version | Description | License Type | ​ |
| :--- | :--- | :--- | :--- | :--- | :--- |
| ​[Metabase​](https://www.metabase.com/docs/latest/) |  v0.40.4 |  v0.40.2 | **Metabase** is an **open source business intelligence tool**. It lets you ask questions about your data, and displays answers in formats that make sense, whether that's a bar graph or a detailed table. | ​ | ​ |
| ​[Druid](https://druid.apache.org/) | 0.21.1 | 0.21.1 | **Apache Druid** is a real-time analytics database designed for fast slice-and-dice analytics \("[OLAP](http://en.wikipedia.org/wiki/Online_analytical_processing)" queries\) on large data sets. Druid is most often used as a database for powering use cases where real-time ingest, fast query performance, and high uptime are important. As such, Druid is commonly used for powering GUIs of analytical applications, or as a backend for highly-concurrent APIs that need fast aggregations. Druid works best with event-oriented data. | ​​[Apache **License** 2.0](https://www.apache.org/licenses/LICENSE-2.0) | ​ |
| [Confluent Kafka](https://dattell.com/data-architecture-blog/comparing-confluent-kafka-and-apache-kafka/)​ | 6.2.0 | 5.4.1 | Apache **Kafka** is a open sourced and community distributed event streaming platform capable of handling trillions of events a day. | ​[Community License](https://www.confluent.io/confluent-community-license-faq/)  | ​ |
| [Postgresql](https://www.postgresql.org/)​ | 13.4 | 9.6 and 10.6 | _**PostgreSQL**_ is a powerful, open source object-relational database system with over 30 years of active development that has earned it a strong reputation for reliability, feature robustness, and performance | ​[PostGres License](https://www.postgresql.org/about/licence/)​ | ​ |

