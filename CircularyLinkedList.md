# Circulary Linked List
> Linked list are traditionally viewed as storing a sequence of items in a linear order, from first to last. Howeever, there are many applications in which data can be more naturally viewed as having a ___cylic order___, with well-defined neighboring relationships, but no fixed beginning or end.
> For example, many multiplayer games are turn-based, with player A taking a turn, then player B, then player C, and so on, but eventually back to player A again, and player B again, with the patter repeating. As another example, city buses and subways ofthen run on a continuous loop, makeing stops in a shceudled order, but with no designated first or last stop per se. 

# Implementation in Java
```java
    public static CircularlyLinedList<E> {
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

        //no head pointer is needed
        private Node<E> tail = null;
        private int size = 0;
        public CircularlyLinedList() {}
        public int size() { return size; }
        public boolean isEmpty() { return size == 0; }
        public E first() {
            if (isEmpty()) return null;
            return tail.getNext().getElement();
        }

        public E last() {
            if (isEmpty()) return nll;
            return tail.getElement();
        }

        public void rotate() {
            if (tail != null)
                tail = tail.getNext();
        }

        public void addFirst(E e) {
            if (size == 0)
                tail = new Node<>(e, null);
                tail.setNext(tail) 
            } else {
                Node<E> newest = new Node<>(e, tail.getNext());
                tail.setNext(newest);
            }
        }

        public void addLast(E e) {
            addFirst(e);
            tail = tail.getNext()
        }

        public E removeFirst() {
            if (isEmpty()) return null;
            Node<E> head = tail.getNext();
            if (head == tail) tail = null;
            else tail.setNext(head.getNext());
            size--;
            return head.getElement;
        }
    }
```

