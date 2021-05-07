
## Create first-repo  

      svnadmin create /var/www/svn/first-repo

- Here we need to put some code in the repo

Download and import the code 

      cd ~
      yum install git -y
      git clone https://github.com/ashishrpandey/maven-project/
      svn import ~/maven-project file:///var/www/svn/first-repo/maven-project  -m "initial import"
      svn checkout file:///var/www/svn/first-repo/maven-project maven-project


Refresh the browser - A new version must be visible 
