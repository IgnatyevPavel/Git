GitHub. HW_2
1. На локальном репозитории сделать ветки для:
- +Postman -> создаём репозиторий на git hub -> git clone https://github.com/IgnatyevPavel/hw_branches.git -> cd hw_branches -> git branch Postman -> git branch(чтобы проверить создалась ли ветка)
- +Jmeter -> git branch Postman -> git branch(чтобы проверить создалась ли ветка)
- +CheckLists -> git branch CheckLists -> git branch(чтобы проверить создалась ли ветка)
- +Bag Reports -> git branch Bag_Reports -> git branch(чтобы проверить создалась ли ветка)
- +SQL -> git branch SQL -> git branch(чтобы проверить создалась ли ветка)
- +Charles -> git branch Charles -> git branch(чтобы проверить создалась ли ветка)
- +Mobile testing -> git branch Mobile_testing -> git branch(чтобы проверить создалась ли ветка и сверить все ли ветки созданы)

2. Запушить все ветки на внешний репозиторий -> git commit -m "new branches" 
-> git push -u origin Bag_Reports
-> git push -u origin Charles
-> git push -u origin CheckLists
-> git push -u origin Jmeter
-> git push -u origin Mobile_testing
-> git push -u origin Postman
-> git push -u origin SQL

3. В ветке Bag Reports сделать текстовый документ со структурой баг репорта -> git checkout Bag_Reports -> touch structure_bag_report.txt -> ls (проверяем создался ли файл)
-> vim structure_bag_report.txt -> нажимаем "i" -> вводим структуру баг репорта -> esc -> :wq
4. Запушить структуру багрепорта на внешний репозиторий -> git add structure_bag_report.txt -> git commit -m "new file structure_bag_report.txt" ->  git push -u origin Bag_Reports
5. Вмержить ветку Bag Reports в Main -> git checkout main -> git merge Bag_Reports 
6. Запушить main на внешний репозиторий. -> git status -> git push
7. В ветке CheckLists набросать структуру чек листа. -> git checkout CheckLists -> touch structure_check_list.txt -> ls (проверяем создался ли файл) -> vim structure_check_list.txt -> нажимаем "i" -> вводим текст -> esc -> :wq
8. Запушить структуру на внешний репозиторий -> git add . -> git status -> git commit -m "new file structure_check_list.txt" -> git push
9. На внешнем репозитории сделать Pull Request ветки CheckLists в main -> заходим в наш профиль на сайте https://github.com/ -> выбираем репозиторий hw_branches -> рядом с уведомлением " CheckLists had recent pushes 4 minutes ago" нажать кнопку "Compare & pull request" -> во вкладке base выбираем main -> в соседней вкладке compare выбираем CheckLists -> заполняем комментарий ниже "Pull Request ветки CheckLists в main" -> жмём кнопку "create pull requsest" -> затем когда веб github.com выведет надпись что эта ветка не конфликтует с базовой веткой "This branch has no conflicts with the base branch" нажимаем "Merge pull request" -> затем нажимаем "confirm merge" 
10. Синхронизировать Внешнюю и Локальную ветки Main -> git checkout main -> git pull

