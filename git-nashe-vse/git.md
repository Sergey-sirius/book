---
description: возможности
---

# Git

## Продукты github

Система управления проектами и версиями кода, а также платформа социальных сетей, созданная для разработчиков [Github](https://github.com/).

Простой хостинг для вашего сайта \([GitHub Pages](https://pages.github.com/)\);

Хостинг для онлайн-презентаций и инструмент для их создания \([GitPitch](https://gitpitch.com/)\);

[GitBook](https://www.gitbook.com/) - платформа для публикации книг, документации или подобного тому.

## Установка Git **и настройка Git**

```text
$ sudo apt-get install git
```

```text
$ git config --global user.name "username"
$ git config --global user.email "username.user@example.com"

# посмотреть настройки
$ git config --list
```

**Отображение статуса репозитория**

Установка дополнительной [утилиты](https://github.com/magicmonty/bash-git-prompt/). 

```text
$ cd ~

$ git clone https://github.com/magicmonty/bash-git-prompt.git .bash-git-prompt --depth=1
```

 добавить в конец файла .bashrc строки:

```text
GIT_PROMPT_ONLY_IN_REPO=1
source ~/.bash-git-prompt/gitprompt.sh
```

теперь при переходе в папку репозитория нам отображается в какой ветке мы находимся.

Для GUI очень неплохой продукт [GitKraken](https://www.gitkraken.com/), для различных версий линукс и виндовс.

## **Инициализация репозитория**

```text
$ git init

```

## Работа с Git

**git status** - статус репзитория

**Файл .gitignore** - файл в котором можно описать какие файлы из локального репозитория не должны попадать в репозиторий.

**git add** - добавить файлы за которыми нужно следить в репозиторий

**git commit** - добавляет в репозиторий все изминения

**git diff -** посмотреть разницу между различными состояниями, после команды git add или commit она уже не покажет изминений. Чтобы показать отличия между staging и последним коммитом, надо добавить параметр --staged.





