# Warehouse video

Put the clip here as `warehouse.mp4`. The video section on the home page appears automatically once this file exists. If the file is missing, the section stays hidden.

Good clip: 10 to 30 seconds, landscape, no sound needed, 1280 x 720 or 1920 x 1080, under about 8 MB.

Free sources whose licenses allow use on a business site: Pexels, Pixabay, Mixkit, Coverr. Useful searches: "warehouse forklift", "pallet racking", "packing boxes", "conveyor boxes", "fulfillment center".

To shrink a large file (needs ffmpeg):

    ffmpeg -i input.mp4 -t 25 -an -vf "scale=1280:-2" -c:v libx264 -crf 28 -preset slow -movflags +faststart warehouse.mp4
