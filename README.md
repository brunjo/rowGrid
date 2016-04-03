# rowGrid.js (no jQuery required)

**rowGrid.js is a small, lightweight (~1kB gzipped) JavaScript plugin for placing images (or other items) in straight rows.**

The grid is similar to grids on Google Image Search, Flickr, Shutterstock and Google+ images.

Features:

 * responsive
 * infinite scrolling
 * support for all modern browsers and IE >= 9

RowGrid.js is also available as jQuery plugin: https://github.com/brunjo/rowGrid.js

[![Example Grid](http://brunjo.github.io/rowGrid.js/example.png)][2]

Do you like this project? Follow me on Twitter [@3runjo][1].

## How does it work?
All items must have the **same height** but the **width can be variable**. RowGrid.js justifies the items in straight rows so that the width of the rows equals the width of the container/parent element.
At first rowGrid.js adjusts the margin between the items. If this is not enough rowGrid.js scales down the items.

## Demos & Examples
Real world example: https://www.pexels.com/

## Installation
Just include row-grid.js:
```HTML
<script src="path/to/row-grid.min.js"></script>
```

You can install it also with Bower or npm:
* Install with [Bower](http://bower.io): `bower install rowGrid`.
* Install with [npm](https://www.npmjs.com): `npm install rowgrid`.

## Usage
It is important that you either **declare the width and height as attributes** on the img tag or that you wait until the images are loaded before you start rowGrid.js.

HTML:
```HTML
<div class="container">
  <div class="item">
    <img src="path/to/image" width="320" height="200" />
  </div>
  <div class="item">
    <img src="path/to/image" width="290" height="200" />
  </div>
  ...
</div>
```
JS:
```JS
var container = document.getElementsByClassName('container')[0];
rowGrid(container, {itemSelector: ".item", minMargin: 10, maxMargin: 25, firstItemClass: "first-item", lastRowClass: 'last-row', resize: true});
```

### Relayout
You can relayout the complete grid with `rowGrid(container);`. If you appended items to the grid you can call `rowGrid(container, 'appended');` to arrange just the new items in the grid. This is useful if you want to implement endless scrolling.


## Parameters

The method `rowGrid()` expects two parameters. The first one has to be a DOM element and the second one a JavaScript object with options:

#### itemSelector (required)
* **value:** ```string``` (CSS Selector)

The selector have to reference to all grid items.
#### minMargin (required)
* **value:** ```number``` or ```null```

This is the minimal horizontal margin between the items. The margin is only between the items not between the first/last item and the container.
#### maxMargin (required)
* **value:** ```number``` or ```null```

This is the maximal horizontal margin between the items.
#### resize
* **value:** ```boolean```
* **default value:** ```true```

If ```resize``` is set to true the layout updates on resize events. This is useful for responsive websites.

#### minWidth
* **value:** ```number```
* **default value:** ```0```

RowGrid.js only applies its grid system if the width of the window is greater than or equals to the specified value.

The default value is `0`. This means the items always get arranged by rowGrid.js.

Also check out the demo in the `example` directory to see this option in action.

#### lastRowClass
* **value:** ```string```
* **default value:** ```last-row```

The first item in the last row gets this class.

#### firstItemClass
* **value:** ```string```
* **default value:** ```undefined```

The first item in every row gets this class.


  [1]: https://twitter.com/3runjo "@3runjo"
  [2]: http://brunjo.github.io/rowGrid.js/ "Demos"
