[< содержанию](./readme.md)

## <center> *Поиск слов по проекту, состоянию проекта в прошлом.* (***git grep***) </center>

***git grep***, в целом, просто дублирует функционал знаменитой юниксовой
команды. Однако, он позволяет слова и их сочетания искать в прошлом проекта, что
бывает очень полезно:

***git grep tst*** — поиск слова ***tst*** в проекте.

***git grep -с tst*** — подсчитать число упоминаний ***tst*** в проекте.


***git grep tst* v1** — поиск в старой версии проекта.

Команда позволяет использовать логическое **И** и **ИЛИ**:

***git grep -e 'first' --and -e 'another'*** — найти строки, где упоминаются и первое слово, и второе.

***git grep --all-match -e 'first' -e 'second'*** — найти строки, где встречается хотя бы одно из слов.

Источник: https://habr.com/ru/post/60347/