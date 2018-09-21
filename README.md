# Vue Image Compare

## Purpose of this fork

- allow click & drag images to compare them
- allow drag & drop of a single image to change only one side
- allow zoom & pan of the comparison to see details

You can see the updated features of this fork on : https://image-compare.netlify.com/ <br>
And still check the original author website : https://marcincichocki.github.io/vue-image-compare/

## Requirements

- [Vue.js](http://vuejs.org/) (^2.0.0)

## Installation

```bash
npm i vue-image-compare --save
```

## Usage

```javascript
import Vue from 'vue';

new Vue({
    components: {
        imageCompare: require('vue-image-compare')
    },
    data() {
        return {
            before: '/img/before.jpg',
            after: '/img/after.jpg'
        }
    }
}).$mount('#app');
```

```html
<div id="app">
    <image-compare :before="before" :after="after"/>
</div>
```

### Props

| Name             | Required             | Type        | Default                                | Description                                                                                                                                             |
| ---------------- | -------------------- | ----------- | :------------------------------------: | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `before`         | :white_check_mark:   | `String`    | `undefined`                            | Path to the image image *before* change                                                                                                                 |
| `after`          | :white_check_mark:   | `String`    | `undefined`                            | Path to the image image *after* change                                                                                                                  |
| `full`           | :x:                  | `Boolean`   | `false`                                | Determines if images are stretched to fill parent element. <br> Can be used with help of CSS `object-fit: cover` to create full page image comparison   |
| `padding`        | :x:                  | `Object`    | <pre>{left: 0, right: 0}</pre>         | Set left and right "padding" in pixels, so handle can **not** reach edge of an image                                                                    |
| `hideAfter`      | :x:                  | `Boolean`   | `false`                                | Hide the after image                                                                                                                                    |
| `zoom`           | :x:                  | `Object`    | <pre>{min: 0.5, max: 2}</pre>          | scale image by                                                                                                                                          |
| `reset`          | :x:                  | `Boolean`   | `false`                                | reset all to original                                                                                                                                   |
| `isZoomable`     | :x:                  | `Boolean`   | `false`                                | enable using the mouse wheel to zoom in/out                                                                                                             |
| `isDraggable`    | :x:                  | `Boolean`   | `false`                                | allow moving the comparison left/right with click + drag                                                                                                |
| `isSwitchable`   | :x:                  | `Boolean`   | `false`                                | allow drag & drop new images to compare                                                                                                                 |
| `labels`         | :x:                  | `Object`    | <pre>{after: '', before: ''}</pre>     | comparison after & before labels                                                                                                                        |

### Slots

- `icon-left` - element to be placed on the left side of the handle
- `icon-right` - element to be placed on the right side of the handle

Example:

```html
<image-compare before="/img/before.jpg" after="/img/after.jpg">
    <i class="fa fa-angle-left" aria-hidden="true" slot="icon-left"></i>
    <i class="fa fa-angle-right" aria-hidden="true" slot="icon-right"></i>
</image-compare>
```

### Events

- `@movment` - when image/handle is dragged left/right

## License

[MIT](/LICENSE)
