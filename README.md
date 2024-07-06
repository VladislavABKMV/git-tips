
# Команды гит

----

## Проверка версии
```bash
git version
```
----


## Первичная настройка git
```bash
$ git config --global user.name "User Namovich" 
# имя или ник нужно написать латиницей и в кавычках

$ git config --global user.email username@yandex.ru
# здесь нужно указать свой настоящий email
```
----


## Сделать папку репозиторием *git init*
```bash
$ cd ~/dev/%целевая_папка% # перешли в нужную папку

$ git init # создали репозиторий
```
----


## «Разгитить» папку, если что-то пошло не так, - *rm -rf .git*
```bash
$ cd <папка с репозиторием> # перешли в папку

$ rm -rf .git # удалили подпапку .git 
```
----


## Проверить состояние репозитория — *git status*
----


## Подготовить файлы к сохранению — *git add*
```bash
$ git add --all # подготовили к сохранению все файлы в репозитории
$ git status # проверили статус
```
----


## Выполнить коммит — *git commit*
```bash
$ git commit -m 'Мой первый коммит!' 
# -m - флаг, который позволяет в одной строке добавлять комментарий к коммиту
```
----


## Просмотреть историю коммитов — *git log*
----


## Привязать удалённый репозиторий к локальному — *git remote add*
```bash
$ cd ~/dev/local-repository
$ git remote add origin git@github.com:%ИМЯ_АККАУНТА%/remote-repository.git
```
----


## Убедиться, что репозитории связаны, — *git remote -v*
```bash
$ git remote -v
origin    git@github.com:%ИМЯ_АККАУНТА%/%ИМЯ-ПРОЕКТА%.git (fetch)
origin    git@github.com:%ИМЯ_АККАУНТА%/%ИМЯ-ПРОЕКТА%.git (push)
```
----


## Отправить изменения на удалённый репозиторий — *git push*
```bash
$ git push -u origin main # Если команда приведёт к ошибке, попробуйте 
                          # заменить main на master.
                          # -u флаг, который необходимо использовать при первом пуше связанного репозитория
```
----

# Hash коммита

## Хэш коммита - идентификатор коммита, полученный с помощью алгоритма SHA-1.
## Хэш обладает свойством: если хоть что-то в исходных данных поменяется, хеш тоже изменится.
## Git хранит таблицу соответствий хеш → информация о коммите в служебных файлах .git.

---

# Log

## Лог - список коммитов с описанием, содержит хеш, автора, дату и сообщение к коммиту.
```BASH
$ git log
```

## Сокращённый лог - список коммитов с описанием, содержит только первые несколько символов хеша и комментарии.
```BASH
$ git log --oneline
```

---
[//]: # (хеш, лог, HEAD, статусы файлов, стили оформления сообщений к коммитам)

