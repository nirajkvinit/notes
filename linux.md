#Convert PPK (Putty private key) to id_rsa (openssh private key)
1. Install puttygen (part of the putty package):
    `sudo apt-get install putty`
2. Convert private.ppk to id_rsa:
	`puttygen private.ppk -O private-openssh -o do_private_key_rsa`

ref: https://techtuts.info/2014/06/convert-ppk-id_rsa-linux/

#Connect to a server via ssh on ubuntu
	`ssh -i do_private_key_rsa <username>@<ip_address> -p <port_number>`

#Extracting .tar.gz files
If your tar file is compressed using a gzip compressor, use this command to uncompress it.
	`$ tar xvzf file.tar.gz`

#compress a directory
	`tar -zcvf archive.tar.gz directory/ `

#Move all files from a directory to another directory
`mv  -v ~/Downloads/* ~/Videos/`

#Human readable total size of a directory
`du -hs /path/to/directory`
-----------------nginx-----------------

#<domain>.org
```
server {
    # URL: Correct way to redirect URL's
    server_name <domain>.org;
    rewrite ^/(.*)$ http://www.<domain>.org/$1 permanent;
}
server {
    server_name www.<domain>.org;
    root /var/www/<domain>.org;
    access_log /var/log/nginx/www.<domain>.org.access.log;
    error_log /var/log/nginx/www.<domain>.org.error.log;
    include global/common.conf;
    include global/wordpress.conf;
}
```

#global/common.conf

```
# Global configuration file.
# ESSENTIAL : Configure Nginx Listening Port
listen 80;
# ESSENTIAL : Default file to serve. If the first file isn't found,
index index.php index.html index.htm;
# ESSENTIAL : no favicon logs
location = /favicon.ico {
    log_not_found off;
    access_log off;
}
# ESSENTIAL : robots.txt
location = /robots.txt {
    allow all;
    log_not_found off;
    access_log off;
}
# ESSENTIAL : Configure 404 Pages
error_page 404 /404.html;
# ESSENTIAL : Configure 50x Pages
error_page 500 502 503 504 /50x.html;
    location = /50x.html {
        root /usr/share/nginx/www;
    }
# SECURITY : Deny all attempts to access hidden files .abcde
location ~ /\. {
    deny all;
}
# PERFORMANCE : Set expires headers for static files and turn off logging.
location ~* ^.+\.(js|css|swf|xml|txt|ogg|ogv|svg|svgz|eot|otf|woff|mp4|ttf|rss|atom|jpg|jpeg|gif|png|ico|zip|tgz|gz|rar|bz2|doc|xls|exe|ppt|tar|mid|m$
    access_log off; log_not_found off; expires 30d;
}
```

#global/wordpress.conf
```
# WORDPRESS : Rewrite rules, sends everything through index.php and keeps the appended query string intact
location / {
    try_files $uri $uri/ /index.php?q=$uri&$args;
}

# SECURITY : Deny all attempts to access PHP Files in the uploads directory
location ~* /(?:uploads|files)/.*\.php$ {
    deny all;
}
# REQUIREMENTS : Enable PHP Support
location ~ \.php$ {
    # SECURITY : Zero day Exploit Protection
    try_files $uri =404;
    # ENABLE : Enable PHP, listen fpm sock
    fastcgi_split_path_info ^(.+\.php)(/.+)$;
    fastcgi_pass unix:/var/run/php5-fpm.sock;
    fastcgi_index index.php;
    include fastcgi_params;
}
# PLUGINS : Enable Rewrite Rules for Yoast SEO SiteMap
rewrite ^/sitemap_index\.xml$ /index.php?sitemap=1 last;
rewrite ^/([^/]+?)-sitemap([0-9]+)?\.xml$ /index.php?sitemap=$1&sitemap_n=$2 last;
```


