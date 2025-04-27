EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    char data;
    struct Node* next;
};
void search(struct Node* head, char key) {
    struct Node* current = head;
    int position = 1;
    int found = 0;

    while (current != NULL) {
        if (current->data == key) {
            printf("Element '%c' found at position %d.\n", key, position);
            found = 1;
            break;
        }
        current = current->next;
        position++;
    }

    if (!found) {
        printf("Element '%c' not found in the linked list.\n", key);
    }
}
struct Node* createNode(char data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    if (!newNode) {
        printf("Memory allocation failed.\n");
        exit(0);
    }
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}
void append(struct Node** head_ref, char new_data) {
    struct Node* new_node = createNode(new_data);
    struct Node* last = *head_ref;

    if (*head_ref == NULL) {
        *head_ref = new_node;
        return;
    }

    while (last->next != NULL)
        last = last->next;

    last->next = new_node;
}
int main() {
    struct Node* head = NULL;
    int n, i;
    char data, key;

    printf("Enter the number of elements in the linked list: ");
    scanf("%d", &n);

    printf("Enter %d characters:\n", n);
    for (i = 0; i < n; i++) {
        scanf(" %c", &data);
        append(&head, data);
    }
    printf("Enter the character to search: ");
    scanf(" %c", &key);
    search(head, key);
    return 0;
}

```

Output:




![Screenshot 2025-04-27 200716](https://github.com/user-attachments/assets/8fd6ce8d-64f3-47e7-8bfb-1b182280bc92)

Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
Aim:
To write a C program to insert a node in a linked list.
Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    char data;
    struct Node* next;
};
void insert(struct Node** head_ref, char new_data) {
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    if (new_node == NULL) {
        printf("Memory allocation failed.\n");
        exit(0);
    }
    new_node->data = new_data;
    new_node->next = NULL;

    if (*head_ref == NULL) {
        *head_ref = new_node;
    } else {
        struct Node* last = *head_ref;
        while (last->next != NULL) {
            last = last->next;
        }
        last->next = new_node;
    }
}
void display(struct Node* head) {
    printf("Linked list elements: ");
    while (head != NULL) {
        printf("%c -> ", head->data);
        head = head->next;
    }
    printf("NULL\n");
}

// Step 4: Main function
int main() {
    struct Node* head = NULL;
    int n, i;
    char data;

    printf("Enter the number of nodes to insert: ");
    scanf("%d", &n);

    printf("Enter %d characters:\n", n);
    for (i = 0; i < n; i++) {
        scanf(" %c", &data);
        insert(&head, data);
    }
    display(head);
    return 0;
}
```

Output:

![Screenshot 2025-04-27 200906](https://github.com/user-attachments/assets/6caac77d-7af2-41d0-9d76-4ae526aca0c2)

 
Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
Aim:
To write a C program to traverse a doubly linked list.

Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
Program:
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node* prev;
    struct Node* next;
};
struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    if (newNode == NULL) {
        printf("Memory allocation failed.\n");
        exit(0);
    }
    newNode->data = data;
    newNode->prev = NULL;
    newNode->next = NULL;
    return newNode;
}
void append(struct Node** head_ref, int new_data) {
    struct Node* new_node = createNode(new_data);
    struct Node* last = *head_ref;

    if (*head_ref == NULL) {
        *head_ref = new_node;
        return;
    }
    while (last->next != NULL) {
        last = last->next;
    }
    last->next = new_node;
    new_node->prev = last;
}
void traverse(struct Node* head) {
    struct Node* temp = head;
    printf("Doubly Linked List elements:\n");
    while (temp != NULL) {
        printf("%d <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}
int main() {
    struct Node* head = NULL;
    int n, i, data;

    printf("Enter the number of nodes: ");
    scanf("%d", &n);

    printf("Enter %d integers:\n", n);
    for (i = 0; i < n; i++) {
        scanf("%d", &data);
        append(&head, data);
    }
    traverse(head);
    return 0;
}

```
Output:


![Screenshot 2025-04-27 201135](https://github.com/user-attachments/assets/1f4f6286-7372-406d-bb89-642a0d6bc87c)


Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
Aim:
To write a C program to insert an element in doubly linked list

Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node* prev;
    struct Node* next;
};
struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    if (newNode == NULL) {
        printf("Memory allocation failed.\n");
        exit(0);
    }
    newNode->data = data;
    newNode->prev = NULL;
    newNode->next = NULL;
    return newNode;
}
void insertEnd(struct Node** head_ref, int new_data) {
    struct Node* new_node = createNode(new_data);

    if (*head_ref == NULL) {
        *head_ref = new_node;
        return;
    }
    struct Node* last = *head_ref;
    while (last->next != NULL) {
        last = last->next;
    }
    last->next = new_node;
    new_node->prev = last;
}
void display(struct Node* head) {
    struct Node* temp = head;
    printf("Doubly Linked List elements:\n");
    while (temp != NULL) {
        printf("%d <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}
int main() {
    struct Node* head = NULL;
    int n, i, data;

    printf("Enter the number of nodes to insert: ");
    scanf("%d", &n);

    printf("Enter %d integer values:\n", n);
    for (i = 0; i < n; i++) {
        scanf("%d", &data);
        insertEnd(&head, data);
    }

    display(head);

    return 0;
}

```
Output:


![Screenshot 2025-04-27 201346](https://github.com/user-attachments/assets/9e994f81-8384-4856-af77-f801d1d0546d)


Result:
Thus, the program to insert an element in doubly linked list is verified successfully.




EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST




Aim:
To write a C function that deletes a given element from a linked list.

Algorithm:
1.	Check if the Linked List is Empty:
o	If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
2.	Traverse the Linked List:
o	Start from the head node and iterate through the list to find the node that contains the given element (data).
3.	Handle Deletion of the First Node:
o	If the element to be deleted is found in the head node:
	Update the head of the linked list to point to the next node (i.e., head = head->next).
	Free the memory allocated to the node to be deleted.
	Exit the function.
4.	Traverse and Delete from the Middle or End:
o	If the element is not in the head node, continue traversing the list by checking each node’s next pointer.
o	When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next).
o	Free the memory allocated to the node to be deleted.
5.	Handle the Case when the Element is Not Found:
o	If the element is not found in any node, print a message indicating the element is not present in the list.
6.	End the Function.


Program:

```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node* next;
};
void deleteElement(struct Node** head_ref, int key) {
    if (*head_ref == NULL) {
        printf("The list is empty. No elements to delete.\n");
        return;
    }
    struct Node* temp = *head_ref;
    struct Node* prev = NULL;
    if (temp != NULL && temp->data == key) {
        *head_ref = temp->next;
        free(temp);
        printf("Element %d deleted successfully.\n", key);
        return;
    }
    while (temp != NULL && temp->data != key) {
        prev = temp;
        temp = temp->next;
    }
    if (temp == NULL) {
        printf("Element %d not found in the list.\n", key);
        return;
    }
    prev->next = temp->next;
    free(temp);
    printf("Element %d deleted successfully.\n", key);
}
void append(struct Node** head_ref, int new_data) {
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    struct Node* last = *head_ref;

    new_node->data = new_data;
    new_node->next = NULL;

    if (*head_ref == NULL) {
        *head_ref = new_node;
        return;
    }

    while (last->next != NULL) {
        last = last->next;
    }

    last->next = new_node;
}
void display(struct Node* head) {
    struct Node* temp = head;
    if (temp == NULL) {
        printf("List is empty.\n");
        return;
    }
    printf("Linked List elements: ");
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}
int main() {
    struct Node* head = NULL;
    append(&head, 10);
    append(&head, 20);
    append(&head, 30);
    append(&head, 40);
    printf("Initial List: \n");
    display(head);
    int key;
    printf("Enter the element to delete: ");
    scanf("%d", &key);
    deleteElement(&head, key);
    printf("Updated List: \n");
    display(head);

    return 0;
}

```

Output:




![Screenshot 2025-04-27 201646](https://github.com/user-attachments/assets/b507f8a0-7750-4481-8948-467f7b5f45b9)



Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





