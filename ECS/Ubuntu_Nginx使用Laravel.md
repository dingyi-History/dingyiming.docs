

Nginx的默认root文件夹

/usr/share/nginx/html
Nginx的服务器配置文件所在目录

/etc/nginx/sites-available/

* ThinkPHP nginx配置

```

server {
        listen 80 default_server;
        listen [::]:80 default_server ipv6only=on;

        root /var/www/jiajiao-web-test/;
        index index.php  index.html index.htm;

        # Make site accessible from http://localhost/
        server_name jiajiaodaojia.cn;

        location / {

                root /var/www/jiajiao-web-test/;
                # First attempt to serve request as file, then
                # as directory, then fall back to index.html
                try_files $uri $uri/ /index.html;
                # Uncomment to enable naxsi on this location
                # include /etc/nginx/naxsi.rules
                if (!-e $request_filename)
                {
                        rewrite ^/PHPParser/(.*)$ /PHPParser/index.php?s=$1 last;
                        break;
                }
                # First attempt to serve request as file, then
                # as directory, then fall back to displaying a 404.
        #       # NOTE: You should have "cgi.fix_pathinfo = 0;" in php.ini
        #
        #       # With php5-cgi alone:
                #fastcgi_pass 127.0.0.1:9000;
        #       # With php5-fpm:
                # Uncomment to enable naxsi on this location
                # include /etc/nginx/naxsi.rules
        }

location ~ \.php$ {
                root /var/www/jiajiao-web-test/;
                try_files $uri = 404;
                fastcgi_split_path_info ^(.+\.php)(/.+)$;
        #       # NOTE: You should have "cgi.fix_pathinfo = 0;" in php.ini
        #
        #       # With php5-cgi alone:
                #fastcgi_pass 127.0.0.1:9000;
                fastcgi_split_path_info ^(.+\.php)(.*)$;
                fastcgi_param PATH_INFO $fastcgi_path_info;
        #       # With php5-fpm:
```
