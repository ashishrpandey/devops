 
 Be in the root mode 
 
    sudo su
  
  Install svn, apache and mod_dav_svn
  
    yum update -y 
    yum install subversion -y
    mkdir -p /var/www/svn
    cd /var/www/svn
    yum install httpd mod_dav_svn -y 
    chown -R apache:apache /var/www/svn
    chmod -R 755 /var/www/svn
    
    
  Create a file 
 
    vi /etc/httpd/conf.modules.d/10-subversion.conf

Populate it with the content below - 

    LoadModule dav_svn_module modules/mod_dav_svn.so
    LoadModule authz_svn_module modules/mod_authz_svn.so
    LoadModule dontdothat_module modules/mod_dontdothat.so

    <Location /svn>
    DAV svn
    SVNParentPath /var/www/svn
    AuthType Basic
    AuthName "SVN Repo”
    AuthUserFile /etc/svnusers
    Require valid-user
    </Location>

Restart Apache and setup credentials (username - svn1)

    systemctl restart httpd
     htpasswd -cm /etc/svnusers svn1

Open browser and login with the above credentials  
  
-  http://127.0.0.1/svn/first-repo
-  http://server-public-IP/svn/first-repo

