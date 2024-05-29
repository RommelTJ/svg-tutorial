# How to Make a Gingerbread Figure with SVG

## Moving styling properties to CSS

Since our SVG is living inside an HTML file now, we can assign CSS classes to each element and move some of the 
attributes to CSS. We can only move the presentation attributes though. Position attributes and attributes that define 
the shapes have to stay in HTML. But colors, stroke, and font attributes can be moved to CSS.

<html lang="en">
  <style>
    .head {
      fill: #cd803d;
    }
  </style>
  <body>
    <svg width="200" height="200" viewBox="-100 -100 200 200">
      <circle class="head" cx="0" cy="-50" r="30" />
    </svg>
  </body>
</html>

```svg
<svg width="200" height="200" viewBox="-100 -100 200 200">
  <circle class="head" cx="0" cy="-50" r="30" />
</svg>
```

```css
.head {
  fill: #cd803d;
}
```


## Rounded lines

We already saw the `fill` and some of the `stroke` properties, but here’s another styling property: `stroke-linecap`. 
This can make our line cap rounded. Note that the legs and the arms are simple lines here.

To give you a comparison if we remove the line cap and set a smaller stroke-width, then this is how it would look like.

<html lang="en">
  <style>
    .limb {
      stroke: #cd803d;
    }
  </style>
  <body>
    <svg width="200" height="200" viewBox="-100 -100 200 200">
      <line class="limb" x1="-40" y1="-10" x2="40" y2="-10" />
      <line class="limb" x1="-25" y1="50" x2="0" y2="-15" />
      <line class="limb" x1="25" y1="50" x2="0" y2="-15" />
    </svg>
  </body>
</html>

```svg
<svg width="200" height="200" viewBox="-100 -100 200 200">
  <line class="limb" x1="-40" y1="-10" x2="40" y2="-10" />
  <line class="limb" x1="-25" y1="50" x2="0" y2="-15" />
  <line class="limb" x1="25" y1="50" x2="0" y2="-15" />
</svg>
```

```css
.limb {
  stroke: #cd803d;
}
```

But by setting a thick stroke width and a round line cap we can shape legs and arms for our figure.

<html lang="en">
  <style>
    .limb2 {
      stroke: #cd803d;
      stroke-width: 35px;
      stroke-linecap: round;
    }
  </style>
  <body>
    <svg width="200" height="200" viewBox="-100 -100 200 200">
      <line class="limb2" x1="-40" y1="-10" x2="40" y2="-10" />
      <line class="limb2" x1="-25" y1="50" x2="0" y2="-15" />
      <line class="limb2" x1="25" y1="50" x2="0" y2="-15" />
    </svg>
  </body>
</html>

```svg
<svg width="200" height="200" viewBox="-100 -100 200 200">
  <line class="limb2" x1="-40" y1="-10" x2="40" y2="-10" />
  <line class="limb2" x1="-25" y1="50" x2="0" y2="-15" />
  <line class="limb2" x1="25" y1="50" x2="0" y2="-15" />
</svg>
```

```css
.limb2 {
  stroke: #cd803d;
  stroke-width: 35px;
  stroke-linecap: round;
}
```

## Rounded Rectangles

Also, note the `rx` property at the rectangle defining the mouth. This will make the edges rounded. It is similar to 
the `border-radius` property for regular HTML elements.

<html lang="en">
  <style>
    .head2 {
      fill: #cd803d;
    }
    .mouth {
      fill: none;
      stroke: white;
      stroke-width: 2px;
    }
  </style>
  <body>
    <svg width="200" height="200" viewBox="-100 -100 200 200">
      <circle class="head2" cx="0" cy="-50" r="30" />
      <rect class="mouth" x="-10" y="-40" width="20" height="5" rx="2" />
    </svg>
  </body>
</html>

```svg
<svg width="200" height="200" viewBox="-100 -100 200 200">
  <circle class="head2" cx="0" cy="-50" r="30" />
  <rect class="mouth" x="-10" y="-40" width="20" height="5" rx="2" />
</svg>
```

```css
.head2 {
  fill: #cd803d;
}

.mouth {
  fill: none;
  stroke: white;
  stroke-width: 2px;
}
```

## Gingerbread figure

Once we put it all together, and add eyes and buttons, this is how the final code looks like:

```svg
<svg class="gingerbread" width="200" height="200" viewBox="-100 -100 200 200">
  <circle class="head3" cx="0" cy="-50" r="30" />

  <circle class="eye3" cx="-12" cy="-55" r="3" />
  <circle class="eye3" cx="12" cy="-55" r="3" />
  <rect class="mouth3" x="-10" y="-40" width="20" height="5" rx="2" />

  <line class="limb3" x1="-40" y1="-10" x2="40" y2="-10" />
  <line class="limb3" x1="-25" y1="50" x2="0" y2="-15" />
  <line class="limb3" x1="25" y1="50" x2="0" y2="-15" />

  <circle class="button" cx="0" cy="-10" r="5" />
  <circle class="button" cx="0" cy="10" r="5" />
</svg>
```

```css
.head3 {
  fill: #cd803d;
}

.eye3 {
  fill: white;
}

.mouth3 {
  fill: none;
  stroke: white;
  stroke-width: 2px;
}

.limb3 {
  stroke: #cd803d;
  stroke-width: 35px;
  stroke-linecap: round;
}
```

<html lang="en">
  <style>
    .head3 {
      fill: #cd803d;
    }
    .eye3 {
      fill: white;
    }
    .mouth3 {
      fill: none;
      stroke: white;
      stroke-width: 2px;
    }
    .limb3 {
      stroke: #cd803d;
      stroke-width: 35px;
      stroke-linecap: round;
    }
  </style>
  <body>
    <div>
      <svg class="gingerbread" width="200" height="200" viewBox="-100 -100 200 200">
        <circle class="head3" cx="0" cy="-50" r="30" />
        <circle class="eye3" cx="-12" cy="-55" r="3" />
        <circle class="eye3" cx="12" cy="-55" r="3" />
        <rect class="mouth3" x="-10" y="-40" width="20" height="5" rx="2" />
        <line class="limb3" x1="-40" y1="-10" x2="40" y2="-10" />
        <line class="limb3" x1="-25" y1="50" x2="0" y2="-15" />
        <line class="limb3" x1="25" y1="50" x2="0" y2="-15" />
        <circle class="button" cx="0" cy="-10" r="5" />
        <circle class="button" cx="0" cy="10" r="5" />
      </svg>
    </div>
  </body>
</html>
