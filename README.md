# Enabling Virtual Host On Apache
###1. We added a host at /etc/hosts
```
sudo vi /etc/hosts/
```
###Added our local
```vi
127.0.0.1 local-phpsandbox.com
```
####2. We added a new virtual host to the httpd-vhost.conf file
###-- it already existed
###-- we used pre-written code
```vi
  <Directory "/Users/Bryant/Desktop/DigitalCrafts/unit4/php">
    Allow from all
    Options +Includes +Indexes +FollowSymLinks
    AllowOverride all
    Require all granted
  </Directory>
</VirtualHost>
```
###3. We enabled the virtual host file in the httpd.conf file (removed the #'s)
-- this is the main Apache config file
###4. We enabled the php module in httpd.conf
```vi
#LoadModule userdir_module libexec/apache2/mod_userdir.so
LoadModule alias_module libexec/apache2/mod_alias.so
LoadModule rewrite_module libexec/apache2/mod_rewrite.so
LoadModule php5_module libexec/apache2/libphp5.so
LoadModule hfs_apple_module libexec/apache2/mod_hfs_apple.so

and 

#Virtual hosts
Include /private/etc/apache2/extra/httpd-vhosts.conf
```

5. We added access to all in httpd.conf
-- this was inside the <directory>
-- this is neccessary because apache locks every door
6. we made Desktop executable
```
 sudo chmod +x ~/Desktop/ 
 ```
7. We restarted apache a ton of times
```
sudo apachectl restart     
sudo apachectl restart     
sudo apachectl restart     
sudo apachectl restart
```
