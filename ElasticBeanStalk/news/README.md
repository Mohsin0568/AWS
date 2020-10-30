# Install elasticbeanstalk cli using below command
brew install awsebcli

# Configue elasticbeanstalk using below cli
####Below command should be run in the project directory.
eb init
Select region, platform and application name

# Create environment 
Config.yaml file will be created in folder .elasticbeanstalk, update the file and add deploy step and specify jar file.

eb create
Enter environment name and load balancer type.
 
