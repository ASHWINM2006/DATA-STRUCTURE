#include <stdio.h>
#include <stdlib.h>
#include <string.h>

struct node {
  int data;
  struct node *next;
  struct node *prev;
};

void create(struct node **head, int n) {
  struct node *nn;
  nn = (struct node *)malloc(sizeof(struct node));
  nn->data = n;
  nn->prev = NULL;
  nn->next = NULL;
  if (*head == NULL) {
    *head = nn;
  } else {
    nn->next = *head;
    *head = nn;
  }
}

void display(struct node *head) {
  struct node *temp = head;
  while (temp != NULL) {
    printf("%d ", temp->data);
    temp = temp->next;
  }
  printf("\n");
}

int main() {
  struct node *head = NULL;
  create(&head, 55);
  display(head);

  return 0;
}
