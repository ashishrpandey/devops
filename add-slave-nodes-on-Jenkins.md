## Adding a slave/node/Agent

# Also refer to this link:
https://docs.aws.amazon.com/aws-technical-content/latest/jenkins-on-aws/worker-nodes.html

## Delegation for tasks between master and agent is fairly automatic
## However you can dictate if you want a particular agent for specific job

        su jenkins -s /bin/bash
        ssh-keygen
       Generating public/private rsa key pair.
       Enter file in which to save the key (/var/lib/jenkins/.ssh/id_rsa):
       Created directory '/var/lib/jenkins/.ssh'.
       Enter passphrase (empty for no passphrase):
       Enter same passphrase again:
       Your identification has been saved in /var/lib/jenkins/.ssh/id_rsa.
       Your public key has been saved in /var/lib/jenkins/.ssh/id_rsa.pub.
       The key fingerprint is:
       8d:47:14:dd:6f:a7:47:2a:7c:f9:1c:e2:b7:33:6c:e7 jenkins@ip-172-31-26-59
       The key's randomart image is:
       +--[ RSA 2048]----+
       |          oo .   |
       |         .  . .  |
       |          .    . |
       |         +      =|
       |        S o.   *.|
       |         .  o.=..|
       |            .oo+.|
       |             . *+|
       |              ooE|
       +-----------------+
       bash-4.2$ cat /var/lib/jenkins/.ssh/id_rsa.pub
       ssh-rsa *****key***


## Create a slave server
- ssh to slave

       sudo su
       useradd -d /var/lib/jenkins jenkins
       mkdir /var/lib/jenkins/.ssh
       vi /var/lib/jenkins/.ssh/authorized_keys
       --- Copy the earlier generated key from master ----
       install java on this slave

       rpm -Uvh jdk-8u121-linux-x-64.rpm
       alternatives --install /usr/bin/java java /usr/java/latest/bin/java 200000
       alternatives --install /usr/bin/javac javac /usr/java/latest/bin/javac 200000
       alternatives --install /usr/bin/jar jar /usr/java/latest/bin/jar 200000
vi /etc/rc.local
--
export JAVA_HOME="/usr/java/latest"
--

## Go to master
manage-jenkins->manage nodes->new node
--give a name to slave and add as permanent agent
configure slave:
Remote root directory: /var/lib/jenkins
