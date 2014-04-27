android-scripts
===============

Utility scripts for Android development.

## andimg

<p align="center" >
  <img src="assets/andimg.png" alt="andimg">
</p>

Resize an image for multiple screen densities.

* Resized images are placed in `drawable-*dpi` directories.
* Generates `XXHDPI`, `XHDPI`, `HDPI` and `MDPI` variants.

### Dependencies

imagemagick, python 2.7+

### Usage
```

andimg [options] [file] [res]

positional arguments:
  file                  Source file to be resized.
  res                   Output image resolution. May be one of the predefined
                        sizes: ['launcher', 'notification', 'action_bar',
                        'small'], or a resolution in the form of 'X,Y'.

optional arguments:
  -h, --help            show this help message and exit
  -o OUT, --output-dir OUT
                        Output directory.
  -e EXT, --extension EXT
                        Output file extension. Defaults to PNG.

                        Output file extension. Defaults to PNG.
```

### Examples

From the root of a project, resize an image from `artwork`, and put it in the `src/main/res` directory:

`andimg -o src/main/res artwork/icon.png 32x32`

As above, but with the standard launcher icon resolution:

`andimg -r src/main/res artwork/icon.png launcher`
