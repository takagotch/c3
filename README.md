### c3
---
https://github.com/c3js/c3

https://c3js.org/
```
npm run serve-static
```

```
<link href="/path/to/c3.css" rel="stylesheet">
<script src="/path/to/d3.v5.min.js" charset="utf-8"></script>
<script src="/path/to/c3.min.js"></script>

<div id="chart"></div>
```

```js
var chart = c3.generate({
  bindto: '#chart',
  data: {
    columns: [
      ['data1', 30, 200, 100, 400, 150, 250],
      ['data2', 50, 20, 10, 40, 15, 25]
    ]
  }
});

require.config({
  baseUrl: '/js',
  paths: {
    d3: "http://d3js.org/d3.v5.min"
  }
});

require(["d3", "c3"], function(d3, c3){
  c3.generate({
  });
});

var chart = c3.generate({
  bindto: '#chart',
  data: {
    columns: [
      ['data1', 30, 200, 100, 400, 150, 250],
      ['data2', 50, 20, 10, 40, 15, 25]
    ],
    axes: {
      data2: 'y2'
    }
  },
  axis: {
    y2: {
      show: true
    }
  }
});

var chart = c3.generate({
  bindto: '#chart',
  data: {
    columns: [
      ['data1', 30, 200, 100 400 150, 250],
      ['data2', 50, 20, 10, 40, 15, 25]
    ],
    axes: {
      data2: 'y2'
    }
  },
  axis: {
    y: {
      label: {
        text: 'Y Label',
        position: 'outer-middle'
      }
    },
    y2: {
      show: true,
      label: {
        text: 'Y2 Label',
        position: 'outer-middle'
      }
    }
  }
});

var chart = c3.generate({
  bindto: '#chart',
  data: {
    columnds: [
      ['data1', 30, 200, 100, 400, 150, 250],
      ['data2', 50, 20, 10, 40, 15, 25]
    ],
    axes: {
      data2: 'y2'
    },
    types: {
      data2: 'bar'
    }
  },
  axis: {
    y: {
      label: {
        text: 'Y Label',
        position: 'outer-middle'
      }
    },
    y2: {
      show: true,
      label: {
        text: 'Y2 Label',
        position: 'outer-middle'
      }
    }
  }
});

var chart = c3.generate({
  bindto: '#chart',
  data: {
    columns: [
      ['data1', 30, 200, 100, 400, 150, 250],
      ['data2', 50, 20, 10, 40, 15, 25]
    ],
    axes: {
      data2: 'y2'
    },
    types: {
      data2: 'bar'
    },
    axis: {
      y: {
        label: {
          text: 'Y Label',
          position: 'outer-middle'
        },
        tick: {
         format: d3.format("$,")
        }
      },
      y2: {
        show: true,
        label: {
          text: 'Y2 Label',
          position: 'outer-middle'
        }
      }
    }
  }
});

chart.load({
  columns: [
    ['data1', 300, 100, 250, 150, 300, 150, 500],
    ['data2', 100, 200, 150, 50, 100, 250]
  ]
});

chart.unload({
  ids: ['data2', 'data3']
});

chart.hide(['data2', 'data3']);
chart.show(['data2', 'data3']);

#chart .c3-line-data2 {
  stroke-width: 5px;
}
```

