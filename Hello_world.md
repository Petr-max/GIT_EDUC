![Логотип](images/GitHub_Logo_White.png)

# Первый файл по контролю версий


## 1. Установка git

устонавливаем по умолчанию <https://git-scm.com/book/en/v2/Getting-Started-Installing-Git>

---

## 2. Настройка git

При первом использовании необходимо представиться. Для этого нужно ввести две команды;

```git config --global user.name "<ваше_имя>"
git config --global user.email "<адрес_почты@email.com>"
```
---

## 3. Работа с GIT

Проверка установленного приложения GIT

Начинаем наше знакомство с контролем версий

Выполнить команду `git version.`

---

## 4. Инициализация репозитория

ввести коману: `git status.`

Если Git установлен, то появится сообщенние с информацией об версии программы, усли нет то сообщение об ошибке

---

## 5. Заголовки и горизонтальные линии

Заголовки H1–H6 выделяются в Markdown с помощью знаков решетки (диез/шарп). Можно просто поставить нужное количество решеток в начале строки, чтобы указать уровень. Или заключить строку с двух сторон по аналогии с HTML-тегами, кому как удобно.

# Это H1

## Это H2 ##

### Это H3

#### Это H4 ####

##### Это H5 #####

###### Это H6

Другой вариант: написать текст первого заголовка, затем нажать Enter и на следующей строке указать любое количество знаков «равно». Аналогичным образом можно выделить H2, только использовать уже нужно дефисы. Заголовки других уровней таким методом оформить нельзя.

Это H1 или Заголовок I

===

Это H2 или Заголовок II

Если отделить последовательность дефисов пустой строкой, то H2 не будет. Получится горизонтальная разделительная линия. Ее можно оформить также с помощью звездочек или знака нижнего подчеркивания. Количество символов и пробелов между ними роли не играет. А вот знак равенства работает только с заголовками H1, горизонтальные линии он не рисует: 

---

## 6. Выделение текста

Форматирование курсивом и жирным точно есть во всех инструментах, где другие функции Markdown могут быть ограничены. Синтаксис выделения текста и расставления акцентов:

__Жирный__

**Тоже жирный**

*Курсив*

_Тоже курсив_

~~Зачеркнутый~~

---

## 7. Списки и отступы

Чтобы оформить строку в элемент маркированного списка, в начале нужно поставить плюс, минус или звездочку. Звездочка не приведет к курсивному выделению, потому что отделяется от слова пробелом.

- Пункт 1

- Пункт 2

- Пункт 3

или

+ Пункт 1

+ Пункт 2

+ Пункт 3

или

* Пункт 1

* Пункт 2

* Пункт 3

---

## 8. Запись изменений в репозиторий

Итак, у вас имеется настоящий Git-репозиторий и рабочая копия файлов для некоторого проекта. Вам нужно делать некоторые изменения и фиксировать «снимки» состояния (snapshots) этих изменений в вашем репозитории каждый раз, когда проект достигает состояния, которое вам хотелось бы сохранить.

Запомните, каждый файл в вашем рабочем каталоге может находиться в одном из двух состояний: под версионным контролем (отслеживаемые) и нет (неотслеживаемые). Отслеживаемые файлы — это те файлы, которые были в последнем снимке состояния проекта; они могут быть неизменёнными, изменёнными или подготовленными к коммиту. Если кратко, то отслеживаемые файлы — это те файлы, о которых знает Git.

Неотслеживаемые файлы — это всё остальное, любые файлы в вашем рабочем каталоге, которые не входили в ваш последний снимок состояния и не подготовлены к коммиту. Когда вы впервые клонируете репозиторий, все файлы будут отслеживаемыми и неизменёнными, потому что Git только что их извлек и вы ничего пока не редактировали.

Как только вы отредактируете файлы, Git будет рассматривать их как изменённые, так как вы изменили их с момента последнего коммита. Вы индексируете эти изменения, затем фиксируете все проиндексированные изменения, а затем цикл повторяется.

---

![Жизненный цикл состояний файлов](images/Жизненный%20цикл%20состояний%20файлов.png)

---

![Сливать ветку](images/Сливать%20ветку.jpg)

---

## 9. Просмотр истории коммитов

![ветки](images/Дерево%20веток.jpg)


После того, как вы создали несколько коммитов или же клонировали репозиторий с уже существующей историей коммитов, вероятно вам понадобится возможность посмотреть что было сделано — историю коммитов. Одним из основных и наиболее мощных инструментов для этого является команда git log.

Следующие несколько примеров используют очень простой проект «simplegit». Чтобы клонировать проект, используйте команду:

$ git clone https://github.com/schacon/simplegit-progit
Если вы запустите команду git log в каталоге клонированного проекта, вы увидите следующий вывод:

$ git log
commit ca82a6dff817ec66f44342007202690a93763949
Author: Scott Chacon <schacon@gee-mail.com>
Date:   Mon Mar 17 21:52:11 2008 -0700

    Change version number

commit 085bb3bcb608e1e8451d4b2432f8ecbe6306e7e7
Author: Scott Chacon <schacon@gee-mail.com>
Date:   Sat Mar 15 16:40:33 2008 -0700

    Remove unnecessary test

commit a11bef06a3f659402fe7563abf99ad00de2209e6
Author: Scott Chacon <schacon@gee-mail.com>
Date:   Sat Mar 15 10:31:28 2008 -0700

    Initial commit

По умолчанию (без аргументов) git log перечисляет коммиты, сделанные в репозитории в обратном к хронологическому порядке — последние коммиты находятся вверху. Из примера можно увидеть, что данная команда перечисляет коммиты с их SHA-1 контрольными суммами, именем и электронной почтой автора, датой создания и сообщением коммита.

Команда git log имеет очень большое количество опций для поиска коммитов по разным критериям. Рассмотрим наиболее популярные из них.

Одним из самых полезных аргументов является -p или --patch, который показывает разницу (выводит патч), внесенную в каждый коммит. Так же вы можете ограничить количество записей в выводе команды; используйте параметр -2 для вывода только двух записей:

`$ git log -p -2`
Эта опция отображает аналогичную информацию но содержит разницу для каждой записи. Очень удобно использовать данную опцию для код ревью или для быстрого просмотра серии внесенных изменений. Так же есть возможность использовать серию опций для обобщения. Например, если вы хотите увидеть сокращенную статистику для каждого коммита, вы можете использовать опцию --stat:

`$ git log --stat`
Следующей действительно полезной опцией является --pretty. Эта опция меняет формат вывода. Существует несколько встроенных вариантов отображения. Опция oneline выводит каждый коммит в одну строку, что может быть очень удобным если вы просматриваете большое количество коммитов. К тому же, опции short, full и fuller делают вывод приблизительно в том же формате, но с меньшим или большим количеством информации соответственно:

`$ git log --pretty=oneline`
Наиболее интересной опцией является format, которая позволяет указать формат для вывода информации. Особенно это может быть полезным когда вы хотите сгенерировать вывод для автоматического анализа — так как вы указываете формат явно, он не будет изменен даже после обновления Git.

`$ git add .gitignor`
Эта команда для создания папки которую Git не будет отслеживать.
Далее следует команда сохранить коммит.

`$ git commit -m "Добавил файл в gitignore"`

---
## 10. Перемещение между сохранениями

![Картинка основных команд git](images/Основные%20команды%20Git.jpg)

Удаление локальной ветки
Чтобы удалить локальную ветку в Git нужно выполнить команду (вместо mybranch необходимо поставить название ветки, которую вы хотите удалить):

`git branch -название ветки`

Обратите внимание на то, что ветка, которую вы удаляете, не должна быть вашей текущей веткой, в которой вы работаете, иначе отобразится ошибка вида:

`error: Cannot delete branch ’mybranch’ checked out at ’/path/to`

Поэтому, если вам нужно удалить текущую ветку, то сначала нужно переключиться на какую-либо другую ветку, а только потом выполнять удаление.

Если вдруг возникает ошибка: 

`The branch ’mybranch’ is not fully merged. If you are sure you want to delete it`

 и вы по прежнему хотите удалить ветку, то для принудительного удаления ветки можно воспользоваться опцией -D:

`git branch -D название ветки`

Удаление удаленной ветки
Чтобы удалить удаленную (remote) ветку используется команда (вместо origin и mybranch необходимо поставить свои данные):

`git push origin --delete название ветки`

Вместо --delete можно просто писать -d:

`git push origin -d название ветки`

---

## 11. Ссылки и картинки

Чтобы поставить гиперссылку без анкора, нужно взять URL в угловые скобки. С e-mail – аналогично.

Если вставлять с анкором, то тогда текст ссылки заключается в квадратные скобки, а адрес страницы – в круглые. Рядом с URL можно прописать тайтл, его объявляют в кавычках (он тоже остается внутри круглых скобок).

Это [ссылка]( "Агентство TexTerra") с тайтлом.

[Эта ссылка]"(http://example.net/)" без заголовка.

---

## 12. Таблицы и чек-боксы

Если поддерживается расширенная версия Markdown, можно вставлять таблицы. Для этого используются всего два символа: вертикальная черта и дефис. Дефисы работают примерно так же, как в случае с горизонтальной линией: отделяют заголовки от других строк, при этом количество символов значения не имеет. Вертикальная черта служит границей между столбцами.

---

## 13. Цитаты и вставки кода

Если безанкорные ссылки оформляются двумя угловыми скобками, то для цитаты нужна только одна такая скобка. Все очень просто:

> Привет! Это цитата

> Это тоже цитата

> Это еще одна цитата

Это ее продолжение (показываем отступом)

> Это тоже

Будет

>
> Одна целая цитата
>

---

Пример – таблица меток для блоков кода, об этом было в предыдущем разделе:

| Язык | Метка |

| -----|------|

| Java Script | javascript |

| C++ |cpp|

| HTML|html|

|Markdown|md|

|JSON|json|

|Python|python|

|SQL|sql|

Для любителей чек-листов есть такая возможность. Чек-бокс получится, если в начале строки вставить пробел, заключенный с двух сторон в квадратные скобки. Можно сразу задать выполненную задачу с помощью [X]. С оформлением ссылок по-другому – в квадратных скобках или текст, или ничего.

---

## 14. Важно: экранирование

Мы разобрали с десяток различных символов, которые используются в разметке Markdown. Но что если эти символы нужны нам в самом тексте? Чтобы спецсимволы не исчезали и не влияли на оформление, нужно использовать экранирование. Как и во многих других языках программирования, этим целям служит обратная косая черта (бэкслеш).
Исключение – когда надо вставить внутри кода грависы (обратные тики). Интерпретатор не посчитает их за обозначение инлайн-кода, если только весь участок кода заключен с двух сторон в двойные грависы. Ничего не понятно? На примере все наглядно:
В отличие от HTML, в Markdown не нужно специально экранировать амперсанд (&) или угловую скобку (<).

---

## 15. Как добавить изображение в Markdown

Несколько простых способов добавить изображение в документ

Визуальная информация воспринимается гораздо легче и эффективнее, чем простой текст. Именно поэтому говорится, что картинка стоит тысячи слов. Так что возможно, что и ты захочешь добавить изображение в свой документ или пост в блоге. Ниже несколько простых способов, как добавить изображение в markdown публикацию или документ.

Markdown - это простой и удобный язык разметки, который можно использовать для форматирования практически любых документов. Если захочешь узнать про него больше, читай официальный The Markdown Guide.

Как добавить изображение из файла
Предположим, что нужные тебе изображения находятся в папке images:

```
 ├─ images
     └─ picture.jpg
     └─ picture-2.jpg
     └─ picture-three.jpg
 ├─ README.md
 ```
Важно: Имей в виду, что если в названии файла содержатся скобки или другие специальные символы, то файл может не отобразится. Если хочешь знать, как правильно называть файлы для веб-проектов, посмотри вот эти рекомендации для имен файлов в интернет проектах.

Первый способ, как отобразить локальное изображение в markdown документе, это использовать следующий код:

```
![Текст с описанием картинки](/images/picture.jpg)
```

Часть в квадратных скобках - это так называемый альтернативный текст, который важен по следующим причинам:

Для доступности. Программы чтения с экрана читают именно его. Например, для тех, кто плохо видит.

Этот текст будет отображаться вместо изображения, если файл изображения не может быть загружен.

Он обеспечивает контекст и описание изображения для поисковых систем, помогая им с поиском.

Часть в круглых скобках - это путь к файлу. Обрати внимание, что перед images стоит /. Без этого символа твой документ может отображаться нормально на твоем компьютере, но после загрузки на сервер в интернете она отображаться перестанет. Это одна из основных причин, почему так случается.

Другой способ, как отобразить локальное изображение в markdown публикации, это использовать тег image в тексте документа:
```
<image src="/images/picture.jpg" alt="Текст с описанием картинки">
```
Одним из преимуществ этого способа заключается в том, что так можно использовать дополнительные возможности для контроля изображения. Специфика зависит от ресурса, на котором ты публикуешь документ.

Любой из этих способов даст нужный результат, так что выбор за тобой.

Как добавить изображение из ссылки
Когда необходимо вставить в документ изображение, которое находится где-то в интернете, то просто используй ссылку на изображение:

```
![Текст с описанием картинки](https://picsum.photos/800/600)
```
или
<image src="https://picsum.photos/800/600" alt="Описание картинки">
https://picsum.photos/800/600

Как добавить подпись к изображению
В markdown коде для этого просто добавь через пробел текст в кавычках:

```
![Описание картинки](/images/picture.jpg "Подпись под картинкой")
```
![С новым годом!!!](images/С%20Новым%20годом!!!.jpg)





