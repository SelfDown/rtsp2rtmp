将rtsp 流转化为rtmp 流

测试rtsp 地址 rtsp://184.72.239.149/vod/mp4://BigBuckBunny_175k.mov


ffmpeg -i rtsp://192.168.2.173:8554/test -vcodec copy -acodec copy -f flv rtmp://localhost:1935/live/livestream


https://wenku.baidu.com/view/97f4d3d7e45c3b3566ec8b3d.html





一、海康的RTSP地址是最变态的，NVR、IPC不同版本不同地址，害我经常要更新文章

NVR/DVR

[101通道1;201通道2](64路内NVR摄像机通道标识33开始)

海康NVR rtsp://admin:12345@127.0.0.1:554/Streaming/Channels/101

早期旧型号url用ch33

rtsp://admin:12345@127.0.0.1:554/h264/ch33/main/av_stream

rtsp://admin:12345@127.0.0.1:554/h264/ch33/sub/av_stream

[主码流1；子码流2；第三码流（可自定义)]

海康枪机好几种rtsp地址，下列是已知

方式一、
rtsp://admin:12345@127.0.0.1:554/Streaming/Channels/1?transportmode=unicast&profile=Profile_1

方式二、

主码流

rtsp://192.168.31.224:554/Streaming/Channels/101?transportmode=unicast&amp;profile=Profile_1

子码流

rtsp://192.168.31.224:554/Streaming/Channels/102?transportmode=unicast&amp;profile=Profile_2

 

海康NVR接入其他品牌摄像机需onvif配置自定义协议1~16 协议类型rtsp自动端口554资源路径为ip后字串1/h264major

 

 

二、杭州中威 rtsp://admin:12345@127.0.0.1:554/Streaming/Channels/1?transportmode=unicast&profile=Profile_1

 [通道号1开始;主码流0；字码流1]

三、大华rtsp://admin:admin@127.0.0.1:554/cam/realmonitor?channel=1&subtype=0   



四、 英飞拓、通昱、金三立rtsp地址一致格式



[h264major:主码流；h264minor：字码流]

英飞拓rtsp://INFINOVA:INFINOVA@127.0.0.1:554/1/h264major 

通昱 rtsp://admin:12345@127.0.0.1:554/h264major

金三立rtsp://Admin:111111@127.0.0.1:554/h264major



五、

三星: rtsp://admin:4321@127.0.0.1:554/onvif/profile2/media.smp
