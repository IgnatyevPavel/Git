# Конспект по теме Git и GitHub
**Git** - это распределенная система контроля версий, которая используется для управления изменениями в файлах проекта. Он позволяет разработчикам отслеживать изменения в коде, создавать ветки для параллельной разработки, объединять изменения из разных веток, откатываться к предыдущим версиям и многое другое.

**GitHub** — веб-сервис для хранения и совместной работы над проектами с использованием Git. Основные причины использования GitHub:
## В чём разница Git от Github?
GitHub - платформа для хостинга и совместной работы над проектами с использованием Git.
Git может использоваться независимо от GitHub

**Git** - это инструмент **командной строки**, с помощью которого можно управлять версиями через **Распределенную архитектуру** т.е. каждый участник проекта имеет полноценную копию всего репозитория, включая историю изменений. что позволяет работать над проектом независимо друг от друга и в любое удобное время.

 **GitHub** - **это веб-сервис**, предоставляющий удаленное хранилище для Git-репозиториев и дополнительные функции для совместной работы над проектами.
## Зачем это нужно тестировщику?
Использование GitHub обеспечивает эффективность и сотрудничество между всеми участниками разработки, улучшает качество ПО и способствует командной работе с помощью следующих возможностей:

## Какой командой скопировать репозиторий?
+ `git clone https://github.com/IgnatyevPavel/Git.git` 
    + вставить URL ссылки в команду хоткей - `shift+insert`, либо правой кнопкой мыши 'Paste'
    + при входе через `cd` в склонированный репозиторий, после указания директории `~/Desktop/QA/GitHub/Git` в скобках будет название ветки, в нашем случае `(main)`

    + после клонирования репозитория команда `git status`, нам укажет, что версия на GitHub и локальная версия синхронизированы 
```git 
$ git status 
On branch main | На главной ветке
Your branch is up to date with 'origin/main'. | В вашей ветке синхронизирована ​​информация с внешним репозиторием «origin/main».

nothing to commit, working tree clean | ничего коммитировать, рабочее дерево чистое (нет изменений которые можно было бы залить на внешний репозиторий)
```
## Перед тем как начать работать с Git:
Заполни имя и почту
+ `git config --global user.name "вводим своё имя из GitHub"`
+ `git config --global user.email "вводим свою почту которую указывал при регистрации в GitHub"`

Чтобы проверить какой user.name и user.email пишем:
  + `git config --global user.name` для проверки user name 
  + `git config --global user.email` для проверки user email
## Что такое Untracked files | неотслеживаемый файл?
Для примера создадим файл с даными в склонированном репозитории

```git
cat > user.txt
*Вводим следующие строки в файл:*
"User 1
User 2
User 3
User 4"

*Для выхода из команды сначала используем enter для перехода на новую строку, затем сочетание клавиш ctrl+c*
```
Затем вводим команду `git status` и она нам покажет что появились untracked | неотслеживаемые файлы 
```git
On branch main 
Your branch is up to date with 'origin/main'.

Untracked files: <----- Есть файлы которые не отслеживаются
  (use "git add <file>..." to include in what will be committed)
        user.txt <----- Название неотслеживаемого файла

nothing added to commit but untracked files present (use "git add" to track) <----- программа говорит нам, что ничего не добавлено для фиксации, 
но присутствуют неотслеживаемые файлы (используйте «git add» для отслеживания)
```
## Как добавить созданный файл в Git для отслеживания?

1. добавить только определённый файл `git add user.txt`
2. добавить все неотслеживаемые файлы `git add .` 

После добавления ответ будет следующим:
```git
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   user.txt <----- программа показала, что файл user.txt добавлен в отслеживаемые файлы git
```
## Статус modified
Присваивается, если после добавления файла в отслеживание Git мы отредактируем файл.
```git
cat >> user.txt
*Вводим следующие строки в файл:*
"User 5" <----- добавим следующий текст в файл
```

То при вводе `git status` мы увидим следующие вещи:
```git 
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   user.txt <----- Файл user.txt ранее был добавлен в отслеживание Git

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   user.txt <----- Программа показывает что файл user.txt модифицирован информация не соответствует файлу, который был ранее добавлен 

  ```

## Запись изменений в хранилище кода GitHub
  При работе с системой контроля версий **коммиты** являются важной частью рабочего процесса. Каждый **коммит фиксирует изменения**, внесенные в кодовую базу программы. Коммиты действуют **как точки сохранения**, с которых можно восстановиться.
 + Команда чтобы создать коммит (фотографию\точку сохранения) репозитория
 ```git 
$ git commit -m 'add file user.txt'
[main 3e4786f] add file user.txt
 2 files changed, 74 insertions(+)
 create mode 100644 Practice/lesson_1_git_intro/user.txt
 ```
+ Чтобы проверить сделан ли коммит используй следующее:
```git
$ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit. <----- Ваша ветка опережает «origin/main» на 1 коммит.
  (use "git push" to publish your local commits) <----- (используйте «git push», чтобы опубликовать локальные коммиты)

nothing to commit, working tree clean
```
+ при следующем коммитировании уже добавленного файла используй команду:
  + `git commit -am 'file user.txt update` 
  
   опция `-a` (add) "фотографирует" все файлы, которые уже отслеживаются. 

## Как создать уникальный ключ на пользователя? SSH
+ Команда `ssh-keygen -t rsa -C "IgnatyevPavel"`

  + Терминал попросит нас ввести директорию для создания файла с ssh ключем, можем пропустить этот этам через `enter`
  + Затем 2 раза нужно будет ввести пароль
  + Рандомный ключ сгененрирован
  + Теперь переходим в `/c/Users/User/.ssh` находим файл `id_rsa.pub` открываем с помощью просмотрщика кода и копируем весь текст в файле
  + Заходим на главную страницу в **GitHub**
  + Через иконку пользователя в правом верхнем углу заходим в `settings`
  + Заходим во вкладку `SSH and GPG keys`, во вкладке напротив `SSH keys` кликаем по `New SSH key`
  + Вставляем скопированный ключ в форму с названием `Key`, заполняем `Title`
  + Жмём `Add SSH key`
  + В окне пароля, вводим пароль
  + Ключ добавлен

## Как создать токен?
+ переходим на свою страницу **Github** -> клик по кружку профиля в правом углу-> `settings`-> в самом низу `Developer Settings`->`Personal access tokens`->`Tokens(classic)`->`Generate new token (classic)`
+ в выпадающем списке настройки `Expiration` ставим `No expiration` и проставляем все галочки, затем `Generate token`
+ копируем созданный токен и вводим его вместо пароля через `shift+insert` или `правую кнопку мыши->Paste` 

## Git push 
**выгрузить на GitHub** локальные изменения используем команду
  + `git push`

## Git fetch
+ Команда для просмотра есть ли **на внешнем репозитории** изменения, без скачивания, просто **просмотр статуса**. Если репозитории **синхронизированы**, то реакции в терминале не будет

## Git pull
+ Команда для выгрузки из внешнего репозитория на локальный репозиторий

## Git branch
+ Показывает все доступные ветки в репозитории и информацию на какой ветке я нахожусь 
```git
User@WIN MINGW64 ~/Desktop/QA/GitHub/Branch (main)
$ git branch
* main
```
## Git init
Команда с помощью которой можно в локальном проекте добавить контроль версий Git.
+ создаём или переходим в папку с проектом
```
$ cd my_project
$ git init
Initialized empty Git repository in C:/Users/User/Desktop/QA/GitHub/Git/Practice
/GIT-INIT/.git/
```
+ После выполнения команды `git init` внутри папки проекта, **Git** создаст скрытую папку `.git` что даёт возможность контролировать версии вашего проекта, создавать ветки и сохранять изменения и использовать любые Git-команды, такие как `git add`, `git commit`, `git branch` и т. д.
+ `git init` выполняется только один раз в начале проекта для инициализации репозитория. (Если склонировать репозиторий, то `git init` уже будет выполнен автоматически, его не нужно повторно запускать.)

Чтобы выгрузить локальный репозиторий (после `git init`) во внешний репозиторий используем команду:
```
git remote add origin https://github.com/username/repository.git
```
+  Замените "username" и "repository" на свои реальные значения.

После этого вы можете делать `git push`. В первый раз необходимо ввести следующую команду, чтобы выгрузить ветку в которой вы находитесь:

`git push -u origin master`

+ Далее используем обычный `git push`, и изменения будут отправляться на удалённый репозиторий.

## Создать новую ветку в репозитории 
  + Важно! Если будете создавать новую ветку(бранчу), то новая бранча будет копией той ветки на которой вы стоите. Пример: если создали ветку `Ali_Pay` из ветки `main`, то `Ali_Pay` является копией ветки `main`. 
```git
User@WIN MINGW64 ~/Desktop/QA/GitHub/Branch (main)
$ git branch Ali_Pay <----- Создать ветку Ali_pay 

User@WIN MINGW64 ~/Desktop/QA/GitHub/Branch (main)
$ git branch <----- Просмотр существующих веток в репозитории
  Ali_Pay
* main

```
##  Переход в другую ветку
```git
User@WIN MINGW64 ~/Desktop/QA/GitHub/Branch (main)
$ git branch <----- Смотрим какие ветки существуют\уже созданы
  Ali_Pay
* main

User@WIN MINGW64 ~/Desktop/QA/GitHub/Branch (main)
$ git checkout Ali_Pay  <-----Меняем ветку
Switched to branch 'Ali_Pay' <-----Смена ветки 

User@WIN MINGW64 ~/Desktop/QA/GitHub/Branch (Ali_Pay) <-----Main cменилось на Ali_pay
$ git branch
* Ali_Pay <----- Текущая ветка отмечается *
  main
```
## Создать новую ветку и прыгнуть в неё
```git 
User@WIN MINGW64 ~/Desktop/QA/GitHub/Branch (Ali_Pay)
$ git branch <----- Смотрим какие ветки существуют\уже созданы
* Ali_Pay
  main

User@WIN MINGW64 ~/Desktop/QA/GitHub/Branch (Ali_Pay)
$ git checkout -b Samsung_Pay <-----Данная команда делает копию ветки Ali_Pay с именем Samsung_Pay и меняет ветку с Ali_Pay на Samsung_Pay
Switched to a new branch 'Samsung_Pay' <-----Смена ветки 

User@WIN MINGW64 ~/Desktop/QA/GitHub/Branch (Samsung_Pay) <-----Ali_Pay cменилось на Samsung_Pay
$ git branch
  Ali_Pay
* Samsung_Pay <----- Текущая ветка отмечается *
  main

```
## Работа с папкой при смене веток
+ Если создать файл `s_pay.txt` в ветке `Samsung_Pay`, закоммитить и запушить изменения, а затем переключиться на ветку `main`, то файл `s_pay.txt` не будет присутствовать. Однако, при возвращении на ветку `Samsung_Pay` файл снова будет доступен.

```git
User@WIN MINGW64 ~/Desktop/QA/GitHub/branch (samsung_pay) <-----обрати внимание на ветку
$ ls -la
total 19
drwxr-xr-x 1 User 197121    0 Oct  4 12:30 ./
drwxr-xr-x 1 User 197121    0 Oct  3 18:53 ../
drwxr-xr-x 1 User 197121    0 Oct  4 12:30 .git/
-rw-r--r-- 1 User 197121    6 Oct  3 18:53 README.md
-rw-r--r-- 1 User 197121    0 Oct  4 12:30 s_pay.txt #<-----созданный файл


User@WIN MINGW64 ~/Desktop/QA/GitHub/branch (samsung_pay)
$ git checkout main #<-----меняем ветку на main и файла s_pay.txt там не будет
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

User@WIN MINGW64 ~/Desktop/QA/GitHub/branch (main)
$ ls -la
total 19
drwxr-xr-x 1 User 197121    0 Oct  4 12:33 ./
drwxr-xr-x 1 User 197121    0 Oct  3 18:53 ../
drwxr-xr-x 1 User 197121    0 Oct  4 12:33 .git/
-rw-r--r-- 1 User 197121    6 Oct  3 18:53 README.md


```
## Как соединить ветки?
+ для этого необходимо встать в ту ветку куда нам нужно переместить файлы, затем вводим команду `git merge samsung_pay` 
```git
User@WIN MINGW64 ~/Desktop/QA/GitHub/branch (main)
$ ls -la 
total 19
drwxr-xr-x 1 User 197121    0 Oct  4 12:33 ./
drwxr-xr-x 1 User 197121    0 Oct  3 18:53 ../
drwxr-xr-x 1 User 197121    0 Oct  4 12:33 .git/
-rw-r--r-- 1 User 197121    6 Oct  3 18:53 README.md
                                                    <----- файла s_pay.txt нет в списке


User@WIN-EHFSEGNSRM5 MINGW64 ~/Desktop/QA/GitHub/branch (main)
$ git merge samsung_pay <----- копируем в текущую ветку файлы из другой ветки samsung_pay
Updating 26799c8..b18ba67
Fast-forward
 s_pay.txt | 0
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 s_pay.txt

User@WIN-EHFSEGNSRM5 MINGW64 ~/Desktop/QA/GitHub/branch (main)
$ ls -la 
total 19
drwxr-xr-x 1 User 197121    0 Oct  4 12:53 ./
drwxr-xr-x 1 User 197121    0 Oct  3 18:53 ../
drwxr-xr-x 1 User 197121    0 Oct  4 12:53 .git/
-rw-r--r-- 1 User 197121    6 Oct  3 18:53 README.md
-rw-r--r-- 1 User 197121    0 Oct  4 12:53 s_pay.txt <-------файл s_pay.txt есть в списке

```
## Конфликт и его разрешение
+ Если в одном репозитории в разных ветках есть файлы с одинаковым названием но разной информацией на конкретной строке, то при объединении этих файлов будет конфликт. Например:
```git
# Файл 1.txt в ветке samsung_pay содержит следующее:

User@WIN MINGW64 ~/Desktop/QA/GitHub/branch (samsung_pay)
$ cat 1.txt 
samsung_pay 

# Меняем ветку:

User@WIN MINGW64 ~/Desktop/QA/GitHub/branch (samsung_pay)
$ git checkout main 
Switched to branch 'main'

# Такой же файл 1.txt в ветке main содержит другую информацию:

User@WIN MINGW64 ~/Desktop/QA/GitHub/branch (main)
$ cat 1.txt 
main 

# Слияние информации из samsung_pay в main:

User@WIN MINGW64 ~/Desktop/QA/GitHub/branch (main)
$ git merge samsung_pay 
Auto-merging 1.txt
CONFLICT (content): Merge conflict in 1.txt #Указывает на конфликт в файле 1.txt
Automatic merge failed; fix conflicts and then commit the result.

# При просмотре файла внутри будет текст указывающий на конфликт:

User@WIN MINGW64 ~/Desktop/QA/GitHub/branch (main|MERGING)
$ cat 1.txt 
<<<<<<< HEAD
main #Текущее изменение
=======
samsung_pay #Входящее изменение
>>>>>>> samsung_pay

# Чтобы разрешить конфликт необходимо отредактировать документ и поместить в него нужную информацию, это могут быть тексты из веток samsung_pay или main, или что-то наиболее подходящее

User@WIN MINGW64 ~/Desktop/QA/GitHub/branch (main|MERGING)
$ cat > 1.txt
ali_pay 

# Для выхода из состояния ветки merging указанного в скобках (main|MERGING) делаем коммит

User@WIN MINGW64 ~/Desktop/QA/GitHub/branch (main|MERGING)
$ git commit -am 'fix conflict' 
warning: in the working copy of '1.txt', LF will be replaced by CRLF the next ti
me Git touches it
[main 1a514c0] update

# Готово, информация зафиксирована

User@WIN-EHFSEGNSRM5 MINGW64 ~/Desktop/QA/GitHub/branch (main)
$ cat 1.txt 
ali_pay
```