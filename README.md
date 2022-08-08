sqlg  repository for tutorial

[![Docker Build status](https://img.shields.io/docker/build/saastoolset/sqlg-airflow?style=plastic)](https://hub.docker.com/r/saastoolset/sqlg-airflow/tags?ordering=last_updated)


[![Docker Hub](https://img.shields.io/badge/docker-ready-blue.svg)](https://hub.docker.com/r/saastoolset/sqlg-airflow/)
[![Docker Pulls](https://img.shields.io/docker/pulls/saastoolset/sqlg-airflow.svg)]()
[![Docker Stars](https://img.shields.io/docker/stars/saastoolset/sqlg-airflow.svg)]()

This repository contains **Dockerfile** of [apache-airflow](https://github.com/apache/incubator-airflow) for [Docker](https://www.docker.com/)'s [automated build](https://registry.hub.docker.com/u/saastoolset/sqlg-airflow/) published to the public [Docker Hub Registry](https://registry.hub.docker.com/).




***
# 1. The proposed environment 
Follwing step will assume those tools are installed

- [Docker](https://www.docker.com/products/docker-desktop/) as container tool
- [Visual Code](https://code.visualstudio.com/download) as IDE
- sqlg as ETL transformation tools

# 2. Envirioment preparation

## 2.1. Create github repo by fork

1. [create fork from sqlg-tutor](https://github.com/saastoolset/sqlg-tutor/fork)

2. Clone sqlg-tuto from github
  - Suggest directory as C:\Proj\saastoolset\sqlg-tutor
   
3. Pull image 

    C:> docker pull mcr.microsoft.com/mssql/server
  
# 3. Database install and run script


## 3.1 Start container 

### 3.1.1. Windows
- Start by option and open in browser, e.g. tutorial model
    
    C:> docker run --name mssql-h1 -d -p 1433:1433 -e "MSSQL_SA_PASSWORD=MyPassw0rd" -e "ACCEPT_EULA=Y" mcr.microsoft.com/mssql/server

### 3.1.2. Linux
- Start by option and open in browser, e.g. tutorial model    
    $ docker run --name mssql-h1 -d -p 1433:1433 -e 'MSSQL_SA_PASSWORD=MyPassw0rd' -e 'ACCEPT_EULA=Y' mcr.microsoft.com/mssql/server

### 3.1.3. Mac
- Start by option and open in browser, e.g. tutorial model    
    $ docker run --name mssql-h1 -d -p 1433:1433 -e 'MSSQL_SA_PASSWORD=MyPassw0rd' -e 'ACCEPT_EULA=Y' mcr.microsoft.com/mssql/server

## 3.2 Connect by sql client
- Use SSMS in MSSQL
    ServerName: 127.0.0.1
    Authentication: SQL Server Authentication
    Login: sa
    Password: MyPassw0rd

## 3.3 Build SQLEXT

  SQLEXT use for ETL date conversion function when call from stored procedure from scheduler.

### 3.3.1 Create database and Sehema from sql client tool
- For tutorial, create DB name as Tutor, schema SQLEXT and TRN are requried
- For implementation project setup, schema will mapping to data zone.

### 3.3.2 Install SQLEXT from sql client tool

- schema.ddl, Create schema for all data zone
- holiday.ddl, Holiday table for working calendar
- fn_AddBusinessDays.sql, Business day function on working calendar
- etldate.sql, ETL date function for SQLG macro
- sp_drop_if_exists.ddl, Drop if function for MSSQL


## 3.4 Install tutorial
Open doc/

### 3.4.1 Build training data
- Verify by sql client 
- Verify tutorial excel


### 3.4.2 Build studend list
- Collect studend list
- Build studend list

# 4. Conduct Training
## 4.1 For instructor

## 4.2 For student

# 5. SQLG in db to db


# 6. SQLG in web application

# 7. SQLG in Data Vault

# 7. SQLG in dbt

# 8. Wanna help?

Fork, improve and PR.
