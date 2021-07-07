# Real-time graphs with ChartJS

Minimal example of real-time chartJS. Based on the [Line (Horizontal Scroll)](https://nagix.github.io/chartjs-plugin-streaming/latest/samples/charts/line-horizontal.html) example from the _chartjs-plugin-streaming_.

The difference between the original examples (see `Sources` section below) and contents of this repository is that all
the redundant code for adding and removing plots (datasets) was removed. Additionally, `Y`-axis range was restricted
to (-100, 100). This way graph is not adjusted to the changing data and the user experience is better. In order for the
graph to adjust to the data again, simply remove this part of the JavaScript code (in `script.js`):

```javascript
    ticks: {
        max: 100,
        min: -100
    }
```

## Static web page

In this example HTML and JavaScript are used to create [a static web page](https://en.wikipedia.org/wiki/Static_web_page).
It means that you need no backend server in order to run it. In order to access this site on a server all you have to do
is to put files from this repository to your serve (e.g., by cloning this repository), and configure a HTTP(S) service, such as `nginx` or `apache` (see below).

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

Base example: https://nagix.github.io/chartjs-plugin-streaming/latest/samples/charts/line-horizontal.html

Found via: https://nagix.github.io/chartjs-plugin-streaming/

### Bare minimum example

https://embed.plnkr.co/plunk/z3Qy9C

https://tobiasahlin.com/blog/introduction-to-chartjs/

https://www.chartjs.org/docs/master/configuration/animations/