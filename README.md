# video-tools

Bits and pieces for dealing with video, such as presets for shrinking videos

The pfohm30fps720mp3variable.json file shrinks a 1GB video file, such as from the press conferences at the Swedish Public Health Agency, by about a factor of 7 in initial tests. From 1GB to 132MB.

It changes resolution to 720, uses H265 instead of H264 and changes to variable bit rate mp3 sound, from AAC.

There are probably a lot more things you can do.

Tidbit: Changing to a variable bit rate mp3 with quality factor 2, shrunk the file in half compared to 320mbps MP3.

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
