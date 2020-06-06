+++
title = "Nginx"
date = 2020-06-06T19:06:21+02:00
+++


Nginx is a high performance simple HTTP server, which can also be used as a reverse proxy, load balancer, etc. Similar to Apache web server, however NGINX is much faster and more lightweight.

[Serving static files with NGINX using Docker Tutorial 1](https://mycodesmells.com/post/serving-static-files-with-nginx)

[Serving static files with NGINX using Docker Tutorial 2](https://www.linkedin.com/pulse/serve-static-files-from-docker-via-nginx-basic-example-arun-kumar/)

## nginx.conf 

```nginx
events {}

http {
    server {
        listen 80;

        root /www;
        index index.html;

        location / {
            include  /etc/nginx/mime.types;
            try_files $uri $uri/ /index.html;
        }
    }
}
```

