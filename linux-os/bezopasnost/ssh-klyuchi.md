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



