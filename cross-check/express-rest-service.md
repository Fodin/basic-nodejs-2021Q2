# Express REST service

Проверку тестов следует проводить в [Node.js последней LTS версии](https://nodejs.org/en/).
При выставлении оценок используйте [рекомендации RSSchool](https://docs.rs.school/#/cross-check-flow?id=%d0%9f%d1%80%d0%b8%d0%bd%d1%86%d0%b8%d0%bf-%d0%be%d1%86%d0%b5%d0%bd%d0%ba%d0%b8-%d1%80%d0%b0%d0%b1%d0%be%d1%82%d1%8b-%d0%bf%d1%80%d0%b8-cross-check-%d0%bf%d1%80%d0%be%d0%b2%d0%b5%d1%80%d0%ba%d0%b5).
Минимальная оценка за таску **не может быть меньше 0**.
Максимально возможная оценка: **170 баллов** - 1 пункт, **10 баллов** - 2 пункт, **10 баллов** - 3 пункт, **10 баллов** - 4 пункт, итого: **200 баллов**.

1. Каждый успешный тест при выполнении скрипта `npm run test` **+10 баллов**.
2. Код приложения, работающий с сущностью `user` разделен по модулям в соответствии с его назначением (к примеру: работа с запросом и ответом в `*.router.js`, бизнес-логика в `*.service.js`, работа с хранилищем данных в `*.repository.js` и т.п.) **+10 баллов**
4. Аналогично пункту 3 для `boards` **+10 баллов**
5. Аналогично пункту 3 для `tasks` **+10 баллов**

## Штрафы:
* Наличие изменений в тестах либо в workflow **минус 100 баллов**
* Каждый коммит после дедлайна **минус 20 баллов**.

## Подсказки:

> ### **Как увидеть различия для папок `test` и `.github` между текущей веткой и веткой master из темплейта**
>  Помимо несовпадения, отображаемого в workflow во время пулл реквеста (`MD5 check`), есть следующий способ:
>  1. Открыть глобальный `.gitconfig`:
>    `git config --global -e`
>  2. Добавить в глобальный `.gitconfig` следующие строки. Если вы не используете VSCode замените `code` на соответстующую вашей IDE команду (или путь к выполняемому файлу).
>    ```
>      [diff]
>        tool = vscode
>      [difftool "vscode"]
>        cmd = code --wait --diff $LOCAL $REMOTE
>    ```
>  3. Добавить в качестве дополнительного удаленного репозитория темплейт
>    ```bash
>      git remote add template https://github.com/rolling-scopes-school/nodejs-course-template.git
>    ```
>  4. Создать локальную копию ветки master из темплейта
>     `git fetch template master:template-master`
>  5. Запустить сравнение для текущей ветки с веткой master темплейта для тестов
>    `git difftool <название текущей ветки> template-master test/`
>  5. Запустить сравнение для текущей ветки с веткой master темплейта для workflow
>    `git difftool <название текущей ветки> template-master .github/`