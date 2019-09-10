General procedure to install Jenkins:


## Summary of setting up Jenkins 
Check the version of java installed on you machine

          $java -version  ## Check if Java is already installed
          
For jenkins Java 8 is required.
- In java is not installed, install the developemnt version of JDK 1.8.0 

          yum install java-1.8.0-openjdk-devel.x86_64 -y 
          
- install some other utilities for Lab (#optional)

          yum install git tree docker -y 
- Download Jenkins from www.jenkins.io/download for your platform
- Install Jenkin
- Launch Jenkin
- It shall open in web-browser at localhost:8080 
- Enter initial passowrd on the first page.
- Change admin password 
- Your Jenkin Dashboard is ready
- Explore it !!!

# Step-by-step installation of Jenkins on ec2 instances 

          yum update -y
          wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins-ci.org/redhat-stable/jenkins.repo  ## Add jenkins in yum repo
          rpm --import http://pkg.jenkins-ci.org/redhat-stable/jenkins-ci.org.key  ##download the key necessary for proper installation
          yum install jenkins  -y        ## install Jenkins
          service jenkins start       ## Start Jenkins
          chkconfig jenkins on        ## Check if Jenkins is working
          cat /var/lib/jenkins/secrets/initialAdminPassword           ## Get the initial admin password gor first login
                    ##use the content of file for initial admin password

If not done already - 

- Edit security group inbound rules
  Add rules for:
   - http at port number 80
   - and "custom tcp rule" at port number 8080

In web browser open : <public ip>:8080    ## e.g 172.13.0.2:8080
- We will get jenkins dashboard:
- Login as admin with the password from (/var/lib/jenkins/secrets/initialAdminPassword).
- Change password.
- Create new user. ##optional


# Connecting it with github webhook 

- To trigger builds every time some code is checked-in to the git, follow below steps:
- At Jenkins:
- In configuration of the project at jenkins under "build trigger" section select "GitHub hook trigger for GITScm polling"
- At github sever:
- Open your github account --> select the project repository -- > opent setting page of the repo --> select web-hooks tab
--> add webhook --> enter in Payload URL folowing URL:   http://<Name of Jenkins server>:8080/github-webhook/  
--> select "just the push event" 


# Setup maven tool 
- maven needs to be installed. If not refere to link https://github.com/ashishrpandey/devops/blob/master/settingup-maven-latest-release.md


- manage jenkins---> 
- configure global tools --> 
- add Java jdk--> 
- add maven home --> 
- add git -->
- in the build step write
          clean package


# Installation steps for ubuntu Machine 

          wget -q -O - https://pkg.jenkins.io/debian/jenkins-ci.org.key | sudo apt-key add -
          sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
          sudo apt-get update
          sudo apt-get install jenkins

