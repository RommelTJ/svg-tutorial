# How to Draw a Bell with SVG

Let's have another example with cubic and quadratic beziers.

Here the bottom of this bell is defined with straight lines.

```svg
<svg width="200" height="200" viewBox="-100 -100 200 200" stroke="black" stroke-width="2">
  <path d="M -50 40 L -50 50 L 50 50 L 50 40" fill="#FDEA96" />
</svg>
```

<svg width="200" height="200" viewBox="-100 -100 200 200" stroke="black" stroke-width="2">
  <path d="M -50 40 L -50 50 L 50 50 L 50 40" fill="#FDEA96" />
</svg>

Then a quadratic Beziers starts the bell cloak.

```svg
<svg width="200" height="200" viewBox="-100 -100 200 200" stroke="black" stroke-width="2">
  <path d="M -50 40 L -50 50 L 50 50 L 50 40 Q 40 40 40 10" fill="#FDEA96" />
</svg>
```

<svg width="200" height="200" viewBox="-100 -100 200 200" stroke="black" stroke-width="2">
  <path d="M -50 40 L -50 50 L 50 50 L 50 40 Q 40 40 40 10" fill="#FDEA96" />
</svg>

Then the line is continued with a cubic Bezier to form the top of the bell.

```svg
<svg width="200" height="200" viewBox="-100 -100 200 200" stroke="black" stroke-width="2">
  <path d="M -50 40 L -50 50 L 50 50 L 50 40 Q 40 40 40 10 C 40 -60 -40 -60 -40 10" fill="#FDEA96" />
</svg>
```

<svg width="200" height="200" viewBox="-100 -100 200 200" stroke="black" stroke-width="2">
  <path d="M -50 40 L -50 50 L 50 50 L 50 40 Q 40 40 40 10 C 40 -60 -40 -60 -40 10" fill="#FDEA96" />
</svg>

Then we reach the bottom part with another quadratic bezier that mirrors the previous one.

```svg
<svg width="200" height="200" viewBox="-100 -100 200 200" stroke="black" stroke-width="2">
  <path d="M -50 40 L -50 50 L 50 50 L 50 40 Q 40 40 40 10 C 40 -60 -40 -60 -40 10 Q -40 40 -50 40" fill="#FDEA96" />
</svg>
```

<svg width="200" height="200" viewBox="-100 -100 200 200" stroke="black" stroke-width="2">
  <path d="M -50 40 L -50 50 L 50 50 L 50 40 Q 40 40 40 10 C 40 -60 -40 -60 -40 10 Q -40 40 -50 40" fill="#FDEA96" />
</svg>

We finish the bell, by adding two circles for the bell-clapper, and the hanger.

```svg
<svg width="200" height="200" viewBox="-100 -100 200 200" stroke="black" stroke-width="2">
  <circle cx="0" cy="-45" r="7" fill="#4F6D7A" />
  <circle cx="0" cy="50" r="10" fill="#F79257" />
  <path d="M -50 40 L -50 50 L 50 50 L 50 40 Q 40 40 40 10 C 40 -60 -40 -60 -40 10 Q -40 40 -50 40" fill="#FDEA96" />
</svg>
```

<svg width="200" height="200" viewBox="-100 -100 200 200" stroke="black" stroke-width="2">
  <circle cx="0" cy="-45" r="7" fill="#4F6D7A" />
  <circle cx="0" cy="50" r="10" fill="#F79257" />
  <path d="M -50 40 L -50 50 L 50 50 L 50 40 Q 40 40 40 10 C 40 -60 -40 -60 -40 10 Q -40 40 -50 40" fill="#FDEA96" />
</svg>
