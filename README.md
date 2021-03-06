# Imager.jsx

> A React component for responsive images in desktop and mobile browsers. Featuring [Imager.js](https://github.com/BBC-News/Imager.js)!

React is used for the initial component rendering.
Its batched state update mechanism is then used to handle multiple image size at once, to avoid layout thrashing.

# Install

*Imager.jsx* is a browserifiable Node module.

```bash
npm i --save imager.jsx
```

If you want to generate a static artifact, clone the repository and run the following commands:

```bash
npm install
npm run build
```

# Usage

*Imager.jsx* is a two-steps use.

## The React Factory

The factory associates an [Imager.js](https://github.com/BBC-News/Imager.js) behaviour with a React component.

```js
var Imager = require('imager.jsx');

var ResponsiveImage = Imager({
  availableWidths: [333, 444, 555],
  availablePixelRatios: [1, 1.3, 2]
});
```

Please refer to the [Imager.js JavaScript Configuration documentation](https://github.com/BBC-News/Imager.js#javascript-configuration) for more informations.

## The React Component

The React component is used to render a responsive image (an `<img />` HTML element).

```html
<ResponsiveImage
 src="http://placehold.it/{width}"
 className="responsive-image"
 alt="alternative text" />
```

The only mandatory attribute is `src`, the equivalent of [Imager.js `data-src` attribute](https://github.com/BBC-News/Imager.js#data-src).

`className` and `alt` are respectively rendered as `class` and `alt` HTML attributes.

# Examples

Clone the project and open the [demo.html page](demo/index.html) for live examples.

## `<img />` element

```js
React.render(<ResponsiveImage src="http://placehold.it/{width}" />, container);
```

This is rendered as:

```html
<img src="http://placehold.it/736" class="image-replace" data-src="http://placehold.it/{width}" alt="">
```

## `<div style="background-image: ..." />` element

```js
React.render(<ResponsiveImage src="http://placehold.it/{width}x{height}">
  <h2>Tile title</h2>
</ResponsiveImage>, container);
```

This is rendered as:

```html
<div style="background-image: url(http://placehold.it/375x640);" class="image-replace" data-src="http://placehold.it/{width}x{height}">
  <h2>Tile title</h2>
</div>
```


# License

    The MIT License (MIT)

    Copyright (c) 2014 Thomas Parisot

    Permission is hereby granted, free of charge, to any person obtaining a copy
    of this software and associated documentation files (the "Software"), to deal
    in the Software without restriction, including without limitation the rights
    to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
    copies of the Software, and to permit persons to whom the Software is
    furnished to do so, subject to the following conditions:

    The above copyright notice and this permission notice shall be included in all
    copies or substantial portions of the Software.

    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
    IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
    FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
    AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
    LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
    OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
    SOFTWARE.

