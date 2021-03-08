
# BlurCaptureLimiter (FireCapture plugin)

## Introduction
The **astrosharpy** package includes a plugin for the planetary capture
software [FireCapture](http://www.firecapture.de/). The basic idea of this plugin,
called *BlurCaptureLimiter*, is to limit the amount of data you collect during
image acquisition. *BlurCaptureLimiter* evaluates the sharpness of each frame during
the capture process and only stores frames which exceed a user defined threshold.
