$vim learn.rb  			## To write basic ruby code
package 'apache' do
	package_name 'httpd'
end

$ruby -c learn.rb 		## checks ruby syntax
$foodcritic learn.rb		## check chef code. It shall give some warning

OR 
$ruby -c learn.rb && foodcritic learn.rb

$chef-client --local-mode learn.rb 

$service status httpd
OR
$systemctl statud httpd
