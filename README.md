hls.js light extended
============

This is an extended [light flavour] of [hls.js] conveniently packaged
as a node module and published on the [NPM registry].

**EXTENDED**
contains Audio Stream Controller

**hls.js light** does not include alternate-audio, subtitles, CMCD, EME (DRM), or Variable Substitution support.

In addition, the following types are not available:

- `AudioStreamController` INCLUDED
- `AudioTrackController` INCLUDED
- `CuesInterface`
- `EMEController`
- `SubtitleStreamController`
- `SubtitleTrackController`
- `TimelineController`
- `CmcdController`

## Installation

via NPM

```sh
npm i hls.js-light-ext
```

or Yarn

```sh
yarn add hls.js-light-ext
```

## Usage

Basic usage would look something like this:

.js

```javascript
import HlsJs from '/hls.js-light-ext'

const videoElement = document.querySelector('video')
const videoSource = videoElement.dataset.src as string
const canPlayNativeHls = videoElement.canPlayType('application/vnd.apple.mpegurl') === 'probably' ||
  videoElement.canPlayType('application/vnd.apple.mpegurl') === 'maybe'

if (HlsJs.isSupported()) {
  hls = new HlsJs()
  hls.loadSource(videoSource)
  hls.attachMedia(videoElement)
} else if (canPlayNativeHls) {
  videoElement.src = videoSource
} else {
  console.error("Your browser doesn't support HLS")
}
```

.html

```html
<video
  data-src="https://mwcdn.co/demo-videos/View_From_A_Blue_Moon_Trailer_HLS/video.m3u8">
</video>
```

Just head over to the official [hls.js] repository or
refer to the [getting started] section of their docs for more in depth examples.

[light flavour]: https://github.com/video-dev/hls.js#build-tasks
[hls.js]: https://github.com/video-dev/hls.js
[NPM registry]: https://www.npmjs.com/package/@mistweaverco/hls.js-light
[getting started]: https://github.com/video-dev/hls.js/blob/master/docs/API.md#getting-started

