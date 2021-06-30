# ChartJS real time graph example

## Nginx confituration

Create a file:
```
vim /etc/nginx/sites-available/chartjs.example.com
```

File contents:
```
server {
  listen 80 default_server;
  listen [::]:80 default_server;
  root /home/ubuntu/chartjs-real-time-example;
  index index.html;
  server_name ulmo.mindyourdata.org www.ulmo.mindyourdata.org;
  location / {
    try_files $uri $uri/ =404;
  }
}
```

Enable site:
```
sudo ln -s /etc/nginx/sites-available/chartjs.example.com /etc/nginx/sites-enabled/
```

Restart `nginx`:
```
sudo systemctl restart nginx
```

A tutorial on how to configure `nginx`: https://medium.com/@jasonrigden/how-to-host-a-static-website-with-nginx-8b2dd0c5b301 

## Sources

### chartjs-plugin-streaming

https://nagix.github.io/chartjs-plugin-streaming/samples/line-horizontal.html

Found via: https://nagix.github.io/chartjs-plugin-streaming/

### Bare minimum example

https://embed.plnkr.co/plunk/z3Qy9C

https://tobiasahlin.com/blog/introduction-to-chartjs/

https://www.chartjs.org/docs/master/configuration/animations/
