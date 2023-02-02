# live7-24

- 下载安装ffmpeg, 需要root

> $ wget --no-check-certificate https://www.johnvansickle.com/ffmpeg/old-releases/ffmpeg-4.0.3-64bit-static.tar.xz
> 
> $ $tar -xJf ffmpeg-4.0.3-64bit-static.tar.xz
> 
> $ cd ffmpeg-4.0.3-64bit-static
> 
> $ mv ffmpeg /usr/bin && mv ffprobe /usr/bin && mv qt-faststart /usr/bin && mv ffmpeg-10bit /usr/bin

- 直播平台保存rmtp推流地址和推流码

`$rtmp="rtmp://a.rtmp.youtube.com/live2/xxxxxx"`

- 上传.MP4文件到~/video, 开启循环直播

```
cd ~/videos
for video in (ls *.mp4)
do
 #ffmpeg -re -i "video" -preset ultrafast -vcodec libx264 -g 60 -b:v 6000k -c:a aac -b:a 128k -strict -2 -f flv ${rtmp}
 ffmpeg -re -i "$video" -c:v copy -c:a aac -b:a 192k -strict -2 -f flv ${rtmp}
done
```


- 资源下载

https://www.vidjuice.com/
