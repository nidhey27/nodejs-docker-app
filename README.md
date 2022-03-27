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
3. Accessing Jenkins
By default jenkins runs at port 8080, You can access jenkins at
```
YOUR-INSTANCE-PUBLIC-IP:8080
# Exmaple: 192.168.x.x:8080
```
4. Configure Jenkins
* The default Username is `admin`
* Grab the default password
* Password Location: `/var/lib/jenkins/secrets/initialAdminPassword`
* Install Suggested Plugins
* Create another admin user id


## Let's install nvm in AWS EC2 using the command
```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash

After that,you need to activate the nvm to use it. activate the nvm using the command,

. ~/.nvm/nvm.sh

nvm install node

## Install Docker
sudo yum update
sudo yum install docker
sudo systemctl enable docker.service
sudo systemctl start docker.service
sudo systemctl status docker.service
```

```
# Setup User to UserGroup
sudo usermod -a -G docker $USER

# Delete All Running Conatiners and Images
docker stop $(docker ps -a -q)
docker rm $(docker ps -a -q)
```
