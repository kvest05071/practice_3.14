[< содержанию](./readme.md)

## <center> *Файл ***.gitignore*** — объясняем ***git***, какие файлы следует игнорировать* </center>

Иногда по директориям проекта встречаются файлы, которые не хочется постоянно
видеть в сводке ***git status***. Например, вспомогательные файлы текстовых
редакторов, временные файлы и прочий мусор.

Заставить ***git status*** игнорировать можно, создав в корне или глубже по дереву
(если ограничения должны быть только в определенных директория) файл
***.gitignore***. В этих файлах можно описывать шаблоны игнорируемых файлов
определенного формата.

Пример содержимого такого файла:

>>>>>>>Начало файла

#комментарий к файлу ***.gitignore***

#игнорируем сам ***.gitignore***


***.gitignore***

#все ***html***-файлы…


*.**html**


#… кроме определенного


***!special.html***


#не нужны объектники и архивы

*.[***ao***]

>>>>>>>>Конец файла

Существуют и другие способы указания игнорируемых файлов, о которых можно узнать
из справки ***git help gitignore***.


Источник: https://habr.com/ru/post/60347/