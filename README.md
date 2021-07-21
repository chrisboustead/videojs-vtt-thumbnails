# videojs-vtt-thumbnails

Video.js plugin that displays thumbnails on progress bar hover, driven by external VTT files.  Based on [this JW Player spec](https://support.jwplayer.com/customer/portal/articles/1407439-adding-preview-thumbnails). Note, this plugin currently only supports sprited thumbnails.

Note: Plugin hides the default skin's mouse display timestamp on hover.

## Table of Contents

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
## Installation

- [Installation](#installation)
- [Usage](#usage)
  - [`<script>` Tag](#script-tag)
  - [Browserify/CommonJS](#browserifycommonjs)
  - [RequireJS/AMD](#requirejsamd)
- [Options](#options)
  - [Example](#example)
  - [Available Options](#available-options)
- [License](#license)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->
## Installation

```sh
npm install --save videojs-vtt-thumbnails
```

## Usage

To include videojs-vtt-thumbnails on your website or web application, use any of the following methods.

### `<script>` Tag

This is the simplest case. Get the script in whatever way you prefer and include the plugin _after_ you include [video.js][videojs], so that the `videojs` global is available.

```html
<script src="//path/to/video.min.js"></script>
<script src="//path/to/videojs-vtt-thumbnails.min.js"></script>
<script>
  var player = videojs('my-video');
  player.vttThumbnails({
    src: 'example/thumbs.vtt'
  });
</script>
```

### Browserify/CommonJS

When using with Browserify, install videojs-vtt-thumbnails via npm and `require` the plugin as you would any other module.

```js
var videojs = require('video.js');

// The actual plugin function is exported by this module, but it is also
// attached to the `Player.prototype`; so, there is no need to assign it
// to a variable.
require('videojs-vtt-thumbnails');

var player = videojs('my-video');

player.vttThumbnails();
```

### RequireJS/AMD

When using with RequireJS (or another AMD library), get the script in whatever way you prefer and `require` the plugin as you normally would:

```js
require(['video.js', 'videojs-vtt-thumbnails'], function(videojs) {
  var player = videojs('my-video');

  player.vttThumbnails();
});
```

## Options

Options are passed in the same object as the source location.

### Example

```js
  var player = videojs('my-video');
  player.vttThumbnails({
    src: 'example/thumbs.vtt',
    withCredentials: true,
    showTimestamp: true
  });
```
### Available Options

- `showTimestamp` (Boolean, Default: false) - Disables the timestamp that is shown on hover.

## License

MIT. Copyright (c) Chris Boustead &lt;chris@forgemotion.com&gt;


[videojs]: http://videojs.com/
