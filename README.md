# Data Migration Tool Guide

This document will describe how to use the Data Migration Tool to migrate data from a dummy database into OpenMRS.

## Step 1. Build The Data Migration Tool

Clone the DMT repo and build it.

````
  $ git clone https://github.com/esaude/data-migration-system.git
  $ cd data-migration-system
  $ mvn clean install
````

## Step 2. Install OpenMRS 1.11.3

Download the [OpenMRS WAR file](http://sourceforge.net/projects/openmrs/files/releases/OpenMRS_Platform_1.11.3/openmrs.war/download) and deploy it to Tomcat.

## Step 3. Prepare Dummy Database

Import the dummy database.

````
  $ mysql -uroot -p
  mysql> create database dummy;
  mysql> use dummy;
  mysql> \. resources/dummy-database-dump.sql
````

