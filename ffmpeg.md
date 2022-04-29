```bat
REM 裁剪视频： - ss 起始时间 -t 裁剪长度 
ffmpeg -ss 00:00:00 -i video.mp4 -vcodec copy -acodec copy -t 00:00:31 output1.mp4
```