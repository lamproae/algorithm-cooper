# Lined list
** 
A linked list, in its simplest form, is a collection of nodes that collectively form a linear sequence. In a singly linked list, each node stores a reference to an object that is an element of the sequence, as well as a reference to the next node of the list. **

# Operation
** Insert a new element at the beginning of a singly linked list**
``` Pseudo code
    Algorithm addFirst(e):
        newest = Node(e)
        newest.next = head;
        head = newest;
        size += 1;
```

** Insert a new element at the tail of a singly linked list**
```Pseduo code
    Algorithm addLast(e):
        newest = Node(e);
        newest.next = null;
        tail.next = newest;
        tail = newest;
        size += 1;
```
** Remove an element from a singly linked list
```Pseduo code
    Algorithm removeFirst():
        if head == null then
            the list is empty.
        head = head.next;
        size -= 1;
```

**We cannot easily delete the last node of a singly lined list. Even if we maintain a reference directly to the last node of the list, we must beable to access the node before the last node in order to remove the last node. But we cannot reach the node before the tail by following next links from the tail. ___ The only way to access this node is to start from the head of the list and search all the way through the list___. But such a sequence of link-hopping operations could take a long time. This is why ___dboule linked list___ is needed.**

**Supported Interfaces:**
```c 
    size()
    isEmpty()
    first()
    last()
    addFirst()
    addLast()
    removeFirst()
```
**

**Java implementation**
```Java
    *SingleLinkedList.java*
    public static SinglyLinedList<E> {
        private static class Node<E> {
            private E element;
            private Node<E> next;
            public Node(E e, Node<e> n) {
                element = e;
                next = n;
            }

            public E getElement() { return element; }
            public Node<e> getNext() { return next; }
            public void setNext(Node<E> n) { next = n; }
        }

        private Node<E> head = null;
        private Node<E> tail = null;
        private int size = 0;
        public SinglyLinedList() {}
        public int size() { return size; }
        public boolean isEmpty() { return size == 0; }
        public E first() {
            if (isEmpty()) return null;
            return head.getElement();
        }

        public E last() {
            if (isEmpty()) return nll;
            return tail.getElement();
        }

        public void addFirst(E e) {
            head = new Node<>(e, head);
            if (size == 0)
                tail = head;
            size++;
        }

        public void addLast(E e) {
            Node<E> newest = new Node<>(e, null);
            if (isEmpty())
                head = newest;
            else
                tail.setNext(newest);
            tail = newest;
            size++;
        }

        public E removeFirst() {
            if (isEmpty()) return null;
            E answer = head.getElement();
            head = head.getNext();
            size--;
            if (size == 0)
                tail = null;
            return answer;
        }
    }
```
