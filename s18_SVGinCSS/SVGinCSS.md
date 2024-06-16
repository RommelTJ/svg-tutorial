# How to Inline SVG in CSS

In many cases, an inlined SVG feels like a bit of noise in HTML. If we add an icon then the icon itself feels more 
like styling than content that should be part of the DOM structure. The good news is, we can move SVG images 
entirely into CSS.

For example, let's take the close button on this page at the top right corner. In HTML the close button is simply 
an anchor element with a class: `<a href="/" class="close"></a>`

Then in CSS we can set a `background-image` property. For this CSS property, we usually provide a link to an image, 
but we can also inline an SVG:

```css
.close {
  display: block;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background-color: gray;

  background-image: url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' width='50' height='50' viewBox='0 0 100 100'><path d='M 30 30 L 70 70 M 30 70 L 70 30' stroke='white' stroke-width='10' /></svg>");
}
```

The inlined SVG above is simply an X as follows (except that the stroke property is set to black in this case for 
visibility). The gray circle around it is made with CSS (by setting the `background-color` and the `border-radius` 
properties).

```svg
<svg xmlns='http://www.w3.org/2000/svg' width='50' height='50' viewBox='0 0 100 100'>
  <path d='M 30 30 L 70 70 M 30 70 L 70 30' stroke='black' stroke-width='10' />
</svg>
```

<svg xmlns='http://www.w3.org/2000/svg' width='50' height='50' viewBox='0 0 100 100'>
  <path d='M 30 30 L 70 70 M 30 70 L 70 30' stroke='black' stroke-width='10' />
</svg>

When we inline an SVG in CSS, we need to set the XML namespace property. Earlier we inlined SVGs into HTML and in 
that case it's optional. In CSS we have to set the `xmlns` property.

## Custom Mouse Cursor with SVG in CSS

Have you ever wondered how to make your website stand out? One way is to set custom mouse cursors. Take a look at 
this page. Do you notice how the cursor isn't the usual one? I've taken over the custom cursors from figma.com.

Here's an example of a custom mouse cursor that’s a simple arrow.

```svg
<svg width='26' height='31'>
  <path d='M 3 3 L 7 26 L 12 16 L 23 14 Z' fill='white' stroke='black' stroke-width='2.5' />
</svg>
```

<svg width='26' height='31'>
  <path d='M 3 3 L 7 26 L 12 16 L 23 14 Z' fill='white' stroke='black' stroke-width='2.5' />
</svg>

Then, you can override the value of the default cursor in the following way. Note that changing the default 
cursor will override all types of cursors on your page.

```css
body {
  cursor: url("data:image/svg+xml,<svg width='26' height='31' xmlns='http://www.w3.org/2000/svg'><path fill='white' stroke='black' stroke-width='2.5' d='M 2.549 2.935 L 6.993 26.043 L 11.646 16.041 L 22.993 14.425 Z' /></svg>"),
    auto;
}
```

Changing the cursor the above way will override all types of cursors on your page. Be sure to set the cursor back to 
the initial value for HTML elements that require something else (this list is not comprehensive).

```css
p,
h1,
h2,
input[type="text"] {
  cursor: text;
}

a,
a *,
button,
button * {
  cursor: pointer;
}
```

