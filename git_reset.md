[< содержанию](./readme.md)

## <center> *Возврат к определенному коммиту, откат изменений, «жесткий» или «мягкий»* (***git reset***) </center>

Помимо работы с индексом (см. выше), ***git reset*** позволяет сбросить состояние
проекта до какого-либо коммита в истории. В ***git*** данное действие может быть двух видов: «мягкого»(***soft reset***) и «жесткого» (***hard reset***).


«Мягкий» (с ключом "--***soft***") резет оставит нетронутыми ваши индекс и все дерево файлов и директорий проекта, вернется к работе с указанным коммитом. Иными
словами, если вы обнаруживаете ошибку в только что совершенном коммите или
комментарии к нему, то легко можно исправить ситуацию:

***git commit…*** — некорректный коммит;

***git reset --soft* HEAD^** — переходим к работе над уже совершенным коммитом,
сохраняя все состояние проекта и проиндексированные файлы ***edit* WRONGFILE**

***edit* ANOTHERWRONGFILE**

***add.***



6.1. ***git commit -c* ORIG_HEAD** — вернутся к последнему коммиту, будет предложено редактировать его сообщение. Если сообщение оставить прежним, то
достаточно изменить регистр ключа -***с***:

6.2. ***git commit* -C ORIG_HEAD**

Обратите внимание на обозначение **HEAD^**, оно означает «обратиться к предку
последнего коммита». Подробней описан синтаксис такой относительной адресации
будет ниже, в разделе «Хэши, тэги, относительная адресация». Соответственно,
**HEAD** — ссылка на последний коммит. Ссылка **ORIG_HEAD** после «мягкого» резета
указывает на оригинальный коммит.


Естественно, можно вернуться и на большую глубину коммитов,

«Жесткий» резет (ключ --**hard**) — команда, которую следует использовать с
осторожностью. ***Git reset --hard*** вернет дерево проекта и индекс в состояние,
соответствующее указанному коммиту, удалив изменения последующих коммитов:

***git add.***

***git commit -m «destined to death»***

***git reset --hard* HEAD~1** — больше никто и никогда не увидит этот позорный коммит.

***git reset --hard* HEAD~3** — вернее, три последних коммита. Никто. Никогда.


Если команда достигнет точки ветвления, удаления коммита не произойдет.

Для команд слияния или выкачивания последних изменений с удаленного репозитария
примеры резета будут приведены в соответствующих разделах.

Источник: https://habr.com/ru/post/60347/