# Hosting a Web Application with Tomcat

Hello, I am Shubham Shinde.

Today, we will learn how to host a web application using a Tomcat server. and the screenshot of my work is also available in other file

## Steps:

1. **Create an RDS Database in AWS:**
   - Launch an RDS instance and choose `mariadb-server` as the database engine.
   - Specify whether the database is for testing or production purposes.
   - Note down the database ID and password for future reference.

2. **Verify and Configure Ports:**
   - Ensure that port `3306` (used by MariaDB) is open.
   - Ensure that port `8080` (used for web applications) is open.

3. **Install and Configure MariaDB:**
   - Install the full MariaDB package on your server.
   - Check the status of the MariaDB service and ensure it is active:
     ```bash
     sudo systemctl status mariadb
     ```
   - If it is not active, start the service:
     ```bash
     sudo systemctl start mariadb
     ```

4. **Connect to MariaDB and Create a Database:**
   - Connect to the MariaDB instance:
     ```bash
     mysql -h <database-link> -u <username> -p
     ```
     Replace `<database-link>`, `<username>`, and enter the password when prompted.
   - Create a new database:
     ```sql
     CREATE DATABASE <database-name>;
     ```
     Replace `<database-name>` with your desired database name. Remember to end the command with a semicolon (`;`).

5. **Configure Tomcat:**
   - Download and install Java.
   - Download and install Tomcat.
   - Ensure Tomcat is running by accessing `http://<EC2_IP>:8080` in your web browser.
   - Place the JAR file in the `lib` directory of Tomcat.
   - Place the WAR file in the `webapps` directory of Tomcat.

6. **Edit Tomcat Configuration:**
   - Edit the `context.xml` file located in the `conf` directory of your Tomcat installation using `vim`:
     ```bash
     vim /path/to/tomcat/conf/context.xml
     ```
   - Add the RDS database username and password to the `context.xml` file.

7. **Deploy Your Application:**
   - Ensure the JAR file is placed in the `lib` directory.
   - Ensure the WAR file is placed in the `webapps` directory.

8. **Verify Deployment:**
   - Search for your application in a web browser using the URL:
     ```text
     http://<EC2_IP>/student/
     ```

## Summary

In this guide, we covered setting up an RDS database, configuring necessary ports, and deploying a web application using Tomcat. We also included steps for installing and configuring MariaDB, and modifying Tomcat configuration files to integrate with the RDS database.


