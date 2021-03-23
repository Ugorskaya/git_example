# Начало работы с GIT
При выполнении задания можно руководствоваться официальным учебником:

Pro Git book

1. Установите GIT на свой компьютер: http://git-scm.ru/

2. Запустите GIT в консоли и создайте новый репозиторий:
    ```
    git init
    ```  
3. Задайте в настройках имя пользователя и электронную почту:
    ```
    git config --local user.name "John Doe"
    git config --local user.email johndoe@example.com
    ```

4. Создайте файлы, необходимые для проекта.

5. Просмотрите состояние изменений:
    ```
    git status
    ```

    Если заметили файлы, в которых были внесены изменения, которых быть не должно (например, случайно изменили файл и эти изменения не нужны), то можно откатить эти изменения:

    ```
    git checkout -- file_0.html
    ```

6. Добавьте файлы в индекс:
    ```
    git add file_a.html
    git add file_b.html
    git add file_c.html
    ...
    git add file_z.html
    ```

    Можно добавить сразу все измененные в проекте файлы с помощью команды:
    ```
    git add -A
    ```
    или
    ```
    git add .
    ``` 

    Но следует быть предельно осторожным.

    После добавления файлов, проверьте состояние:

    ```
    git status
    ```

    Если все хорошо, то можно продолжить.

    Если же заметили новые файлы, которые не должны были попасть в репозиторий, то их необходимо отменить:

    ```
    git rm --cached file_x.html
    ```

    Если были изменены файлы, которые сейчас не нужно проталкивать в репозиторий:

    ```
    git reset HEAD file_n.html
    ```


7. Создайте новый коммит из измененных файлов:
    ```
    git commit -m "commit description"
    ```

    Вместо *commit description* необходимо дать осмысленное описание вашего коммита.


8. Создайте новый репозиторий на одном из хостингов репозиториев:

    - [GitHub](https://github.com/)
    - [BitBucket](https://bitbucket.org/)
    - [GitLab](https://gitlab.com/)
    - [GIT Forlabs](https://git.hostfl.ru/)

9. Добавьте удаленный репозиторий в ваш локальный:

    ```
    git remote add origin https://git.hostfl.ru/Ugorskaya/git_example.git
    ```

    Вместо `https://git.hostfl.ru/Ugorskaya/git_example.git` необходимо указать URL вашего репозитория.

10. Отправьте ваши изменеия в удаленный репозиторий:

    ```
    git push -u origin master
    ```

    Обратите внимание, что для первой отправки необходимо указать ветку на удаленном репозитории.

    В последующем отправить коммит в удаленный репозиторий можно будет командой `git push`.

11. Удостоверьтесь, что ваши файлы сохранены в удаленном репозитории.

12. Добавьте файлы в свой проект и/или измените несколько существующих файлов.

13. Отправьте изменения в удаленный репозиторий.

14. Пометьте текущий коммит как первую версию вашего проекта:

    ```
    git tag v1.0
    ```

    Команда создает новую метку (тег) с именем `v1.0`.

15. Отправьте созданную метку на сервер:

    ```
    git push origin v1.0
    ```

16. Создайте новую ветку в своем проекте:

    ```
    git branch test1
    ```

    `test1` - это имя вашей ветки.


    Проверьте список ваших текущий веток:

    ```
    git branch
    ```

    Затем переключитесь на новую ветку:

    ```
    git checkout test1
    ```

    Можно сразу создать новую ветку и переключиться на нее:

    ```
    git checkout -b test1
    ```

17. Добавьте файлы и/или измените существующие в новой ветке, создайте из них коммит.

18. Отправьте новую ветку в удаленный репозиторий:

    ```
    git push -u origin test1
    ```

    В дальнейшем в новую ветку можно отправлять обычной командой `git push`.

19. Переключитесь на ветку **master**:

    ```
    git checkout master
    ```

20. Измените и/или добавьте несколько файлов в ветке **master**, создайте их них коммит, отправьте в удаленный репозиторий.

21. Вернитесь на ветку **test1**.

22. Измените и/или добавьте несколько файлов в ветке **test1**, создайте их них коммит, отправьте в удаленный репозиторий.

23. Объедините изменения из ветки **test1** в ветку **master**.

    Стоит учесть, что целесообразнее, сначала втянуть изменения из ветки **master** в ветку **test1**, а затем переключиться на ветку **master** и слить с изменениями из ветки **test1**.

    ```
    git merge master

    git push

    git checkout master

    git merge test1

    git push
    ```

    На любом из этапов объединения может возникнуть конфликт, если необходимо уладить.

    Если конфликт разрешается вручную, то необходимо выполнить `git add conflicted_file.html` и сделать коммит.

24. Создайте метку с новой версией `v1.1` и отправьте ее на сервер.

25. Предоставьте ссылку на ваш репозиторий.
