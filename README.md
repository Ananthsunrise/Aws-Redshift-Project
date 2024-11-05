# Aws-Redshift-Project

It is a datawarehouse.
It is used for analysis.
Database-->  frequent update, for application running
Datawarehouse --> Infrequent update, for decision making

**Architecture of Redshift :**
we sent a query from client applications.It is reaching redshift through jdbc or odbc connection. Leader node split the query and sent it to compute nodes. Compute nodes are done parellel processing of data with the help of node slides. Finally leader node takes response from compute nodes and snet to client applications.

**advantages of redshift :** 
1.easy to setup,deploy and manage.
2.scales up or down nodes quickly.
3.faster perfomance.(it supports coloumnar datastore)
4.no upfront cost
5.allows to query from datalake.

d**escription:**
In this project, we are using redshift to extract data from s3 and analyse that data.

**Step 1 : create IAM role for redshift to access s3.**
Go to IAM->Click create role->select redshift->click redshift customize->click s3 full access.

**Step 2:create cluster in redshift**
go to redshift->click create cluster->click prouction->click ra3.4x large->give 2 nodes(so total nodes 3)->give database name,admin name,password->attach IAM role->click create cluster

**Step 3 : uploade sample file in s3**
go to s3->click create bucket->disable all public aacess->upload above attached  files which contain user data and venue->clcik permissions->choose individual ACL permissions->select everyone read access ->click acknowledgement that means i understand->click create

**Step 4 : extract dat from s3 using query**
Go to AWS redshift ->Go to created cluster->click  change connection->click connect database->select public schema->create 2 tables according to files upload in s3 using the attached query.->execute copy queries to extract data.

Now you can successfully extracted data from s3 and uploades in this tables.
