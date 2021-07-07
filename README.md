# Real-time graphs with chartJS

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

The contents of this reporitory can be cloned to the server and upon configuring `apache` or `nginx` it will be visible
in the web.

## Sources

### chartjs-plugin-streaming

https://nagix.github.io/chartjs-plugin-streaming/latest/samples/charts/line-horizontal.html

Found via: https://nagix.github.io/chartjs-plugin-streaming/

### Bare minimum example

https://embed.plnkr.co/plunk/z3Qy9C

https://tobiasahlin.com/blog/introduction-to-chartjs/

https://www.chartjs.org/docs/master/configuration/animations/