# linked-list

#include <stdio.h>
#include <stdlib.h>
struct Node
{
 int data;
 struct Node *next;
}*first=NULL;

void create(char A[],int n)
{
 int i;
 struct Node *t,*last;
 first=(struct Node *)malloc(sizeof(struct Node));
 first->data=A[0];
 first->next=NULL;
 last=first;

 for(i=1;i<n;i++)
 {
 t=(struct Node*)malloc(sizeof(struct Node));
 t->data=A[i];
 t->next=NULL;
 last->next=t;
 last=t;
 }
}
void Display(struct Node *p)
{
 int i;
  for(i=1;i<9;i++){
   printf("-----    ");
 }
   printf("\n");
 while(p!=NULL)
 {
 printf("|%c|-|--> ",p->data);
 p=p->next;
 }
  printf("\n");
  for(i=1;i<9;i++){
   printf("-----    ");
 }
   printf("\n");
}
/*void RDisplay(struct Node *p)
{
 if(p!=NULL)
 {
 RDisplay(p->next);
 printf("|%d|-|->",p->data);
 }
}*/

int main()
{
 struct Node *temp;
 char A[]={'A','B','C','D','E','F','G','H'};
 create(A,8);

 Display(first);

 return 0;
}
