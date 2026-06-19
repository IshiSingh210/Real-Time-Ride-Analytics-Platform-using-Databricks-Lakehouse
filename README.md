# Real-Time Ride Analytics Platform using Databricks Lakehouse

## Overview

Built an end-to-end real-time analytics platform for a ride-hailing company using Databricks Lakehouse architecture.

The solution ingests ride events through Azure Event Hubs, processes streaming and batch data using Lakeflow Declarative Pipelines (formerly Delta Live Tables), and creates analytical datasets using a Star Schema model.

Key capabilities include:

* Real-time ride ingestion from Event Hubs
* Batch and streaming data integration
* Bronze, Silver, and Gold architecture
* Slowly Changing Dimensions (Type 1 & Type 2)
* Auto CDC using Lakeflow Pipelines
* Delta Lake storage format
* Business-ready analytical data model

---

## Tech Stack

* Databricks
* PySpark
* Lakeflow Declarative Pipelines (SDP)
* Delta Lake
* Azure Event Hubs
* Azure Data Lake Storage Gen2
* Kafka API
* SQL
* Jinja2

---

## Data Flow

### Bronze Layer

Raw ingestion layer containing:

* Ride events from Azure Event Hubs
* Reference mapping datasets from ADLS

Tables:

* rides_raw
* bulk_rides
* map_cities
* map_vehicle_types
* map_vehicle_makes
* map_payment_methods
* map_ride_statuses
* map_cancellation_reasons

---

### Silver Layer

Data standardization and enrichment layer.

Activities:

* JSON parsing
* Schema enforcement
* Streaming ingestion
* Lookup enrichment
* One Big Table (OBT) generation

Output:

* silver_obt

---

### Gold Layer

Dimensional model for analytics.

Dimensions:

* dim_passenger
* dim_driver
* dim_vehicle
* dim_payment
* dim_booking
* dim_location (SCD Type 2)

Fact:

* fact_rides

---

## Advanced Features

### Real-Time Streaming

Ride events are continuously consumed using Kafka-compatible Azure Event Hubs.

### Change Data Capture

Lakeflow Auto CDC is used for dimension maintenance.

### Slowly Changing Dimensions

* Type 1: Passenger, Driver, Vehicle, Payment, Booking
* Type 2: Location

### Event Time Processing

Watermarks are implemented to handle late-arriving events.

---

## Business Use Cases

* Ride demand analysis
* Revenue monitoring
* Driver performance tracking
* Vehicle utilization analysis
* City-wise operational reporting
* Customer behavior analytics

---

## Future Enhancements

* Data Quality Framework
* Great Expectations integration
* Gold Aggregation Layer
* CI/CD with Databricks Asset Bundles
* Infrastructure as Code using Terraform
* Real-time dashboarding with Power BI

---

## Skills Demonstrated

PySpark | Databricks | Delta Lake | Lakeflow Pipelines | Streaming Data Processing | CDC | SCD Type 1 & Type 2 | Event Hubs | Kafka | Data Modeling | Azure Data Lake
