# Git Intro (git add; git commit; git push)
Git - это распределенная система контроля версий, которая используется для управления изменениями в файлах проекта. Он позволяет разработчикам отслеживать изменения в коде, создавать ветки для параллельной разработки, объединять изменения из разных веток, откатываться к предыдущим версиям и многое другое.

GitHub — веб-сервис для хранения и совместной работы над проектами с использованием Git. Основные причины использования GitHub:
#### В чём разница Git от Github?
Git это инструмент командной строки, который предоставляет функциональность управления версиями кода, в то время как GitHub - это веб-сервис, предоставляющий удаленное хранилище для Git-репозиториев и дополнительные функции для совместной работы над проектами. 

Git может использоваться независимо от GitHub, но GitHub в основном используется как платформа для хостинга и совместной работы над проектами с использованием Git.
#### Зачем это нужно тестировщику?
Использование GitHub обеспечивает эффективность и сотрудничество между тестировщиками и разработчиками, улучшает качество ПО и способствует командной работе с помощью следующих возможностей:
+ Централизованное хранение исходного кода с возможностью доступа всей команде.
+ Отслеживание изменений в коде с помощью Git, включая информацию об авторе и времени изменений.
+ Инструменты для совместной работы над кодом, комментирования и обсуждения изменений.
+ Создание и работа в отдельных ветках кода для тестирования без влияния на основную разработку.
+ Управление задачами, отслеживание ошибок и запросов на изменения функций.
+ Версионирование кода и контроль изменений.
+ Совместная работа и коммуникация через комментарии и вопросы.
+ Чтобы фраза "забери мою ветку с Гита" не вызывала страх.


#### Какой командой скопировать репозиторий?
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
#### Чтобы вносить изменения, сделай следующее:
git config --global user.name "вводим своё имя из GitHub"
git config --global user.email "вводим свою почту которую указывал при регистрации в GitHub"

#### Чтобы проверить какой user.name и user.email
+ пишем:
  + git config --global user.name для проверки user name 
  + git config --global user.email для проверки user email
#### Что такое Untracked files | неотслеживаемый файл?
для примера создаём файл с даными в склонированном репозитории

```git
cat > user.txt
*Вводим следующие строки в файл:*
User 1
User 2
User 3
User 4

*Для выхода из команды сначала используем enter для перехода на новую строку, затем сочетание клавиш ctrl+c*
```
затем вводим команду `git status` и она нам покажет что появились untracked файлы 
```git
On branch main 
Your branch is up to date with 'origin/main'.

Untracked files: | есть файлы которые не отслеживаются
  (use "git add <file>..." to include in what will be committed)
        user.txt | название неотслеживаемого файла

nothing added to commit but untracked files present (use "git add" to track) | ничего не добавлено для фиксации, 
но присутствуют неотслеживаемые файлы (используйте «git add» для отслеживания)
```
#### Статус untracked
Есть два варианта добавления в отслеживание Git 
1. добавить только определённый файл `git add user.txt`
2. добавить все неотслеживаемые файлы `git add .` 

После добавления через удобный вариаен ответ будет следующим:
```git
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   user.txt | файл user.txt добавлен в отслеживаемые файлы git
```
#### Статус modified
Если после добавления файла через команду `git add` в отслеживание git мы добавим новые строки в файл `user.txt` 
```git
cat >> user.txt
*Вводим следующие строки в файл:*
"User 5"
*Для выхода из команды сначала используем enter для перехода на новую строку, затем сочетание клавиш ctrl+c*
```

То при вводе `git status` мы увидим следующие вещи:
```git 
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   user.txt | <-----файл user.txt добавлен в отслеживание 

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   user.txt | <-----и файл user.txt модифицирован

  ```
  чтобы добавить в отслеживание также используем команду `git add .` либо `git add user.txt`. Это предварительная подготовка чтобы отправить файл на Git репозиторий

#### Запись изменений в хранилище кода GitHub
  при работе с системой контроля версий коммиты являются важной частью рабочего процесса и помогают в совместной работе над проектом. каждый коммит фиксирует изменения, внесенные в кодовую базу программы. Коммиты действуют как точки сохранения, с которых можно восстановиться.
 + Команда чтобы создать "фотографию" репозитория
 ```git 
$ git commit -m 'add file user.txt'
[main 3e4786f] add file user.txt
 2 files changed, 74 insertions(+)
 create mode 100644 Practice/lesson_1_git_intro/user.txt
 ```
+ чтобы проверить сделан ли коммит
```git
$ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit. | Ваша ветка опережает «origin/main» на 1 коммит.
  (use "git push" to publish your local commits) | (используйте «git push», чтобы опубликовать локальные коммиты)

nothing to commit, working tree clean
```
+ при следующем изменении уже добавленного файла можно использовать команду `git commit -am 'file user.txt update` 
+ опция `-a` "фотографирует" все файлы, которые уже отслеживаются. если присутствуют новые файлы, которые еще не отслеживаются Git, то добавляем их вручную с помощью `git add.`

+ чтобы выгрузить на GitHub локальные изменения используем команду `git push`

#### Как создать уникальный ключ на пользователя?

+ Команда `ssh-keygen -t rsa -C "IgnatyevPavel"`

  + Далее терминал попросит нас ввести директорию для создания файла с ssh ключем, можем пропустить этот этам через `enter`
  + Затем 2 раза нужно будет ввести пароль
  + Рандомный ключ сгененрирован
  + Переходим в `/c/Users/User/.ssh` находим файл `id_rsa.pub` открываем с помощью просмотрщика кода копируем весь текст в файле
  + Заходим на главную страницу в GitHub
  + Через иконку пользователя в правом верхнем углу заходим в `settings`
  + Заходим во вкладку `SSH and GPG keys`, во вкладке напротив `SSH keys` кликаем по `New SSH key`
  + Вставляем скопированный ключ в форму с названием `Key`, заполняем `Title`
  + Жмём `Add SSH key`
  + В окне пароля, вводим пароль
  + Ключ добавлен


#### Как создать токен?
+ переходим на свою страницу Github -> клик по кружку профиля в правом углу-> settings-> в самом низу Developer Settings->Personal access tokens->Tokens(classic)->Generate new token (classic)
+ далее в настройках ставим Expiration в статус No expiration и проставляем все галочки, затем Generate token
+ копируем созданный токен и вводим его вместо пароля через shift+insert или правую кнопку мыши->Paste 




#### Git fetch

+ Команда для просмотра есть ли на внешнем репозитории какие то изменения, без скачивания, просто посмотреть. Если репозитории синхронизированы, то реакции в терминале не будет

#### Git pull

+ Команда для выгрузки из внешнего репозитория на локальный репозиторий

#### Git Branch
+ Показывает все доступные ветки в репозитории и информацию на какой ветке я нахожусь 
```git
User@WIN MINGW64 ~/Desktop/QA/GitHub/Branch (main)
$ git branch
* main

```
#### Создать новую ветку в репозитории 
  + Важно! если мы сделали ветку Ali_Pay из ветки main, то Ali_Pay является копией ветки main. Поэтому когда вы создаёте ветку, очень важно из какой ветки вы будете создавать её, если будете создавать новую бранчу, эта новая бранча будет копией той ветки на которой вы стоите  
```git
User@WIN MINGW64 ~/Desktop/QA/GitHub/Branch (main)
$ git branch Ali_Pay

User@WIN MINGW64 ~/Desktop/QA/GitHub/Branch (main)
$ git branch
  Ali_Pay
* main

```
####  Перейти из одной ветки в другую
```git
User@WIN MINGW64 ~/Desktop/QA/GitHub/Branch (main)
$ git branch
  Ali_Pay
* main

User@WIN MINGW64 ~/Desktop/QA/GitHub/Branch (main)
$ git checkout Ali_Pay  <-----Меняем ветку
Switched to branch 'Ali_Pay' <-----Ветка поменялась

User@WIN MINGW64 ~/Desktop/QA/GitHub/Branch (Ali_Pay) <-----Main cменилось на Ali_pay
$ git branch
* Ali_Pay
  main
```
#### Создать новую ветку и сразу прыгнуть в неё
```git 
User@WIN MINGW64 ~/Desktop/QA/GitHub/Branch (Ali_Pay)
$ git branch
* Ali_Pay
  main

User@WIN MINGW64 ~/Desktop/QA/GitHub/Branch (Ali_Pay)
$ git checkout -b Samsung_Pay <-----Данная команда делает копию ветки Ali_Pay под именем Samsung_Pay и меняет ветку с Ali_Pay на Samsung_Pay
Switched to a new branch 'Samsung_Pay' <-----Ветка поменялась

User@WIN MINGW64 ~/Desktop/QA/GitHub/Branch (Samsung_Pay) <-----Ali_Pay cменилось на Samsung_Pay
$ git branch
  Ali_Pay
* Samsung_Pay
  main

```
#### Работа с папкой при смене веток
+ Если создать файл s_pay.txt в ветке Samsung_Pay, закоммитить и запушить изменения, а затем переключиться на ветку main, то файл s_pay.txt не будет присутствовать. Однако, при возвращении на ветку Samsung_Pay файл снова будет доступен.

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
#### Как соединить ветки?
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
#### Как появляется конфликт при объединении двух веток?
+ Если в двух разных ветках есть файлы с одинаковым названием и разной информацией на конкретной строке, то при объединении этих файлов будет отображаться конфликт. Например:
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