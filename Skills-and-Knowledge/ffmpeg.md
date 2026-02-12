# get codec:
ffprobe -v error -select_streams v:0 -show_entries stream=codec_name -of default=noprint_wrappers=1:nokey=1 video.mkv

# change code:
ffmpeg -i input.av1 -c:v libx264 output.mp4

# cut:
ffmpeg -i input.mp4 -t 10 -c copy output.mp4

# Single frame:
ffmpeg -i input.mp4 -vf "select=eq(n\,99)" -vframes 1 output.png

# change fps:
ffmpeg -i input.mp4 -r <new_fps> output.mp4
(will change to 264 codec)