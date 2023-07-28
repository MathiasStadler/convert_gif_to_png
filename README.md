# png,gif via ocr to txt files bash

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

- run script in terminal

```bash



```