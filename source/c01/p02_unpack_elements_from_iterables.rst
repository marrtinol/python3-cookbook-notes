====================================
1.2 解压任意长度的可迭代对象给多个变量 √
====================================


Python 中的星号变量可以代表任意长度的列表. 例如:


.. code-block:: python

    >>> record = ('Carl', 'carl@example.com', '346-253-1235', '534-546-3245')
    >>> name, email, *phone_numbers = record
    >>> name
    'Carl'
    >>> email
    'carl@example.com'
    >>> phone_numbers
    ['346-253-1235', '534-546-3245']


上面解压出的 ``phone_numbers`` 变量永远是列表类型, 不管其中的元素数量是多少 (包括 0 个). 例如:

.. code-block:: python

    >>> record = ('Carl', 'carl@example.com')
    >>> name, email, *phone_numbers = record
    >>> phone_numbers
    []



使用星号表达式可以很容易地将一个列表分割成前后两部分, 这跟 Haskell
中的语法很像, 例如:

.. code-block:: python

    >>> items = [1, 2, 3, 4, 5, 6, 7]
    >>> head, *tail = items
    >>> head
    1
    >>> tail
    [2, 3, 4, 5, 6, 7]

很容易实现一个递归算法, 例如:

.. code-block:: python

    >>> def sum(items):
    ...     head, *tail = items
    ...     return head + sum(tail) if tail else head
    ...
    >>> sum(items)
    28

**Warning**: 由于 Python 对递归没有优化, 以上递归算法是低效的.

附带一个 Haskell 中递归版本的累加算法:

.. code-block:: haskell

    sum :: (Num a) => [a] -> a
    sum (x:xs) = x + sum xs
    sum [] = 0


尾递归版本的累加算法:

.. code-block:: haskel

    sum :: (Num a) => [a] -> a -> a
    sum (x:xs) total = sum xs x + total
    sum [] total = total


完全是规则式的, 很简洁很清楚有木有.


--------------

Last update: Jul 8, 2017
