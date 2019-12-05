### FFmpeg将MP4文件转为ts并生成m3u8文件

### ffmpeg -i input.mkv -acodec copy -vcodec copy out.mp4  || ffmpeg -i input.mkv -acodec libfaac -vcodec libx264 out.mp4
### ffmpeg -i out.mp4 -vcodec copy -vbsf h264_mp4toannexb output.ts
### ffmpeg -i output.ts -c copy -map 0 -f segment -segment_list playlist.m3u8 -segment_time 10 output%03d.ts
 
* output.ts是源文件名，playlist.m3u8是生成的m3u8文件名，10 是切片秒数，output%03d.ts是输出文件名
