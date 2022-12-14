[< содержанию](./readme.md)

## <center> *Хэш — уникальная идентификация объектов* </center>

В ***git*** для идентификации любых объектов используется уникальный (то есть с
огромной вероятностью уникальный) хэш из 40 символов, который определяется
хэшируюшей функцией на основе содержимого объекта. Объекты — это все: коммиты,
файлы, тэги, деревья. Поскольку хэш уникален для содержимого например: файла,
то и сравнивать такие файлы очень легко — достаточно просто сравнить две строки
в сорок символов.

Больше всего нас интересует тот факт, что хэши идентифицируют коммиты. В этом
смысле хэш — продвинутый аналог ревизий ***Subversion***. Несколько примеров
использования хэшей в качестве способа адресации:

***git diff f292ef5d2b2f6312bc45ae49c2dc14588eef8da2*** — найти разницу текущего
состояния проекта и коммита за номером… Ну сами видите, каким.

***git diff f292ef5*** — то же самое, но оставляем только шесть первых символов. ***Git*** поймет, о каком коммите идет речь, если не существует другого коммита с таким началом хэша.

***git diff f292*** — иногда хватает и четырех символов.

***git log febc32...f292*** — читаем лог с коммита по коммит.


Разумеется, человеку пользоваться хэшами не так удобно, как машине, именно поэтому были введены другие объекты — тэги.

Источник: https://habr.com/ru/post/60347/