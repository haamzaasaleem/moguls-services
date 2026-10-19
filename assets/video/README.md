# Warehouse video

`warehouse.mp4` (H.264) and `warehouse.webm` (VP9) are the same 16 second clip, muted, 1280 x 720. `warehouse-poster.jpg` shows while it loads. If the video files are missing, the home page video section stays hidden.

The clip is cut from three Pexels stock videos (14910119, 15762361 and 15762450): an aisle walk, a pass along carton shelving and a worker scanning cartons, joined with short crossfades.

To replace it with your own footage, export a new `warehouse.mp4` and make the WebM and poster from it (needs ffmpeg):

    ffmpeg -i input.mp4 -t 20 -an -vf "scale=1280:-2" -c:v libx264 -crf 27 -preset slow -movflags +faststart warehouse.mp4
    ffmpeg -i warehouse.mp4 -c:v libvpx-vp9 -crf 38 -b:v 0 -an warehouse.webm
    ffmpeg -ss 0.5 -i warehouse.mp4 -frames:v 1 -q:v 4 warehouse-poster.jpg
