# How to use the transform property of SVG elements

## How to Draw a Star with SVG

A star is a simple shape. We could define it as a bunch of polygons and set each point individually. But then we 
would need to know each coordinate. Instead of that, we can define just one arm, and then repeat it five times with 
a rotation to get the same shape. We will use the `transform` attribute to set a rotation.

First, let’s define an arm. In this example, each arm consists of two polygons.

```svg
<svg width="200" height="200" viewBox="-100 -100 200 200">
  <polygon points="0,0 36,-50 0,-100" fill="#EDD8B7" />
  <polygon points="0,0 -36,-50 0,-100" fill="#E5C39C" />
</svg>
```

<svg width="200" height="200" viewBox="-100 -100 200 200">
  <polygon points="0,0 36,-50 0,-100" fill="#EDD8B7" />
  <polygon points="0,0 -36,-50 0,-100" fill="#E5C39C" />
</svg>

We can group them with a `g` element and rotate them together. You can think of the `g` element as the `div` element 
in HTML. It can contain other elements and attributes defined on the group element apply to its children.

Then we `rotate` each arm into the correct position.

```svg
<svg width="200" height="200" viewBox="-100 -100 200 200">
  <g transform="translate(0 5)">
    <g>
      <polygon points="0,0 36,-50 0,-100" fill="#EDD8B7" />
      <polygon points="0,0 -36,-50 0,-100" fill="#E5C39C" />
    </g>
    <g transform="rotate(72)">
      <polygon points="0,0 36,-50 0,-100" fill="#EDD8B7" />
      <polygon points="0,0 -36,-50 0,-100" fill="#E5C39C" />
    </g>
    <g transform="rotate(-72)">
      <polygon points="0,0 36,-50 0,-100" fill="#EDD8B7" />
      <polygon points="0,0 -36,-50 0,-100" fill="#E5C39C" />
    </g>
    <g transform="rotate(144)">
      <polygon points="0,0 36,-50 0,-100" fill="#EDD8B7" />
      <polygon points="0,0 -36,-50 0,-100" fill="#E5C39C" />
    </g>
    <g transform="rotate(-144)">
      <polygon points="0,0 36,-50 0,-100" fill="#EDD8B7" />
      <polygon points="0,0 -36,-50 0,-100" fill="#E5C39C" />
    </g>
  </g>
</svg>
```

<svg width="200" height="200" viewBox="-100 -100 200 200">
  <g transform="translate(0 5)">
    <g>
      <polygon points="0,0 36,-50 0,-100" fill="#EDD8B7" />
      <polygon points="0,0 -36,-50 0,-100" fill="#E5C39C" />
    </g>
    <g transform="rotate(72)">
      <polygon points="0,0 36,-50 0,-100" fill="#EDD8B7" />
      <polygon points="0,0 -36,-50 0,-100" fill="#E5C39C" />
    </g>
    <g transform="rotate(-72)">
      <polygon points="0,0 36,-50 0,-100" fill="#EDD8B7" />
      <polygon points="0,0 -36,-50 0,-100" fill="#E5C39C" />
    </g>
    <g transform="rotate(144)">
      <polygon points="0,0 36,-50 0,-100" fill="#EDD8B7" />
      <polygon points="0,0 -36,-50 0,-100" fill="#E5C39C" />
    </g>
    <g transform="rotate(-144)">
      <polygon points="0,0 36,-50 0,-100" fill="#EDD8B7" />
      <polygon points="0,0 -36,-50 0,-100" fill="#E5C39C" />
    </g>
  </g>
</svg>

You might notice that we define our polygons to start from the origin of the coordinate system 
(which is the center of the image). By default, the rotation is also around the origin of the coordinate system.

Because we have five arms, the bottom of the image is a bit shorter than the top of the image. To center the image, 
we can group the whole star together and use the translate transformation to move everything down by 5 units 
along the Y coordinates.
