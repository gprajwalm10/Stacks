
# Stack Implementation using Linked List in Java

This Java program demonstrates a stack implementation using a singly linked list.

## Structure

### Outer Class: `StackLL`
- Contains the entire stack implementation within the `StackDS` class.

### Inner Class: `StackDS`

#### Static Nested Class: `Node`
- Represents a node in the linked list.
- Fields:
  - `int data`: Stores the value.
  - `Node next`: Points to the next node in the list.

#### Static Class: `Stack`
- Manages stack operations using the linked list.
- Fields:
  - `static Node head`: Points to the top of the stack.
- Methods:
  - `push(int data)`: Adds an element to the top of the stack.
  - `isEmpty()`: Checks if the stack is empty.
  - `pop()`: Removes and returns the top element of the stack.
  - `peek()`: Returns the top element without removing it.

### `main` Method
- Demonstrates the usage of the stack:
  1. Pushes elements `1`, `2`, `3`, and `4`.
  2. Pops and prints each element until the stack is empty.

## Execution Flow

1. `stack.push(1)` → Stack: 1
2. `stack.push(2)` → Stack: 2 → 1
3. `stack.push(3)` → Stack: 3 → 2 → 1
4. `stack.push(4)` → Stack: 4 → 3 → 2 → 1

Loop:
- Prints `4`, `3`, `2`, `1` (LIFO order), popping each after printing.

## Output
```
4
3
2
1
```

This shows the Last-In-First-Out (LIFO) behavior of the stack.

## Java Code

```java
public class StackLL {

    //stack using Linked List
    public class StackDS {
        private static class Node {
            int data;
            Node next;

            Node(int data) {
                this.data = data;
                next = null;
            }
        }

        static class Stack {
            public static Node head = null;

            public static void push(int data) {
                Node newNode = new Node(data);

                if(head == null) {
                    head = newNode;
                    return;
                }
                newNode.next = head;
                head = newNode;
            }

            public static boolean isEmpty() {
                return head == null;
            }

            public static int pop() {
                if(isEmpty()) {
                    return -1;
                }
                Node top = head;
                head = head.next;
                return top.data;
            }

            public static int peek() {
                if(isEmpty()) {
                    return -1;
                }
                Node top = head;
                return top.data;
            }
        }

        public static void main(String args[]) {
            Stack stack = new Stack();
            stack.push(1);
            stack.push(2);
            stack.push(3);
            stack.push(4);

            while(!stack.isEmpty()) {
                System.out.println(stack.peek());
                stack.pop();
            }
        }
    }
}
```

