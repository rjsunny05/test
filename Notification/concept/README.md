# Notification Documentation 



| Author          | Created on | Version   | Last updated by | Last edited on | Internal Reviewer | L0     | L1      | L2     |
|-----------------|------------|-----------|------------------|----------------|--------------------|--------|---------|--------|
| Rajeev Ranjan | 02-05-25   | version 1 | N/A              | N/A            | Priyanshu          | Khushi Malhotra | Mukul Joshi| Piyush Upadhyay|

## Table of Contents

1. [**Introduction**](#introduction)  
2. [**Objective**](#objective)  
3. [**Architecture**](#architecture)  
4. [**System Requirements**](#system-requirements)  
5. [**Setup Requirements**](#setup-requirements)  
6. [**Required Ports**](#required-ports)  
7. [**Capabilities**](#capabilities)  
8. [**Dependencies**](#dependencies)  
9. [**Installation Guide**](#installation-guide)  
10. [**Data Storage & Caching Mechanisms**](#data-storage--caching-mechanisms)  
11. [**Final Thoughts**](#final-thoughts)  
12. [**Service Information**](#service-information)
13. [Environment Variable](#environment-variable)  
14. [**Contact Information**](#contact-information)  
15. [**Reference Links**](#reference-links)

## Introduction

The Notification Service is a Python-based microservice designed to handle email notifications for the OT-Microservices ecosystem. It operates either on a scheduled basis (monthly) or on-demand (external trigger), integrating with SMTP servers to deliver emails to employees. The service works in conjunction with employee-api, attendance-api, and salary-api to send relevant notifications.

## Objective

The primary objective of the Notification Service is to automate and manage all email communications within the OT-Microservices platform. It serves as a centralized notification system that can be triggered either:
- Automatically on a monthly schedule
- Manually via external API calls
The service ensures timely delivery of important notifications like salary slips, attendance regularizations, and policy updates.

## Architecture

![image (1)](https://github.com/user-attachments/assets/294d8ed0-8b20-4309-85b5-c078354532b9)


## System Requirements

| Hardware Specifications | Recommendation      |
| :--------------------- | :------------------ |
| Processor             | dual-core           |
| RAM                   | 2GB                 |
| Disk                  | 10GB                |
| OS                    | Ubuntu (22.04)     |

## Setup Requirements

| Component       | Requirement                                                                 |
|----------------|-----------------------------------------------------------------------------|
| Python         | Version 3.8+ required                                                      |
| SMTP Server    | Access to configured SMTP server with credentials                          |
| Elasticsearch  | Optional for logging and monitoring (version 7.x+)                         |

## Required Ports

| **Port** | **Service**     | **Description**                                                                 |
|----------|----------------|---------------------------------------------------------------------------------|
| `25/587/465` | SMTP       | Ports for email delivery (depending on SMTP server configuration)              |
| `9200`   | Elasticsearch  | Default port for Elasticsearch connections (optional)                          |

## Capabilities

| Capability                  | Explanation                                                                                               |
| :-------------------------- | :-------------------------------------------------------------------------------------------------------- |
| **Scheduled Notifications** | Automatically sends monthly notifications at the beginning of each month                                  |
| **On-Demand Notifications** | Supports immediate notification triggering via external mode                                              |
| **SMTP Integration**        | Flexible integration with any SMTP server for email delivery                                             |
| **Template Support**        | Supports customizable email templates for different notification types                                   |
| **Error Handling**          | Robust error handling and retry mechanisms for failed email deliveries                                   |
| **Logging**                | Comprehensive logging to Elasticsearch for monitoring and troubleshooting                                |

## Dependencies

| Technology        | Purpose                                                                                                           |
| :---------------- | :---------------------------------------------------------------------------------------------------------------- |
| **Python 3.8+**   | Core programming language for the service                                                                        |
| **SMTP Protocol** | Standard email delivery protocol                                                                                |
| **Elasticsearch** | Optional for centralized logging and monitoring                                                                 |
| **Make**         | Build automation for development tasks                                                                          |
| **Docker**       | Containerization for deployment                                                                                |

## Installation Guide

You can follow the Notification api POC for installation and startup steps. It provides a detailed guide to set up and run the API smoothly.

## Data Storage & Caching Mechanisms

The Notification Service primarily relies on:

1. **SMTP Server**: For actual email delivery
2. **Elasticsearch (Optional)**: For storing logs and notification history

## Final Thoughts

The Notification Service provides a robust and flexible solution for managing all email communications within the OT-Microservices ecosystem. Its dual-mode operation (scheduled and on-demand) makes it adaptable to various use cases, while its simple integration with standard SMTP servers ensures wide compatibility. The service is designed to be lightweight yet powerful enough to handle all organizational notification needs.

## Service Information

| **Command/Mode**       | **Description**                                                                                   |
|------------------------|---------------------------------------------------------------------------------------------------|
| `-m scheduled`         | Runs the service in scheduled mode (monthly executions)                                          |
| `-m external`          | Runs the service once for immediate notifications                                                |
| Environment Variables  | Configure SMTP and Elasticsearch connections                                                     |

## Environment Variable

|**ENVIRONMENT VARIABLE**|**DEFAULT VALUE**|**DESCRIPTION**|
|------------------------|-----------------|---------------|
| CONFIG_FILE | `/app/config.yaml` | Path of configuration file |
| FROM | - | From is the name of the sender from which mail will be sent |
| SMTP_USERNAME | - | Username for the SMTP server |
| SMTP_PASSWORD | - | Password of the SMTP username |
| SMTP_SERVER | - | Name of the SMTP server |
| SMTP_PORT | - | Port number on which SMTP server is listening |
| ELASTIC_USERNAME | - | Username for the elasticsearch server |
| ELASTIC_PASSWORD | - | Password of the elasticsearch server |
| ELASTIC_HOST | - | DNS name or IP of the elasticsearch server |
| ELASTIC_PORT | - | Port number on which elasticsearch is listening |

## Contact Information

| Name         | Email address          |
|--------------|------------------------|
| Rajeev  | rajeevsunny05@gmail.com |

## Reference Links

| Links | Description      |
|-----  |------------------|
| [Notification Service Repo](https://github.com/OT-MICROSERVICES/notification-service) | Source code repository |
| [SMTP Protocol Guide](https://www.cloudflare.com/learning/email-security/smtp/) | SMTP protocol documentation |
| [Elasticsearch Docs](https://www.elastic.co/guide/index.html) | Elasticsearch official documentation |

--- 















