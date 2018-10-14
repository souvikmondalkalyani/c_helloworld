//link list to insert
//To delete
//To find value
//TO travers the system
#include<stdio.h>
#include<conio.h>
#include<stdlib.h>
#include<string.h>
#include<malloc.h>
(struct node*) ceatenode(struct node *p);
void Insertnode(struct node *p);
void Insertbeg(struct node *p);
void Insertmiddile(struct node *p);
void Traversalnode(struct node *p);
void deletenode(struct node *p);

int main()
{
    while(1)
    {

    struct node
    {
        int info;
        struct node *link;
    }

    int choice;
    struct node *start;
    printf("enter your choice from bellow\n\n");
    puts("1.TO INSERT A NODE\n2.TO INSERT A NODE AT END\n3.TO INSERT A NODE AT BEGINING\n"
         "4.TO INSERT A NODE AT MIDDILE\n5.TO TRAVERS AT NODES\n6.TO DELETE A NODE\n7.TO EXIT");
    scanf("%d",&choice);
    switch(choice)
    {
    case 1:
        {
            start=ceatenode(start);
            break;
        }
    case 2:
        {
            if(start==NULL)
                return;
            else
            {
                Insertnode(start);
                break;
            }
        }
    case 3:
        {
            Insertbeg(start);
            break;
        }
    case 4:
        {
          Insertmiddile(start);
          break;
        }
    case 5:
        {
           Traversalnode(start);
           break;
        }
    case 6:
        {
            deletenode(start);
            break;
        }
    case 7:
        {
            exit(1);
            break;
        }
    default:
        {
            printf("enter a valid choice\n\n");
        }
    }
    }
    getch();
    return 0;
}
(struct node*) ceatenode(struct node *p)
{
    p=(struct node *)malloc(sizeof(struct node));
    p->link=NULL;
    printf("enter the value item\n");
    scanf("%d",&(p->info));
    return (p);

}
void Insertnode(struct node *p)
{
    if(p==NULL)
    {
        printf("there is no node avilaible\n\n");
        return;
    }
    else
    {
        while(p!=NULL)
        p=p->link;
            struct node *s=(struct node*)malloc(sizeof(struct node));
        s->link=NULL;
        printf("enter the item\n");
        scanf("%d",&(s->info));
        p->link=s;
    }
}
void Insertmiddile(struct node *p)
{
    int i;
    printf("enter the element number\n");
    scanf("%d",&i);
    for(int k=0;k<i;k++)
    {
        p++;
    }
    struct node *k=(struct node*)malloc(sizeof(struct node));
    struct node *n=p->link;
    p->link=k;
    k->link=n;
}
void Traversalnode(struct node *p)
{
    while(p!=NULL)
    {
        printf("%d",p->info);
        p=p->link;
    }
}
void deletenode(struct node *p)
{
    int value;
    printf("enter the item\n");
    scanf("%d",&value);
    while(p->link->info==value)
    {
        struct node *tmp;
        tmp=p->link;
        p->link=tmp->link;
        free(tmp);
    }
    p=p->link;
}

