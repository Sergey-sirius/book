---
description: werwerewr
---

# Установка for LinuxMint

## Создание виртуального окружения, c Python 3.6.3 по умолчанию:

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

## Список [IDE](https://wiki.python.org/moin/IntegratedDevelopmentEnvironments/) для комфортной работы в Python

## Система управления пакетами pip

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



