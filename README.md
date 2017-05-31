# livecam-macos

This repos is extended from [livecam](https://github.com/sepehr-laal/livecam), and has correction to well-run on MacOS.


## Installation via Mac Brew

```bash
brew install gstreamer
...
brew reinstall gst-plugins-bad —with-applemedia
```
Documentation http://brewformulas.org/Gstreamer

All plugins required: gst-plugins-bad, gst-plugins-base, gst-plugins-good, gst-plugins-ugly, gstreamer



## Run on MacOS

```bash
gst-launch-1.0 avfvideosrc capture-screen=true ! videoscale ! videoconvert ! video/x-raw,width=640,height=480 ! osxvideosink

gst-launch-1.0 videotestsrc is-live=true ! x264enc ! qtmux ! filesink location=test.mp4

gst-launch-1.0 avfvideosrc is-live=true ! videoscale ! videoconvert ! video/x-raw,width=640,height=480 ! osxvideosink

gst-launch-1.0 avfvideosrc device-index=0 ! "video/x-raw(memory:GLMemory),width=1280,height=720" ! glimagesink

gst-launch-1.0 avfvideosrc device-index=0 ! videoscale ! videoconvert ! video/x-raw,width=640,height=480 ! osxvideosink
```

Documentation https://gstreamer.freedesktop.org/documentation/plugins.html

