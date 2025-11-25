# CST8916 – Assignment 2

## Cloud Service Providers Comparison Report

## Executive Summary

This report compares the real-time and remote data services offered by Amazon Web Services (AWS), Microsoft Azure, and Google Cloud Platform (GCP). Since modern applications rely heavily on APIs, event-driven messaging, and real-time analytics, the goal is to understand how each provider supports these capabilities and where they differ. The comparison focuses on RESTful APIs, GraphQL support, WebSockets, data streaming platforms, and real-time analytics tools.

Overall, AWS offers the broadest ecosystem, especially for serverless and real-time workloads. Services like API Gateway, AppSync, Kinesis, and MSK make it strong for large distributed systems. Azure focuses more on enterprise environments, offering strong API governance, hybrid cloud support, and real-time tools such as Event Hubs and Stream Analytics. GCP stands out for high-throughput, low-latency data pipelines, with Pub/Sub, Dataflow, and BigQuery providing powerful streaming and analytics performance.

The key takeaway is that each provider fits different needs. AWS is ideal for event-driven apps and managed GraphQL workloads. Azure is best for organizations already using Microsoft technologies. GCP is strongest when global messaging speed and large-scale analytics are priorities. This report also includes real-world scenarios showing how to choose the right platform based on performance, cost, and integration needs.

---

## Introduction

The purpose of this report is to compare AWS, Azure, and GCP in terms of their support for real-time communication and remote data access. These capabilities are essential for applications that rely on APIs, WebSockets, and streaming analytics. Each provider offers these features, but the services vary in maturity, scalability, and usability.

This comparison covers five service areas: RESTful API hosting, GraphQL support, WebSocket communication, data streaming platforms, and real-time analytics tools. Understanding these differences helps teams make better decisions depending on their technical and business requirements.

The cloud providers discussed are:

- **Amazon Web Services (AWS)** – broad service portfolio and strong serverless focus
- **Microsoft Azure** – enterprise-focused platform with strong hybrid support
- **Google Cloud Platform (GCP)** – optimized for high-performance data workloads

---

## 3. Service Comparison

### 3a. RESTful API Services

#### **AWS – API Gateway**

- Supports REST, HTTP, and WebSocket APIs
- Serverless and integrates with Lambda, DynamoDB, and CloudWatch
- Pricing based on request volume and data transfer

**Source:** https://aws.amazon.com/api-gateway/

---

#### **Azure – API Management (APIM)**

- Provides API policies, rate limiting, transformations, and developer portals
- Strong governance features for enterprise teams
- Pricing depends on tier (Consumption, Basic, Standard, Premium)

**Source:** https://learn.microsoft.com/azure/api-management/

---

#### **GCP – API Gateway / Apigee**

- **API Gateway**: Lightweight gateway for serverless APIs
- **Apigee**: Full lifecycle API management with analytics and traffic control
- Pricing varies based on calls and enabled features

**Sources:**  
https://cloud.google.com/api-gateway  
https://cloud.google.com/apigee

---

**Summary:** AWS is ideal for serverless REST APIs, Azure is the best for enterprise API governance, and GCP (with Apigee) offers strong API lifecycle management and developer tooling.

---

### 3b. GraphQL Services

#### **AWS – AppSync (Native GraphQL Service)**

- Fully managed GraphQL API service
- Built-in real-time subscriptions
- Integrates directly with DynamoDB, Lambda, and OpenSearch

**Source:** https://aws.amazon.com/appsync/

---

#### **Azure – No native GraphQL service**

- GraphQL must be implemented using Apollo or Hasura
- Can run on Azure App Service, Azure Functions, or Kubernetes

**Source:**  
https://learn.microsoft.com/azure/architecture/example-scenario/graphql/azure

---

#### **GCP – No managed GraphQL**

- Deploy third-party GraphQL servers on Cloud Run, GKE, or App Engine

**Source:** https://cloud.google.com/run

---

**Summary:** AWS is the only provider with a fully managed GraphQL solution.

---

### 3c. WebSocket Services

#### **AWS – API Gateway WebSocket**

- Supports persistent WebSocket connections
- Works well with Lambda for serverless real-time apps

**Source:**  
https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-websocket-api.html

---

#### **Azure – Web PubSub**

- Managed WebSocket service designed for chat apps, dashboards, and IoT
- Auto-scaling and reliable message delivery

**Source:** https://learn.microsoft.com/azure/azure-web-pubsub/

---

#### **GCP – No native WebSocket service**

- WebSockets can be implemented manually on Cloud Run
- Firebase Realtime Database offers event-driven updates

**Source:** https://firebase.google.com/

---

**Summary:** AWS and Azure support WebSockets natively; GCP requires custom setups.

---

### 3d. Data Streaming Services

#### **AWS**

- **Kinesis Data Streams** for ingestion
- **MSK (Managed Kafka)** for Apache Kafka workloads

**Source:** https://aws.amazon.com/kinesis/

---

#### **Azure**

- **Event Hubs** for large-scale ingestion
- Integrates with Functions and Stream Analytics

**Source:** https://learn.microsoft.com/azure/event-hubs/

---

#### **GCP**

- **Pub/Sub** for global, low-latency event streaming

**Source:** https://cloud.google.com/pubsub

---

**Summary:** AWS and Azure both support Kafka-based solutions; GCP Pub/Sub excels in global throughput and simplicity.

---

### 3e. Stream Analytics

#### **AWS – Kinesis Data Analytics**

- Uses SQL or Apache Flink for stream processing

**Source:** https://aws.amazon.com/kinesis/data-analytics/

---

#### **Azure – Stream Analytics**

- Real-time analytics engine with SQL-like queries
- Integrates with dashboard tools and Event Hubs

**Source:** https://learn.microsoft.com/azure/stream-analytics/

---

#### **GCP – Dataflow + BigQuery**

- Apache Beam-based pipelines
- BigQuery supports near real-time analytics

**Sources:**  
https://cloud.google.com/dataflow  
https://cloud.google.com/bigquery

---

**Summary:** Azure provides the easiest configuration experience, while GCP offers the strongest performance for large-scale workloads.

---

## 4. Use Case Analysis

### Use Case Comparison Table

| Use Case                                      | Recommended CSP                 | Reasoning (Cost, Performance, Integration, Ecosystem)                                                                                                                                                                                                                                                                          |
| --------------------------------------------- | ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **1. High-Volume IoT Sensor Monitoring**      | **Google Cloud Platform (GCP)** | **Performance:** Pub/Sub handles massive throughput with low latency. **Cost:** More predictable pricing compared to Kafka-style architectures. **Integration:** Dataflow + BigQuery provide seamless real-time analytics. **Ecosystem:** Strong data + ML tooling for anomaly detection.                                      |
| **2. Real-Time Chat / Messaging Application** | **Amazon Web Services (AWS)**   | **Performance:** API Gateway WebSockets + DynamoDB offer millisecond response times. **Cost:** Pay-per-connection model scales well for chat workloads. **Integration:** Tight integration between AppSync, Lambda, Cognito, and DynamoDB. **Ecosystem:** Best real-time + GraphQL environment with reliable serverless tools. |

## Conclusion

AWS, Azure, and GCP each offer strong but different capabilities for real-time and remote data scenarios. AWS has the most complete real-time service stack, with the advantage of a fully managed GraphQL service. Azure is the best fit for organizations with enterprise or hybrid-cloud needs due to its governance and integration tools. GCP provides excellent performance and scalability for data-heavy streaming workloads. The best choice ultimately depends on whether the priority is speed, cost, enterprise integration, or analytics performance.

---

## References

Amazon Web Service. _Amazon API Gateway_. https://aws.amazon.com/api-gateway/

Amazon Web Services. _AWS AppSync_. https://aws.amazon.com/appsync/

Amazon Web Services. _Amazon Kinesis_. https://aws.amazon.com/kinesis/

Amazon Web Services. _Amazon DynamoDB_. https://aws.amazon.com/dynamodb/

Amazon Web Services. _AWS IoT Core_. https://aws.amazon.com/iot-core/

Amazon Web Services. _AWS Lambda_. https://aws.amazon.com/lambda/

Microsoft. _Azure API Management_. https://learn.microsoft.com/azure/api-management/

Microsoft. _Azure Web PubSub_. https://learn.microsoft.com/azure/azure-web-pubsub/

Microsoft. _Azure Event Hubs_. https://learn.microsoft.com/azure/event-hubs/

Google Cloud. _API Gateway_. https://cloud.google.com/api-gateway

Google Cloud. _Apigee API Platform_. https://cloud.google.com/apigee

Google Cloud. _Pub/Sub_. https://cloud.google.com/pubsub

Google Cloud. _Dataflow_. https://cloud.google.com/dataflow

Google Cloud. _BigQuery_. https://cloud.google.com/bigquery

Google Cloud. _Firestore_. https://cloud.google.com/firestore

Google Cloud. _Cloud Run_. https://cloud.google.com/run

---

## AI Usage Disclosure

I used ChatGPT to help me brainstorm, organize my content, and improve the clarity of the writing. All analysis and final decisions in the report reflect my own understanding of the material.
