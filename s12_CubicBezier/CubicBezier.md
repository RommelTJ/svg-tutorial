# How to Draw Cubic Bézier Curves with SVG

Quadratic Bézier curves are great when we want to bend a line, but they are limited. We cannot draw a bulky curve or 
make smooth connections between line segments.

With cubic Bézier curves, we have not one but two control points. The first control point defines the curve's initial 
direction, and the second one sets how the curve should reach its endpoint.

```svg
<svg width="450" height="450">
  <path d="M 100 350 C 70 100, 380 100, 350 350" stroke="white" stroke-width="20" fill="none" />
</svg>
```
<svg width="450" height="450">
  <path d="M 100 350 C 70 100, 380 100, 350 350" stroke="white" stroke-width="20" fill="none" />
</svg>

## Connecting lines

Cubic Béziers are great for making smooth connections between line segments. We can set the first control point 
to continue the previous line segment and then place the second control point in line with the following line segment.

```svg
<svg width="200" height="200" viewBox="-100 -100 200 200">
  <path d="M -90,0 L -30,-30 C 30,-60 60,-30 30,30 L 0,90"  fill="none" stroke="red" stroke-width="10" />
</svg>
```

<svg width="200" height="200" viewBox="-100 -100 200 200">
  <path d="M -90,0 L -30,-30 C 30,-60 60,-30 30,30 L 0,90"  fill="none" stroke="red" stroke-width="10" />
</svg>

```svg
<svg width="200" height="200" viewBox="-100 -100 200 200">
  <path 
    d="
      M -30,70 
      L 30,0
      C 90,-70 -80,-30 -20,10
      L 40,50"
    fill="none"
    stroke="red"
    stroke-width="10"
  />
</svg>
```

<svg width="200" height="200" viewBox="-100 -100 200 200">
  <path 
    d="
      M -30,70 
      L 30,0
      C 90,-70 -80,-30 -20,10
      L 40,50"
    fill="none"
    stroke="red"
    stroke-width="10"
  />
</svg>

## How to draw a Profile icon with SVG

A simple icon we can create with cubic Béziers is a profile icon. 
The head is a circle, and the body is a cubic Bézier and a straight line.

In this example, however, we do not use the `L` command to finish the body. 
Instead, we use the `Z` command to close the path. 
The `Z` command closes the path by drawing a straight line from the current point to the starting point.

```svg
<svg width="200" height="200" viewBox="-100 -100 200 200" fill="none" stroke="black" stroke-width="10">
  <circle cy="-40" r="20" />
  <path d="M -50,70 C -50,-20 50,-20 50,70 Z"/>
</svg>
```

<svg width="200" height="200" viewBox="-100 -100 200 200" fill="none" stroke="black" stroke-width="10">
  <circle cy="-40" r="20" />
  <path d="M -50,70 C -50,-20 50,-20 50,70 Z"/>
</svg>
