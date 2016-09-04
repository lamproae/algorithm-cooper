# Queue 
**Queue is a collection of objects that are inserted and removed according to the first-in,first-out(FIFO) principle. That is, elements can be inserted at any time, but only the element that has been in the queue the longest can be next removed.**

# required Interface

``` Java
    enqueue(e)
    dequeue()

    first()
    size()
    isEmpty()
```

# Queue definition

```Java
    public interface Queue<E> {
        int size();
        boolean isEmpty();
        void enqueue();
        E first();
        E dequeue();
```

# java.util.Queue

# Array-Based Queue Implementation

```Java
    public class ArrayQueue<E> implements Queue<E> {
        private E[] data;
        private int f = 0;  //index of the front element
        private int sz = 0; // current number of elements

        public ArrayQueue() { this.(CAPACITY); }
        public ArrayQueue(int capacity) {
            data = (E[]) new Object[capacity];
        }

        public int size() { return sz; }

        public boolean isEmpty() { reutrn (sz == 0); }

        public void enqueue(E e) throws IllegalStateException {
            if (sz = data.length) throw new IllegalStateException("Queue is full");
            int avail = (f+sz) % data.length;
            data[avail] = e;
            sz++;
        }

        public E first() {
            if (isEmpty()) return null;
            return data[f];
        }

        public E dequeue() {
            if (isEmpty()) return null;

            E answer = data[f];
            data[f] = null;
            f = (f+1)%data.length;
            size--;
            return answer;
        }
    }
```

# Implementing a Queue with a Singly Linked List

```Java
    public class LinkedQueue<E> implements Queue<E> {
        private SinglyLinkedList<E> list = new SinglyLinkedList<>();
        public LinkedQueue() {}
        public int size() { return list.size(); }
        public boolean isEmpty() { return list.isEmpty(); }
        public void enqueue(E element) { list.addLast(element); }
        public E first() { return list.first(); }
        public E dequeue { return list.removeFirst(); } 
    }
```
