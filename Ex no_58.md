# EX 58 C Function to display queue elements using Linked List.(use integer data in the queue)
## DATE: 11/05/2025
## AIM:
To write a C Function to display queue elements using Linked List.

## Algorithm
1.Define a structure Node with an integer data type and a pointer to the next node.

2.Create a enqueue() function to add an integer element to the end of the queue (add a node to the linked list).

3.Create a dequeue() function to remove an integer element from the front of the queue (remove the head node of the list).

4.Create a display() function to traverse the queue and print all elements.

5.Use main() to manage the queue and perform operations like enqueue, dequeue, and display.
## Program:
```
/*
C Function to display queue elements using Linked List.(use integer data in the queue)

Developed by: Kamalesh S
RegisterNumber:  212223060108
*/
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

void enqueue(struct Node** front, struct Node** rear, int value)
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

int dequeue(struct Node** front)
{
    if (*front == NULL)
    {
        printf("Queue underflow.\n");
        return -1;
    }

    struct Node* temp = *front;
    int dequeuedData = temp->data;
    *front = (*front)->next;
    free(temp);
    return dequeuedData;
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
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main()
{
    struct Node* front = NULL;
    struct Node* rear = NULL;

    enqueue(&front, &rear, 10);
    enqueue(&front, &rear, 20);
    enqueue(&front, &rear, 30);
    
    printf("Queue elements: ");
    display(front);

    printf("Dequeued element: %d\n", dequeue(&front));
    
    printf("Queue after dequeue: ");
    display(front);

    return 0;
}


```

## Output:

![image](https://github.com/user-attachments/assets/71615d9f-9d4b-4c77-9efe-6bca543b90e8)


## Result:
Thus the program was executed and the output was verified successfully.
