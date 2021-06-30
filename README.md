# ChartJS real time graph example

In this example HTML and JavaScript are used to create [a static web page](https://en.wikipedia.org/wiki/Static_web_page). It means that you need no backend server in order to run it. In order to access this site on a server all you have to do is to put files from this repository to your serve (e.g., by cloning this repository), and configure a HTTP(S) service, such as `nginx` or `apache` (see below).

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
  server_name chartjs.example.com www.chartjs.example.com;
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
