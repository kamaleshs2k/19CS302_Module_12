# EX 59 C functions to perform-enqueue, dequeue, peek, display in Queue using Linked List.(use character data in Queue).
## DATE:11/05/2025
## AIM:
To write a C functions to perform-enqueue, dequeue, peek, display in Queue using Linked List.

## Algorithm
1.Define a structure Node with a character data type and a pointer to the next node.

2.Implement the enqueue() function to insert a character at the end of the queue (insert at the rear of the linked list).

3.Implement the dequeue() function to remove a character from the front of the queue (remove the head node).

4.Implement the peek() function to view the character at the front of the queue without removing it.

5.Implement the display() function to traverse and display all elements from front to rear.

## Program:
```
/*
functions to perform-enqueue, dequeue, peek, display in Queue using Linked List.(use character data in Queue).

Developed by: Kamalesh S
RegisterNumber:  212223060108
*/
#include <stdio.h>
#include <stdlib.h>

struct Node {
    char data;
    struct Node* next;
};

void enqueue(struct Node** front, struct Node** rear, char value)
{
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;

    if (*rear == NULL)
    {
        *front = *rear = newNode;
        return;
    }

    (*rear)->next = newNode;
    *rear = newNode;
}

char dequeue(struct Node** front)
{
    if (*front == NULL)
    {
        printf("Queue underflow.\n");
        return '\0';
    }

    struct Node* temp = *front;
    char dequeuedData = temp->data;
    *front = (*front)->next;
    free(temp);
    return dequeuedData;
}

char peek(struct Node* front)
{
    if (front == NULL)
    {
        printf("Queue is empty.\n");
        return '\0';
    }
    return front->data;
}

void display(struct Node* front)
{
    if (front == NULL)
    {
        printf("Queue is empty.\n");
        return;
    }

    struct Node* temp = front;
    while (temp != NULL)
    {
        printf("%c ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main()
{
    struct Node* front = NULL;
    struct Node* rear = NULL;

    enqueue(&front, &rear, 'A');
    enqueue(&front, &rear, 'B');
    enqueue(&front, &rear, 'C');
    
    printf("Queue elements: ");
    display(front);

    printf("Dequeued element: %c\n", dequeue(&front));
    
    printf("Queue after dequeue: ");
    display(front);

    printf("Peek element: %c\n", peek(front));

    return 0;
}

```

## Output:

![image](https://github.com/user-attachments/assets/21436397-ee70-4a5c-bdbe-dbf4cc35792c)


## Result:
Thus the program was executed and the output was verified successfully.
