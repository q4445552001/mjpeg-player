# mjpeg-player

jpg 陽春型網頁播放器

由 ffmpeg 轉出來的jpg格式在網頁上播放
自動調整圖片大小
且會自動偵測視窗大小是否改變

ffmpeg 程式碼:

rtmp_server="rtmp://0.0.0.0:80/rtmp/rtmp"
fps=4
bitrate=5
out="/var/camera/hls/mjpeg.jpg"

ffmpeg \
    -i $rtmp_server \
    -q:v $bitrate \
    -probesize 32 \
    -vf fps=$fps \
    -update 1 \
    -y $out

