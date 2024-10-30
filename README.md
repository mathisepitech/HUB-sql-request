---
title: SQL-REQUEST
author: Mathis Liberati / Mathis Champin
date: 2024-05-04
---

# HUB-sql-request

## part 0 - Installation


Some instalattion is requiered before going further :kissing_heart:
> Don't forget the famous _sudo dnf upadate_

### Guide: Starting MySQL on Fedora
This guide explains how to start the MySQL service on a Fedora system.

  
### Steps

1. **Check MySQL Installation:** Open a terminal and run the following command to check if MySQL is already installed: 
    ``` 
    sudo dnf list installed | grep mysql
    ```

2. **Install MySQL if Needed:** If MySQL is not installed, run the following command to install it:
    ```
    sudo dnf install mysql-server
    ```

3. **Start the MySQL Service:** Once MySQL is installed, start the service using the following command:
    ```
    sudo systemctl start mysqld
    ```

4. **Check Service Status:** To verify if MySQL has started successfully, run the following command:
    ```
    sudo systemctl status mysqld
    ```
> if something green appears in ur screen that means you know how to follow a guide :clap:

5. **Enable Automatic Startup: Optional** - to have MySQL start automatically on system boot, run the following command:
    ```
    sudo systemctl enable mysqld
    ```

### Note
To get more information or for add some security features to your MYSQL service u can take a look:
[installation_mysql_fedora](https://doc.fedora-fr.org/wiki/Installation_et_configuration_de_MySQL)

But for this workshop we recommand you to do this part at the end.

### Guide: Starting MySQL WORKBENCH on Fedora
Using the intrepretor command of MYSQL can be kind of boring (we will still use it, but you will understand soon :cat:).

Lets install something more adequate to execute script sql :+1:.

### Guide: Starting MySQL WORKBENCH on Fedora
This guide explains how to start the MySQL WORKBENCH service on a Fedora system.

### Steps

1. **Check MySQL WORKBENCH Installation:**
   ```
    sudo dnf list installed | grep mysql-workbench-community
   ```
2. **Install MySQL WORKBENCH if Needed:**
  ```
  sudo dnf install https://dev.mysql.com/get/mysql80-community-release-fc36-1.noarch.rpm
  sudo dnf install mysql-workbench
  ```
3. **Launch MySQL Workbench:** Once the installation is complete, you can launch MySQL Workbench from the Fedora applications menu or by typing `mysql-workbench` in the terminal.

4. **Bind MySQL Workbench to your MySQL Service**

   Next to the _MySQL Connections__ click ont the :heavy_plus_sign:

   A window open, your only job is to enter the field `Connection name` and press ok.
   
   By doing that you create a connection to mysql workbench and your mysql service .
    
## part 1 - Create your own database / tables and insert data into

### Steps 1 create database in MYSQL

To start the terminal interace of mysql you can enter in a terminal:
```
mysql --user root
```
now create a database properly name base on the two scripts given in the `ressources` folder and print the databases freshly created
> like in C programation don't forget the ';' at the end of every command

### Steps 2 first use of  MYSQL WORKBENCH

Lets take a look at our usefull tool.

Go to the connection you early create and execute the two scripts given in the `ressources` folder

> You might have to add something to make the scripts work.

## part 2 - Simple requets - Order by

### Steps

1. Get the list of the 10 most populated cities in 2012

2. Get the list of the 50 cities with the lowest area

3. Obtain the list of overseas departments, that is, those whose department number begins with “97”

4. Obtain the name of the 10 most populated cities in 2012, as well as the name of the associated department

5. Obtain the list of the name of each department, associated with its code and the number of communes within these departments, sorting in order to obtain in priority the departments that have the most communes

6. Get the list of the 10 largest departments, in terms of area

## part 3 - More advanced request

1. Count the number of cities whose name begins with “Saint”

2. Obtain the list of cities which have a name existing several times, and sort to first obtain those whose name is most often used by several municipalities

3. Obtain in a single SQL query the list of cities whose area is greater than the average area

4. Obtain the list of departments with more than 2 million inhabitant

5.Replace the hyphens with a blank space, for all cities starting with “SAINT-” (in the column that contains capitalized names)  lol
