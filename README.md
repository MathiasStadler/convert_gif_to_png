# convert gif to png

- create script

```bash
cat <<EOT > src/convert_gif_2_png.sh
#!/bin/bash
set -e
if [[ \$1 == "" ]] #Where "\$1" is the positional argument you want to validate 
 then
 echo "ERROR: file to convert failed !!!"
 exit 0
fi
ORIGINAL_FILE_NAME=\$1
echo "convert source file => \$ORIGINAL_FILE_NAME to ";
ORIGINAL_FILE_EXTENSION=".\${ORIGINAL_FILE_NAME##*.}"
echo "ORIGINAL_FILE_EXTENSION => \$ORIGINAL_FILE_EXTENSION"
TARGET_FILE_NAME="\$(basename \$ORIGINAL_FILE_NAME \$ORIGINAL_FILE_EXTENSION)"
echo "basename => \$TARGET_FILE_NAME"
echo "COMMAND => convert \$ORIGINAL_FILE_NAME \$TARGET_FILE_NAME.png"
convert \$ORIGINAL_FILE_NAME \$TARGET_FILE_NAME.png
echo \$TARGET_FILE_NAME".png"
if [ \$? -eq 0 ] 
then 
  echo "Successfully created file" 
else 
  echo "Could not create file" >&2 
fi
EOT

```

- make script executable in terminal

```bash
chmod +x ./src/convert_gif_2_png.sh 
```

- run script with samples

```bash
./src/convert_gif_2_png.sh ./samples/sample_page_one.jpg 
./src/convert_gif_2_png.sh ./samples/sample_page_two.jpg 
./src/convert_gif_2_png.sh ./samples/sample_page_third.jpg
```
