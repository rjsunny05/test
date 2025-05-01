# REDIS POC

| Author          | Created on | Version   | Last updated by | Last edited on | Internal Reviewer | L0     | L1      | L2     |
|-----------------|------------|-----------|------------------|----------------|--------------------|--------|---------|--------|
| Rajeev Ranjan | 1-05-25   | version 1 | N/A              | N/A            | Priyanshu          | Khushi Malhotra | Mukul Joshi| Piyush Upadhyay|

## Table of Contents

1. [What is Redis](#what-is-redis)  
2. [Pre-requisites](#pre-requisites)  
3. [Software Overview](#software-overview)  
4. [System Requirements](#system-requirements)  
5. [Important Ports](#important-ports)  
6. [Redis Installation on Ubuntu](#redis-installation-on-ubuntu)  
7. [Contact Information](#contact-information)  
8. [References](#references)

## What is Redis

The purpose of this POC is to evaluate Redis as a caching solution for the application, testing its performance, scalability, and integration capabilities.
To read more about redis you can take a look on this documentation [redis](link)

## Pre-requisites

Before diving into the Installation of scyllaDB, let’s ensure the following prerequisites meet as its requirements.

## Software Overview
|                  |         |
|:----------------:|:-------:|
| **Software Name:**| Redis|
|**Version:**| 6.x or higher recommended|

## System Requirements
| **Requirements** | **Details** |
|---------|---------|
| OS |  Ubuntu 22.4 |
| Vm type | t2 micro |
| Disk space | 100 MB or more |

## Important Ports

| Port | Description      |
| :--- | :--------------- |
| 6379 | Used by Redis |

## Redis Installation on Ubuntu

This guide provides the steps to install and configure Redis on Ubuntu.



## Installation Steps

### Step 1: Update System Packages

Before starting the installation, ensure your system packages are up-to-date.

``` bash
sudo apt update
```
### Step 2: Install Redis

To install Redis, use the apt package manager

``` bash
sudo apt install redis-server -y
```
![Image](https://github.com/user-attachments/assets/72b89f48-3c59-49f7-9081-2488a7458c89)

### Step 3: Start Redis Service
Run the following command to start the Redis service:

``` bash
sudo systemctl start redis-server
sudo systemctl enable redis-server
```
### Step 4: Check Redis Service Status
To confirm that Redis has started successfully, use the following command:

``` bash
sudo systemctl status redis-server
```
![Image](https://github.com/user-attachments/assets/9f869f9d-c3fa-449b-ace3-19ce867c1fae)

### Step 5. Stop Redis Service
To stop the Redis service, run:

``` bash
sudo systemctl stop redis-server
```
### Step 6: Configure Redis
To set up a password and username for Redis, follow these steps:
#### 1. Open the Redis configuration file:

``` bash
sudo vi /etc/redis/redis.conf
```
#### 2. Set a Password:
Find the line with # requirepass foobared and replace it with:

``` bash
requirepass <your_password_here>
```

#### 3. Configure a Username: 
For Redis 6.x and above, you can set up a username with Access Control Lists (ACLs). Add this to the redis.conf file:

``` bash
user <user_name> on ><your_password> ~* +@all
```
- *<user_name> is the username* 
- *<your_password> is the password*
- *~* allows access to all keys*
- *+@all grants full command permissions to this user*

![Image](https://github.com/user-attachments/assets/624470a9-81fb-4263-b858-5871dcc28a42)

#### 4. Save and Close the file.

#### 5. Restart Redis
To apply these changes, restart the Redis service:

``` bash
sudo systemctl restart redis
```


#### 6. Connect to Redis with Username and Password
Now, you can authenticate to Redis using both a username and password.

Start the Redis CLI:

``` bash
redis-cli
AUTH <user_name> <your_password>
```
![Image](https://github.com/user-attachments/assets/9ab592a9-3015-47ab-8d7a-17f48ef93f52)


#### 7. Verify the Connection: 
After authenticating, you can test the connection by running a simple command PING:

``` bash
PING
```
If you see PONG, it means authentication was successful.

![Image](https://github.com/user-attachments/assets/14a8ab9a-c207-4258-8d14-e83879d19883)




### Contact Information

| Name         | Email address          |
|--------------|------------------------|
| Rajeev Ranjan          |     rajeevsunny05@gmail.com |

 
### References

| Link                                                                                                           | Description                                               |
|---------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|
| [Redis Documentation - Linux Installation](https://redis.io/docs/latest/operate/oss_and_stack/install/install-redis/) | Document format followed from this link.                 |
| [Introduction vs. Overview](https://backendless.com/redis-what-it-is-what-it-does-and-why-you-should-care/) | This link explains the difference between Overview & Introduction. |
| [Redis Documentation - GitHub](https://github.com/avengers-p11/Documentation/tree/main/OT%20MS%20Understanding/Redis/Redis%20Documentation) | Link to Redis documentation on GitHub. 
