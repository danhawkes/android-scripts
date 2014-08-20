android-scripts
===============

Utility scripts for Android development.

## andkey

Quickly generate a keystore for signing an application.

…because keytool's too fussy when you don't care about the X509 details:

![](assets/andkeystore-keytool.gif)

### Usage

```
usage: andkey [-h] [-o OUT] [-cn CN] [-ou OU] [-on ON] [-ln LN] [-l SN]
              [-cc CC]
              alias

Quickly generate a key store suitable for signing an Android application. The
cipher, key size and validity are set to recommended values. Various X509
attributes are set to 'Unknown' unless otherwise specified.

positional arguments:
  alias                 Alias for the key

optional arguments:
  -h, --help            show this help message and exit
  -o OUT, --output OUT  Output file
  -cn CN, --common-name CN
                        X509 Common name
  -ou OU, --org-unit OU
                        X509 Organization unit
  -on ON, --org-name ON
                        X509 Organization name
  -ln LN, --locality-name LN
                        X509 Locality name
  -l SN, --state-name SN
                        X509 State/Province name
  -cc CC, --country CC  X509 Country code
```

### Examples

Generate a keystore with a single alias, 'myapp', and call it 'myapp.keystore':

`andkey myapp -o 'myapp.keystore'``  

## andimg

Resize an image for multiple screen densities.

* Resized images are placed in `drawable-*dpi` directories.
* Generates `XXHDPI`, `XHDPI`, `HDPI` and `MDPI` variants.

![](assets/andimg.png)

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

Output:
```
src/main/res/drawable-mdpi/icon.png     [32x32]
src/main/res/drawable-hdpi/icon.png     [48x48]
src/main/res/drawable-xhdpi/icon.png    [64x64]
src/main/res/drawable-xxhdpi/icon.png   [96x96]
```
As above, but with the standard launcher icon resolution:

`andimg -r src/main/res artwork/icon.png launcher`
