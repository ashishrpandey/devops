# Steps to install maven 

Tested on AWS ec2-instance running on Amazon Linux 2 AMI

    sudo su 
    wget https://www-us.apache.org/dist/maven/maven-3/3.6.2/binaries/apache-maven-3.6.2-bin.tar.gz -P /tmp

    sudo tar xf /tmp/apache-maven-3.6.2-bin.tar.gz -C /opt
    sudo ln -s /opt/apache-maven-3.6.2 /opt/maven
    sudo echo "
      export JAVA_HOME=/usr/lib/jvm/jre-openjdk
      export M2_HOME=/opt/maven
      export MAVEN_HOME=/opt/maven
      export PATH=${M2_HOME}/bin:${PATH}
      " >/etc/profile.d/maven.sh

    sudo chmod +x /etc/profile.d/maven.sh
    source /etc/profile.d/maven.sh


Go to your maven-project's directory and check if the maven is working:

    mvn -version



