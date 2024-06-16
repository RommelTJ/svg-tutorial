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
