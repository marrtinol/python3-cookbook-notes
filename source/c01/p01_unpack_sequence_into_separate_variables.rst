================================
1.1 解压序列赋值给多个变量
================================


任何的序列(或者是可迭代对象)可以通过一个简单的赋值语句解压并赋值给多个变量. 唯一的前提就是变量的数量必须跟序列元素的数量是一样的. 可迭代对象包括列表, 元组, 字符串, 文件对象, 迭代器和生成器.

代码示例：

.. code-block:: python

    >>> p = (1, 2)
    >>> x, y = p
    >>> x
    1
    >>> y
    2
    >>> p = {3, 4}
    >>> x, y = p
    >>> x
    3
    >>> y
    4
    >>> p = [5, 6]
    >>> x, y = p
    >>> x
    5
    >>> y
    6
    >>> p = { 'a': 'A', 'b': 'B'}
    >>> x, y = p
    >>> x
    'a'
    >>> y
    'b'
    >>> s = 'Hello'
    >>> a, b, c, d, e = s
    >>> a
    'H'

甚至对于更深的层级也可以提取, 只要变量也使用同样的层级结构, 例如:

.. code-block:: python

    >>> data = [ 'ACME', 50, 91.1, (2012, 12, 21) ]
    >>> name, shares, price, date = data
    >>> name
    'ACME'
    >>> date
    (2012, 12, 21)
    >>> name, shares, price, (year, mon, day) = data
    >>> year
    2012
    >>> mon
    12
    >>> day
    21


如果只想提取一部分值, 可以使用任意变量名去占位, 通常使用 ``_``. 例如:


.. code-block:: python

    >>> data = [ 'Hello', 'Mike', 'Welcome', 'to', 'Python world']
    >>> _, name, _, _, addr = data
    >>> name
    'Mike'
    >>> addr
    'Python world'

``_`` 是不是跟 Mathematica 中的不命名匹配很像, 哈哈.


--------------

Last update: Jul 8, 2017
