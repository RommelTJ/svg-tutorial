# How to Draw a Forest with SVG

Rotation is not the only way we can generate images from simple shapes. In this example, we define a tree shape and 
then place it at various positions in different sizes to draw a forest.

First, we create a background out of a rectangle and a circle.

```svg
<svg width="200" height="200" viewBox="-100 -100 200 200">
  <rect x="-100" y="-100" width="200" height="200" fill="#F1DBC3" />
  <circle cx="0" cy="380" r="350" fill="#F8F4E8" />
</svg>
```

<svg width="200" height="200" viewBox="-100 -100 200 200">
  <rect x="-100" y="-100" width="200" height="200" fill="#F1DBC3" />
  <circle cx="0" cy="380" r="350" fill="#F8F4E8" />
</svg>

Then we define a tree shape from a simple polygon and a line.

```svg
<svg width="200" height="200" viewBox="-100 -100 200 200">
  <polygon points="-10,0 10,0 0,-50" fill="#38755b" />
  <line x1="0" y1="0" x2="0" y2="10" stroke="#778074" stroke-width="2" />
</svg>
```

<svg width="200" height="200" viewBox="-100 -100 200 200">
  <polygon points="-10,0 10,0 0,-50" fill="#38755b" />
  <line x1="0" y1="0" x2="0" y2="10" stroke="#778074" stroke-width="2" />
</svg>

This tree shape, however, shouldn't appear on the UI like this. We can hide it by moving the entire tree into the 
`defs` section. The `defs` section is a hidden compartment of our image. Things here don't show up on the screen, but 
we can refer to them and use them later.

Then, we can reuse it similarly as in the snowflake example. We wrap the two elements into a group, set an id, and 
then reuse it with the use element.

Here, we also position the reused elements by setting an x and y coordinate, and we use the scale transformation to 
add some perspective to the image.

```svg
<svg width="200" height="200" viewBox="-100 -100 200 200">
  <defs>
    <g id="tree">
      <polygon points="-10,0 10,0 0 -50" fill="#38755b" />
      <line x1="0" y1="0" x2="0" y2="10" stroke="#778074" stroke-width="2" />
    </g>
  </defs>

  <rect x="-100" y="-100" width="200" height="200" fill="#F1DBC3" />
  <circle cx="0" cy="380" r="350" fill="#F8F4E8" />

  <use href="#tree" x="-30" y="25" transform="scale(2)" />
  <use href="#tree" x="-20" y="40" transform="scale(1.2)" />
  <use href="#tree" x="40" y="40" />
  <use href="#tree" x="50" y="30" transform="scale(1.5)" />
</svg>
```

<svg width="200" height="200" viewBox="-100 -100 200 200">
  <defs>
    <g id="tree">
      <polygon points="-10,0 10,0 0 -50" fill="#38755b" />
      <line x1="0" y1="0" x2="0" y2="10" stroke="#778074" stroke-width="2" />
    </g>
  </defs>

  <rect x="-100" y="-100" width="200" height="200" fill="#F1DBC3" />
  <circle cx="0" cy="380" r="350" fill="#F8F4E8" />

  <use href="#tree" x="-30" y="25" transform="scale(2)" />
  <use href="#tree" x="-20" y="40" transform="scale(1.2)" />
  <use href="#tree" x="40" y="40" />
  <use href="#tree" x="50" y="30" transform="scale(1.5)" />
</svg>
