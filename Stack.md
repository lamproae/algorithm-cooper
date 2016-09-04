# Stack

**A stack is a collection of objects that are inserted and removed according to the last-in,first-out(LIFO) principle**

# Stack is a fundamental data structure. It is used in many application, including the following.

1. Internet Web browsers store the address of recently visited sites on a stack. Each time a user visits a new site, that site's address is "pushed" onto the stack of addresses. The browser then allows the user to "pop" back to previously visited sites using the "back" button.
2. Text editors usually provide an "undo" mechanism that cancels recent editing operations and reverts to former states of a document. This undo operation can be accomplished by keeping text changes in a stack.

# Required Interface

```Java
    push(e);
    pop(); 
    top();
    size();
    isEmpty();
```

# java.util.Statck

# Java implementation Stack Interface

```Java
    public interface Stack<E> {
        int size();
        boolean isEmpty();
        void push(E e);
        E top();
        E pop():
    }

```

# A simple Array-Based Stack

```Java
    public class ArrayStack<E> implements Stack<E> {
        public static final int CAPACITY = 1000;
        private E[] data;
        private int t = -1;

        public ArrayStack() { this(CAPACITY); }
        public ArrayStack(int capicity) {
            data = (E[]) new Object[capicity];
        }

        public int size() { return (t + 1); }
        public boolean isEmpty { return (t == -1); }

        public void push(E e) throws ILLegalStateExecption {
            if (size() == data.length) throw new ILLegalStateExecption("Stack is full");
            data[++t] = e;
        } 

        public E top() {
            if (isEmpty()) return null;
            return data[t];
        }

        public E pop() {
            if (isEmpty()) return null;
            E answer = data[t];
            data[t] = null;
            t--;
            return answer;
        }
    }
```
**The array implemenation of a stack is simple and efficient. Nevertheless, this implementation has one negtaive aspect --- it relies on a fixed-capacity array, which limits the ultimate size of the stack.**

# Implementing a Stack with a Singly Linked List

**When designing a Stack with a Singly Linked List, we need to decide if the top of the stack is at the front or back of the list. There is clearly a best choice here, however, since we can insert and delete elements in constant time only at the front. With the top of the stack stored at the front of the list, all methods execute in constant time.**


## The Adapter Pattern

**The ___Adapter___ design patter applies to any context where we effectively want to modify an existing class so that its methods match those of a related, but different, class or interface. One general way to apply the adapter patthern is to define a new class in such a way that it contains an instance of the existing class as a hidden filed, and then to implement each method of the new class useing methods of this hidden instance variable. By applying the adapter pattern in this way, we have created a new class that performs some of the same functions as an existing class, but repackaged in a more convenient way.**

```Java
    public class LinkedStack<E> implements Stack<E> {
        private SinglyLinkedList<E> list = new SinglyLinkedList<>();
        public LinkedStack() {}
        public int size() { return list.size(); }
        public boolean isEmpty() { return list.isEmpty(); }
        public void push(E element) { list.addFirst(element); }
        public E top() { return list.first(); }
        public E pop() { return list.removeFirst(); }
    }
```

