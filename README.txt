The encoder of Furion, which is based on the x264 lib.

We modify the x264 encoder to support direct encoding, allowing each P frame directly refers to one I frame.

Thus all P frames are only depenting with the I frame.

To compile the encoder, run:

./configure 

to see if your machine supports lavf (to read png/jpeg frames) and lsmash (to support mp4 format).

then run:

make

make install

to compile the encoder.

An example of using the encoder:

x264 --crf 25 --tune fastdecode --fps 64 --keyint 1 --min-keyint 1 --no-scenecut --input-res 4096*1024 --bframes 0  -o /Volumes/Backup/viking_test_4K_crf=25_fps=64.mp4 /Volumes/Software/Viking/sunlh_%3d.png