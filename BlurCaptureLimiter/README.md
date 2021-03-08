
# BlurCaptureLimiter (FireCapture plugin)

## Introduction
The **astrosharpy** package includes a plugin for the planetary capture software [FireCapture](http://www.firecapture.de/). The basic idea of this plugin, called *BlurCaptureLimiter*, is to limit the amount of data you collect during image acquisition. *BlurCaptureLimiter* evaluates the sharpness of each frame during the capture process and only stores frames which exceed a user defined threshold.

The most recent version of *BlurCaptureLimiter* works only for mono images. Colour images will be supported at a later stage.

## Installation
Download the plugin (which comes in a jar file) from [here](https://github.com/alexjarosch/astrosharpy/blob/main/BlurCaptureLimiter/jar/BlurCaptureLimiter.jar). You will have to place this jar file in plugin folder in your FireCapture base folder. Best you create a sub-folder called *BlurCaptureLimiter* and place the jar file in there.
If you use a 64 bit system, the file structure should look like this:
```
path_to_firecapture/plugins/x64/BlurCaptureLimiter/BlurCaptureLimiter.jar
```
and for a 32 bit system
```
path_to_firecapture/plugins/x86/BlurCaptureLimiter/BlurCaptureLimiter.jar
```

## Usage

The *BlurCaptureLimiter* plugin has a slider control with which you set the blur capture limit. Assuming you have centered and focused your planet, the following would be a good recording procedure to use the plugin:

1. Configure the frame recording (ROI, gain, exposure time, ...).
2. Start the BlurCaptureLimiter plugin.
3. Let the plugin observe the frame stream for a few minutes and observe the blur measure values for the current seeing conditions.
4. Set the threshold close to the best seeing limit, say at 0.95.
5. Start the recording (with a given time or frame number limit). Only frames above that relative sharpness are recorded.

The output field labelled *Current (each 100th frame)* displays the estimated sharpness measure for each 100th frame in the frame stream. This is done so that you still can observe the estimated sharpness value even for very high frame rates. However the capturing limiter operates on each and every frame in the stream.

*BlurCaptureLimiter* uses a relative sharpness measure which is scaled by the best observed frame during the time *BlurCaptureLimiter* is running. If you want to reset this measure, just restart the plugin. Also the threshold is relative to the best observed frame. For a threshold of 0.95 only the top 5% quality frames are recorded.

You can use *BlurCaptureLimiter* to monitor changes in the local seeing conditions during your session. If the estimated sharpness values drop significantly (below 0.7), then the local seeing go worse.

## Mathematical background.

Up to come...
