# remove read-only passwd of pdf

> tested on 22.04.1-Ubuntu

## install

> apt update && sudo apt install ghostscript

## remove password ( command on cli)

```bash
gs -q -dNOPAUSE -dBATCH -sDEVICE=pdfwrite -sOutputFile=/tmp/unencrypted.pdf  -f /tmp/encrypted.pdf 
 
```
