### Flowr.js

Flowr is a jquery plugin to show your content in a justified view. This plugin tries to emulate the way images are displayed on flickr's favorites and groups pages.

### Demo

http://kalyan02.github.com/flowr-js/

### Features

1. Load content from a json into a justified view, all you need to do is pass original sizes.
2. You can append more items to existing view and content will just flow.

### Example 1

```
$("#imageContainer").flowr({
	data : jsonContent,
	height : 240,
	render : function(params) {
		return "<img src='" + params.itemData.url + "' />";
	},
});
```

### Example 2

```
$("#imageContainer").flowr({
	data : jsonContent,
	height : 240,
	render : function(params) {
		return "<img src='" + params.itemData.url + "' />";
	},
	itemHeight : function(data) { return data.size.height; },
	itemWidth : function(data) { return data.size.width; },
});
```

### Appending data

```
$("#imageContainer").flowr({
	data : jsonContent,
	append : true
});
```

### All options

 * data - (array) - Pass data/items to be rendered as an array. Each item will be made available for your callback.
 * padding - (pixels) - spacing between items
 * height - (pixels) - minimum height of each row
 * render - (function) - callback to fetch HTML
 * append - (bool) - true for appending more items
 * widthAttr - (string) - by default flowr tries to pick up width attribute. if your data structure has a different attribute, specify it.
 * heightAttr - (string) - as above
 * itemWidth - (function) - callback to fetch width. _arg.itemData_ will contain your initial data
 * itemHeight - (function) - callback to fetch height
 * complete - (function) - on render complete callback 
 * rowClassName - (css class) - css class for div which wraps each row
 * maxWidth - (pixels) - Width of container. Defaults to container's width
 * maxScale - (number) - If the last line has only 1 or 2 elements, what is the max scale to be allowed.
