---
description: проверено  Linux Mint 20
---

# Install

## **Проверить и установить в системе Python.**

Обычно в linux уже какая то версия уже установлена, проверяем:

```text
$ python -V
```

### Для установки набросал скрипт \(cat install\_python.sh\):

```text
#!/bin/bash

sudo apt-get install build-essential ca-certificates curl \
gcc libbz2-dev libffi-dev libncurses5-dev libncursesw5-dev \
libreadline-dev libssl-dev libsqlite3-dev llvm \
make python3-dev tk-dev wget xz-utils zlib1g-dev

wget https://www.python.org/ftp/python/3.6.3/Python-3.6.3.tgz

tar xvf Python-3.6.3.tgz

cd Python-3.6.3
./configure --enable-optimizations --enable-loadable-sqlite-extensions

make -j8

sudo -H make altinstall

sudo -H pip3.6 install virtualenvwrapper

#Перезапуск командного интерпретатора
cd ~
echo "export VIRTUALENVWRAPPER_PYTHON=/usr/local/bin/python3.6" >> .bashrc
echo "export WORKON_HOME=~/venv" >> .bashrc
echo ". /usr/local/bin/virtualenvwrapper.sh" >> .bashrc
exec bash

#pip
sudo -H pip install --upgrade pip
```

