# Литература для начинающих

Здесь вы не найдете знаменитой "книги дракона" и других подобных учебников. На мой взгляд, такие учебники не подходят для самообучения. Для начинающих полезно использовать конструктивный подход: практическое создание компилятора некоторого учебного языка прямо в процессе изучения минимального объема теории.

## Никлаус Вирт. Построение компиляторов (2010)

*Комментарий от @true-grue*. Небольшой (131 страница) учебник по созданию компилятора подмножества языка Оберон для RISC-процессора. Книга содержит необходимый минимум теории, написана ясным языком. Среди недостатков: компилятор предлагается писать на самом Обероне и это оборачивается некоторой тяжеловесностью реализации с упором на низкоуровневое кодирование. На мой взгляд, это один из лучших учебников для начального чтения по тематике компиляторов для императивных языков. 

*Комментарий от @vkazanov*. В этой маленькой книге изложен виртовский подход к разработке компиляторов, в котором отбрасываются любые усложнения вроде оптимизаций или сложностей кодогенерации, и читатель идет к работающему языку самым коротким путем. Теории тут нет, все пояснения делаются на пальцах, формируя интуитивное понимание проблем. Соглашусь с @true-grue в том, что это очень хороший вводный учебник, после которого, в общем-то, уже можно читать код популярных интерпретатируемых языков вроде Python или Emacs Lisp. Несколько портит впечатление только использование старомодного и многословного Оберона, но ничего непреодолимого в этом языке нет.

## Н. Вирт. Алгоритмы + структуры данных = программы (1985)

*Комментарий от @true-grue*. Хорошо известный в советское время учебник Вирта по базовым алгоритмам и структурам данных. Какое он имеет отношение к компиляторам? Последний раздел в книге называется "Структура языков и трансляторы". Там в сжатой форме рассказывается, как построить компилятор для подмножества Паскаля PL/0 с порождением кода для стековой виртуальной машины. Из этого раздела, очевидно, потом и родился отдельный учебник "Построение компиляторов". Раздел занимает всего 70 страниц, и с азами создания компиляторов вполне способен познакомить. Но читать его лучше тем, кто не боится "архаичного" стиля, ведь оригинальное издание книги вышло в далеком 1976 году! Кстати говоря, в более поздних редакциях этого учебника вы уже не найдете раздела по компиляторам.

## Essentials of Compilation: An Incremental Approach

[Скачать](https://jeapostrophe.github.io/courses/2018/spring/406/notes/book.pdf)

[Исходные тексты на github](https://github.com/IUCompilerCourse/Essentials-of-Compilation)

*Комментарий от @true-grue*. Современный курс по созданию компилятора для Лисп-подобного языка. К достоинствам подхода авторов относится выбор S-выражений в качестве входного языка. То есть задача лексического и синтаксического анализа не рассматривается. И это имеет свои плюсы, поскольку такой подход позволяет сконцентрироваться на действительно важных вещах (middle-end, back-end). При этом особенно глубоко авторы в дебри реализации функциональных языков не уходят, сведения из курса вполне применимы и для реализации компилятора императивного языка. Изложение ведется с использованием Racket (диалект Лиспа), широко применяется сопоставление с образцом. Помимо прочего изучаются: выбор инструкций, распределение регистров, проверка типов, сборка мусора и так далее.  Курс небольшой, всего 119 страниц. Можно рекомендовать всем начинающим компиляторщикам, знакомым с Лиспом.

Существует версия курса для языка [Python](https://github.com/langjam/langjam/blob/main/resources/Python_compiler.pdf).

Данный курс и некоторые другие курсы со сходным содержанием были вдохновлены следующей статьей: [A Ghuloum. An Incremental Approach to Compiler Construction](https://github.com/namin/inc/blob/master/docs/paper.pdf?raw=true). Основная мысль статьи в том, что простейший компилятор (для Лисп-подобного языка) вполне по силам начинающему, если работа над компилятором будет вестись инкрементально: на каждом небольшом шаге мы будем иметь пусть и примитивный, но, все-таки, работающий компилятор. Кстати говоря, истоки данного подхода можно проследить в известной серии заметок [J. Crenshaw. Let's Build a Compiler](https://compilers.iecc.com/crenshaw/). Профессиональный отзыв о данном подходе можно прочесть в заметке [My First Fifteen Compilers](https://blog.sigplan.org/2019/07/09/my-first-fifteen-compilers/).

*Комментарий от @vkazanov*. По совету @true-grue ознакомился с Essentials of Compilation. Думаю, это мой новый фаворит из всех небольших вводных курсов по компиляции. Использование Lisp в качестве промежуточного представления позволяет абстрагироваться от всяких неинтересных вещей вроде синтаксиса/семантики, и шаг за шагом приближать внутреннее представление кода до ассемблера. Думаю, совершенно не важно, что это Lisp, т.к. использование s-выражений только упрощает визуализацию внутренних представлений после каждого из преобразований. 

## T. Parr. Language Implementation Patterns: Create Your Own Domain-Specific and General Programming Languages

*Комментарий от @true-grue*. Для многих программистов теория компиляции важна в связи с желанием создавать различные небольшие DSL для своих задач. Здесь может оказать помощь рассматриваемая книга, которую отличает очень большое количество практически полезных примеров. Автор сумел "на пальцах" объяснить полезные методы построения парсеров (включая подход packrat), различные техники обхода AST (включая term rewriting), способы создания стековых и регистровых виртуальных машин, методы source-to-source трансляции. Изложение ведется с использованием инструментария ANTLR (автором которого T. Parr и является) и языка Java. По теме введения в создание собственных little languages и простых генераторов программ данную книгу можно смело советовать, у нее практически нет конкурентов.

*Комментарий от @vkazanov*. По долгу службы мне чаще приходится иметь дело с небольшими языками запросов, которые конвертируются в запросы на SQL или байт-код специализированных мини-БД. Одна из характерных проблем в данном случае - коротко вводить в курс дела коллег-программистов, не имеющих опыта разработки парсеров или, тем более, бэкэндов компиляторов. Так вот, эта книга - лучшая рекомендация в данном случае. 

## [Robert Nystrom. Crafting Interpreters](http://craftinginterpreters.com/contents.html) (2020)

*Комментарий от @true-grue*. В последнее время появляется много литературы, где вопросы построения интерпретаторов и компиляторов разъясняются "простыми словами". Иной раз авторы слишком увлекаются частными вопросами реализации и не дают читателю возможность "за деревьями увидеть лес". В этом плане небольшая книга от Rob Nystrom выделяется в лучшую сторону. Во-первых, ее автор -- практикующий разработчик с большим опытом в области создания игр. Во-вторых, вопросами компиляции он интересуется серьезно. В частности, его старую заметку в блоге на тему реализации парсера Пратта можно считать одной из лучших на эту тему.

Crafting interpreters -- это небольшое введение в построение компиляторов и интерпретаторов для начинающих. От читателя требуется только знание языка Си и знакомство с языками в духе JavaScript или Python. Подобный динамически-типизированный язык и будет разработан в процессе изучения книги. Главный плюс Crafting Interpreters, на мой взгляд, в том, что ее автор обладает талантом рассказывать просто о сложном. 

## Douglas Thain. Introduction to Compilers and Language Design, 2nd edition, 2020. (Revision Date: January 15, 2021)

Доступна в печатном виде и бесплатно в виде PDF: https://www3.nd.edu/~dthain/compilerbook/

В книге сжато излагаются все основные аспекты компиляции: лексический анализ, синтаксический анализ, деревья абстрактного синтаксиса и семантический анализ, промежуточные представления, представление данных в памяти, порождение кода, оптимизации. Изложение ведётся на языке C, используются инструменты Flex и Bison. В качестве сквозного примера рассматривается несложный императивный язык программирования.

## Mak R. Writing Compilers and Interpreters: A Software Engineering Approach (2009)

## Хантер Р. Компиляторы. Краткий справочник (2018)

*Комментарий от @vkazanov*. Небольшая вводная книга, около 200 страниц, рассказывающая о базовых вопросах компиляции. Упоминаются лексический, синтаксический и семантический анализ, коротко по размещению переменных в памяти и кодогенерации. Темы изложены лаконично, элементы теории удачно перемежаются с простыми примерами (разбор методом рекурсивного спуска, lex, yacc и т.д.). Основная проблема книги - поверхностность и незаконченность, то есть работающего компилятора читатель все же не увидит. С другой стороны, в качестве вводной она вполне сойдет. 

*Комментарий от @true-grue*. На русский язык до сих пор не переведены Аппель с Мучником, но вот Хантера у нас переводят с удовольствием. Есть и советское издание 1984 года, и переводы от «Вильямса» 2002 и 2017 года. Хантер написал несколько книг, но материал, на мой взгляд, в них различается мало — читателя обучают создавать компилятор Паскаля с помощью самых базовых подходов. Я не заметил у автора каких-то интересных педагогических приемов и, в целом, предпочел бы Хантеру Вирта.
