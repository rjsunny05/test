# Licence scanning Documentation





| Author      | Created on  | Version    | Last updated by | Last edited on | Internal reviewer |   L0     |    L1     |    L2   |
|-------------|-------------|------------|-----------------|----------------|-------------------|----------|-----------|-----------|
| Rajeev Ranjan    |     | version 1  | N/A        |     N/A   |     Priyanshu         | Khushi Malhotra  | Mukul Joshi     | Piyush Upadhyay  |  

## Table Of Contents
 1. [Introduction](#1-introduction)
 2. [Why License Scanning?](#2-why-license-scanning)
 3. [License Scanning Tools](#3-license-scanning-tools)
 4. [Tool Comparison](#4-tool-comparison)
 5. [Tool Recommendation](#5-tool-recommendation)
 6. [Advantages and Disadvantages](#6-advantages-and-disadvantages)
 7. [Best Practices](#7-best-practices)
 8. [[Conclusion](#8-conclusion)
 9. [Contacts Information](#9-contacts-information)
 10. [References](#10-references)

---

## 1. Introduction
- License scanning is a critical process in software development that ensures compliance with open-source and third-party licenses. It involves identifying, tracking, and managing licenses associated with dependencies used in a project.

- Integrating license scanning into Continuous Integration (CI) pipelines automates compliance checks, reducing legal risks and ensuring adherence to licensing obligations. This documentation provides a comprehensive guide on implementing license scanning in CI workflows.

---

## 2. Why License Scanning?

- **Legal Compliance:** Avoid violations of open-source licenses (e.g., GPL, MIT, Apache).

- **Risk Mitigation:** Prevent lawsuits, fines, or forced source code disclosures.

- **Security:** Some licenses may impose restrictions affecting software distribution.

- **Transparency:** Maintain an audit trail of third-party dependencies.

- **CI/CD Integration:** Automate checks to catch issues early in development.

---
## 3. License Scanning Tools

| Tool             | Description                                                                 |
|-------------------|-----------------------------------------------------------------------------|
| **FOSSA**         | Comprehensive license compliance and dependency analysis tool.             |
| **Black Duck**     | Open-source security and license compliance solution.                     |
| **WhiteSource**    | Manages open-source components and license compliance.                    |



---


## 4. Tool Comparison

| Feature / Aspect          | FOSSA                                             | Black Duck                                          | FOSSology                                          |
|---------------------------|---------------------------------------------------|----------------------------------------------------|---------------------------------------------------|
| **License Detection**     | Comprehensive across multiple languages           | Extensive across various languages and managers    | Focuses on source code analysis                    |
| **Vulnerability Scanning**| Open-source dependency scanning                    | Identifies vulnerabilities in OSS components       | Primarily license analysis, lacks security scanning|
| **Integration**           | Supports CI/CD tools, multiple workflows          | Integrates with popular DevOps tools               | Supports custom integrations through APIs         |
| **Ease of Use**           | User-friendly interface                           | Generally user-friendly                            | More technical interface                           |
| **Community Support**     | Active community support, regular updates         | Strong support, backed by Synopsys                 | Open-source with community contributions          |
| **Scalability**           | Scales for various project sizes                  | Enterprise-level scalability                       | Suitable for small to mid-sized projects          |
| **Customization**         | Flexible in reporting and policies                | Customizable policies and reporting                | Customization requires more technical expertise   |
| **Cost (Free Elements)**  | Free version with limited features                | Primarily commercial with trial options           | Open-source; support costs may apply              |



---
   


## 5. Tool Recommendation
**FOSSA** is recommended due to:

| Feature                        | Description                                                                     |
|--------------------------------|---------------------------------------------------------------------------------|
| **Multi-language Support**     | Comprehensive license detection across multiple programming languages.          |
| **Vulnerability Scanning**     | Robust scanning capabilities for identifying security risks.                   |
| **User-Friendly Interface**    | Easy navigation and seamless integration with CI/CD tools.                     |
| **Continuous Monitoring**      | Tracks and monitors changes in licenses over time for proactive compliance.    |

## 6. Advantages and Disadvantages

| **Advantages**                                      | **Disadvantages**                                   |
|-----------------------------------------------------|----------------------------------------------------|
| - Ensures legal compliance                           | - Misidentification of licenses                    |
| - Identifies license types                           | - Overhead from alerts                             |
| - Reduces legal risks                               | - License interpretation challenges                 |
| - Automated scanning                                | - Tool updates required                            |
| - Centralized documentation                          | - Dependency management                             |
| - Informed choices                                  | - Doesn’t address all compliance issues            |
| - Facilitates open source strategy                   | - Partial coverage                                 |
| - Seamless integration with CI/CD pipelines          | - Financial investment for comprehensive tools     |


---

## 7. Best Practices

| **Best Practice**           | **Description**                                                                       |
|-----------------------------|---------------------------------------------------------------------------------------|
| **Start Early**             | Include license scanning early in the development lifecycle.                          |
| **Update Databases**        | Keep license databases up-to-date.                                                    |
| **Integrate with CI/CD**     | Automate scans within the development workflow.                                       |
| **Automate Workflows**      | Use automated workflows for license approval.                                         |
| **Regular Audits**          | Regularly audit codebases for new dependencies.                                       |
| **Monitor License Changes** | Track changes as the project evolves.                                                 |

---

## 8. Conclusion
License scanning in CI ensures legal compliance and reduces risks. Automating this process improves efficiency and security while maintaining transparency in software development.

---

## 9. Contacts Information

| Name| Email Address      |
|-----|--------------------------|
| Rajeev Ranjan          |     rajeev.rajan.snaatak@mygurukulam.co |



---

## 10. References

| Tool        | Link                                                                   |
|-------------|------------------------------------------------------------------------|
| FOSSA       | [FOSSA](https://fossa.com)                                 |
| Black Duck  | [blackduck software](https://www.blackducksoftware.com) |
| POC        | [Licence scanning POC](https://github.com/avengers-p11/Documentation/blob/main/Application%20CI%20Design/Generic%20CI%20operation/Licence%20scanning/POC.md)                                     |
| WhiteSource | [whitesource software](https://www.whitesourcesoftware.com) |
