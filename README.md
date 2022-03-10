# Install Jenkins on AWS EC2

## Prerequisites
1. EC2 Instance
    * With Internet Access
    * Security Group with Port 8080 open for internet
2. Java 11 should be installed

## Install Jenkins

1. Get the latest version of jenkins from https://pkg.jenkins.io/redhat-stable/ and install
```
sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
sudo amazon-linux-extras install epel 
sudo amazon-linux-extras install java-openjdk11 

# On CentOS 
sudo yum install epel-release # repository that provides 'daemonize'
sudo yum install jenkins
```
2. Start Jenkins
```
# Start jenkins service
sudo service jenkins start

# Setup Jenkins to start at boot,
sudo chkconfig jenkins on
```
