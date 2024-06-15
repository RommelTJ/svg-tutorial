# How to Draw an Arc with SVG

If you thought that cubic Béziers were the most complicated parts of an SVG, then I have bad news for you. Arcs are 
way more complex. The good news, though, is that they are rarely used, and we won’t use them much in the upcoming 
examples either.

```svg
<svg width="450" height="450">
  <path d="M 145 174 A 150 120 20 0 0 288 314" stroke="white" stroke-width="20" fill="none" />
</svg>
```

<svg width="450" height="450">
  <path d="M 145 174 A 150 120 20 0 0 288 314" stroke="white" stroke-width="20" fill="none" />
</svg>

## The different parameters of an SVG arc

The arc to command has 7 parameters:  
* `A rx ry rotation large-arc-flag sweep-flag x y`
  * `rx` - horizontal radius of the arc.
  * `ry` - vertical radius of the arc.
  * `rotation`- Used to turn an ellipse by an angle. It's not rotated around its center to maintain the same start and end points.
  * `large-arc-flag` - boolean flag to indicate to draw the long way.
  * `sweep-flag` - boolean flag to flip the arc the other way
  * `x` - x coordinate of the endpoint of the arc.
  * `y` - y coordinate of the endpoint of the arc.

The last two parameters `(40, 40)` are still the endpoint of the arc.  
The first two defines a horizontal and vertical radius `(70, 70)`. If we draw a circle, those two values are the same.

```svg
<svg width="200" height="200" viewBox="-100 -100 200 200">
  <path d="M -40 -40 A 70 70 0 0 0 40 40" fill="none" stroke="red" stroke-width="2"/>
</svg>
```

<svg width="200" height="200" viewBox="-100 -100 200 200">
  <path d="M -40 -40 A 70 70 0 0 0 40 40" fill="none" stroke="red" stroke-width="2"/>
</svg>

You might realize, that even with the same starting point and endpoint, and the same radiuses, there can be 
four different variations. The 5th argument is a boolean flag, and we can use it to flip the arc the other way 
(now it changed to 1).

```svg
<svg width="200" height="200" viewBox="-100 -100 200 200">
  <path d="M -40 -40 A 70 70 0 0 1 40 40" fill="none" stroke="red" stroke-width="2"/>
</svg>
```

<svg width="200" height="200" viewBox="-100 -100 200 200">
  <path d="M -40 -40 A 70 70 0 0 1 40 40" fill="none" stroke="red" stroke-width="2"/>
</svg>

You might notice that in both cases, the arc ends up the shortest possible way with these parameters. It is also 
possible to go the long way and still keep the same start and endpoints, and the same radiuses. Then the 4th argument 
is another boolean flag that sets if we want to go the long way (now we also changed it to 1). This also has two 
variations. You can mirror it, by flipping the 5th argument to the other value.

```svg
<svg width="200" height="200" viewBox="-100 -100 200 200">
  <path d="M -40 -40 A 70 70 0 1 1 40 40" fill="none" stroke="red" stroke-width="2"/>
</svg>
```

<svg width="200" height="200" viewBox="-100 -100 200 200">
  <path d="M -40 -40 A 70 70 0 1 1 40 40" fill="none" stroke="red" stroke-width="2"/>
</svg>

<svg width="200" height="200" viewBox="-100 -100 200 200">
  <path d="M -40 -40 A 70 70 0 1 0 40 40" fill="none" stroke="red" stroke-width="2"/>
</svg>

To complicate things even further, if we set the horizontal and vertical radiuses to two different values, we end up 
with an elliptic arc `(70, 40)`. Again, the start and end points are the same, and this also has four different 
variations.

```svg
<svg width="200" height="200" viewBox="-100 -100 200 200">
  <path d="M -40 -40 A 70 40 0 1 1 40 40" fill="none" stroke="red" stroke-width="2"/>
</svg>
```

<svg width="200" height="200" viewBox="-100 -100 200 200">
  <path d="M -40 -40 A 70 40 0 1 1 40 40" fill="none" stroke="red" stroke-width="2"/>
</svg>

Finally, if we draw an ellipse we can also turn it by an angle. We can set this by the 3rd parameter `(30)`. What makes 
things even more twisted, is that our imaginary ellipse is not rotated around its center, because this arc still has 
to maintain the same start and end points. In case we draw a circle, the rotation does not affect the arc.

```svg
<svg width="200" height="200" viewBox="-100 -100 200 200">
  <path d="M -40 -40 A 70 40 30 1 1 40 40" fill="none" stroke="red" stroke-width="2" />
</svg>
```

<svg width="200" height="200" viewBox="-100 -100 200 200">
  <path d="M -40 -40 A 70 40 30 1 1 40 40" fill="none" stroke="red" stroke-width="2" />
</svg>

## Drawing a Moon Icon

After drawing a Sun Icon it's time to draw a Moon icon. We draw a single path. We start with a move-to command to 
get to the starting position (upper corner). Then, we draw two arcs. We draw a longer arc to get down to the bottom 
corner and then return to the starting position with a shorter arc.

```svg
<svg width="200" height="200" viewBox="0 0 30 30">
  <path d="M 23, 5 A 12 12 0 1 0 23, 25A 12 12 0 0 1 23, 5" />
</svg>
```

<svg width="200" height="200" viewBox="0 0 30 30">
  <path d="M 23, 5 A 12 12 0 1 0 23 25 A 12 12 0 0 1 23 5" />
</svg>

Note how these two arcs look very different despite using the same radiuses. The large arc flag and the sweep flag 
mirror each other. The first arc goes the long way between the two endpoints, and the second goes the short way. 
Note that the first one goes counterclockwise (as it goes down), and the second goes clockwise (as it goes up).

## Drawing a candy cane

Now after all these introductions we finally got to today's example. We are only going to draw a simple arc in this one.

```svg
<svg width="200" height="400" viewBox="-100 -200 200 400">
  <path class="body" d="M 50 120 L 50 -80 A 50 50 0 0 0 -50 -80" stroke="#cd803d" stroke-width="45" />
</svg>
```

```css
.body {
  stroke-linecap: round;
  fill: none;
}
```

<svg width="200" height="400" viewBox="-100 -200 200 400">
  <path class="body" d="M 50 120 L 50 -80 A 50 50 0 0 0 -50 -80" stroke="#cd803d" stroke-width="45" />
</svg>

To draw a candy cane, we draw a thick line that consists of a straight line and a half circle. Then we draw the same line 
again, with a slightly thinner stroke width. By setting two different colors for them, they will look as if one is the 
border of the other.

For the finishing touches, we add a few straight lines inside this shape as markings.

```css
.body {
  stroke-linecap: round;
  fill: none;
}

.red-mark {
  stroke: #d1495b;
  stroke-width: 2.5px;
}

.green-mark {
  stroke: #234236;
  stroke-width: 2.5px;
}
```

```svg
<svg width="200" height="400" viewBox="-100 -200 200 400">
  <path class="body" d="M 50 120 L 50 -80 A 50 50 0 0 0 -50 -80" stroke="#cd803d" stroke-width="45" />
  <path class="body" d="M 50 120 L 50 -80 A 50 50 0 0 0 -50 -80" stroke="white" stroke-width="40" />

  <line class="green-mark" x1="-35" y1="-90" x2="-60" y2="-100" />
  <line class="red-mark" x1="-15" y1="-115" x2="-25" y2="-135" />
  <line class="green-mark" x1="20" y1="-110" x2="35" y2="-130" />
  <line class="red-mark" x1="40" y1="-60" x2="60" y2="-80" />
  <line class="green-mark" x1="40" y1="-10" x2="60" y2="-30" />
  <line class="red-mark" x1="40" y1="40" x2="60" y2="20" />
  <line class="green-mark" x1="40" y1="90" x2="60" y2="70" />
</svg>
```

<svg width="200" height="400" viewBox="-100 -200 200 400">
  <style>
    .body {
      stroke-linecap: round;
      fill: none;
    }
    .red-mark {
      stroke: #d1495b;
      stroke-width: 2.5px;
    }
    .green-mark {
      stroke: #234236;
      stroke-width: 2.5px;
    }
  </style>
  <path class="body" d="M 50 120 L 50 -80 A 50 50 0 0 0 -50 -80" stroke="#cd803d" stroke-width="45" />
  <path class="body" d="M 50 120 L 50 -80 A 50 50 0 0 0 -50 -80" stroke="white" stroke-width="40" />

  <line class="green-mark" x1="-35" y1="-90" x2="-60" y2="-100" />
  <line class="red-mark" x1="-15" y1="-115" x2="-25" y2="-135" />
  <line class="green-mark" x1="20" y1="-110" x2="35" y2="-130" />
  <line class="red-mark" x1="40" y1="-60" x2="60" y2="-80" />
  <line class="green-mark" x1="40" y1="-10" x2="60" y2="-30" />
  <line class="red-mark" x1="40" y1="40" x2="60" y2="20" />
  <line class="green-mark" x1="40" y1="90" x2="60" y2="70" />
</svg>
