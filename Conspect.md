# Git
GitHub - Это программа для 
## Зачем он нужен тестировщику?
Для
## Какой командой скопировать репозиторий?
+ `git clone https://github.com/IgnatyevPavel/Git.git` 
    + чтобы быстро вставить ссылку в команду используй хоткей - `shift+insert`
    когда мы зайдём в склонированный репозиторий, в скобках после указания директории будет название ветки, в нашем случае ` ~/Desktop/QA/GitHub/Git (main)`
    + если сделать команду `git status`, нам покажется 
```
$ git status 
On branch main | На главной ветке
Your branch is up to date with 'origin/main'. | В вашей ветке синхронизирована ​​информация с внешним репозиторием «origin/main».

nothing to commit, working tree clean | ничего коммитировать, рабочее дерево чистое (нет изменений которые можно было бы залить на внешний репозиторий)
```
## Что такое неотслеживаемый файл?
Создаём файл с даными 
`cat > user.txt`
    *Вводим следующие строки в файл:*
  ```
User1
User2
User3
User4
  ```
  + Для выхода из команды сначала используем **enter** для перехода на новую строку, затем сочетание клавиш **ctrl+c**

затем вводим команду `git status`
```git
On branch main 
Your branch is up to date with 'origin/main'.

Untracked files: | есть файлы которые не отслеживаются
  (use "git add <file>..." to include in what will be committed)
        user.txt | название неотслеживаемого файла

nothing added to commit but untracked files present (use "git add" to track) | ничего не добавлено для фиксации, но присутствуют неотслеживаемые файлы (используйте «git add» для отслеживания)
```
## Два варианта добавления для отслеживания файла
+ добавить только определённый файл `git add user.txt`
```
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   user.txt
```
+ добавить все неотслеживаемые файлы `git add .` 
## Статус modified
Если после добавления файла в отслеживание git с помощью команды `git add user.txt` мы добавим в него строки
`cat >> user.txt`
    *Вводим следующие строки в файл:*
  ```
User5
  ```
  + Для выхода из команды сначала используем **enter** для перехода на новую строку, затем сочетание клавиш **ctrl+c**
  то при вводе git status мы увидим следующее
```git 
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   user.txt

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   user.txt | файл модифицирован

  ```
  чтобы добавить в отслеживание также используем команду `git add .` либо `git add user.txt`. Это предварительная подготовка чтобы отправить файл на Git репозиторий

  # Запись изменений в хранилище кода GitHub
  при работе с системой контроля версий коммиты являются важной частью рабочего процесса и помогают в совместной работе над проектом. каждый коммит фиксирует изменения, внесенные в кодовую базу программы. Коммиты действуют как точки сохранения, с которых можно восстановиться.
  `git commit -m 'add file user.txt'` - команда чтобы создать "фотографию" репозитория

