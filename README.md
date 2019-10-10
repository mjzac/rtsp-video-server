# RTSP Video Steaming Server

This project includes video capturing using FFmpeg (AVFoundation as a backend), pre-processing (resampling and framerate control) functionality.

Live555 Framework based video server is implemented for unicast video transmision using an RTSP.

Code is written in C++ programming language. 

# Building and running (macOS)

1. `brew install ffmpeg`
2. `brew install boost`
3. `brew install log4cpp`
4. Download and make [live555](http://www.live555.com/) [`./genMakefiles macos && make` ]
5. Clone the repo and `cd` into it
6. `mkdir build && cd $_`
7. `Live555Dir=<path to live555 src directory> cmake ..`
8. `./RTSPServer`

You should see output like:

    Input #0, avfoundation, from 'left_cam':
      Duration: N/A, start: 26011.230833, bitrate: N/A
        Stream #0:0: Video: rawvideo (NV12 / 0x3231564E), nv12, 640x480, 29.97 tbr, 1000k tbn, 1000k tbc
        Stream #0:1: Audio: pcm_f32le, 44100 Hz, stereo, flt, 2822 kb/s

        Output #0, null, to 'null':
     
      Metadata:
        encoder         : Lavf58.20.100
        Stream #0:0: Video: hevc (libx265) (Main), yuv420p, 640x480, q=2-31, 90k tbn
    2019-10-10 16:19:24,387 [INFO  ] - /Users/melson/code/github/rtsp-video-server/src/LiveCameraRTSPServer.cpp:87
      Play the stream of the 'left_cam' camera using the following URL: rtsp://192.168.0.100:8554/left_cam
    2019-10-10 16:19:24,387 [INFO  ] - /Users/melson/code/github/rtsp-video-server/src/LiveCameraRTSPServer.cpp:87
      Play the stream of the 'right_cam' camera using the following URL: rtsp://192.168.0.100:8554/right_cam


9. Play the stream by entering the url `rtsp://<your ip address>:8554/left_cam` into vlc.