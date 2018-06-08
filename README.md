# mule4-skeleton-mysql-project
This is an example application that can be used as a template for building a Mule 4.1 MySql application. This application has a scheduled flow that selects undeleted records from one table and inserts them into another table.

Note, the scope features of minimal-logging are not displayed correctly by Studio 7.1 or 7.2. Support for displaying SDK connector scopes is expected in Studio 7.3.

## Uses

The project contains examples using:

* Database connector with MySql (MariaDB)
* The minimal-logging connector, 
* The secure property connector (formally called the secure-property-placeholder),
* Maven deployment using the mule-maven-plugin descriptor.

## Purpose
This project is an example only. It contains a scheduling component to periodically (every ten minutes), use the minimal-logging operations to generate a new transaction id, display three (enter, warning and exit) log messages.


## Runtime properties

The properties mule.env and mule.key need to be set in the Mule runtime in order for the property configurations to be located. 
For Studio, add the following VM command line values when running the API:

 -Dmule.env=local -Dmule.key=Mulesoft12345678

## Maven Settingss

The Mule deployment assumes that certain deployment properties will come from profiles specified when the mvn command is executed. An example-settings.xml is provided as a reference
for creating your own settings.xml file. This is a standard feature of Maven and is described in its online documentation. Once the settings.xml file has been created, export a u and a p shell environment variables containing your Anypoint user name and password. Then use this maven command to deploy the API project:

```
mvn clean install deploy -Denv=xxx -DmuleDeploy
```
Replacing the xxx's with the appropriate values.
