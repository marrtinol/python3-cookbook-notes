================================
1.3 保留最后 N 个元素 √
================================


``collections`` 模块中的 ``deque`` 类用于生成队列。
使用 ``deque(maxlen=N)`` 构造函数会新建一个固定大小的队列。当新的元素加入并且这个队列已满的时候，最老的元素会自动被移除掉。

代码示例：

.. code-block:: python

    >>> from collections import deque
    >>> q = deque(maxlen=3)
    >>> q.append(1)
    >>> q.append(2)
    >>> q.append(3)
    >>> q
    deque([1, 2, 3], maxlen=3)
    >>> q.append(4)
    >>> q
    deque([2, 3, 4], maxlen=3)
    >>> q.append(5)
    >>> q
    deque([3, 4, 5], maxlen=3)


更一般的， ``deque`` 类可以被用在任何你只需要一个简单队列数据结构的场合。如果你不设置最大队列大小，那么就会得到一个无限大小队列，你可以在队列的两端执行添加和弹出元素的操作。

代码示例：

.. code-block:: python

    >>> q = deque()
    >>> q.append(1)
    >>> q.append(2)
    >>> q.append(3)
    >>> q
    deque([1, 2, 3])
    >>> q.appendleft(4)
    >>> q
    deque([4, 1, 2, 3])
    >>> q.pop()
    3
    >>> q
    deque([4, 1, 2])
    >>> q.popleft()
    4

在队列两端插入或删除元素时间复杂度都是 ``O(1)`` ，而在列表的开头插入或删除元素的时间复杂度为 ``O(N)`` 。
