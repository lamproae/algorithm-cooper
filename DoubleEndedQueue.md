# Double Ended Queue

**Double Ended Queue is a structure that suports insertion and deletion at both the front and the back of the queue.**

**The deque abstract data type is more general that both the stack and the queue ADTs. The extra generality can be suseful in some applications. For example, we described a restaurant using a queue to maintain a waitlist. Occasionally, the first persion might be removed from the queue only to find that a table was not available; typically, the restaurant will reinsert the person at the first position in the queue. It may also be that a customer at the end of the queue may grow impatient and leave the restauratn.**

# Required Interface

```Java
    addFirst(e);
    addLast(e);
    removeFirst();
    removeLast():

    first();
    last();
    size();
    isEmpty();
```

# Deque interface in Java

```Java
    public interface Deque<E> {
        int size();
        boolean isEmpty();
        E first();
        E last();
        void addFirst();
        void addLast();
        E removeFirst();
        E removeLast();
    }
```

# Implementing a Deque

**We can implement the deque ADT efficiently using either an array or a linked list for storing elements.**

##Implementing a Deque with a Circular Array

**If using an array, we recommand a representation similar to the ArrayQueue class, treating the array in circular fashin and storing the index of the first element and the current size of the deque as fields; the index of the last element can be calculated, as needed, using modular arithmetric.**

**One extra concern is avoiding use of negative value with the modulo operator. When removing the first element, the front index is advanced in circular fashin, with the assigment f = (f + 1) % N. But when an element is inserted at the front, the first index must effectively be decremented in circular fashion and it is a mistake to assign f = (f - 1) % N. The problem is that when f is 0, the goal should be to "decrement" it to the other end of the arrary, and thus ot index N-1. Howerver, a calculation such as -1 % 10 in java results in the value -1. A standard way to decrement and index circularly is instead to assign f = (f - 1 + N) % N. Add the additional term of N before the modulus is calculted assures that the result is a positive value.**

# Implemention a Dque with a Doubly Linked List

**Because the deque requires insertion and removal at both ends, a doubly linked list is most appropriate for implementaing all operations efficiently.**


