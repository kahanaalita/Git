# **Git и GitHub: Основные концепции и команды**

## **1. Настройка Git**

### **Установка имени пользователя**
```bash
git config --global user.name "Ваше Имя"
```
### **Установка email**
```bash
git config --global user.email "ваш_email@example.com"
```
### **Проверка настроек**
```bash
git config --list
```

## **2. Инициализация репозитория**

### **Создание нового репозитория**
```bash
git init
```
### **Клонирование существующего репозитория**
```bash
git clone git@github.com:username/repository.git
```

## **3. Основные операции**

### **Проверка статуса репозитория**
```bash
git status
```
### **Добавление файлов в индекс**
```bash
git add filename.txt
git add .  # Добавить все файлы
```
### **Создание коммита**
```bash
git commit -m "сообщение коммита"
```
### **Просмотр истории коммитов**
```bash
git log
git log --oneline  // Сокращенный вид
```

## **4. Работа с ветками**

### **Проверка текущей ветки**
```bash
git branch
```
### **Создание новой ветки**
```bash
git branch new-branch-name
```
### **Переключение на другую ветку**
```bash
git checkout branch-name
```
### **Создание и переключение на новую ветку**
```bash
git checkout -b new-branch-name
```
### **Слияние веток**
```bash
git merge branch-name
```
### **Удаление ветки**
```bash
git branch -d branch-name
```

## **5. Работа с удаленным репозиторием**

### **Добавление удаленного репозитория**
```bash
git remote add origin git@github.com:username/repository.git
```
### **Отправка изменений в удаленный репозиторий**
```bash
git push origin branch-name
git push origin main
```
### **Получение изменений из удаленного репозитория**
```bash
git pull origin branch-name
git pull origin main
```
### **Просмотр удаленных репозиториев**
```bash
git remote -v
```

## **6. Отмена изменений**

### **Отмена изменений в рабочей директории**
```bash
git checkout -- filename.txt
```
### **Отмена индексации файла**
```bash
git reset HEAD filename.txt
```
### **Отмена последнего коммита (с сохранением изменений)**
```bash
git reset --soft HEAD^
```

## **7. Работа с тегами**

### **Создание легковесного тега**
```bash
git tag v1.0
```
### **Создание аннотированного тега**
```bash
git tag -a v1.1 -m "Версия 1.1"
```
### **Отправка тегов в удаленный репозиторий**
```bash
git push origin --tags
```

## **8. Полезные команды**

### **Просмотр различий**
```bash
git diff
git diff --staged  // Для индексированных файлов
```
### **Временное сохранение изменений**
```bash
git stash
git stash pop  // Применить сохраненные изменения
```
### **Игнорирование файлов (.gitignore)**
- Создайте файл .gitignore и добавьте в него шаблоны файлов для игнорирования

## **9. Работа с GitHub**

### **Форк репозитория на GitHub**
- Используйте кнопку "Fork" на странице репозитория

### **Создание Pull Request**
- После пуша изменений, используйте интерфейс GitHub для создания PR

### **Синхронизация форка с оригинальным репозиторием**
```bash
git remote add upstream https://github.com/original-owner/original-repository.git
git fetch upstream
git merge upstream/main
```

## **10. Клонирование репозитория с GitHub**

1. Перейти в нужную директорию
```bash
cd /путь/к/директории
```
2. Клонировать репозиторий
```bash
git clone https://github.com/username/repository.git
```
3. Перейти в склонированную директорию
```bash
cd repository
```
4. Проверить статус (опционально)
```bash
git status
```

## **11. Удаление и восстановление файлов из индекса**

### **Удаление файла из рабочей директории и из Git**
```bash
git rm файл.txt
git commit -m "Удален файл.txt"
```
### **Удаление нескольких файлов**
```bash
git rm файл1.txt файл2.txt файл3.txt
```
### **Восстановление файла**
```bash
git restore имя файла
```

## **12. Переименование файла**

### **Автоматическое отслеживание переименования**
```bash
git mv старое_имя.txt новое_имя.txt
git commit -m "Переименован файл старое_имя.txt в новое_имя.txt"
```
### **Переименование вручную**
```bash
mv старое_имя.txt новое_имя.txt
git rm старое_имя.txt
git add новое_имя.txt
git commit -m "Переименован файл старое_имя.txt в новое_имя.txt"
```
### **Переименование и перемещение файла**
```bash
git mv старый_путь/старое_имя.txt новый_путь/новое_имя.txt
git commit -m "Перемещен и переименован файл"
```

## **13. Анализ истории изменений в Git**

### **Просмотр различий между коммитами**
```bash
git diff <commit-hash>
```
### **Просмотр истории коммитов**
```bash
git log
git log -p  // Выводит диф для каждого коммита
```
### **Просмотр изменений в рамках одного коммита**
```bash
git show 5120bea3e5528c29f8d1da43731cbe895892eb6d
```
### **Определение, кто менял каждую строку файла**
```bash
git blame INFO.md
```
### **Поиск совпадений в файлах проекта**
```bash
git grep line
git grep -i line  // Поиск без учета регистра
```

## **14. Очистка неотслеживаемых файлов и директорий**

### **Удаление неотслеживаемых файлов и директорий**
```bash
git clean -fd
```

## **15. Отмена коммитов в Git**

### **Создание нового коммита для отмены изменений**
```bash
git revert <commit-hash>
```
### **Удаление последних n коммитов**
```bash
git reset [--hard] HEAD~[n]
```
### **Отмена последнего коммита, оставляя изменения**
```bash
git reset --mixed
```

## **16. Изменение последнего коммита (amend)**

### **Добавление забытых файлов и изменение последнего коммита**
```bash
git add README.md
git commit --amend
```

## **17. Работа с индексом в Git**

### **Добавление отдельных файлов в индекс**
```bash
git add somefile
```
### **Коммит с добавлением файла в индекс**
```bash
git commit -m 'add somefile'
```
### **Быстрый коммит для одного-двух файлов**
```bash
git commit INFO.md -m 'update INFO.md'
```
### **Добавление всех изменений в индекс**
```bash
git add .
```
### **Коммит со всеми изменениями в индекс**
```bash
git commit -am 'do something'
```
### **Интерактивное добавление изменений в индекс**
```bash
git add -i
```

## **18. Перемещение по истории в Git**

### **Просмотр истории коммитов (сокращенный вывод)**
```bash
git log --oneline
```
### **Переключение на конкретный коммит по его хешу**
```bash
git checkout e6f625c
```
### **Возврат на последний коммит в текущей ветке**
```bash
git checkout main
```
### **Проверка текущего местоположения**
```bash
git branch
```

## **19. Использование .gitignore**

### **Создание и настройка .gitignore**
```bash
touch .gitignore
```
### **Пример содержимого .gitignore**
```plaintext
access.log
node_modules/
/coverage/
/db/*.sqlite3
doc/**/*.txt
```
### **Добавление .gitignore в репозиторий**
```bash
git add .gitignore
git commit -m 'update gitignore'
```
### **Удаление файла из репозитория, если он уже был добавлен**
```bash
git rm --cached <filename>
git commit -m 'remove ignored file'
```

## **20. Использование git stash в Git**

### **Сохранение текущих изменений в stash**
```bash
git stash
```
### **Просмотр

 списка stash**
```bash
git stash list
```
### **Восстановление последних изменений из stash**
```bash
git stash pop
```
### **Восстановление конкретных изменений из stash**
```bash
git stash apply stash@{n}
```
### **Удаление последних изменений из stash**
```bash
git stash drop
```
### **Удаление всех изменений из stash**
```bash
git stash clear
```
