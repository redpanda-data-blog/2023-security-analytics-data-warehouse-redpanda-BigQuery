# How to integrate Redpanda and BigQuery

## Overview

This repository contains a comprehensive guide and necessary scripts to build a security analytics data warehouse using Redpanda and Google BigQuery. It demonstrates how to integrate real-time data streaming with advanced analytics for effective cybersecurity threat detection and analysis.

## Prerequisites

- Python 3.11 or higher
- Docker (Recent version)
- Redpanda (Follow installation instructions from the [Redpanda website](https://docs.redpanda.com/current/get-started/quick-start/))

## Folder Structure

Your working directory should follow this structure:

```
panda_bigquery
├── configuration
├── plugins
```

## Steps to Setup

### 1. Generate the Dataset

Generate dummy security event data using the `generate_data.py` script. This script creates a variety of security event logs.

### 2. Setup BigQuery

Create a dataset in BigQuery to store and analyze the streamed data. Name your dataset “security_analytics_data” and your table “security-events”.

### 3. Create Topics on Redpanda Cloud

Create a Redpanda topic “security-events” for streaming the generated dataset.

### 4. Setup Redpanda for BigQuery Connection

Configure Kafka Connect and a sink connector for BigQuery integration. Use the `connect.properties` and `bigquery-sink-connector.properties` in the `configuration` folder.

### 5. Start Kafka Connect Cluster

Run the Kafka Connect cluster with the configuration files to establish data pipeline between Redpanda and BigQuery.

### 6. Data Production and Streaming

Use the `produce.py` script to send the generated data to the Redpanda topic, which will be streamed to BigQuery.

### 7. Examine Data in BigQuery

Run various SQL queries in BigQuery to analyze the streamed data. Queries examples are provided in the main guide.

## Conclusion

This setup allows for an efficient real-time data streaming and analysis system, crucial for cybersecurity threat detection. Redpanda ensures fast data ingestion, while BigQuery provides scalable data processing capabilities.

## Additional Resources

- [Redpanda Documentation](https://docs.redpanda.com/current/home/)
- [Redpanda Blog](https://redpanda.com/blog)
- [Redpanda Community on Slack](https://redpandacommunity.slack.com/join/shared_invite/zt-264shn87r-9E_SLmYAvcexfFZpT~D6xg#/shared-invite/email)
