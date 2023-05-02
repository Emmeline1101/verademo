If you are having trouble installing Docker,you will need to install the dependencies
manually.

## Installing MariaDB

1. Download MariaDB from https://mariadb.com/downloads/community/

2. Run MySQL Client for MariaDB

   > You should search for `MySQL Client (MariaDB 10.11 (x64))`

3. Create database named blab and select this database

   ```
   CREATE DATABASE blab;
   use blab;
   ```

4. Run commands from `db` to create the tables

   > Copy the commands and paste them into the terminal.

## Installing Java, Maven

1. Install Java JDK 8 from https://docs.aws.amazon.com/corretto/latest/corretto-8-ug/downloads-list.html

   > make sure you are running the correct Java version via `java -version`
   > You may need to edit environment variable to use the specified Java version.

2. Install Maven following instructions on https://maven.apache.org/install.html

## Building the project

1. Navigate to `app` directory, and compile the project with

   ```
   mvn clean package
   ```

2. Run the project via

   ```
   mvn spring-boot:run
   ```

3. Navigate to `http://localhost:8080` and explore the project.
