# How to Build a Christmas Tree with SVG

We can't always use basic shapes to assemble our images. A polygon is the easiest way to draw a freeform shape. 
Polygons have a points property that sets a list of coordinates that are connected with straight lines.

We can make the crown of the tree from three triangles. We start with the one at the bottom, and we add it layer by 
layer.

### Step 1: Base Layer

<div>
  <svg width="200" height="400" viewBox="-100 -200 200 400">
    <polygon points="0,0 80,120 -80,120" fill="#234236" />
  </svg>
</div>

```svg
<svg width="200" height="400" viewBox="-100 -200 200 400">
  <polygon points="0,0 80,120 -80,120" fill="#234236" />
</svg>
```

### Step 2: Add the middle layer

<div>
  <svg width="200" height="400" viewBox="-100 -200 200 400">
    <polygon points="0,0 80,120 -80,120" fill="#234236" />
    <polygon points="0,-40 60,60 -60,60" fill="#0C5C4C" />
  </svg>
</div>

```svg
<svg width="200" height="400" viewBox="-100 -200 200 400">
    <polygon points="0,0 80,120 -80,120" fill="#234236" />
    <polygon points="0,-40 60,60 -60,60" fill="#0C5C4C" />
</svg>
```

### Step 3: Top layer

<div>
  <svg width="200" height="400" viewBox="-100 -200 200 400">
    <polygon points="0,0 80,120 -80,120" fill="#234236" />
    <polygon points="0,-40 60,60 -60,60" fill="#0C5C4C" />
    <polygon points="0,-80 40,0 -40,0" fill="#38755B" />
  </svg>
</div>

```svg
<svg width="200" height="400" viewBox="-100 -200 200 400">
    <polygon points="0,0 80,120 -80,120" fill="#234236" />
    <polygon points="0,-40 60,60 -60,60" fill="#0C5C4C" />
    <polygon points="0,-80 40,0 -40,0" fill="#38755B" />
</svg>
```

### Step 4: Add the trunk rectangle

<div>
  <svg width="200" height="400" viewBox="-100 -200 200 400">
    <polygon points="0,0 80,120 -80,120" fill="#234236" />
    <polygon points="0,-40 60,60 -60,60" fill="#0C5C4C" />
    <polygon points="0,-80 40,0 -40,0" fill="#38755B" />
    <rect x="-20" y="120" width="40" height="30" fill="brown" />
  </svg>
</div>

```svg
<svg width="200" height="400" viewBox="-100 -200 200 400">
    <polygon points="0,0 80,120 -80,120" fill="#234236" />
    <polygon points="0,-40 60,60 -60,60" fill="#0C5C4C" />
    <polygon points="0,-80 40,0 -40,0" fill="#38755B" />
    <rect x="-20" y="120" width="40" height="30" fill="brown" />
</svg>
```
