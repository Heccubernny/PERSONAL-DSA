# List of Stack Implementations 
### 1
```python
# Python3 program to demonstrate working of LIFO
 
# Pushing element on the top of the stack
def stack_push(stack):
    for i in range(5):
        stack.append(i)
    return stack
  
# Popping element from the top of the stack
def stack_pop(stack):
    print("Pop :")
  
    for i in range(5):
        y = stack[-1]
        stack.pop()
        print(y)
    return stack
  
# Displaying element on the top of the stack
def stack_peek(stack):
    element = stack[-1]
    print("Element on stack top :", element)
  
# Searching element in the stack
def stack_search(stack, element):
    pos = -1
    co = 0
    while(len(stack) > 0):
        co+=1
        if(stack[-1] == element):
            pos = co
            break
        stack.pop()
  
    if (pos == -1):
        print( "Element not found")
    else:
        print("Element is found at position", pos)
 
stack = []
stack_push(stack) 
stack_pop(stack)
stack_push(stack)
stack_peek(stack) // Element on stack top : 4
stack_search(stack, 2) // Element is found at position: 3
stack_search(stack, 6) //Element not found
```
```txt
Complexity
Time Complexity: O(n)

Space complexity: O(n) 
```


### 2
#### Implementing Stack using Arrays:

```python
# Python program for implementation of stack
  
# import maxsize from sys module 
# Used to return -infinite when stack is empty
from sys import maxsize
  
# Function to create a stack. It initializes size of stack as 0
def createStack():
    stack = []
    return stack
  
# Stack is empty when stack size is 0
def isEmpty(stack):
    return len(stack) == 0
  
# Function to add an item to stack. It increases size by 1
def push(stack, item):
    stack.append(item)
    print(item + " pushed to stack ")
      
# Function to remove an item from stack. It decreases size by 1
def pop(stack):
    if (isEmpty(stack)):
        return str(-maxsize -1) # return minus infinite
      
    return stack.pop()
  
# Function to return the top from stack without removing it
def peek(stack):
    if (isEmpty(stack)):
        return str(-maxsize -1) # return minus infinite
    return stack[len(stack) - 1]
  
# Driver program to test above functions    
stack = createStack()
push(stack, str(10))
push(stack, str(20))
push(stack, str(30))
print(pop(stack) + " popped from stack")

```
```txt
output
10 pushed into stack
20 pushed into stack
30 pushed into stack
30 Popped from stack
Top element is : 20
Elements present in stack : 20 10 
```


### 3

#### Implementing Stack using Linked List:

```python
# Python program for linked list implementation of stack
  
# Class to represent a node
  
  
class StackNode:
  
    # Constructor to initialize a node
    def __init__(self, data):
        self.data = data
        self.next = None
  
  
class Stack:
  
    # Constructor to initialize the root of linked list
    def __init__(self):
        self.root = None
  
    def isEmpty(self):
        return True if self.root is None else False
  
    def push(self, data):
        newNode = StackNode(data)
        newNode.next = self.root
        self.root = newNode
        print ("% d pushed to stack" % (data))
  
    def pop(self):
        if (self.isEmpty()):
            return float("-inf")
        temp = self.root
        self.root = self.root.next
        popped = temp.data
        return popped
  
    def peek(self):
        if self.isEmpty():
            return float("-inf")
        return self.root.data
  
  
# Driver code
stack = Stack()
stack.push(10)
stack.push(20)
stack.push(30)
  
print ("% d popped from stack" % (stack.pop()))
print ("Top element is % d " % (stack.peek()))
```

```txt
10 pushed to stack
20 pushed to stack
30 pushed to stack
30 popped from stack
Top element is 20
Elements present in stack : 20 10 
```
