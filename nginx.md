server {
    listen 80;
    listen [::]:80;

    root /var/www/ivajebaat3;
    index index.php index.html index.htm index.nginx-debian.html;

    server_name www.ivajebaat3.net;

    location / {
		#try_files $uri $uri/ /index.php$is_args$args;
		#try_files $uri $uri/ =404;
		try_files $uri /index.html index.php;
    }

    location ~ \.php$ {
        include snippets/fastcgi-php.conf;
        fastcgi_pass unix:/run/php/php7.0-fpm.sock;
    }
}
