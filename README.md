[image-js-playground](https://dirkarnez.github.io/image-js-playground/)
=======================================================================
### API documentation
- [image-js 0.35.5 | Documentation](https://image-js.github.io/image-js/)


### Notes
- - for `toDataURL()`, `{ useCanvas: true }` is used for greater compression since it is intended for web
- image-js is improving - in `resize`, "bilinear" is apparently better than "nearestNeighbor", but not yet supported

```js
// playground requires you to assign document definition to a variable called dd

var dd = {
  background: function(currentPage, pageSize) {
    return {image: 'sampleImage.jpg'}
  }
};

595.28, 841.89
```
