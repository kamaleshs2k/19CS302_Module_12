# EX 56 C function to display stack elements using Linked List.(store integer data in stack) .
## DATE:11/05/2025
## AIM:
To write a C function to display stack elements using Linked List.

## Algorithm
1.Define a structure Node with an integer data and a pointer to the next node.

2.Create a function push() to insert an integer element into the stack (insert at the beginning of the list).

3.Create a function display() to traverse the stack and print the elements.

4.Create a function pop() to remove the top element from the stack (remove from the beginning).

5.Use main() to manage the stack and perform operations like pushing, displaying, and popping.
## Program:
```
/*
C function to display stack elements using Linked List.(store integer data in stack) .

Developed by: Kamalesh S
RegisterNumber:  212223060108
*/
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

void push(struct Node** top, int value)
{
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = *top;
    *top = newNode;
}

void display(struct Node* top)
{
    struct Node* temp = top;
    if(temp == NULL)
    {
        printf("Stack is empty.\n");
        return;
    }
    while(temp != NULL)
    {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int pop(struct Node** top)
{
    if(*top == NULL)
    {
        printf("Stack underflow.\n");
        return -1;
    }
    struct Node* temp = *top;
    int poppedData = temp->data;
    *top = (*top)->next;
    free(temp);
    return poppedData;
}

int main()
{
    struct Node* stack = NULL;

    push(&stack, 10);
    push(&stack, 20);
    push(&stack, 30);
    
    printf("Stack elements: ");
    display(stack);

    printf("Popped element: %d\n", pop(&stack));
    
    printf("Stack after pop: ");
    display(stack);

    return 0;
}

```

## Output:

![image](https://github.com/user-attachments/assets/4f9cb880-1121-431e-825f-044c93b47c92)


## Result:
Thus the program was executed and the output was verified successfully.
