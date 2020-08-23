---
title: CopyOnWriteArrayList分析
date: 2020-07-08 21:18:22
tags:
categories:
- java
---

- **读写分离**

1. 写操作是在一个复制数组上进行的，读操作是在原数组上进行的。读写分离，互不影响。
2. 写操作会加锁，防止并发写入时导致数据丢失。
3. 写操作结束后会把原数组的引用指向该复制数组。

```java
// 写
public boolean add(E e) {
    final ReentrantLock lock = this.lock;
    lock.lock();
    try {
        Object[] elements = getArray();
        int len = elements.length;
        Object[] newElements = Arrays.copyOf(elements, len + 1);
        newElements[len] = e;
        setArray(newElements);
        return true;
    } finally {
        lock.unlock();
    }
}

final void setArray(Object[] a) {
    array = a;
}

// 读
@SuppressWarnings("unchecked")
private E get(Object[] a, int index) {
    return (E) a[index];
}

```

- **适用场景**

    - **优点**：
    
      在写的同时允许读操作，读操作的性能得到了极大的提升，比较适合读多写少的场景。
    
    - **缺点**：
        - 内存占用：写操作需要复制一个新的数组，导致内存占用是原来的两倍多。
        - 数据不一致：不能实时读到最新的数据，会出现读写同时发生的时候部分数据还未被同步到读数组。
        
    所以CopyOnWriteArrayList不适合内存敏感和对实时性要求很高的场景。

    