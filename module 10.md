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
    int data;
    struct Node *next;
 };
 void search(struct Node *head, int value) {
    struct Node *current = head;
    int position = 1;
    while (current != NULL) {
        if (current->data == value) {
            printf("Element %d found at position %d.\n", value, 
position);
            return;
        }
        current = current->next;
        position++;
    }
    printf("Element %d not found in the list.\n", value);
 }
 int main() {
    struct Node *head = NULL, *newNode, *temp;
    int n, value;
    printf("Enter number of elements in the linked list: ");
    scanf("%d", &n);
    for (int i = 0; i < n; i++) {
        newNode = (struct Node*)malloc(sizeof(struct Node));
        printf("Enter element %d: ", i + 1);
        scanf("%d", &newNode->data);
        newNode->next = NULL;
        if (head == NULL) {
            head = newNode;
        } else {
            temp = head;
            while (temp->next != NULL) {
                temp = temp->next;
            }
            temp->next = newNode;
        }
    }
    printf("Enter element to search: ");
    scanf("%d", &value);
    search(head, value);
    return 0;
 }
```

Output:

![image](https://github.com/user-attachments/assets/35047550-48e8-4845-9c35-835e34ff8a7d)



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
    int data;
    struct Node *next;
 };
 void insert(struct Node **head, int value) {
    struct Node newNode = (struct Node)malloc(sizeof(struct Node));
    struct Node *temp = *head;
    newNode->data = value;
    newNode->next = NULL;
    if (*head == NULL) {
        *head = newNode;
    } else {
        while (temp->next != NULL) {
            temp = temp->next;
        }
        temp->next = newNode;
    }
 }
 void display(struct Node *head) {
    struct Node *temp = head;
    if (temp == NULL) {
        printf("The list is empty.\n");
        return;
    }
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
 }
 int main() {
    struct Node *head = NULL;
    int n, value;
    printf("Enter number of elements to insert: ");
    scanf("%d", &n);
    for (int i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &value);
        insert(&head, value);
    }
     printf("Linked List: ");
     display(head);
     return 0;
 }
```
Output:
![image](https://github.com/user-attachments/assets/4e677b4d-aafe-46d2-b29a-b9d54c4c110d)


 
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
    struct Node *next;
    struct Node *prev;
 };
 void traverse(struct Node *head) {
    struct Node *temp = head;
     if (temp == NULL) {
        printf("The list is empty.\n");
        return;
    }
    printf("Traversing the doubly linked list: ");
    while (temp != NULL) {
        printf("%d <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
 }
 int main() {
    struct Node *head = NULL, *newNode, *temp;
    int n, value;
    printf("Enter the number of elements to insert: ");
    scanf("%d", &n);
    for (int i = 0; i < n; i++) {
        newNode = (struct Node*)malloc(sizeof(struct Node));
        printf("Enter element %d: ", i + 1);
        scanf("%d", &newNode->data);
        newNode->next = NULL;
        newNode->prev = NULL;
        if (head == NULL) {
            head = newNode;
        } else {
            temp = head;
            while (temp->next != NULL) {
                temp = temp->next;
            }
            temp->next = newNode;
            newNode->prev = temp;
        }
    }
    traverse(head);
    return 0;
 }
```

Output:
![image](https://github.com/user-attachments/assets/83d0ca35-0dc5-42d7-85b3-f2b8012b17d8)



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
    struct Node *next;
    struct Node *prev;
 };
 void insert(struct Node **head, int value) {
    struct Node newNode = (struct Node)malloc(sizeof(struct Node));
    struct Node *temp = *head;
    newNode->data = value;
    newNode->next = NULL;
    newNode->prev = NULL;
    if (*head == NULL) {
        *head = newNode;
        return;
    }
     while (temp->next != NULL) {
        temp = temp->next;
    }
    temp->next = newNode;
    newNode->prev = temp;
 }
 void display(struct Node *head) {
    struct Node *temp = head;
    if (temp == NULL) {
        printf("The list is empty.\n");
        return;
    }
    printf("Doubly Linked List: ");
    while (temp != NULL) {
        printf("%d <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
 }
 int main() {
    struct Node *head = NULL;
    int n, value;
    printf("Enter the number of elements to insert: ");
    scanf("%d", &n);
    for (int i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &value);
        insert(&head, value);
    }
    display(head);
    return 0;
 }
```

Output:
![image](https://github.com/user-attachments/assets/93caf48f-533d-4cd3-ab05-2eb2f08b36ed)



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
    struct Node *next;
 };
 void deleteNode(struct Node **head, int value) {
    if (*head == NULL) {
        printf("The list is empty.\n");
        return;
    }
    struct Node *temp = *head, *prev = NULL;
    if (temp != NULL && temp->data == value) {
        *head = temp->next;
        free(temp);
        printf("Element %d deleted from the list.\n", value);
        return;
    }
    while (temp != NULL && temp->data != value) {
        prev = temp;
        temp = temp->next;
    }
    if (temp == NULL) {
        printf("Element %d not found in the list.\n", value);
        return;
    }
    prev->next = temp->next;
    free(temp);
    printf("Element %d deleted from the list.\n", value);
 }
 void display(struct Node *head) {
    if (head == NULL) {
        printf("The list is empty.\n");
        return;
    }
    struct Node *temp = head;
    printf("Linked List: ");
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
 }
 int main() {
    struct Node *head = NULL;
    int n, value, deleteValue;
    printf("Enter the number of elements to insert: ");
    scanf("%d", &n);
    for (int i = 0; i < n; i++) {
        struct Node newNode = (struct Node)malloc(sizeof(struct Node));
        printf("Enter element %d: ", i + 1);
        scanf("%d", &newNode->data);
        newNode->next = head;
        head = newNode;
    }
    display(head);
    printf("Enter the element to delete: ");
    scanf("%d", &deleteValue);
    deleteNode(&head, deleteValue);
    display(head);
    return 0;
 }
```

Output:
![image](https://github.com/user-attachments/assets/db35226f-6691-48cf-a433-3f1187a3f3a7)






Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





