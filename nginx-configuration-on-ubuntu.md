# nginx-configuration-on-ubuntu
\
**System Packages Update**
```
$sudo apt update
```
\
**Install Nginx Package**
```
$sudo apt install nginx
```
\
**Check Version**
```
$sudo dpkg -l nginx
```
\
**Check Status**
```
$sudo systemctl status nginx
```
\
**Enable**
```
$sudo systemctl enable nginx
```
\
**Disable**
```
$sudo systemctl disable nginx
```
\
**Start**
```
$sudo systemctl start nginx
```
\
**Stop**
```
$sudo systemctl stop nginx
```
\
**Restart**
```
$sudo systemctl restart nginx
```
\
**Reload**
```
$sudo systemctl reload nginx
```
\
**-----------------------------------------------------------------------------**

##### Nginx server configuration details
```
$ls /etc/ngnix/*
```
##### Nginx default hosting path
> /var/www/html
##### Nginx default hosting file
> index.nginx-debian.html

**-----------------------------------------------------------------------------**

Configure **ufw** firewall settings top open port 80,443,22,... as required.

**-----------------------------------------------------------------------------**

Check the server Private & Public IP Address and search in the browser to see default site is working.
##### To check local IP in ubuntu
```
$ifconfig
```
##### To check Public IP in ubuntu
```
$curl ifconfig.me
```

**-----------------------------------------------------------------------------**


## Create another site (called virtual host) in the same server
**To create a server block file, First, create a directory for your domain as shown.**
```
$sudo mkdir -p /var/www/mywebsite.com/html
```

**Next, assign the ownership to the new directory using the $USER variable.**
```
$sudo chown -R $USER:$USER /var/www/mywebsite.com/html
```

**Ensure that you also assign directory permissions accordingly allowing the owner to have all the permissions (read, write and execute) and granting**
```
$sudo chmod -R 755 /var/www/mywebsite.com
```

**Inside the domain directory, create an index.html a file that will contain the web content of the domain.**
```
$sudo vim /var/www/mywebsite.com/html/index.html
```
```
<html>
    <head>
        <title>Welcome to MyWebSite!</title>
    </head>
    <body>
        <h1>It is my new website.</h1>
    </body>
</html>
```
> **Press Esc Key -> type :wq! then hit Enter**

**For Nginx webserver to serve the content you’ve just added, you need to create a server block with the appropriate directives. In this case, we**
```
$sudo vim /etc/nginx/sites-available/mywebsite.com
```
```
server {
        listen 80;
        listen [::]:80;

        root /var/www/mywebsite.com/html;
        index index.html index.htm index.nginx-debian.html;

        server_name mywebsite.com  www.mywebsite.com;

        location / {
                try_files $uri $uri/ =404;
        }
}
```
> **Press Esc Key -> type :wq! then hit Enter**

**Now enable the server block file by linking it to the sites-enabled directory from which the Nginx server reads on startup**
```
$sudo ln -s /etc/nginx/sites-available/mywebsite.com /etc/nginx/sites-enabled/
```

**For the changes to be effected, restart the Nginx webserver.**
```
$sudo systemctl restart nginx
```

**Just to be sure that all configurations are in order, run the command:**
```
$nginx -t
```


