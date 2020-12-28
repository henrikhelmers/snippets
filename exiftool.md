# Exiftool


## Determine Adobe RGB or sRGB

When the color space is sRGB, include the sRGB profile and set the following Exif tags:
- ColorSpace = 1
- InteroperabilityIndex = "R98"
- InteroperabilityVersion = "0100"

When the color space is Adobe RGB, include the Adobe RGB 1998 profile, and set the following Exif tags:
- ColorSpace = 65535
- InteroperabilityIndex = "R03"
- InteroperabilityVersion = '0100'

When the color space is anything else, include the appropriate ICC profile and set the following Exif tags:
- ColorSpace = 65535
- delete the InteroperabilityIndex field
- delete the InteroperabilityVersion field


## Show all QuickTime data
`exiftool -a -s -G1 -time:all`
