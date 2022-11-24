# 数据结构

## 一、栈

```python
class Stack:

    def __init__(self):
        self.item = []
        self.count = 0

    def pop(self):
        if not self.is_empty():
            item = self.item.pop()
            self.count -= 1
            return item

    def push(self, item):
        self.item.insert(0, item)
        self.count += 1

    def is_empty(self):
        return self.item == []

    def size(self):
        return self.count
```



## 二、队列

```python
class Queue:

    def __init__(self):
        self.item = []

    def enqueue(self, item):
        self.item.insert(0, item)

    def dequeue(self):
        if not self.is_empty():
            return self.item.pop()

    def is_empty(self):
        return self.item == []

    def size(self):
        return len(self.item)


# 队列模拟栈
'''q1 = Queue()
a = [1,2,3,4]
for i in a:
    q1.enqueue(i)
q2 = Queue()
print(q1.item)
while not q1.isEmpty():
    print(q1.dequeue())
while q1.size()>0:
    while q1.size()>1:

        item = q1.dequeue()
        q2.enqueue(item)
    print(q1.dequeue())
    q1,q2=q2,q1'''

```

## 三、双端队列

```python
class Deque:

    def __init__(self):
        self.item = []

    def add_front(self, item):
        self.item.insert(0, item)

    def add_rear(self, item):
        self.item.append(item)

    def remove_front(self):
        if not self.is_empty():
            return self.item.pop()

    def remove_rear(self):
        if not self.is_empty():
            return self.item.pop(0)

    def is_empty(self):
        return self.item == []

    def size(self):
        return len(self.item)
```

## 四、链表

```python
class Node:
    def __init__(self, item=None):
        self.item = item
        self.next = None


class Link:

    def __init__(self):
        self._head = None
        self.count = 0

    def add(self, item):
        node = Node(item)
        node.next = self._head
        self._head = node
        self.count += 1

    def append(self, item):
        cur = self._head
        node = Node(item)
        pre = None
        if not self._head:
            self._head = node
        else:
            while cur is not None:
                pre = cur
                cur = cur.next
            pre.next = node
        self.count += 1

    def search(self, item):
        ex = False
        cur = self._head
        while cur is not None:
            if cur.item == item:
                ex = True
                break
            cur = cur.next
        return ex

    def insert(self, index, item):
        node = Node(item)
        cur = self._head
        ex = 0
        if index <= 0:
            self.add(item)
        elif index > self.size():
            self.append(item)
        else:
            while cur is not None:
                pre = cur
                cur = cur.next
                if ex == index - 1:
                    pre.next = node
                    node.next = cur
                    break
                ex += 1
        self.count += 1

    def remove(self, item):
        cur = self._head
        if not self.is_empty():
            if cur.item == item:
                self._head = cur.next
            else:
                while cur is not None:
                    pre = cur
                    cur = cur.next
                    if cur.item == item:
                        pre.next = cur.next
                        break
            self.count -= 1

    def reverse(self):
        if self.size() <= 1:
            return
        cur = self._head
        pre = None
        nt = cur.next
        while cur:
            cur.next = pre
            pre = cur
            cur = nt
            if cur is not None:
                nt = cur.next
        self._head = pre

    def travel(self):
        cur = self._head
        while cur is not None:
            print(cur.item,end=" ")
            cur = cur.next

    def is_empty(self):
        return self._head is None

    def size(self):
        return self.count
```

## 五、二叉树

```python
class TreeNode:

    def __init__(self, item):
        self.item = item
        self.left = None
        self.right = None

class Tree:

    def __init__(self):
        self.root = None

    def add(self, item):
        node = TreeNode(item)
        if self.root is None:
            self.root = node
            return
        queue = [self.root]

        while queue:
            cur = queue.pop(0)
            if cur.left is None:
                cur.left = node
                break
            else:
                queue.append(cur.left)
            if cur.right is None:
                cur.right = node
                break
            else:
                queue.append(cur.right)

    def travel(self):
        if self.root is None:
            return
        queue = [self.root]
        while queue:
            cur = queue.pop(0)
            print(cur.item,end=" ")
            if cur.left is not None:
                queue.append(cur.left)
            if cur.right is not None:
                queue.append(cur.right)

    def pre_travel(self,root):
        if root is None:
            return
        print(root.item,end=" ")
        self.pre_travel(root.left)
        self.pre_travel(root.right)

    def mid_travel(self,root):
        if root is None:
            return
        self.mid_travel(root.left)
        print(root.item, end=" ")
        self.mid_travel(root.right)

    def back_travel(self,root):
        if root is None:
            return
        self.back_travel(root.left)
        self.back_travel(root.right)
        print(root.item, end=" ")
```

# 排序

## 一、冒泡排序

```python
def sort(alist):
    for j in range(len(alist) - 1):
        for i in range(len(alist) - 1 - j):
            if alist[i] > alist[i + 1]:
                alist[i], alist[i + 1] = alist[i + 1], alist[i]
    return alist
```

## 二、选择排序

```python
def choice_sort(alist):
    for j in range(len(alist) - 1):
        max_index = 0
        for i in range(1, len(alist) - j):
            if alist[max_index] < alist[i]:
                max_index = i
        alist[max_index], alist[len(alist) - 1 - j] = alist[len(alist) - 1 - j], alist[max_index]
    return alist
```

## 三、插入排序

```python
def insert_sort(alist):
    for i in range(len(alist)):
        while i > 0:
            if alist[i] < alist[i - 1]:
                alist[i], alist[i - 1] = alist[i - 1], alist[i]
            i -= 1
    return alist
```

## 四、希尔排序

```python
def shell_sort(alist):
    gap=len(alist)//2
    while gap >=1:
        for i in range(gap,len(alist)):
            while i>0:
                if alist[i] < alist[i - gap]:
                    alist[i], alist[i - gap] = alist[i - gap], alist[i]
                    i-=gap
                else:
                    break
        gap //= 2
    return alist
```

