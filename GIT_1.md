# HW#1:GIT Homework 1 ![Terminal](https://img.shields.io/badge/GitBash-2.42.0.windows.1-f14e32) ![Editor](https://img.shields.io/badge/VScode-1.81.1-0071bc) ![OS](https://img.shields.io/badge/Windows-20H2-0014a8)

#### Как выполнять задание?
>Для выполнения задания у вас должен быть установлен для Windows - GitBash.
>Создан аккаунт в GitHub
>Все шаги сценария выполняйте в терминале GitBash, Terminal, в папке под гитом.
>Как отправить ДЗ на проверку.
> 1. Создайте текстоовый файл как в первом ДЗ по Terminal.
> 2. Сценарий перенесите в этот файл.
> 3. На против каждого действия - напишите команду в GitBash
>
>Файл со сценарием и ссылку на свой гит хаб отправляйте менторам на проверку.


### JSON
*4. Создать внешний репозиторий c названием JSON.*
`-> зайти в аккаунт на git hub -> рядом с Recent Repositories жмём кнопку New -> в поле Repository name пишем JSON, ставим галочку на "Public" и "add readme file" -> жмём create repository. `
___
*5. Клонировать репозиторий JSON на локальный компьютер.*
`-> на веб интерфейсе GitHub жмём на раздел "Repositories" -> далее на созданную ветку JSON -> кликаем на кнопку Code -> копируем HTTPS ссылку -> пишем в терминал команду git clone https://github.com/IgnatyevPavel/JSON.git`
___
*6. Внутри локального JSON создать файл “new.json”.*
`-> cd JSON -> touch new.json`
___
*7. Добавить файл под гит.*
`-> веряем статус репозитория git status -> затем добавляем файл git add new.json`
___
*8. Закоммитить файл.*
`-> git commit -m "Added file -new.json"`
___
*9. Отправить файл на внешний GitHub репозиторий.*
`-> git push`
___
*10. Отредактировать содержание файла “new.json” - написать информацию о себе (ФИО, возраст, количество домашних животных, будущая желаемая зарплата). Всё написать в формате JSON.*
`-> vim new.json -> нажимаем клавишу "i" -> вводим текст -> после ввода текста нажимаем esc -> вводим на клавиатуре :wq `
___
*11. Отправить изменения на внешний репозиторий.*
`-> проверяем файлы репозитория git status -> отправляем изменения git commit -am "change data on file new.json" -> git push`
___
*12. Создать файл preferences.json*
`-> touch preferences.json `
___
*13. В файл preferences.json добавить информацию о своих предпочтениях (Любимый фильм, любимый сериал, любимая еда, любимое время года, сторона которую хотели бы посетить) в формате JSON.*
`-> vim preferences.json -> нажимаем клавишу "i" -> вводим текст -> после ввода текста нажимаем esc -> вводим на клавиатуре :wq  `
___
*14. Создать файл sklls.json добавить информацию о скиллах которые будут изучены на курсе в формате JSON*
`-> touch sklls.json -> vim sklls.json -> нажимаем клавишу "i" -> вводим текст -> после ввода текста нажимаем esc -> вводим на клавиатуре :wq `
___
*15. Отправить сразу 2 файла на внешний репозиторий.*
`-> git status -> gid add . -> git commit -m "added 2 new file on repositories" -> git push`
___
*16. На веб интерфейсе создать файл bug_report.json.*
`-> заходим на сайт https://github.com/ -> переходим в репозиторию JSON -> add file -> create new file -> вводим название файла bug_report.json `
___
*17. Сделать Commit changes (сохранить) изменения на веб интерфейсе.*
`-> в поле Commit new file, вводим create bug_report.json -> ставим галочку на commit directly to the main branch. -> жмём кнопку commit new file`
___
*18. На веб интерфейсе модифицировать файл bug_report.json, добавить баг репорт в формате JSON.*
`-> нажимаем на файл bug_report.json -> edit this file -> вводим текст в формате json `
___
*19. Сделать Commit changes (сохранить) изменения на веб интерфейсе.*
`-> в поле commit changes вводим update bug_report.json -> нажимаем на кнопку commit changes `
___
*20. Синхронизировать внешний и локальный репозиторий JSON*
`-> git pull`
___




### XML
*21. Создать внешний репозиторий c названием XML.*
`-> перейти на сайт https://github.com/ -> рядом с Recent Repositories жмём кнопку New -> в поле Repository name пишем XML, ставим галочку на "Public" и "add readme file" -> жмём create repository.`
___
*22. Клонировать репозиторий XML на локальный компьютер.*
`-> на сайте https://github.com/ -> жмём на кнопку "Code" -> копируем HTTPS ссылку https://github.com/IgnatyevPavel/XML.git -> пишем в терминал git bash -> cd .. (если мы находимся в репозитории JSON, нам нужно выйти из папки) -> git clone https://github.com/IgnatyevPavel/XML.git`
___
*23. Внутри локального XML создать файл “new.xml”.*
`-> cd XML-> touch new.xml`
___
*24. Добавить файл под гит.*
`-> git add new.xml`
___
*25. Закоммитить файл.*
`-> git commit -m "added new file new.xml"`
___
*26. Отправить файл на внешний GitHub репозиторий.*
`-> git push`
___
*27. Отредактировать содержание файла “new.xml” - написать информацию о себе (ФИО, возраст, количество домашних животных, будущая желаемая зарплата). Всё написать в формате XML.*
`->vim new.xml -> нажимаем кнопку i -> вводим текст -> esc -> вводим на клавиатуре :wq `
___
*28. Отправить изменения на внешний репозиторий.*
`-> git status -> git commit -am "Change data on file new.xml" -> git push`
___
*29. Создать файл preferences.xml*
`-> touch preferences.xml`
___
*30. В файл preferences.xml добавить информацию о своих предпочтениях (Любимый фильм, любимый сериал, любимая еда, любимое время года, сторона которую хотели бы посетить) в формате XML.*
`vim preferences.xml -> нажимаем кнопку i -> вводим текст -> esc -> вводим на клавиатуре :wq `
___
*31. Создать файл sklls.xml добавить информацию о скиллах которые будут изучены на курсе в формате XML*
`-> touch skills.xml -> vim skills.xml -> нажимаем кнопку i -> вводим текст -> esc -> вводим на клавиатуре :wq `
___
*32. Сделать коммит в одну строку.*
`-> git commit -am "Added 2 new files"`
___
*33. Отправить сразу 2 файла на внешний репозиторий.*
`-> git push`
___
*34. На веб интерфейсе создать файл bug_report.xml.*
`-> заходим на сайт https://github.com/ -> переходим в репозиторию XML -> add file -> create new file -> вводим название файла bug_report.xml`
___
*35. Сделать Commit changes (сохранить) изменения на веб интерфейсе.*
`-> в поле Commit new file, вводим create bug_report.xml -> ставим галочку на commit directly to the main branch. -> жмём кнопку commit new file`
___
*36. На веб интерфейсе модифицировать файл bug_report.xml, добавить баг репорт в формате XML.*
`-> нажимаем на файл bug_report.xml -> edit this file -> вводим текст в формате xml`
___
*37. Сделать Commit changes (сохранить) изменения на веб интерфейсе.*
`-> в поле commit changes вводим update bug_report.xml -> нажимаем на кнопку commit changes `
___
*38. Синхронизировать внешний и локальный репозиторий XML*
`-> git pull`
___