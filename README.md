# Репозиторий для **pull request**
* В своём аккаунте на GitHub создать копию репозитория **"AndreyBulgakov19/SCV_Git_PR"** с помощью кнопки **"Fork"**.
---
* Клонировать копию репозитория на локальный компьютер.
---
* Создать новую ветку.
---
* Добавить файл с инструкцией в новую ветку.
---
* Дополнить инструкцию разделами по работе с удалёнными репозиториями, pull request.
---
* Зафиксировать изменения (коммиты).
---
* Отправить изменения на GitHub.
---
* На сайте GitHub выполнить **Pull request**.
---

                        
# Работа c GIT #
## 1. Проверка наличия установленного Git
В терминале выполнить команду `git --version`.
Если Git установлен появится сообщение о версии программы, иначе будет сообщение об ошибке.
## 2. Установка Git
Загружаем последнюю версию Git с сайта. [Загрузка Git](https://git-scm.com/downloads)
Устанавливаем с настройками по умолчанию.
## 3. Настройка Git
При первом использовании Git необходимо представиться. Для этого нужно ввести в терминале две команды:
```
git config --global user.name «Ваше имя английскими буквами»
git config --global user.email Ваша почта@example.com
```
```C#
while (n < 0)
{
    n++;
}
```
## 4. Инициализация репозитория
В терминале переходим к папке, в которой хотим создать репозиторий. Выполняем команду:
```
git init
```
## 5. Запись изменений в репозиторий
Далее необходимо добавить файл в отслеживание (подготавливает к сохранению файл) следующей командой:
```
git add <file>
```
и с помощью команды `git status` проверяем отслеживаемый файл, который подсветился зеленным цветом. Для того чтобы подготовить все файлы измененные в директории могут использоваться команды
```
git add .
git add --all
```
Для того чтобы зафиксировать изменения в репозитории необходимо воспользоваться коммандой:
```
git commit -m <>
```
`-m` сокращенное от message, в кавычках мы указываем то изменние которое внесли, чтобы нам было легче ориентироваться в коммитах.
`-a` сокращенное add (заменяет команду `git add`), индекс служит только для сохранения изменений, при этом она не предназначена для добавления в отслеживание файл.
`--amend` данное добавление позволяет удалить текущий заголовок и пишет новый, например так
```
git commit --amend -m <file_name_new>
```
Если вдруг мы хотим посмотреть последние изменния то можно воспользоваться командой:
```
git diff
```
Если вдруг мы вошли во встроенный редактор с помощью команды `git commit` необходимо нажать клавишу `I`, внизу появится слово "ВСТАВКА", далее набираем комментарий. Затем необходимо переключится на англ. раскладку и нажимаем клавишу `Esc`. Далее внизу печатаем - `:wq`, что означает сохранить и выйти. Делается это в случае если комментарии очень большие.
С помощью команды 
```
git restore <file>
```
можно удалить все внесенные изменения, которые не были сохранены.
Также можно убрать файл из отслеживания с помощью команды
```
git restore --staged <file>
```
Также сюда можно добавить картинку по синтаксису языка MarkDown:
![YazikMarkDown](YazikMarkDown.png)
## 6. Просмотр истории в коммитах
Чтобы посмотреть историю коммитов необходимо в терминале набрать следующую команду:
```
git log
```
В данном списке отобразится история коммитов с ее хэш-суммами(по которым в дальнейшем можно будет перемещаться).С данной командой можно сочетать следующие индексы:
`--oneline` - отображает краткую историю коммитов
`--graph` - для визуализации просмтра
`-<number>` - для вывода определенного числа последних коммитов
`-p` - показывает разницу между коммитами
## 7. Перемещение между сохранениями
Для перемещения используется команда:
```
git checkout <хэш-сумма коммита (достаточно 4-5 первых символов,
либо в логе щелкнуть ЛКМ дважды на хэш-сумме коммита)>
git checkout <master>
```
Есть более новая команда:
```
git switch
```
Данная команда используется с символом - `-`, чтобы вернутся в ветку **master**. Также можно использовать ее для создания новой ветки и перехода в нее в следующем виде:
```
git switch -c <new_branch_name>
```
## 8. Игнорирование файлов
Для того чтобы исключить из отслеживаня в репозитории определенный файлы или папки, необходимо там создать файл ***.gitignore*** и записать в него их названия или шаблоны(например расширение формата `.jpg`), соответствующие таким файлам или папкам.удали меня
## 9. Создание веток в Git
По умолчанию имя основной ветки в Git - *master*.
Создать ветку можно командой:
```
git branch <название для новой ветки>
```
Список веток в репозитории можно посмотреть с помощью команды:
```
git branch
```
Текущая ветка будет отмечена звездочкой: **\*createBranches**
Для перехода в другую ветку можно использовать следующие команды:
```
git checkout <branch_name>
git checkout -b <new_branch_name>   (для создания и переключения на новую ветку)
git switch <branch_name>
git switch -c <new_branch_name>     (для создания и переключения на новую ветку)
git switch -        (для переключения между двумя последними активными ветками)
```
## 10. Слияние веток и разрешение конфликтов
Для слияния выбранной ветки необходимо перейти в ту ветку, к которой хотим присоединить новую ветку, и с текущей ветки нужно выполнить команду:
```
git merge <название выбранной ветки>
```
После слияния выдает сообщение о том что ветки слились, и другие параметры, как например по типу слияния fast-forward(если не вносились изменения параллельно в основной ветке то git как бы продолжает ее сливая с новой, т.е. все коммиты как бы переносит в основную ветку; если изменения вносились то создается дополнительный коммит слияния и в логе будет видно эти ветки). Если была изменена одна и та же часть файла в обеих ветках, то может возникнуть конфликт, который потребует участия пользователя. Чтобы разрешить конфликт нужно выбрать один из вариантов, либо объединить содержимое по-своему, затем закомитить их. VSCode предлагает варианты разрешения.
## 11. Удаление веток
Чтобы удалить ветку, необходимо предварительно выйти из нее, сохранив изменения, затем сделать слияние (если оно того требует). Для удаления веток необходимо использовать команду `git branch` с индексом `-d`:
```
git branch -d <branch_name>
```
Также при удалении можно использовать индекс `-D` который означает принудительное удаление вне зависимости от того, сохранили ли вы изменения или нет, слили ветку или нет.
## 12. Работа с удаленными репозиториями
1. Создать аккаунт на GitHub
2. Создать локальный репозиторий
3. Создать удаленный репозиторий
При создании удаленного репозитория GitHub предлагает следующие варианты:
Создать с нуля "ручками":
```
echo "# 111" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/Aks-var-fj/111.git
git push -u origin main
```
или отправить готовый репозиторий с ПК:
```
git remote add origin https://github.com/Aks-var-fj/111.git
git branch -M main
git push -u origin main
```
При отправке первый раз требует авторизации на GitHub.

4. Связать удаленный репозиторий с локальным
 
 Для того чтобы добавить удаленный репозиторий к проекту необходимо использовать команду:
 ```
 git remote add <name_reposytory> (по умолч - origin) <url-adress reposytory in web>
 ```
Команда `git remote` так же позволяет показать ветки, а та же команда с индексом `-v` позволяет увидеть связь.
Для того чтобы получить изменения и слиять их с удаленного репозитория используется команда:
```
git pull
```
Данная команда выполняет два действия последовательно, сначала получает изменения `git fetch`, затем производит слияние веток `git merge`. При этом будет отображаться статистика.
При возникновении конфликтов их можно решить ранее упомянутым способом в программе VSC, либо на сайте удаленного репозитория.
## 13. Работа с чужими репозиториями
Ищем на GitHub любой интересующий нас репозиторий и делаем его `Fork` к себе на страницу. Далее переходим на сайте в свои репозитории и получаем ссылку на данный репозиторий (обязательно со своей страницы). Открываем папку на локальном компьютере(не репозиторий) и запускаем терминал. Далее копируем его на локальный компьютер с помощью команды:
```
git clone <url reposytory>
```
Переходим с помощью команды `cd <name_reposytory>` в данный репозиторий и производим работы с данным репозиторием. 