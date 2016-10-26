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

Таким образом, используйте Python 2, если у вас есть действитель веская причина, например: использование важной библиотеки, которая не портирована на Python 3, либо вы, как и я, абсолютный фанат Python 2.

Check out `Can I Use Python 3? <https://caniusepython3.com/>`_ to see if any
software you're depending on will block your adoption of Python 3.

`Further Reading <http://wiki.python.org/moin/Python2orPython3>`_

It is possible to `write code that works on Python 2.6, 2.7, and Python 3
<https://docs.python.org/3/howto/pyporting.html>`_. This
ranges from trivial to hard depending upon the kind of software
you are writing; if you're a beginner there are far more important things to
worry about.

Implementations
~~~~~~~~~~~~~~~

When people speak of *Python* they often mean not just the language but also
the CPython implementation. *Python* is actually a specification for a language
that can be implemented in many different ways.

CPython
-------

`CPython <http://www.python.org>`_ is the reference implementation of Python,
written in C. It compiles Python code to intermediate bytecode which is then
interpreted by a virtual machine. CPython provides the highest
level of compatibility with Python packages and C extension modules.

If you are writing open-source Python code and want to reach the widest possible
audience, targeting CPython is best. To use packages which rely on C extensions
to function, CPython is your only implementation option.

All versions of the Python language are implemented in C because CPython is the
reference implementation.

PyPy
----

`PyPy <http://pypy.org/>`_ is a Python interpreter implemented in a restricted
statically-typed subset of the Python language called RPython. The interpreter
features a just-in-time compiler and supports multiple back-ends (C, CLI, JVM).

PyPy aims for maximum compatibility with the reference CPython implementation
while improving performance.

If you are looking to increase performance of your Python code, it's
worth giving PyPy a try. On a suite of benchmarks, it's currently `over 5 times
faster than CPython <http://speed.pypy.org/>`_.

PyPy supports Python 2.7. PyPy3 [#pypy_ver]_, released in beta, targets Python 3.

Jython
------

`Jython <http://www.jython.org/>`_ is a Python implementation that compiles
Python code to Java bytecode which is then executed by the JVM (Java Virtual Machine).
Additionally, it is able to import and use any Java class like a Python
module.

If you need to interface with an existing Java codebase or have other reasons to
need to write Python code for the JVM, Jython is the best choice.

Jython currently supports up to Python 2.7. [#jython_ver]_

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
