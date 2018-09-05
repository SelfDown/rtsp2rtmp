将rtsp 流转化为rtmp 流

测试rtsp 地址 rtsp://184.72.239.149/vod/mp4://BigBuckBunny_175k.mov


ffmpeg -i rtsp://192.168.2.173:8554/test -vcodec copy -acodec copy -f flv rtmp://localhost:1935/live/livestream
