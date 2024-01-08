# nginx rtmp server

```
sudo apt update
sudo apt install nginx
sudo apt install libnginx-mod-rtmp
```

add rtmp config
```
sudo nano /etc/nginx/nginx.conf

load_module /usr/lib/nginx/modules/ngx_rtmp_module.so;

rtmp {
    server {
        listen 1935;
        chunk_size 4000;

        application live {
            live on;
            record off;
        }
    }
}
```

restart nginx
```
sudo systemctl restart nginx
```

if needed to link
```
sudo ln -s /usr/share/nginx/modules-available/mod-rtmp.conf /etc/nginx/modules-enabled/50-mod-rtmp.conf
```
