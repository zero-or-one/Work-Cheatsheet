Linked List
Definition

A Linked List is a linear data structure where each element (node) points to the next. It is useful for dynamic memory allocation where array resizing is expensive.
Types:

    Singly Linked List: Nodes have a single pointer to the next node.
    Doubly Linked List: Nodes have pointers to both the next and the previous nodes.

Time Complexity

    Access: O(n)
    Search: O(n)
    Insertion/Deletion (Head or Tail): O(1)

Example in Python

python

class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    def append(self, data):
        new_node = Node(data)
        if not self.head:
            self.head = new_node
        else:
            temp = self.head
            while temp.next:
                temp = temp.next
            temp.next = new_node

# Usage:
ll = LinkedList()
ll.append(1)
ll.append(2)
ll.append(3)