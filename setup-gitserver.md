
In this example we will take 2 servers 
1 Local and 1 Remote git servers

Install git on both Local as well as Remote servers 

    yum install git -y 

logged-in to local Machine as ec2-user
 
    ssh-keygen -t rsa
 
 First make your own server password/key less
 
    cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
    ssh ec2-user@ip-172-31-18-250
    chmod 700 singaporekeypair.pem
    scp -i singaporekeypair.pem -r ~/.ssh* ec2-user@172.31.22.112:~/
    ssh ec2-user@172.31.22.112

On server (as user ec2-user) 172.31.22.112:

    mkdir new-project.git
    cd new-project.git
    git init --bare

On the local Machine (as user ec2-user) 172.31.18.250: 
    
    mkdir new-project
    cd new-
    cd new-project/
    ls
    git init
    touch a
    git add .
    git commit -m "initial release"
    git remote add origin  ssh://ec2-user@172.22.112:/home/ec2-user/new-project.git/
 
 Go to the Git Server
    
    git log 
    

