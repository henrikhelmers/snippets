# Exiftool


## Determine Adobe RGB or sRGB

When the color space is sRGB, include the sRGB profile and set the following Exif tags:
- ColorSpace = 1
- InteroperabilityIndex = "R98"
- InteroperabilityVersion = "0100"

When the color space is Adobe RGB, include the Adobe RGB 1998 profile, and set the following Exif tags:
- ColorSpace = 65535
- InteroperabilityIndex = "R03"
- InteroperabilityVersion = "0100"

When the color space is anything else, include the appropriate ICC profile and set the following Exif tags:
- ColorSpace = 65535
- Delete the InteroperabilityIndex field
- Delete the InteroperabilityVersion field


## Show all QuickTime data
```
exiftool -a -s -G1 -time:all
```


## Set all time fields
```
for f in "$@"
do
/usr/local/bin/exiftool −overwrite_original_in_place "-filemodifydate<datetimeoriginal" "-trackcreatedate<datetimeoriginal" "-mediacreatedate<datetimeoriginal" "-trackmodifydate<datetimeoriginal" "-mediamodifydate<datetimeoriginal" "-quicktime:CreateDate<datetimeoriginal" "-quicktime:ModifyDate<datetimeoriginal" "$f"
done
```
