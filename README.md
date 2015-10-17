# Data Migration Tool Guide

This document will describe how to use the Data Migration Tool or Data Import Tool to migrate data from a dummy database into OpenMRS.

## Instructions

### Step 1. Build The Data Migration Tool

Clone the DMT or DIT repo(s) and build it.

````
  $ git clone https://github.com/esaude/data-migration-system.git
  $ cd data-migration-system
  $ mvn package
This command generates a zip file for the data-migration-system.

 OR
  $ git clone https://github.com/Ch3ck/openmrs-module-dataimporttool.git
  $ cd openmrs-module-dataimporttool
  $ mvn clean install 
  
  Refer to module README for further instructions.
````

### Step 2. Install OpenMRS 1.11.3

Download the [OpenMRS WAR file](http://sourceforge.net/projects/openmrs/files/releases/OpenMRS_Platform_1.11.3/openmrs.war/download) and deploy it to Tomcat.

### Step 3. Prepare Dummy Database

Import the dummy database.

````
  $ mysql -uroot -p
  mysql> create database dummy;
  mysql> use dummy;
  mysql> \. resources/source_medical_dummy.sql
````

### Step 4. Complete The Mapping Spreadsheet

The mapping sheet we are using can be download from _ROOT_DIR/resouces/dummy-data-mapping-version.xls

Once the mappings have been correctly specified and the file has been downloaded and saved. Update the `file_name` and `location` values in the [`config.xml`](https://github.com/esaude/data-migration-system/blob/master/src/main/resources/config.xml) file.

Or Specify their locations in the migrations settings page for the DIT Module


### Step 4. Linux Users Only

I 1.) Install the MySQL/Mariadb java connector/driver[MariaDB Connector](https://code.mariadb.com/connectors/java/).
      Alternatively you can copy the mariadb connector.jar files to the appropriate /usr/lib/java*/jre/lib/ext/ directory
  
  2.) Modify the [`config.xml`](https://github.com/esaude/dmt-guide/tree/master/resources/config.xml)(eSaude DMT Tool Only)


### Step 5. Run The DMT

Execute the jar file `PROJECT_ROOT\data-migration-system-1.0-SNAPSHOT.jar` located in `PROJECT_ROOT\data-migration-system-[VERSION]`. Run the command `java -jar data-migration-system-[VERSION].jar`

For further Instructions running the DIT Module consult the README of the module.

## Resources

1.) [Google Sheets](https://docs.google.com/spreadsheets/d/1ljn2hyf9Qk3IFfQWYiCmuwgJxDWn2hnzX4m2dLhR0mk/edit#gid=1416522886)

2.) [MariaDB Connector](https://code.mariadb.com/connectors/java/)

3.) [Sample Linux Config](https://github.com/esaude/dmt-guide/tree/master/resources/config.xml)

If you have any further questions send an email to ch3ck [at] openmrs [dot] org 

### Documentation

The docs can be downloaded from [the OpenMRS DMT wiki page](https://wiki.openmrs.org/pages/viewpageattachments.action?pageId=80379983).

