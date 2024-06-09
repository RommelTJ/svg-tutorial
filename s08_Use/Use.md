# How to reuse image elements with SVG

Instead of repeating the same code over and over again we can also reuse image elements.

## How to draw a Sun icon with SVG

Let's draw a simple sun icon. We start with a circle element to draw the core of the sun, and we draw a line to 
draw a sunray.

```svg
<svg width="200" height="200" viewBox="-15 -15 30 30">
  <circle r="6" />
  <line
    stroke="black"
    stroke-width="2"
    stroke-linecap="round"
    x1="0"
    y1="11"
    x2="0"
    y2="14"
  />
</svg>
```

<svg width="200" height="200" viewBox="-15 -15 30 30">
  <circle r="6" />
  <line
    stroke="black"
    stroke-width="2"
    stroke-linecap="round"
    x1="0"
    y1="11"
    x2="0"
    y2="14"
  />
</svg>

Now, once we have one ray, we can reuse the same line element to draw the others. We can give this ray an `id` and 
reuse it with the use element.

Then, we can move the lines to their correct position with the `transform` command in the same way we did with the 
star example, except that this time, we increment the rotation by 45 degrees for each ray.

```svg
<svg width="200" height="200" viewBox="-15 -15 30 30">
  <circle r="6" />

  <line
    id="ray"
    stroke="black"
    stroke-width="2"
    stroke-linecap="round"
    x1="0"
    y1="11"
    x2="0"
    y2="14"
  />

  <use href="#ray" transform="rotate(45)" />
  <use href="#ray" transform="rotate(90)" />
  <use href="#ray" transform="rotate(135)" />
  <use href="#ray" transform="rotate(180)" />
  <use href="#ray" transform="rotate(225)" />
  <use href="#ray" transform="rotate(270)" />
  <use href="#ray" transform="rotate(315)" />
</svg>
```

You can use the Sun icon above and the Moon icon we are about to cover later to create a toggle button that can 
switch between bright and dark modes.
