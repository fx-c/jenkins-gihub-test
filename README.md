# jenkins-gihub-test
#just for testings
What is Docker?                :
====================
Docker is a software use to create docker images and run containerized  apps. 

Docker is used by Developers, Administrator and others to build 
    and run applications as containers.

Docker Editions:
    Docker CE --> Comunity Edition --> Open Source(Free)
    Docker EE --> Enterprise Edition --> Commercial

Type: Containerization
Vendor: Docker INC

O.S --> Cross Platform(Docker can be installed in any O.S)

    Docker Can Be Installed in Linux, Windows OS, mac OS  

Docker CE Can be installed in Most of the linux except redhat.

Docker EE can installed in all O.S including redhat.

Docker CE --> OpenSouce Free

Docker EE --> Commerical :
   DTR --> Docker Trusted Registry(Private Repo to main docker images)
   UCP --> Universal Control Plane --> It's GUI for managing Docker Machines

Containerzation Platforms/Softwares.     :
    Docker,  = 80%
    CoreOS,
    Rocket --> 

Dockerfile     --> It's a file used to create docker images.

Docker Image  It's a package which contains
    application Code e.g ebay.war 
       and
    It's dependencies(Softwares, ENV Vars ..etc)
                     
Docker Container--> It's runtime instance of docker image
                    where our application is running.
     The standard unit where the application service is deployed or running.


DockerRepo/Registry. --> We can store and share the docker images.   

    Public Repo --> Docker hub is It is generally a public repo. 
                Which contains all the open source softwares as 
        a docker images. We can think of docker hub as play store for docker images.


    Private Repo(Nexus,JFrog,D.T.R(Docker Trusted Registory)) --> 
            We can store and share the docker images with in our company
        network using private repo
        
 PaaS  = 
 IaaS  = EC2
 SaaS  = DockerHub, New Relic, GitHub, 

Docker Enigine/Daemon/Host --> It's a software or program using which we can 
                               create images & RUN contianers.

Docker is cross platform.

Docker CE
   Docker CE will not be supported by Redhat.
   
   

Docker EE
  Docker EE will be support most of the os including redhat.

      
First Create Account in docker hub
https://hub.docker.com

What is docker hub?
It's a public repository for docker images. You can think as play store for
docker images.

Install Docker on AWS Ubuntu
############################
#!/bin/bash
sudo apt update -y 
sudo apt install docker.io -y
sudo usermod -aG docker ubuntu 

NB: apt and apt-get are package managers for ubuntu servers 
sudo docker info

ssh -i "key23.pem" ubuntu@ec2-18-222-184-232.us-east-2.compute.amazonaws.com  

https://github.com/LandmakTechnology/maven-web-app/blob/master/ansible-setup

# Check docker is installed or not
   docker info

# You will get permison denied error as regular user 
    dosn't have permisions to execute docker commands.Add user to docker group.

sudo usermod -aG docker $USER 
or 
sudo usermod -aG docker ubuntu

sudo usermod -aG docker simon

# Exit From Current SSH Terminal & SSH(Login) again.Then execute 
docker ps

Install Docker on AWS RHEL
############################
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
sudo dnf install docker-ce-3:18.09.1-3.el7 -y
sudo systemctl enable docker
sudo systemctl start docker


sudo docker info
adduser simon

# Check docker is installed or not
docker info

# You will get permison denied error as regular user dosn't have permisions to execute docker commands.Add user to docker group.

sudo usermod -aG docker $simon 
sudo usermod -aG docker ec2-user

# Exit From Current SSH Terminal & SSH(Login) again .Then execute 
docker ps

# Amazon Linux 2
================
sudo yum update -y		
sudo yum install docker -y
sudo systemctl start docker

Add Regural user to dockergroup
sudo usermod -aG docker  <username>

ex:
sudo usermod -aG docker ec2-user

Once you add user to group exit from the server and login again.
# Get docker information
docker info

#Install Docker in Linux (Works for most of linux flavors).
sudo curl -fsSL get.docker.com | /bin/bash


Docker Home/Working Dir: 
/var/lib/docker

Dockerfile   --> It's file which will have instructions to create docker image.
# Sample DockerFile Content

FROM tomcat:8-jdk8-corretto
COPY target/*.war /usr/local/tomcat/webapps/myapps.war

FROM tomcat:9.0.40-jdk8
# Dummy text to test 
COPY target/myapps.war /usr/local/tomcat/webapps/myapps.war

docker run --name myapps -d -p 8080:8080 myapp:1  

http://18.212.175.83:8080/maven-web-app/

docker create 

Docker Image -->  	It's a pacakage which will have all application code and 
                    required softwares 
                    plus configurations 
                    for your application to deploy.

Docker Container --> It's runtime instance of a docker image where application will be running.
