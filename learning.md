# IntroLists

#include <stdio.h>
#include <stdlib.h>

struct node_t {int number; struct node *next;};

int main(void)
{
    struct node_t *head = malloc(sizeof(struct node_t)); //read type right to left
                                                        //head is a pointer to node_t struct
    struct node_t *tmp = head; // this works because head is a pointer
    
    for (int i = 0; i < 5; i++){
        struct node_t *next2 = malloc(sizeof(struct node_t));
        tmp->next = next2;
        tmp->number = i + 1;
        tmp = next2;
    }
    
    tmp=head;
    
    for (int j = 0; j < 5; j++){
        printf("0x%x\r\n", tmp); // not &tmp bc tmp is already a pointer
        tmp = tmp->next;
    }
}
