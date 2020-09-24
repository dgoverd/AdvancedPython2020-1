# Lab 2. Bash

## Задача 1

Создайте в своей пользовательской директории папку `custom_tmp`.
И напишите .sh скрипт, который после запуска один раз в 10 секунд выводит на экран количество файлов и папок в этой директории `~/custom_tmp`.
Считаться должны файлы и папки, находящиеся непосредственно в `custom_tmp`, рекурсивно обходить все папки в `custom_tmp` не надо.
Запустите этот скрипт в отдельном терминальном окне (или в сессии-окне `tmux`).
В другом терминале (или в другой сессии `tmux`) создайте в `~/custom_tmp` несколько файлов, папок и проверьте, что вывод программы меняется.

Пример вывода (каждая строчка печатается спустя 10 секунд после предыдущей):
```bash
$ Contents of custom_tmp: 0 files, 0 folders
$ Contents of custom_tmp: 9 files, 5 folders
$ ...
```

И пара примеров возможного содержания `custom_tmp` и ожидаемого вывода программы:
```bash
custom_tmp
├── file1.txt
└── file2.txt

$ Contents of custom_tmp: 2 files, 0 folders

custom_tmp
├── file1.txt
└── folder1

$ Contents of custom_tmp: 1 files, 1 folders

custom_tmp
├── file1.txt
└── folder1
    ├── file1.txt
    └── file2.txt

$ Contents of custom_tmp: 1 files, 1 folders
```

В качестве решения задачи надо подготовить описанный .sh скрипт.

### P.S.

В bash-скриптах можно ещё использовать цикл `while`.


## Задача 2*

Напишите скрипт, который как в предыдущей задаче, но вместо вывода информации о содержимом `custom_tmp` просто удаляет *все* файлы и папки в `custom_tmp`.
Вне зависимости от того, кто владелец удаляемого файла или папки.

В качестве решения надо написать сам скрипт и указать, что необходимо сделать, чтобы скрипт работал, как описано (описание действий можно включить в скрипт в виде комментариев).

### P.S.

Помимо read-write-execute прав, в Linux у файлов есть ещё несколько возможных атрибутов.
Так, SetUID бит обеспечивает запуск процесса с теми же правами, что и у владельца файла (вне зависимости от того, кто запускает файл).
В Windows аналога SetUID, похоже, [нет](https://superuser.com/questions/973349/is-there-a-windows-equivalent-of-the-setuid).


## Задача 3*

Напишите скрипт, который как в предыдущей задаче, но который удаляет только те файлы и папки в `custom_tmp`, последнее изменение которых было не меньше, чем 10 секунд назад на момент проверки.


## Задача 4*

Сделайте так, чтобы скрипт из предыдущей задачи всегда автоматически запускался при загрузке системы.

В качестве решения надо предоставить последовательность команд, которые надо исполнить, чтобы настроить автозапуск скрипта (можно в виде .txt файла, или в виде отдельного небольшого скрипта).

## Ссылки

* [Bash-скрипты: начало](https://habr.com/ru/company/ruvds/blog/325522)
* [Bash-скрипты, часть 2: циклы](https://habr.com/ru/company/ruvds/blog/325928)