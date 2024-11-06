# linked-list-operation
#include<stdio.h>
#include<stdlib.h>
struct node
{
    int data;
    struct node *next;
};
// Linked list traversal
void linkedlisttraversal(struct node *ptr)
{
    while(ptr!=NULL){
        printf("Element:%d\n",ptr->data);
        ptr=ptr->next;
    }

}
// Linked list insertion at first position
struct node *insertatfirst(struct node *head,int data){
    struct node *ptr=(struct node *)malloc(sizeof(struct node));
    ptr->data=data;
    ptr->next=head;
    return ptr;
}
// Linked list insert at index
struct node *insertAtIndex(struct node *head,int data , int index){
    struct node *ptr=(struct node *)malloc(sizeof(struct node));
    struct node *p=head;
    int i=0;
    while(i!=index-1){
        p=p->next;
        i++;
    }
    ptr->data=data;
    ptr->next=p->next;
    p->next=ptr;
    return head;

}
// linkedlist insertion at end
struct node *insertAtEnd(struct node *head,int data){
    struct node *ptr=(struct node *)malloc(sizeof(struct node));
    ptr->data=data;
    struct node *p=head;
    while(p->next!=NULL){
        p=p->next;
    }
    p->next=ptr;
    ptr->next=NULL;
    return head;
}
// linked list after a node
struct node *insertAfterNode(struct node *head, struct node *prevNode,int data){
    struct node *ptr=(struct node *)malloc(sizeof(struct node));
    ptr->data=data;
    ptr->next=prevNode->next;
    prevNode->next=ptr;

    return head;
}


int main()
{
    struct node *head;
    struct node *second;
    struct node *third;
    head=(struct node *)malloc(sizeof(struct node));
    second=(struct node *)malloc(sizeof(struct node));
    third=(struct node *)malloc(sizeof(struct node));
    head->data=7;
    head->next=second;

    second->data=11;
    second->next=third;

    third->data=66;
    third->next=NULL;


    // printf("Linked list before insertion\n"); 
    linkedlisttraversal(head);
    // head=insertatfirst(head,56);
    // linkedlisttraversal(head);
    // head=insertAtIndex(head,56,1);
    // head=insertAtEnd(head,56);
    // head=insertAfterNode(head,second,45);
    // printf("\nLinked list after insertion\n");
    // linkedlisttraversal(head);
}
