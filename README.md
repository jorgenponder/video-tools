# video-tools

Bits and pieces for dealing with video, such as presets for shrinking videos

The pfohm30fps720mp3variable.json file shrinks a 1GB video file, such as from the press conferences at the Swedish Public Health Agency, by about a factor of 7 in initial tests. From 1GB to 132MB.

It changes resolution to 720, uses H265 instead of H264 and changes to variable bit rate mp3 sound, from AAC.

There are probably a lot more things you can do.

Tidbit: Changing to a variable bit rate mp3 with quality factor 2, shrunk the file in half compared to 320mbps MP3.

The original videe was, according to ffmpeg:
    
    Video: h264 (Main) (avc1 / 0x31637661), yuv420p, 1920x1080 [SAR 1:1 DAR 16:9], 1997 kb/s, 30 fps, 30 tbr, 90k tbn, 60 tbc (default)
    Audio: aac (LC) (mp4a / 0x6134706D), 48000 Hz, stereo, fltp, 179 kb/s (default)
    
The resulting video is:

    Video: hevc (Main) (hvc1 / 0x31637668), yuv420p(tv, bt709), 1280x720 [SAR 1:1 DAR 16:9], 122 kb/s, 29.99 fps, 30 tbr, 90k tbn, 30 tbc (default)
    Audio: mp3 (mp4a / 0x6134706D), 48000 Hz, stereo, fltp, 101 kb/s (default)

## Usage

```HandBrakeCLI -i inputfile.mp4 -o outputfile.mp4 --preset-import-file pfohm30fps720mp3variable.json --preset 'pfohm30fps720mp3variable'```

## Dependencies

HandBrakeCLI, which on Ubuntu Linux can be installed with:

```sudo apt install handbrake-cli```

## Notes

VideoQualitySlider 50 looks absolutely terrible (higher value is worse quality). 38% reduction in overall file size.

40 looks not great, but possibly bearable.  33% reduction in overall file size.

35 looks fine-ish, 11% reduction in overall file size.

32 looks great

Lowering the resolution to 576 made no difference in file size.

Lowering the mp3 quality to "5" gave a 5% smaller video file.

With the preset JSON file, about 46% of the file size is sound. You could probably then get down to 75% of total file size with some worse sound quality. However sound is the most important part of a press conference video.
