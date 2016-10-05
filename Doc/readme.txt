YUV Toolkit
=================================================
http://www.yuvtoolkit.com

YUV Toolkit is an Open Source, cross platform raw
yuv player and analyzer. It is currently in early
stage of development, and current development 
focus is on playback features.

New in 0.0.3 build X
=================================================
* New Features

- Added support for more formats: YUYV, YVYU, BGR (24 and 32 bits) and RGB565
- File name parsing improvements
  - based on the last matching string in file path
  - supports CIF, QCIF, VGA, QVGA, QQVGA, 1080P etc
- Many improvements in YTS script engine
  - Support for custom time stamps using YTS script
  - Allow changing of video title using YTS script
  - Support for Javascript extension in YTS
  - Experimental "subjective" extension for subjective testing
  - Support for reading and writing text using YTS script
  - Sample scripts included
- Support for *.rgb file extension

* Bug fixes

- No file option pops up when resolution is missing from file name
- Video stops playing after changing the resolution
- Crash when playing 4:2:2 files
- Crash when displaying distortion map with MSE only
- Video restarts after changing the renderer 
- When paused, change of resolution doesn't always apply
- Files >2Gb not working

New in 0.0.2
=================================================
* Major New Features

- New video pipeline, more efficient playback and more reliable seeking.
- Support for 720P 60FPS playback of 4 side-by-side videos using D3D 
  renderer if harddrive is fast enough.
- Support for MSE and PSNR objective measures and error map visualization.
- Improved platform support in Windows and Mac as default program for 
  opening yuv files.

* Minor New Features

- Playback of a selected time interval (Select using Ctrl-HOME and 
  Ctrl-END, remove by ESC)
- Improved perception of start-up time (i.e. show window early).
- Continue playback after seeking to a new frame using mouse.
- Accelerating seeking when pressing down arrow keys.
- HOME and END keys for beginning and end of video.
- Improved algorithm for video layout (minimizing background).
- New toolbar
- Removed QPaint renderer

* Changes in YTS scripting API

- Added new openFiles API to load several files at same time 
  (more reliable):

yt.openFiles([
  '480p/Andrei_2_sony_hd_640x480_30fps.yuv',
  '480p/David-12-iSight-LowLight-640x480-15fps.yuv'
  ]);


Known Issues
=================================================
When video FPS is not dividable by the screen update frequency, playback 
speed will not be 100%. YUV Toolkit does not try to apply pulldown scheme
to correct the playback speed. For instance, if you try to play 30FPS 
video on 50Hz screen, the playback speed will be about 83%.

Some options are disabled since they are not yet implemented. You
can not select which video to compare, and you cannot choose how 
distortion values are color mapped.


Version History
=================================================

0.0.1
-----
Initial Release
Support for Windows and OsX
Direct3D renderer for windows
OpenGL and QPaint based cross platform renderers