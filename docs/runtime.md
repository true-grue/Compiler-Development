# Литература по вопросам, относящимся к средам выполнения

## Виртуальные машины

Шитый код

[Bell J. R. Threaded code //Communications of the ACM. – 1973. – Т. 16. – №. 6. – С. 370-372.](http://home.iae.nl/users/mhx/Forth_Bell.pdf)

## JIT-компиляция

[Aycock J. A brief history of just-in-time //ACM Computing Surveys (CSUR). – 2003. – Т. 35. – №. 2. – С. 97-113.](https://prism.ucalgary.ca/bitstream/handle/1880/45368/2001-689-12.pdf?sequence=2&isAllowed=y)


[Tratt L. Fast Enough VMs in Fast Enough Time](https://tratt.net/laurie/blog/entries/fast_enough_vms_in_fast_enough_time.html)

Подробное введение в (мета-)трассирующую JIT-компиляцию на примере PyPy + RPython. Разбираются (упрощённые) примеры построения и оптимизации трасс, строится "мост" к практическому использованию PyPy для реализации собственной языковой ВМ с JIT-компиляцией.


[Carl Friedrich Bolz, Laurence Tratt, The Impact of Meta-Tracing on VM Design and Implementation, Science of Computer Programming, 98(3):402-421](https://tratt.net/laurie/research/pubs/html/bolz_tratt__the_impact_of_metatracing_on_vm_design_and_implementation/)

Most modern languages are implemented using Virtual Machines (VMs). While the best VMs use Just-In-Time (JIT) compilers to achieve good performance, JITs are costly to implement, and few VMs therefore come with one. The RPython language allows tracing JIT VMs to be automatically created from an interpreter, changing the economics of VM implementation. In this paper, we explain, through two concrete VMs, how meta-tracing RPython VMs can be designed and optimised, and, experimentally, the performance levels one might reasonably expect from them.


[Würthinger T, Wimmer C, Humer C, Wöß A, Stadler L, Seaton C, Duboscq G, Simon D, Grimmer M. Practical partial evaluation for high-performance dynamic language runtimes. InProceedings of the 38th ACM SIGPLAN Conference on Programming Language Design and Implementation 2017 Jun 14 (pp. 662-676).](https://chrisseaton.com/rubytruffle/pldi17-truffle/pldi17-truffle.pdf)

Статья является отличным кратким введением в практическое использование фреймворка Truffle для тех, кто уже знает как производить парсинг исходного кода, построение и непосредственную интерпретацию AST (ещё полезно знать про inline caches). Даются примеры и произвдится сравнение скорости нескольких интерпретаторов промышленных динамических языков программирования:  JavaScript, Ruby и R.


## Параллельное и конкурентное выполнение

## Сборка мусора

[The Garbage Collection Handbook: The Art of Automatic Memory Management](https://www.amazon.com/Garbage-Collection-Handbook-Management-Algorithms/dp/1420082795) ([Web version](http://gchandbook.org/))


[Memory Management Reference](https://www.memorymanagement.org/)

Веб-сайт, посвящённый вопросам управления памятью &mdash; как ручного, так и автоматического. Содержит
- глоссарий
- вводные статьи
- список литературы
- ответы на частые вопросы

Статьи дают краткое представление о проблематике управления памятью от железа через операционную систему к уровню приложения.
Упоминают базовые техники аллокации и рекламации памяти (трассировка, подсчёт ссылок). Кратко описывают подходы к управлению памятью
в языках программирования, как распространённых, так и исторических. В основном ссылаются на соответствующие разделы глоссария.

Сайт можно рекомендавать в качестве обзорного введения в тематику сборки мусора и как обширный справочный материал.


## Языковые машины

Forth

Smalltalk

[Smalltalk-80: The Language and its Implementation; Adele Goldberg and DavidRobson](http://stephane.ducasse.free.fr/FreeBooks/BlueBook/Bluebook.pdf)

Prolog

Lisp

Pascal

Lua

## Среды выполнения

Standard ML

[Appel A. W. A runtime system //Lisp and Symbolic Computation. – 1990. – Т. 3. – №. 4. – С. 343-380.](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.35.4846&rep=rep1&type=pdf)

Машинный код в системах с раздельной компиляцией

[Levine John R. Linkers and Loaders (The Morgan Kaufmann Series in Software Engineering and Programming)](http://www.staroceans.org/e-book/LinkersAndLoaders.pdf)

Книга раскрывает цель и ключевые особенности статического и динамического связывания, обычно нерассматриваемые в теоретических курсах.

[Stephen Kell Dominic P. Mulligan Peter Sewell, The Missing Link: Explaining ELF Static Linking, Semantically](https://www.cl.cam.ac.uk/~pes20/rems/papers/oopsla-elf-linking-2016.pdf)

В статье рассказывается про практические особенности процесса связывания с точки зрения теоретиков Computer Science. Объясняются особенности терминологии link-speak.
