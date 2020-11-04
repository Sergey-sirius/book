# SSH ключи

## Настройка ssh ключей

```text
# генерируем ключ для аккаунта на github
$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
Enter a file in which to save the key (/home/you/.ssh/id_rsa): key_name [Press enter]
# ssh-agent in the background
$ eval "$(ssh-agent -s)"
> Agent pid 59566

# добавляем сгенерированый ключ агенту
$ ssh-add ~/.ssh/key_name

# Add the SSH key to your GitHub account.
cat ~/.ssh/key_name

# скопировать ключ и в разделе settings добавить
```

### 

## Безопасность для GitHub

#### Аутентификация на GitHub

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



