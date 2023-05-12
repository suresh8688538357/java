# Spring Boot MySQL Example

Pre-requisitess:

1. Set up a VM with Ubuntu 20.04 
2. Update and upgrade packages
```
apt-get update 
apt-get upgrade
```
3. Navigate to root
```
sudo su
```
4. Install GIT
```
apt install git
```
5. Install JAVA 1.8.0
```
apt-get install openjdk-8-jdk
```
6. Install MAven
```
apt-get install maven
```
7. Install MYSQL server
```
apt-get update
apt-get install mysql-server
systemctl start mysql.service
```
8. Install MySQL Client
```
apt-get install mysql-client
```
9. Configure root username and password for MYSQL

```mysql
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password123';
exit
```


Setup Database:
1. Connect to MYSQL server and create below database
```
mysql -uroot -ppassword123
CREATE DATABASE springboot_mysql_example;
SHOW DATABASES;
exit
```
Application Build and Deployment:
1. Clone source code in to ubuntu machine
2. Configuration changes in application properties files
Navigate to "application.properties" file and open
```
cd spring-boot-mysql-example/src/main/resources/
vi application.properties
```
Ensure below entries have correct MYSQL Connection credentials:

_spring.datasource.url= jdbc:mysql://localhost:3306/springboot_mysql_example?useSSL=false_  
_spring.datasource.username= root_  
_spring.datasource.password= password123_  

SAVE the file and EXIT


3. Build the application
Navigate to root folder of the application. Change path location according to your machine
```
cd spring-boot-mysql-example
mvn install
```
Expected Output:
[INFO] BUILD SUCCESS

4. Validate build
Navigate to target folder
```
cd spring-boot-mysql-example/target
JAR file (spring-boot-mysql-0.0.1-SNAPSHOT.jar) must present in Target folder
```
5. RUN JAR File
```
cd spring-boot-mysql-example/target
java -jar spring-boot-mysql-0.0.1-SNAPSHOT.jar
```
Expected Output:
Started SpringBootMySqlApplication in 6.593 seconds (JVM running for 7.206)


6. Browse Application:
http://192.168.200.135:8080/
Change IP to Ubuntu machine IP



