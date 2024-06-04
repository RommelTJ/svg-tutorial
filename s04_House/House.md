# How to Build a House with SVG

In this example, we combine everything we learned so far. We use circles, rectangles, lines, polylines, and polygons 
here.

We start with the front itself. Note that we not only have a class on the wall element but on the whole SVG as well.

```svg
<svg class="house1" width="200" height="200" viewBox="-100 -100 200 200" >
  <polygon class="wall1" points="-65,80 -65,-10 0,-70 65,-10 65,80" />
</svg>
```

```css
.house1 {
  stroke: black;
  stroke-width: 2px;
  fill: white;
}
```

<html lang="en">
  <style>
    .house1 {
      stroke: black;
      stroke-width: 2px;
      fill: white;
    }
  </style>
  <body>
    <svg class="house1" width="200" height="200" viewBox="-100 -100 200 200" >
      <polygon class="wall1" points="-65,80 -65,-10 0,-70 65,-10 65,80" />
    </svg>
  </body>
</html>

Then we add a roof on top of it. This is the only thing that is new here. We use a `polyline`. The difference 
between a `polyline` and a `polygon` is that a `polygon` will always close itself, and the `polyline` will stay open. 
Note that we are using the `stroke-linecap` property again as we did with the gingerbread figure example.

```svg
<svg class="house2" width="200" height="200" viewBox="-100 -100 200 200" >
    <polyline class="roof2" points="-75,-8 0,-78 75,-8" />
</svg>
```

```css
.house2 .roof2 {
    fill: none;
    stroke: #d1495b;
    stroke-width: 10px;
    stroke-linecap: round;
}
```

<html lang="en">
  <style>
    .house2 .roof2 {
      fill: none;
      stroke: #d1495b;
      stroke-width: 10px;
      stroke-linecap: round;
    }
  </style>
  <body>
    <svg class="house2" width="200" height="200" viewBox="-100 -100 200 200" >
      <polyline class="roof2" points="-75,-8 0,-78 75,-8" />
    </svg>
  </body>
</html>

Then we keep adding simple elements for the door, the windows, and the stairs. The final code for the image will be as 
follows:  

```svg
<svg class="house3" width="200" height="200" viewBox="-100 -100 200 200">
  <polygon class="wall3" points="-65,80 -65,-10 0,-70 65,-10 65,80" />
  <polyline class="roof3" points="-75,-8 0,-78 75,-8" />

  <rect class="door3" x="-45" y="10" width="30" height="60" rx="2" />
  <circle class="door-knob3" cx="-35" cy="40" r="2" />
  <rect class="stair3" x="-47" y="70" width="34" height="5" />
  <rect class="stair3" x="-49" y="75" width="38" height="5" />

  <rect class="window3" x="5" y="15" width="40" height="35" rx="5" />
  <line x1="5" y1="32.5" x2="45" y2="32.5" />
  <line x1="25" y1="15" x2="25" y2="50" />
  <rect class="window-sill3" x="2" y="48" width="46" height="5" rx="5" />

  <circle class="window3" cx="0" cy="-25" r="15" />
  <line x1="-15" y1="-25" x2="15" y2="-25" />
  <line x1="0" y1="-40" x2="0" y2="-10" />
</svg>
```

```css
.house3 {
  stroke: black;
  stroke-width: 2px;
  fill: white;
}

.house3 .roof3 {
  fill: none;
  stroke: #d1495b;
  stroke-width: 10px;
  stroke-linecap: round;
}

.house3 .door3 {
  fill: #d1495b;
}

.house3 .stair3 {
  fill: gray;
}

.house3 .window3 {
  fill: #fdea96;
}

.house3 .window-sill3 {
  fill: #d1495b;
  stroke-linecap: round;
}
```

<html lang="en">
  <style>
    .house3 {
      stroke: black;
      stroke-width: 2px;
      fill: white;
    }
    .house3 .roof3 {
      fill: none;
      stroke: #d1495b;
      stroke-width: 10px;
      stroke-linecap: round;
    }
    .house3 .door3 {
      fill: #d1495b;
    }
    .house3 .stair3 {
      fill: gray;
    }
    .house3 .window3 {
      fill: #fdea96;
    }
    .house3 .window-sill3 {
      fill: #d1495b;
      stroke-linecap: round;
    }
  </style>
  <body>
    <svg class="house3" width="200" height="200" viewBox="-100 -100 200 200">
      <polygon class="wall3" points="-65,80 -65,-10 0,-70 65,-10 65,80" />
      <polyline class="roof3" points="-75,-8 0,-78 75,-8" />
      <rect class="door3" x="-45" y="10" width="30" height="60" rx="2" />
      <circle class="door-knob3" cx="-35" cy="40" r="2" />
      <rect class="stair3" x="-47" y="70" width="34" height="5" />
      <rect class="stair3" x="-49" y="75" width="38" height="5" />
      <rect class="window3" x="5" y="15" width="40" height="35" rx="5" />
      <line x1="5" y1="32.5" x2="45" y2="32.5" />
      <line x1="25" y1="15" x2="25" y2="50" />
      <rect class="window-sill3" x="2" y="48" width="46" height="5" rx="5" />
      <circle class="window3" cx="0" cy="-25" r="15" />
      <line x1="-15" y1="-25" x2="15" y2="-25" />
      <line x1="0" y1="-40" x2="0" y2="-10" />
    </svg>
  </body>
</html>
