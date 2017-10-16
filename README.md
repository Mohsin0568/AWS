# Aws-tutorial
Steps to start Tomcat and Deploy Java Application

Create EC2 Instance and assign below Security Groups:
1) Custom TCP Rule with Port Range 8080
2) SSH
3) HTTP

Launch EC2 Instance and Run below Commands

# Check Yum Updates
1) sudo su
2) yum list installed
3) yum update

# Install Java8
1) yum install java-1.8.0
2) yum remove java-1.7.0-openjdk

# Install Tomcat8
yum install tomcat8 tomcat8-webapps tomcat8-admin-webapps tomcat8-docs-webapp

# Edit Tomcat configuration files to setup admin User
cd  /usr/share/tomcat8
vim /usr/share/tomcat8/conf/tomcat-users.xml

