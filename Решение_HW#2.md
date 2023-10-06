# GitHub. HW_2 ![OS](https://img.shields.io/badge/Windows-20H2-0014a8) ![Browser](https://img.shields.io/badge/Google_Chrome-117.0.5938.149-4285F4) ![Terminal](https://img.shields.io/badge/GitBash-2.42.0.windows.1-f14e32) ![Editor](https://img.shields.io/badge/VScode-1.81.1-0071bc)

1. На локальном репозитории сделать ветки для:
+ Postman 
    + -> Создаём репозиторий на GitHub с названием: `work` 
    + -> `git clone https://github.com/IgnatyevPavel/work.git` 
    + -> `cd work` 
    + -> `git branch Postman` 
+ Jmeter 
    + -> `git branch Jmeter` 
+ CheckLists 
    + -> `git branch CheckLists` 
+ Bag Reports 
    + -> `git branch Bag_Reports`
+ SQL 
    + -> `git branch SQL` 
+ Charles 
    + -> `git branch Charles` 
+ Mobile testing 
    + -> `git branch Mobile_testing` 
    + -> `git branch` (чтобы проверить все ли ветки создалась)
___
2. Запушить все ветки на внешний репозиторий 
    + -> `git push -u origin Bag_Reports`
    + -> `git push -u origin Charles`
    + -> `git push -u origin CheckLists`
    + -> `git push -u origin Jmeter`
    + -> `git push -u origin Mobile_testing`
    + -> `git push -u origin Postman`
    + -> `git push -u origin SQL`
___
3. В ветке Bag Reports сделать текстовый документ со структурой баг репорта 
    + -> `git checkout Bag_Reports` 
    + -> `touch structure.txt` 
    + -> `ls` (проверяем создался ли файл)
    + -> `vim structure_bag_report.txt` 
    + -> нажимаем `i`
    + -> вводим структуру баг репорта 
>   Структура баг репорта:
>1. Дата: 
>2. Номер бага:
>1. Название проекта:
>4. Версия билда:
>1. Краткое описание бага:
>2. Подробное описание бага (если требуется):
>3. Шаги воспроизведения (STR):
>4. Фактический результат (Actual result):
>5. Ожидаемый результат (Expected result):
>6. Вложения (скриншот, видео, логи):
>2. Устройство на котором найден баг:
>3. Компонент (идентификатор, который помогает понять в какой части программы находится баг)
>5. Серьёзность (severity):
>	+ Blocker
>	+ Critical
>	+ Major
>	+ Minor
>	+ Trivial
>6. Приоритет (priority):
>	+ High
>	+ Medium
>	+ Low
>9. Окружение (environment):
>	+ Dev
>	+ Stage
>	+ Prod
>7. Статус бага: 
>8. Автор бага:
>

+ -> `esc` + `:wq`

___
4. Запушить структуру багрепорта на внешний репозиторий 
    + -> `git add structure.txt` 
    + -> `git commit -m "new file structure.txt"`
    + ->  `git push`
___
5. Вмержить ветку Bag Reports в Main    
    + -> `git checkout main` 
    + -> `git merge Bag_Reports` 
    + -> `git commit -m 'new file structure.txt'`
___
6. Запушить main на внешний репозиторий. 
    + -> `git status`
    + -> `git push`
___
7. В ветке CheckLists набросать структуру чек листа. 
+ -> `git checkout CheckLists` 
+ -> `touch structure_check_list.txt` 
+ -> `ls` (проверяем создался ли файл) 
+ -> `vim structure_check_list.txt`
+ -> нажимаем `i` 
+ -> вводим текст:

>Структура чек листа с примером заполнения:
>
>    Чек-лист - список проверок, без указания шагов. показывает что мы будем тестировать и результат, отражает то что мы хотим сделать, что хотим не забыть и то что будем проверять
>
    >1. Дата:
    >2. Проект:
    >3. Версия билда:
    >4. Автор: 
>
>| Номер проверки |Описание проверки|Статус|Комментарий|
>|-:|:-:|:-:|-:|
>|1| Запуск приложения                             | passed   | 
>|2| Проверить отображение в горизонтальном режиме | failed   | сделать баг-репорт
>|3| Проверить переход по вкладкам                 | blocked  | сделать баг-репорт

+ -> `esc` + `:wq`
___
8. Запушить структуру на внешний репозиторий 
    + -> `git add structure_check_list.txt `
    + -> `git commit -m "new file structure_check_list.txt" `
    + -> `git status` 
    + -> `git push`
___
9. На внешнем репозитории сделать Pull Request ветки CheckLists в main 
+ Откройте страницу GitHub в браузере
+ Зайдите в репозиторий `work` 
+ В уведомлении `CheckLists had recent pushes less than a minute ago` кликните на `Compare & pull request`
+ На странице `Comparing changes` укажите `base`: `main` и `compare`:`CheckLists` 
+ Заполните `Title` и комментарий ниже `Leave a comment`
+ Кликните на `Create pull requsest` 
+ После этого в середине страницы github.com выведет надпись что эта ветка не конфликтует с базовой веткой `This branch has no conflicts with the base branch ` нажимаем "Merge pull request"
+ Нажмите `Confirm merge` 
___
10. Синхронизировать Внешнюю и Локальную ветки Main 
    + `git checkout main `
    + `git pull`

