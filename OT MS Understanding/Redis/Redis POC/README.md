# REDIS POC

| **Author** | **Created on** | **Version** | **Last updated by** | **Last edited on** |
|------------|----------------|-------------|----------------------|---------------------|
| Anugra .W. Lepcha       | 11-11-24      | version 1   | Anugra .W. Lepcha                | 12-11-24           |



## REDIS

The purpose of this POC is to evaluate Redis as a caching solution for the application, testing its performance, scalability, and integration capabilities.

## Redis Setup Prerequisites

| **Requirement**        | **Details**                  |
|------------------------|------------------------------|
| **OS**                 | Ubuntu or other Linux-based OS |
| **RAM**                | 2 GB minimum                 |
| **Disk Space**         | 100 MB or more               |
| **Processor**          | Dual-core recommended        |
| **Network**            | Port 6379 open               |
| **Redis Version**      | 6.x or higher recommended    |

## Redis Installation on Ubuntu

This guide provides the steps to install and configure Redis on Ubuntu.

## Prerequisites

- Ubuntu 20.04 or later
- A user with `sudo` privileges

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
![alt text](image.png)
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
![alt text](image-1.png)
### 5. Stop Redis Service
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
#### 2. Set a Password::
Find the line with # requirepass foobared and replace it with:

``` bash
requirepass <your_password_here>
```

#### 3.(Optional) Configure a Username:
For Redis 6.x and above, you can set up a username with Access Control Lists (ACLs). Add this to the redis.conf file:

``` bash
user <user_name> on ><your_password> ~* +@all
```
- *<user_name> is the username* 
- *<your_password> is the password*
- *~* allows access to all keys*
- *+@all grants full command permissions to this user*

#### 4. Save and Close the file.

 #### 5.Restart Redis
To apply these changes, restart the Redis service:

``` bash
sudo systemctl restart redis
```
![alt text](image-2.png)
#### 6. Connect to Redis with Username and Password
Now, you can authenticate to Redis using both a username and password.

Start the Redis CLI:

``` bash
redis-cli
AUTH <user_name> <your_password>
```
![alt text](image-3.png)

#### 7. Verify the Connection: 
After authenticating, you can test the connection by running a simple command PING:

``` bash
PING
```
If you see PONG, it means authentication was successful.
![alt text](image-4.png)

### Contact Information

| **Name** | **Email address**            |
|----------|-------------------------------|
| Anugra .W. Lepcha    |  wangchuklepcha801@gmail.com           |

 
### References


Link                                                                                       | Description                                              |
|--------------------------------------------------------------------------------------------|----------------------------------------------------------|
| [Redis Documentation - Linux Installation](https://redis.io/docs/latest/operate/oss_and_stack/install/install-redis/) | Document format followed from this link.                 |  
| [Introduction vs. Overview](https://backendless.com/redis-what-it-is-what-it-does-and-why-you-should-care/) | This link explains the difference between Overview & Introduction. |