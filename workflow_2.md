[< содержанию](./readme.md)

Предположим, что вы и несколько ваших напарников создали общественный
репозитарий, чтобы заняться неким общим проектом. Как выглядит самая
распространенная для git модель общей работы?

git clone http://yourserver.com/~you/proj.git
… возможно, прошло некоторое время.

git pull

git diff HEAD^

git checkout -b bad-feature
… работаем некоторое время.

git commit -a -m «Created a bad feature»

git checkout master

git pull

git merge bad-feature

git commit -a

git diff HEAD^
… запускаем тесты проекта, обнаруживаем, что где-то произошла ошибка. Упс.


git reset --hard ORIG_HEAD

git checkout bad-feature
… исправляем ошибку.

git -m bad-feature good-feature

git commit -a -m «Better feature»

git checkout master

git pull

git merge good-feature

git push

git branch -d good-feature



Итак, первым делом создаем (1) создаем копию удаленного репозитария (по
умолчанию команды вроде git pull и git push будут работать с ним). «Вытягиваем»
последние обновления (2); смотрим, что же изменилось(3); создаем новую ветвь и
переключаемся в нее (4); индексируем все изменения и одновременно создаем из них
коммит (5); переключаемся в главную ветвь (6), обновляем ее (7); проводим
слияние с веткой bad-feature(8) и, обнаружив и разрешив конфликт, делаем коммит
слияния (9).

После совершения коммита отслеживаем изменения(10), запускаем, например,
юнит-тесты и с ужасом обнаруживаем, что после слияния проект валится на большей
части тестов.

В принципе, тесты можно было прогнать и до коммита, в момент
слияния (между пунктами 8 и 9); тогда бы хватило «мягкого» резета.

Таким образом, приходится совершить «жесткий» (11) сброс произошедшего слияния,
ветки вернулись в исходное до состояние. После чего переключаемся в неудачную
ветку (12), вносим необходимые изменения и переименовываем ветку (13). Совершаем
коммит (14); переходим в главную ветку(15), опять ее обновляем (16). На этот раз
бесконфликтно делаем слияние (17), закидываем изменения в удаленный репозитарий
(18) и удаляем ненужную теперь ветку (19). Закрываем ноутбук, одеваемся и идем
домой под утро.

Источник: https://habr.com/ru/post/60347/