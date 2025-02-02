
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

```BASH
$ git status # вывод список файлов со статусами staged, modified и untracked
```

### Git использует статусы файлов для отслеживания изменений в репозитории.
### Статусы файлов включают: untracked, staged, modified, and tracked.
### Untracked файлы - новые файлы, не отслеживаемые Git'ом.
### Staged файлы - файлы, добавленные в staging area командой git add.
### Modified файлы - файлы с изменениями, найденными Git'ом.
### Tracked файлы - файлы, закоммиченные или добавленные в staging area.
### Жизненный цикл файла в Git: создание, добавление в staging area, коммит, изменение, повторное добавление в staging area, коммит.
### Команда git status показывает статусы файлов: staged, modified, untracked.

## Изменение статусов:

```mermaid
graph LR;
  untracked -- "git add" --> staged;
  modified -- "git add" --> staged;
  staged    -- "git commit"     --> tracked/committed;
  tracked/committed    -- "внесение изменений в файл"     --> modified;
  
  %% Схема изменения статусов
```

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
## Лог - список коммитов с описанием, содержит хеш, автора, дату и сообщение к коммиту.
```BASH
$ git log
```

## Сокращённый лог - список коммитов с описанием, содержит только первые несколько символов хеша и комментарии.
```BASH
$ git log --oneline
```
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
# HEAD

## Файл HEAD указывает на последний (самый новый) коммит.

## При работе с Git указатель HEAD используется часто, вместо хеша последнего коммита можно просто написать слово HEAD.

---

# Сообщения к коммитам

## Сообщения к коммитам важны для определения содержимого коммита и облегчения работы с ним.
## Сообщения должны быть короткими, информативными и легко читаемыми.
##  Разные команды и проекты могут использовать разные стили оформления сообщений.
- Общие рекомендации включают длину сообщения от 30 до 72 символов, использование глаголов в инфинитиве и указание Jira-ID при корпоративном стиле.
- Conventional Commits предлагает стандартизированный формат коммита с указанием типа изменений.
- GitHub-стиль позволяет указывать ссылки на задачи в сообщениях коммитов.
- Рекомендации для использования инфинитивов и повелительного наклонения в сообщениях на разных языках также существуют.

[//]: # (стили оформления сообщений к коммитам)

