# Start Tomcat Server in AWS Linux EC2 Instance
Steps to start Tomcat and Deploy Java Application

## Create EC2 Instance and assign below Security Groups:
1) Custom TCP Rule with Port Range 8080
2) SSH
3) HTTP

### Launch EC2 Instance and Run below Commands

## Check Yum Updates
```
sudo su
yum list installed
yum update
```

## Install Java8

This step can be skipped if Java8 is already installed. Check for Directory **java-1.8.0** at location **usr/share**. If **java-1.18.0** is already available then skip Java8 installation.

```
yum install java-1.8.0
```

## Install Tomcat8
```
yum install tomcat8 tomcat8-webapps tomcat8-admin-webapps tomcat8-docs-webapp
```

## Edit Tomcat User files to setup admin User
```
cd  /usr/share/tomcat8
vim /usr/share/tomcat8/conf/tomcat-users.xml
```
Add below line in tomcat-users tag
```
<user name="admin" password="YOURPASSWORD" roles="admin,manager,admin-gui,admin-script,manager-gui,manager-script,manager-jmx,manager-status" />
```

## Start Tomcat Service
```
service tomcat8 start
service tomcat8 status
```

## Set Tomcat Server as Auto Start
Run below command to start Tomcat Server automatically when EC2 instance is restarted
```
sudo chkconfig --list tomcat8
sudo chkconfig tomcat8 on
```
