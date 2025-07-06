
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
