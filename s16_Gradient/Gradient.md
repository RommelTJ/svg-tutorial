[# How to Use Gradients with SVG

The filling of a shape can be defined as a gradient. Today add a subtle 3D effect to our Christmas decoration and 
build a snowman.

## Upgrade the Christmas ornament

Let's upgrade the Christmas Ornament.

```svg
<svg width="200" height="200" viewBox="-100 -100 200 200">
    <circle cx="0" cy="20" r="70" fill="#D1495B"/>
    <rect x="-17.5" y="-65" width="35" height="20" fill="#F79257" />
    <circle cx="0" cy="-75" r="12" fill="none" stroke="#F79257" stroke-width="2" />
</svg>
```

<svg width="200" height="200" viewBox="-100 -100 200 200">
    <circle cx="0" cy="20" r="70" fill="#D1495B"/>
    <rect x="-17.5" y="-65" width="35" height="20" fill="#F79257" />
    <circle cx="0" cy="-75" r="12" fill="none" stroke="#F79257" stroke-width="2" />
</svg>

We can add a subtle 3D effect by filling the main circle with a gradient. Here we define a `radialGradient` in the 
`defs` section. It has a different syntax than CSS, but the capabilities are rather similar.

We define its ID, center position with `cx` and `cy`, set its radian, and the stop colors. Then we can use it as an 
attribute for the `fill` property of a shape.

```svg
<svg width="200" height="200" viewBox="-100 -100 200 200">
  <defs>
    <radialGradient id="shine" cx="0.25" cy="0.25" r="0.35">
      <stop offset="0%" stop-color="#e3a8b0" />
      <stop offset="100%" stop-color="#D1495B" />
    </radialGradient>
  </defs>
  
  <circle cx="0" cy="20" r="70" fill="url(#shine)" />
  <rect x="-17.5" y="-65" width="35" height="20" fill="#F79257" />
  <circle cx="0" cy="-75" r="12" fill="none" stroke="#F79257" stroke-width="2" />
</svg>
```

<svg width="200" height="200" viewBox="-100 -100 200 200">
  <defs>
    <radialGradient id="shine" cx="0.25" cy="0.25" r="0.35">
      <stop offset="0%" stop-color="#e3a8b0" />
      <stop offset="100%" stop-color="#D1495B" />
    </radialGradient>
  </defs>

  <circle cx="0" cy="20" r="70" fill="url(#shine)" />
  <rect x="-17.5" y="-65" width="35" height="20" fill="#F79257" />
  <circle cx="0" cy="-75" r="12" fill="none" stroke="#F79257" stroke-width="2" />
</svg>

## Building a Snowman

For the snowman we draw two circles with a similar gradient as follows.

```svg
<svg width="200" height="200" viewBox="-100 -100 200 200" style="background-color: lightblue">
  <defs>
    <radialGradient id="snowball" cx="0.25" cy="0.25" r="1">
      <stop offset="0%" stop-color="white" />
      <stop offset="50%" stop-color="white" />
      <stop offset="100%" stop-color="#d6d6d6" />
    </radialGradient>
  </defs>

  <circle cx="0" cy="0" r="80" fill="url(#snowball)" />
</svg>
```

<svg width="200" height="200" viewBox="-100 -100 200 200" style="background-color: lightblue">
  <defs>
    <radialGradient id="snowball" cx="0.25" cy="0.25" r="1">
      <stop offset="0%" stop-color="white" />
      <stop offset="50%" stop-color="white" />
      <stop offset="100%" stop-color="#d6d6d6" />
    </radialGradient>
  </defs>

  <circle cx="0" cy="0" r="80" fill="url(#snowball)" />
</svg>

Then we add a polygon for the nose, two circles for the eyes, and two lines for the arm. Simple.

```svg
<svg width="200" height="400" viewBox="-100 -200 200 400" style="background-color: lightblue">
  <defs>
    <radialGradient id="snowball" cx="0.25" cy="0.25" r="1">
      <stop offset="0%" stop-color="white" />
      <stop offset="50%" stop-color="white" />
      <stop offset="100%" stop-color="#d6d6d6" />
    </radialGradient>
  </defs>

  <circle cx="0" cy="60" r="80" fill="url(#snowball)" />
  <circle cx="0" cy="-40" r="50" fill="url(#snowball)" />
  <polygon points="10,-46 50,-40 10,-34" fill="#e66465" />

  <circle cx="0" cy="-55" r="5" />
  <circle cx="20" cy="-55" r="5" />

  <line x1="-40" y1="30" x2="-90" y2="-30" stroke="black" stroke-width="5" />
  <line x1="-65" y1="0" x2="-90" y2="-10" stroke="black" stroke-width="5" />
</svg>
```

<svg width="200" height="400" viewBox="-100 -200 200 400" style="background-color: lightblue">
  <defs>
    <radialGradient id="snowball" cx="0.25" cy="0.25" r="1">
      <stop offset="0%" stop-color="white" />
      <stop offset="50%" stop-color="white" />
      <stop offset="100%" stop-color="#d6d6d6" />
    </radialGradient>
  </defs>

  <circle cx="0" cy="60" r="80" fill="url(#snowball)" />
  <circle cx="0" cy="-40" r="50" fill="url(#snowball)" />
  <polygon points="10,-46 50,-40 10,-34" fill="#e66465" />

  <circle cx="0" cy="-55" r="5" />
  <circle cx="20" cy="-55" r="5" />

  <line x1="-40" y1="30" x2="-90" y2="-30" stroke="black" stroke-width="5" />
  <line x1="-65" y1="0" x2="-90" y2="-10" stroke="black" stroke-width="5" />
</svg>
