# Circular Queue

# Circular Queue interface

```Java
    public interface CircularQueue<E> extends Queue<E> {
        /**
         * Rotates the front element of the queue to the back of the queue.
         */
        void rotate();
    }
```

**This class has an advantage over the traditional LinkedQueue, because a call to Q.rotate() is implemented more efficiently than the combination of calls, Q.enqueue(Q.dequeue()), because no nodes are created, destroyed, or relinked by the implementation of a rotate operation on circularly linked list.**

**A circular queue is an excellent abstraction for applications in which elements are cyclically arranged, such as for multiplayer, turn based games, or round-robin scheduling of computiong process.**
