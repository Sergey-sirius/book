---
description: werwerewr
---

# Установка for LinuxMint

## **Проверить и установить в системе Python.**

Обычно в linux уже какая то версия уже установлена, проверяем:

```text
$ python -V
```

#### Для установки набросал скрипт \(cat install\_python.sh\):

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

### Создание виртуального окружения, c Python 3.6.3 по умолчанию:

```text
#!/bin/bash

# Создание виртуального окружения, c Python 3.6.3 по умолчанию
#mkvirtualenv --python=/usr/local/bin/python3.6 py36

# переход в созданное виртуальное окружение
# workon py36

# Выход из виртуального окружения:
# deactivate

# удалить созданое окружение 
# rmvirtualenv py36

#
# Для Python с версии 3.5 рекомендуется использовать модуль venv
# создан необходимое окружение в папке
python3.6 -m venv new_env/py363

# перехода в виртуальное окружение
source new_env/py363/bin/activate

# Выход из виртуального окружения:
# deactivate
```

### Список [IDE](https://wiki.python.org/moin/IntegratedDevelopmentEnvironments/) для комфортной работы в Python

### Система управления пакетами pip

В зависимости от версии Python \(настроеного окружения\) нужно использовать pip \(2.7\) или pip3 \(3.5\)

```text
pip --version

pip3 --version
```

### **Установка и удаление модулей**

```text
# install
pip install tabulate

# remove 
pip uninstall tabulate

# update 
pip install --upgrade tabulate

# альтернативный вариант вызова pip
python3.6 -m pip install tabulate
```



