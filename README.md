#include<stdio.h>
#include<string.h>
#include <cstdlib>
#define SIZE 200
char name [SIZE] [50];
char email [SIZE] [50];
int id [SIZE];
int op;
void registration ();
void search();
void list ();
int main (void) {

	do{
		system("cls");
		printf("\n----Menu----\n1 - To register\n2 - To list\n3 - To search\n4 - To exit");
		scanf("%d", &op);
		switch(op){
			case 1:
				registration();
			break;
			case 2:
					list ();
			break;
			case 3:
				search ();	
			break;
			case 4:
			system("exit");
				break;		
			default:
				printf("Invalid");
				getchar();
				getchar();
				break;	
		}
	}while (op!=4);
	}

void list(){
	int i;
	for(i=0; i<SIZE; i++){
		if(id[i]>0){
				printf("\nName: %s\nEmail: %s\nId: %d", name[i], email[i], id[i] );
		}else{
			break;
		}
	
	}
	getchar();
	getchar();
}

void registration (){
	static int line;
	do{
		printf("\nname: ");
		scanf("%s", &name[line]);
		printf("\nemail: ");
		scanf("%s", &email[line]);
		printf("\nid: ");
		scanf("%d", &id[line]);
		printf("\ntype 1 to continue or another number to exit ");
		scanf("%d", &op);
		line++;
		
			}while (op==1);
} 
void search () {
	int idSearch;
	char emailsearch[50];
	int i;
	do{
		printf("\nType 1 to search for id or 2 to search for email");
		scanf("%d", &op);
		switch(op){
			case 1:
				printf("id: ");
				scanf("%d", &idSearch);
				for(i=0; i<SIZE; i++){
					if(id[i]==idSearch){
						printf("\nName: %s\nEmail: %s\nId: %d", name[i], email[i], id[i] );
					}
				}
				break;
				case 2:
					printf("\nEmail");
					scanf("%s", emailsearch);
					for(i=0 ; i<SIZE; i++){
						if(strcmp (email[i], emailsearch) ==0){
							printf("\nName: %s\nEmail: %s\nId: %d", name[i], email[i], id[i]);
						}
					}
					break;
					default:
						printf("\ninvalid");
						break;
		}
		printf("\nType 1 to continue searching ");
		scanf("%d", &op);
	}while(op==1);
}
