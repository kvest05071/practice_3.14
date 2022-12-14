[< содержанию](./readme.md)

## <center> *Переключение между ветками, извлечение отдельных файлов из истории коммитов* (***git checkout***) </center>

Команда ***git checkout*** позволяет переключаться между последними коммитами (если упрощенно) веток:

***checkout some-other-branch***

***checkout -b some-other-new-branch*** — создаст ветку, в которую и произойдет
переключение.

Если в текущей ветке были какие-то изменения по сравнению с последним коммитом в
ветке(**HEAD**), то команда откажется производить переключение, дабы не потерять
произведенную работу. Проигнорировать этот факт позволяет ключ ***-f***:

***checkout -f some-other-branch***

В случае, когда изменения надо все же сохранить, используют ключ ***-m***. Тогда команда перед переключением попробует залить изменения в текущую ветку и, после
разрешения возможных конфликтов, переключиться в новую:

***checkout -m some-other-branch***


Вернуть файл (или просто вытащить из прошлого коммита) позволяет команда вида:

***git checkout somefile*** — вернуть ***somefile*** к состоянию последнего коммита
***git checkout HEAD~2 somefile*** — вернуть ***somefile*** к состоянию на два коммита назад по ветке.

Источник: https://habr.com/ru/post/60347/