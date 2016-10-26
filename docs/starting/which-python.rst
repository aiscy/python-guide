Выбор версии интерпретатора
======================

.. _which-python:

The State of Python (2 vs 3)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Во время выбора интерпретатора всегда встает один вопрос:
"Какую версию Python мне выбрать: 2 или 3"?
И ответ на него вовсе не столь очевиден, как может показаться.


Вот несколько ключевых моментов:

1. Python 2.7 был стандартом в течении *длительного* времени.
2. В Python 3 были внесены существенные изменения, понравившиеся далеко не всем.
3. Python 2.7 будет получать исправления критических уязвимостей вплоть до 2020 [#pep373_eol]_.
4. Python 3 непрерывно развивается, так же, как и Python 2 в прошлом.

Итак, теперь вы понимаете, почему это непростой выбор.


Рекомендации
~~~~~~~~~~~~~~~

Скажу прямо:


**Выбирайте Python 3, если...**

- Вам все равно.
- Вам нравится Python 3.
- Не видете разницы между 2 и 3 версией.
- Не знаете что выбрать.
- Вы не сопротивляетесь переменам.

**Или Python 2, если...**

- Вам нравится Python 2 и не нравится путь развития Python 3.
- Для вас важно, что синтаксис языка и его среда выполнения никогда не изменятся.
- Этого требует программное обеспечение, от которого вы зависите.


И все же.... 3?
~~~~~~~~~

Если вы все еще не смогли определиться с версией интерпретатора,
то в таком случае я советую остановиться на последней версии Python 3.x, поскольку каждый релиз приносит новые возможности, улучшение существующих библиотек и исправление ошибок. Прогресс неумолим.

Таким образом, используйте Python 2, если у вас есть действительно веская причина, например: использование важной библиотеки, которая не портирована на Python 3, либо вы, как и я, абсолютный фанат Python 2.

На сайте `Can I Use Python 3? <https://caniusepython3.com/>`_ вы можете проверить, поддерживает ли нужная вам библиотека Python 3.

`Подробнее о различиях между 2 и 3 версией <http://wiki.python.org/moin/Python2orPython3>`_

Так же стоит упомянуть о возможности `писать код, который будет совместим с 2.6, 2.7, и 3.x
<https://docs.python.org/3/howto/pyporting.html>`_. Усилия, которые необходимо приложить для обеспечения совместимости, варьируются от
типа программного обеспечения, которое вы пишите.
Если вы новичок, то есть множество более важных вещей, о которых следует беспокоиться.

Различные реализации интерпретатора
~~~~~~~~~~~~~~~

Когда кто-то говорит о *Python*,  обычно подразумевается не только сам язык, но и его реализация 
на интерпретаторе CPython. *Python* это скорее спецификация языка, которая может быть реализована множеством способов.

CPython
-------

`CPython <http://www.python.org>`_ является эталонной реализацией языка Python,
интерпретатор написан на C. Он компилирует исходный код программы в промежуточный байт-код, который затем интерпретируется виртуальной машиной. CPython обеспечивает высочайшую совместимость с Python-пакетами и расширениями, написанными на C.

Если вы пишите программу с открытым исходным кодом и хотите охватить максимально широкую аудиторию, то CPython будет лучшим выбором. Если необходимо использовать библиотеки, написанные на C, то CPython является единственным вариантом.

Все версии языка Python реализованы на C, потому что CPython является эталонной реализацией.

PyPy
----

`PyPy <http://pypy.org/>`_ это интерпретатор Python, реализованный в ограниченном
статически типизированное подмножестве языка Python - RPython. Из особенностей стоит отметить JIT компиляцию и поддержку множества бэкендов (C, CLI, JVM).

PyPy стремится к максимальной совместимости с CPython, ускорив при этом выполнение кода.

Если вы ищете способ увеличить производительность вашего кода, то стоит попробовать PyPy. Основываясь на показаниях бенчмарков, он примерно  `5 раз быстрее, чем CPython <http://speed.pypy.org/>`_.

PyPy на данный момент поддерживает Python 2.7. PyPy3 [#pypy_ver]_, нацелен на Python 3, но пока находится в бете.

Jython
------

`Jython <http://www.jython.org/>`_ это реализация Python, которая компилирует
Python код в байт-код Java, который затем выполняет JVM (Java Virtual Machine).
Кроме того, есть возможность импортировать и использовать любой Java-класс, как модуль языка Python.

Если вам нужно взаимодействовать с уже существующим кодом Java, или есть другие причины писать Python код для JVM, то Jython будет хорошим выбором.
Jython на текущий момент поддерживает версию Python 2.7. [#jython_ver]_

IronPython
----------

`IronPython <http://ironpython.net/>`_  is an implementation of Python for the .NET
framework. It can use both Python and .NET framework libraries, and can also
expose Python code to other languages in the .NET framework.

`Python Tools for Visual Studio <http://ironpython.net/tools/>`_ integrates
IronPython directly into the Visual Studio development environment, making it
an ideal choice for Windows developers.

IronPython supports Python 2.7. [#iron_ver]_

PythonNet
---------

`Python for .NET <http://pythonnet.github.io/>`_ is a package which
provides near seamless integration of a natively installed Python
installation with the .NET Common Language Runtime (CLR).  This is the
inverse approach to that taken by IronPython (see above), to which it
is more complementary than competing with.

In conjunction with Mono, PythonNet enables native Python
installations on non-Windows operating systems, such as OS X and
Linux, to operate within the .NET framework.  It can be run in
addition to IronPython without conflict.

PythonNet supports from Python 2.3 up to Python 2.7. [#pythonnet_ver]_

.. [#pypy_ver] http://pypy.org/compat.html

.. [#jython_ver] https://hg.python.org/jython/file/412a8f9445f7/NEWS

.. [#iron_ver] http://ironpython.codeplex.com/releases/view/81726

.. [#pythonnet_ver] http://pythonnet.github.io/readme.html

.. [#pep373_eol] https://www.python.org/dev/peps/pep-0373/#id2
