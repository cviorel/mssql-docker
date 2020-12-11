
# Overview

* Build a docker image based on Ubuntu 18.04 running SQL Server 2019
* Review the `ag.sql` with the T-SQL you want to run after SQL Server has started

# How to Run
## Clone this repo
```
git clone https://github.com/cviorel/mssql-docker.git
```
## Modify the dockerfile
Modify the `linux\dockerfile` to specify if you want to build 3 nodes, or only one node
By default we're building a 3 nodes Availability Group

## Modify the .sql files
Modify the `linux\ag.sql` file with the TSQL that you want to customize the SQL Server container with

## Build the image 
Build with `docker build`:
```
cd mssql-docker
docker build -t mssql2019-custom -f linux/dockerfile .
```

## Run the container

Then spin up the 3 node AG build run:
```
docker-compose up -d
```

Note: MSSQL passwords must be at least 8 characters long, contain upper case, lower case and digits.  
