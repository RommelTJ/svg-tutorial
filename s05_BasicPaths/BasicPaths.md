# How to Draw Basic Paths with SVG

Once we covered basic shapes, it’s time to move on to the `path` element. The `path` is the most powerful SVG element. 
We can define pretty much anything with paths and if you open any SVG file, you will mostly see paths.

The shape of a path is defined by the `d` attribute. Here we define several drawing commands. 
A command always starts with a letter defining the command type and ends with a coordinate.

Here we only have the two most basic commands, **move-to** (`M`) and **line-to** (`L`).  
* The move-to command moves the cursor to a point without drawing a line 
* The line-to command draws a straight line from the previous point. 
* A command always continues the previous command. 
* When we draw a line we only define the endpoint. 
* The starting point will be the previous command’s endpoint.

## Hamburger menu icon

Before we get to the arrow example, let’s draw a simple hamburger menu icon. We draw three lines within the same 
path with the move-to (`M`) and line-to (`L`) commands. 

First, we move to the start of the top line (`M -40, -40`) and draw a line to its end (`L 40, -40`).

```svg
<svg
  width="200"
  height="200"
  viewBox="-100 -100 200 200"
>
  <path
    d="
        M -40, -40
        L  40, -40"
    stroke="#333333"
    stroke-width="25"
    stroke-linecap="round"
  />
</svg>
```

Then we continue and draw to more lines the same way. What is cool about paths, is that they don't have to be 
continuous. We can have several move-to commands within the same path. The commas between the X and Y coordinates 
are optional. We skip them this time.

```svg
<svg width="200" height="200" viewBox="-100 -100 200 200">
  <path d="
        M -40 -40
        L  40 -40 
        M -40   0 
        L  40   0 
        M -40  40 
        L  40  40"
    stroke="#333333"
    stroke-width="25"
    stroke-linecap="round"
  />
</svg>
```

<svg width="200" height="200" viewBox="-100 -100 200 200">
  <path 
    d="M -40 -40 L  40 -40 M -40   0 L  40   0 M -40  40 L  40  40" 
    stroke="#333333" 
    stroke-width="25" 
    stroke-linecap="round" 
  />
</svg>

## Heart Icon

Here's another example made with a move to command and two line to commands.

```svg
<svg width="200" height="200" viewBox="-100 -100 200 200">
  <path 
    d="
        M -30 -20 
        L   0  10 
        L  30 -20"
    fill="none"
    stroke="black"
    stroke-width="80"
    stroke-linecap="round"
  />
</svg>
```

<svg width="200" height="200" viewBox="-100 -100 200 200">
  <path 
    d="
        M -30 -20 
        L   0  10 
        L  30 -20"
    fill="none"
    stroke="black"
    stroke-width="80"
    stroke-linecap="round"
  />
</svg>

In the example above if we reduce the value of the `stroke-width` property, then we realize that the code above is 
actually a simple V shape.
