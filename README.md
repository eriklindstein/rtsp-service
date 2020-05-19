# RTSP Service

## Build

Install dependencies:
```
sudo apt install gstreamer1.0-rtsp libgstrtspserver-1.0-dev gstreamer1.0-plugins-ugly
```

Build:
```
gcc -Wall test-launch.c -o test-launch $(pkg-config --cflags --libs gstreamer-1.0 gstreamer-rtsp-server-1.0)
```

Expose a test screen as a JPEG RTP:

```
./test-launch "videotestsrc ! jpegenc ! rtpjpegpay name=pay0 pt=26" 
```
