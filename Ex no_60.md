# EX 60 C function to find the peek element of the queue using linked list.
## DATE: 11/05/2025
## AIM:
To write a C function to find the peek element of the queue using linked list.

## Algorithm
1.Define a structure Node with a character data type and a pointer to the next node.

2.Implement a peek() function that takes the front of the queue as a parameter.

3.Inside peek(), check if the queue is empty by verifying if front is NULL.

4.If the queue is not empty, return the data of the front node.

5.If the queue is empty, print a message indicating that the queue is empty and return an appropriate value (e.g., '\0').

## Program:
```
/*
C function to find the peek element of the queue using linked list.

Developed by: Kamalesh S
RegisterNumber:  212223060108
*/
#include <stdio.h>
#include <stdlib.h>

struct Node {
    char data;
    struct Node* next;
};

char peek(struct Node* front)
{
    if (front == NULL)
    {
        printf("Queue is empty.\n");
        return '\0';  // Return a null character if the queue is empty
    }
    return front->data;  // Return the data at the front of the queue
}

int main()
{
    struct Node* front = NULL;
    struct Node* rear = NULL;

    // Sample queue (enqueue example)
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = 'A';
    newNode->next = NULL;
    front = rear = newNode;

    newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = 'B';
    newNode->next = NULL;
    rear->next = newNode;
    rear = newNode;

    // Peek element
    char frontElement = peek(front);
    if (frontElement != '\0') {
        printf("Front element of the queue: %c\n", frontElement);
    }

    return 0;
}

```

## Output:

![image](https://github.com/user-attachments/assets/ff73e6e2-049e-4dec-8b42-647e7f8c31cf)


## Result:
Thus the program was executed and the output was verified successfully.
