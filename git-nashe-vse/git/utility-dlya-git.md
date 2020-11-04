# Утилиты для Git

* **Отображение статуса репозитория**

Утилита для коммандной строки, установка дополнительной [утилиты](https://github.com/magicmonty/bash-git-prompt/). \([https://github.com/magicmonty/bash-git-prompt/](https://github.com/magicmonty/bash-git-prompt/)\)

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

* **GitKraken**

Для GUI очень неплохой продукт [GitKraken](https://www.gitkraken.com/), для различных версий линукс и виндовс.

![](../../.gitbook/assets/gk1.png)

