---
description: возможности
---

# Продукты Git

## Продукты github

Система управления проектами и версиями кода, а также платформа социальных сетей, созданная для разработчиков [Github](https://github.com/).

Простой хостинг для вашего сайта \([GitHub Pages](https://pages.github.com/)\);

Хостинг для онлайн-презентаций и инструмент для их создания \([GitPitch](https://gitpitch.com/)\);

[GitBook](https://www.gitbook.com/) - платформа для публикации книг, документации или подобного тому.

#### [Настройка ssh ключей](https://itnote.ksw.su/linux-os/bezopasnost/ssh-klyuchi)

#### ~~~~[Установка Git **и настройка Git**](https://itnote.ksw.su/git-nashe-vse/git/nastroika-git)\*\*\*\*

#### [Утилиты для Git](https://itnote.ksw.su/git-nashe-vse/git/utility-dlya-git)

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

## Аутентификация на GitHub

После регистрации на Github для удобства и безопасности работы лучше использовать аутентификацию по ключам SSH. При генерации нового SSH-ключа используйте e-mail, привязаный к GitHub:

```text
$ cd ~/.ssh
$ ssh-keygen -t rsa -b 4096 -C "mail_account@gmail.com"
```

При генерации ключ сохраним под именем githubkey.

```text
#запуск агента
$ eval "$(ssh-agent -s)"

# добавить ключ в агент
$ ssh-add ~/.ssh/githubkey
```

Для добавления сгенерированого ключа надо его скопировать.

```text
$ cat ~/.ssh/githubkey.pub
```

Заходим на страницу «Settings» GitHub, выбрать поле «SSH and GPG keys» и вставляем ключ.

Чтобы проверить, всё ли прошло успешно, попробуйте выполнить команду.

```text
$ ssh -T git@github.com

Hi username! You've successfully authenticated, but GitHub does not provide shell access.
```



