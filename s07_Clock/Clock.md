# How to Draw a Clock with SVG and JavaScript

Generating images with central symmetry is one of the many use cases of rotating image elements. In this example, 
we create a clock that shows the actual time. We draw the clock with SVG and use JavaScript to turn the hour and 
minute handles in the right direction.

SVG elements can be manipulated from JavaScript the same way as any other HTML element. In this example, 
we are using a short code snipped to show the actual time on a clock. We access the hour and minute hands in 
JavaScript with `getElementById` then set their `transform` attribute with a rotation that reflects the current time.

There's another trick here worth mentioning. The dots here showing each hour are drawn as a dashed circle. 
This works similar to how we can set the `border-style` CSS property for regular HTML elements. 
In SVG we can fine-tune the length of each dash segment and the space in between with the `stroke-dasharray` property. 
We can also set an offset with `stroke-dashoffset`.

```svg
<svg width="200" height="200" viewBox="-100 -100 200 200">
  <rect x="-100" y="-100" width="200" height="200" fill="#CD803D" />

  <circle r="55" stroke="#FCCE7B" stroke-width="10" fill="white" />

  <circle
    r="45"
    stroke="#B6705F"
    stroke-width="6"
    stroke-dasharray="6 17.56194490192345"
    stroke-dashoffset="3"
    fill="none"
  />

  <g stroke="#5f4c6c" stroke-linecap="round">
    <line id="hours" y2="-20" stroke-width="8" />
    <line id="minutes" y2="-35" stroke-width="6" />
  </g>
</svg>
```

```html
<script>
  const hoursElement = document.getElementById("hours");
  const minutesElement = document.getElementById("minutes");

  const hour = new Date().getHours() % 12;
  const minute = new Date().getMinutes();

  hoursElement.setAttribute("transform", `rotate(${(360 / 12) * hour})`);
  minutesElement.setAttribute("transform", `rotate(${(360 / 60) * minute})`);
</script>
```

<html lang="en">
  <script>
    const hoursElement = document.getElementById("hours2");
    const minutesElement = document.getElementById("minutes2");
    const hour = new Date().getHours() % 12;
    const minute = new Date().getMinutes();
    hoursElement.setAttribute("transform", `rotate(${(360 / 12) * hour})`);
    minutesElement.setAttribute("transform", `rotate(${(360 / 60) * minute})`);
  </script>
  <body>
    <svg width="200" height="200" viewBox="-100 -100 200 200">
      <rect x="-100" y="-100" width="200" height="200" fill="#CD803D" />
      <circle r="55" stroke="#FCCE7B" stroke-width="10" fill="white" />
      <circle r="45" stroke="#B6705F" stroke-width="6" stroke-dasharray="6 17.56194490192345" stroke-dashoffset="3" fill="none" />
      <g stroke="#5f4c6c" stroke-linecap="round">
        <line id="hours2" y2="-20" stroke-width="8" />
        <line id="minutes2" y2="-35" stroke-width="6" />
      </g>
    </svg>
  </body>
</html>
