 Stack
Definition

A Stack is a linear data structure following LIFO (Last In, First Out) principle. It is used for function calls, recursion, and undo operations in software.
Time Complexity

    Push (Insert): O(1)
    Pop (Remove): O(1)
    Peek (Access Top Element): O(1)

Example in Python

python

stack = []  # Initialize a stack

stack.append(1)  # Push
stack.append(2)
print(stack.pop())  # Pop -> Output: 2

