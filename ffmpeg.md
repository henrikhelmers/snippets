# FFMPEG


## Discarded Fujifilm mov > mp4 Automator script
```
for f in "$@"
do
FOLDER=$(dirname "${f}")
FILENAME=$(basename -- "$f")
EXTENSION="${FILENAME##*.}"
FILENAME="${FILENAME%.*}"
OUTPUT="${HOME}/Downloads/${FILENAME}.mp4"
/usr/local/bin/ffmpeg -i "$f" -vf scale=320:-1 -preset ultrafast -c:v libx265 -crf 22 -pix_fmt yuv420p10le -c:a aac -b:a 256k -tag:v hvc1 "$OUTPUT"
/usr/local/bin/exiftool −overwrite_original_in_place -r -tagsFromFile "$f" -all:all "$OUTPUT"
done
```


## .mov recompress
```ffmpeg -i a.MOV -map_metadata 0 -c copy -movflags use_metadata_tags c.MOV
exiftool -TagsFromFile a.MOV "-all:all>all:all" c.MOV
```