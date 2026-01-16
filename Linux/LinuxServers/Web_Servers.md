# Webserver

Different webservers

* [Apache](#apache)
* [nginX](#nginx)
* [lighthttpd](#lighthttpd)

## Apache

Most popular web server

### Apache2ctl utility commands

| Command | Description |
| --- | --- |
| Start | Starts the Apache Server |
| stop | Stops the Apache Server, terminating any active connections |
| restart | Restarts the Apache server, closing any existing connections |
| fullstatus | Displays a full status report from the Apache Server |
| status | Displays a short status report from the Apache server |
| graceful | Restarts the Apache Server, but existing connections are not terminated |
| graceful-stop | Stops the Apache server, but existing connections are not terminated |
| configtest | Parses the configuration files and reports any syntax errors |
| help | Displays the list of commands |

### Apache File Structure

* /etc/apache/apache.conf: Apache 1.3.x installation for Ubuntu systems
* /etc/apache2/apache2.conf: Apache2 installation for Ubuntu systems
* /etc/httpd/conf/httpd.conf: Apache 1.3.x and 2.x installation for Red hat Systems

### Configuration

```
DocumentRoot "/var/www/html"

<IfDefine variable>
Directive
</IfDefine>

<Directory /var/www/html/mydata>
Directive
</Directory>

UserDir public_html

NameVirtualHost 192.168.1.77
<VirtualHost 192.168.1.77>
ServerName www.myhost1.com
DocumentRoot /var/www/html/host1
</VirtualHost>

<VirtualHost 192.168.1.77>
ServerName www.myhost2.com
DocumentRoot /var/www/html/host2
</VirtualHost>

Listen 192.168.1.77:80
Listen 192.168.1.78:80
<VirtualHost 192.168.1.77>
ServerName www.myhost1.com
DocumentRoot /var/www/html/myhost1
</VirtualHost>
<VirtualHost 192.168.1.78>
ServerName www.myhost2.com
DocumentRoot /var/www/html/myhost2
</VirtualHost>

Listen 443
SSLEngine On
SSLCertificateFile /etc/apache2/certs/mycert.pem
SSLCertificateKeyFile /etc/apache2/certs/myserver.key

```

### Common Apache Configuration Directives

| Directive | Description |
| --- | --- |
| Listen | The TCP port (and optional IP address) to listen for client requests |
| User | The user account used to start the Apache server daemon |
| Group | The group account used to start the Apache server daemon |
| ServerAdmin | Email address of the server administrator |
| ServerName | The domain name of the server |
| ServerRoot | The location of the base configuration files |
| DocumentRoot | The location of the default data directory |
| DirectoryIndex | The default file served when a client requests an index of a directory |
| ErrorDocument | The file to serve when a specific error type occurs |
| ErrorLog | The log file location to use for logging error messages |
| LogFormat | The format of each log file entry |
| AccessFileName | The file that lists restrictions on we page files in a directory |
| Include | Includes configuration settings defined in an external file |
| StartServers | The number of servers to start to handle concurrent requests |
| MaxClients | The maximum num number of servers to handle concurrent requests |
| MinSpareServers | The minimum number of extra servers to have running |
| MaxSpareServers | The maximum number of extra servers to have running |
| LoadModule | Load and enable the specified feature module into the server |

### Apache Logs

* /var/log/apache2/error.log -> Ubuntu
* /var/log/httpd/error.log -> Red Hat

### UserDir filename

* UserDir public\_html -> http: //localhost/~rich/test .html

## nginX

Advanced replacement of apache, improving on performance and providing some additional features

### Install nginx

* Debian

```
sudo apt-get instal nginx

```

* Red Hat

```
sudo dnf install nginx

```

### Start nginx

```
sudo systemctl start nginx
sudo systemctl enable nginx

```

### Configuring nginx

* /etc/nginx/sites-enables/default file

```
server {
    listen 80 default_server;
    listen [::]:80 default_server;
    server_name _;
    root /usr/share/nginxhtml;

    include /etc/nginx/default.d/*.conf;
    location / {

    }

    error_page 404 /404.html;
    location = /40x.html {

    }

    error_page 500 502 503 504 /50x.html;
    location = /50x.html {

    }
}

```

## lighthttpd

Low memory usage and low cpu usage, making it ideal for smaller server applications

## Securing Internet services

* inetd:
* xinetd:
* /etc/init.d

```
update-rc.d -f samba remove
invoke-rc.d samba stop

/etc/init.d/inetd restart

ls /etc/xinetd.d
/etc/init.d/xinetd restart

ls /etc/init.d
sudo systemctl stop smb
/etc/init.d/smb stop

```