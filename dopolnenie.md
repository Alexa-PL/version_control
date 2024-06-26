# Инструкция по работе с Git

#Подсказки по командной строке

Команда смены директории
```sh
cd c:\folder_name
```

Команда отображения текущей директории. MacOS,Linux
```sh
pwd
```

Листинг текущей директории
Windows:
```sh
dir
```
Linux,MacOS:
```sh
ls
```
Удаление файла в Windows:
```sh
del <filename>
```
в Linux, MacOS:
```sh
rm <filename>
```
## Создание репозитория

Создать новый локальный репозиторий:
```sh
git init {имя проекта}
```
Скачать репозиторий:
```sh
git clone {url}
```
## Состояние репозитория

Список незакоммиченных файлов:
``` sh
git status
```
Изменения в еще не добавленных в индекс файлов:
```sh
git diff
```
Изменения в уже добавленных в индекс файлов:
```sh
gif diff --cached
```
Все изменения:
```sh
dit diff HEAD
```
Получить даты изменений и их авторов:
```sh
git blame {имя файла}
```
Изменения между двумя коммитами:
```sh
git diff hash1 hash2
```
Получить список изменений файла в определенном коммите:
```sh
git show hash:file
```
Показать историю изменений, включая диффы:
```sh
git log -p {файл или папка}
```
## Работа с ветками

Список локальных веток:
```sh
git branch
```
Список всех веток:
```sh
git branch -av
```
Переключиться на ветку mybranch:
```sh
git checkout mybranch
```
Создать ветку mybranch и переключиться на нее:
```sh
git checkout -b mybranch
```
Удалить ветку mybranch:
```sh
git branch -d mybranch
```
Создать тег для текущего коммита:
```sh
git tag {имя тега}
```
## Сохраняем изменения

Добавить файл в индекс:
```sh
git add {имя файла}
```
Добавить все файлы в папке:
```sh
git add 
```
Закоммитить добавленные в индек файлы с сообщением:
```sh
git commit -m "сообщение"
```

Закоммитить все файлы с сообщением:
```sh
git commit -am "сообщение"
```

Удалить измененный файл из индекса, оставив изменения в нем:
```sh
git reset {имя файла}
```

Отменить все изменения в папке и вернуть все к последнему коммиту:
```sh
git reset --hard
```

## Обновление

Скачать измения из удаленного репозитория:
```sh
git fetch
```

Cкачать изменения из удаленного репозитрия и смержить:
```sh
git pull
```

Скачать изменения из удаленного репозитория и наложить незапущенные коммиты поверх скаченных:
```sh
git pull --rabase
```
Отправить локальные коммиты в удаленный репозиторий:
```sh
git push
```
## Подсказки

Использование подсказок:
```sh
git {имя комманды} --help
```
# Ветки

>выводит список веток что у нас есть:
```sh
git branch
```
>команда для очестки терминала:
```sh
clear
```
>создание другой ветки:
```sh
git branch {имя_другой_ветки}
```
>>*Звёздочка в терминале показывает ту ветку на которой мы распологаемся*

>удаление ненужной ветки:
```sh
git branch -d {имя ветки}
```
Для того чтобы Git не обращал внимание на фал с картинкой мы его просто добавим в файл gitignore. 
Для этого мы создаем новый файл {.gitignore}.
Далее в терминале мы пишем команды: git add{.gitignore}; git commit -m "Добавили gitignore файл".
Потом мы проверяем статус и всё работает,наш файл-картинка невидимы.

>Опция --graph в команде git log отображает ASCII-граф с ветвлениями и историей слияний.

>>Эта опция позволяет увидеть небольшой граф в формате ASCII, который показывает текущую ветку и историю слияний.
```sh
git log --graph
``
Слияние веток
```sh
git merge {имя_ветки}
```
# Работа с удалёнными репозиториями

* Сделать копию локального репозитория
```sh
git clone
```
_Копия чужого репозитория называется **fork**_

* «Стянуть/выкачать» все изменения из удаленного репозитория на свой компьютер
```sh
git pull
```
* Выкачивает данные из удаленного репо и делает слияние с локальным репо
```sh
git pull
```
* отправить изменения в удаленный репозиторий
```sh
git push
```
**Особенности, которые есть у команды push:**
1. _git должен знать адрес удаленного репозитория;_
2. _git должен быть "авторизован" на внесение изменений в удаленном репозитории_
