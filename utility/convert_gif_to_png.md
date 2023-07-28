# convert pictures form format gif to png

## used tool convert

### install via

```bash
sudo apt-get install imagemagick imagemagick-doc 
```

### version

```bash
convert -version
Version: ImageMagick 6.9.11-60 Q16 x86_64 2021-01-25 https://imagemagick.org
Copyright: (C) 1999-2021 ImageMagick Studio LLC
License: https://imagemagick.org/script/license.php
Features: Cipher DPC Modules OpenMP(4.5) 
Delegates (built-in): bzlib djvu fftw fontconfig freetype heic jbig jng jp2 jpeg lcms lqr ltdl lzma openexr pangocairo png tiff webp wmf x xml zlib
```

## view jpg start from shell

```bash
eog xvz.jpg

#e.g.
eog 1690380478072.jpg
```

## covert in png format

```bash
convert ~/Downloads/1690268873786.jpg ~/Downloads/1690268873786.png

//or
cat <<EOT > convert_gif_2_png.sh
#!/bin/bash
set -e
if [[ \$1 == "" ]] #Where "\$1" is the positional argument you want to validate 
 then
 echo "ERROR: file to convert failed !!!"
 exit 0
fi
ORIGINAL_FILE=\$1
echo "convert  \$ORIGINAL_FILE to ";
ORIGINAL_FILE_EXTENSION=".\${ORIGINAL_FILE##*.}"
TARGET_FILE_NAME="$(basename \$FILE_NAME \$ORIGINAL_FILE_EXTENSION)"
convert \$ORIGINAL_FILE_EXTENSION \$TARGET_FILE_NAME".png"
echo \$TARGET_FILE_NAME".png"
if [ \$? -eq 0 ] 
then 
  echo "Successfully created file" 
else 
  echo "Could not create file" >&2 
fi
EOT

```

> [bash error handling from here](https://madflojo.medium.com/understanding-exit-codes-in-bash-6942a8b96ce5)

# weiter
https://devconnected.com/how-to-check-if-file-or-directory-exists-in-bash/