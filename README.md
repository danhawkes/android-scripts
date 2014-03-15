android-scripts
===============

Utility scripts for Android development.

## andimg

Resize an image for multiple Android densities.

### Dependencies

imagemagick, python 2.7+

### Usage
```
andimg [-h] [-o OUT] [-e EXT] file x y

Resize an image for multiple Android densities.

positional arguments:
  file                  Source file to be resized.
  x                     Target X resolution for mdpi (1x) image.
  y                     Target Y resolution for mdpi (1x) image.

optional arguments:
  -h, --help            show this help message and exit
  -o OUT, --output-dir OUT
                        Output directory.
  -e EXT, --extension EXT
                        Output file extension. Defaults to PNG.
```
