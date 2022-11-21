# 数据结构

## 一、栈

```python

class Stack:

    def __init__(self):
        self.item=[]
        self.count=0

    def pop(self):
        if not self.isEmpty():
            item=self.item.pop()
            self.count-=1
            return item

    def push(self,item):
        self.item.insert(0,item)
        self.count+=1

    def isEmpty(self):
        return self.item==[]

    def size(self):
        return self.count


stack=Stack()
a = [i for i in range(5)]

for i in a:
    stack.push(i)


print(stack.size())
print(stack.item)
```



## 二、队列

```python

class Queue:

    def __init__(self):
        self.item = []

    def enqueue(self,item):
        self.item.insert(0,item)

    def dequeue(self):
        if not self.isEmpty():
            return self.item.pop()

    def isEmpty(self):
        return self.item == []

    def size(self):
        return len(self.item)

#队列模拟栈
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

    def addFront(self,item):
        self.item.insert(0,item)

    def addRear(self,item):
        self.item.append(item)

    def removeFront(self):
        if not self.isEmpty():
            return self.item.pop()

    def removeRear(self):
        if not self.isEmpty():
            return self.item.pop(0)

    def isEmpty(self):
        return self.item == []

    def size(self):
        return len(self.item)

```

## 四、链表

```python
# 链表
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
            while cur:
                pre = cur
                cur = cur.next
            pre.next = node
        self.count += 1

    def search(self, item):
        ex = False
        cur = self._head
        while cur:
            if cur.item==item:
                ex=True
                break
            cur=cur.next
        return ex

    def insert(self,pop,item):
        node=Node(item)
        cur = self._head
        ex=0
        if pop<=0:
            self.add(item)
        elif pop>self.size():
            self.append(item)
        else:
            while cur:
                pre=cur
                cur = cur.next
                if ex==pop-1:
                    pre.next=node
                    node.next=cur
                    break
                ex+=1
```

