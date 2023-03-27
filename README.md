# video-tools

Bits and pieces for dealing with video, such as presets for shrinking videos

The pfohm30fps720mp3variable.json file shrinks a 1GB video file, such as from the press conferences at the Swedish Public Health Agency, by about a factor 0f 7 in initial tests.

It changes resolution to 720, uses H265 instead of H264 and changes to variable bit rate mp3 sound, from AAC.

There are probably a lot more things you can do.

Tidbit: Changing to variable bit rate mp3 with quality factor 2, shrunk the file in half compared to 320mbps MP3.

## Usage

```HandBrakeCLI -i inputfile.mp4 -o outputfile.mp4 --preset-import-file pfohm30fps720mp3variable.json --preset 'pfohm30fps720mp3variable'```

## Dependencies

HandBrakeCLI, which on Ubuntu Linux can be installed with:

```sudo apt install handbrake-cli```
