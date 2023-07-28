# file comes from which package

> tried on on 22.04.1-Ubuntu

## 1

### [description source from here](https://www.cyberciti.biz/faq/equivalent-of-rpm-qf-command/)

### install via bash

```bash
sudo apt install apt-file
```

### setup tool

> update package with files list

```bash
apt-file update
```

### test it

```bash
apt-file search login
```

## 2

```bash
dpkg -S /bin/ls

output: coreutils: /bin/ls

```
