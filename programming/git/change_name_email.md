# Как изменить имя пользователя и e-mail для проектов в определенной папке

___

1. Создать папку `~/.config/git`:
    ```bash
    mkdir ~/.config/git 
    ```
2. Создать простой текстовый файл (например, по имени пользователя):
    ```bash
    vim ~/.config/git/user
    ```
3. Вставить в файл информацию о пользователе:
    ```
   [user]
        name = user
        email = user@example.com
   ```
4. Добавить в файл `~/.gitconfig` следующую информацию:
    ```
   [includeIf "gitdir:<указать_путь_до_необходимой_папки>/*/"]
        path = ~/.config/git/user 
   ```

### Проверяем

Создать git проект в необходимой папке и выполнить следующие команды:
```bash
git config --get user.name
git config --get user.email
```
