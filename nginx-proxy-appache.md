# nginx proxy appache

s



```text
server {
listen   80;
root /var/www/;
index index.php index.html index.htm;
server_name example.com;
location / {
try_files $uri $uri/ /index.php;
}
location ~ \.php$ {
proxy_set_header X-Real-IP  $remote_addr;
proxy_set_header X-Forwarded-For $remote_addr;
proxy_set_header Host $host;
proxy_pass http://127.0.0.1:8080;
}
location ~ /\.ht {
deny all;
}
}
```

link 

```text
sudo ln -s /etc/nginx/sites-available/example /etc/nginx/sites-enabled/example
sudo rm /etc/nginx/sites-enabled/default
```

потом ставим apache2

порт 

```text
sudo nano /etc/apache2/ports.conf
NameVirtualHost 127.0.0.1:8080
Listen 127.0.0.1:8080
```



```text
sudo cp /etc/apache2/sites-available/default /etc/apache2/sites-available/example
sudo nano /etc/apache2/sites-available/example
```

внести изменения в адрес порта.

корректно ли задан Document Root

```text
sudo netstat -plunt
```



