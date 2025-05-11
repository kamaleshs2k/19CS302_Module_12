# EX 57 C function to perfom push,pop and peek functions in Stack using Linked List.( store float data in stack)
## DATE: 11/05/2025
## AIM:
To write a C function to perfom push,pop and peek functions in Stack using Linked List.

## Algorithm
1.Define a structure Node with a float data type and a pointer to the next node.

2.Implement the push() function to insert a float value at the top of the stack (insert at the beginning of the linked list).

3.Implement the pop() function to remove the top element from the stack and return its value.

4.Implement the peek() function to view the top element without removing it.

5.Use the main() function to demonstrate push, pop, and peek operations.

## Program:
```
/*
function to perfom push,pop and peek functions in Stack using Linked List.( store float data in stack)

Developed by: Kamalesh S
RegisterNumber:  212223060108
*/
#include <stdio.h>
#include <stdlib.h>

struct Node {
    float data;
    struct Node* next;
};

void push(struct Node** top, float value)
{
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = *top;
    *top = newNode;
}

float pop(struct Node** top)
{
    if (*top == NULL)
    {
        printf("Stack underflow.\n");
        return -1;
    }
    struct Node* temp = *top;
    float poppedData = temp->data;
    *top = (*top)->next;
    free(temp);
    return poppedData;
}

float peek(struct Node* top)
{
    if (top == NULL)
    {
        printf("Stack is empty.\n");
        return -1;
    }
    return top->data;
}

int main()
{
    struct Node* stack = NULL;

    push(&stack, 10.5);
    push(&stack, 20.7);
    push(&stack, 30.9);
    
    printf("Top element (peek): %.2f\n", peek(stack));

    printf("Popped element: %.2f\n", pop(&stack));
    
    printf("Top element after pop (peek): %.2f\n", peek(stack));

    return 0;
}


```

## Output:

![image](https://github.com/user-attachments/assets/245df9d7-8106-4860-9fe8-a8499826f720)


## Result:
Thus the program was executed and the output was verified successfully.
