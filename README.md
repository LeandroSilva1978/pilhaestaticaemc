
#include<stdio.h>
#include<conio.h>

#define max 5

//variáveis globais

int pilha[max]; //pilha de pratos
int topo = 0;

//protótipos das funções
void mostrar();
void empilhar();
void desempilhar();

int main()
{
	int op;
	//MENU:
	do{
		system("cls");
		printf("\n****EMPILHAR PRATOS***\n\n");
		printf("\n1 - Empilhar\n (Digite: 1 - Prato Vermelho\n 2- Prato Verde\n 3- Prato Azul\n 4- Prato Branco\n 5- Prato Laranja)");
		printf("\n2 - Desempilhar");
		printf("\n3 - Mostrar");
		printf("\n0 - Sair\n");
		scanf("%d" , &op);
		switch(op){
			case 1:
				empilhar();
				break;
			case 2:
				desempilhar();
				break;
			case 3:
				mostrar();
				break;
		}//fim switch
	}while(op != 0);
	
	return 0;
	system("PAUSE");
}//fim do main

void empilhar()
{
	if(topo == max)
		printf("\n Overflow!");
	else
	{
		printf("\n Digite o dado -->");
		scanf("%d", &pilha[topo]);
		topo++;
	}//fim do else
}//fim de empilhar

void desempilhar()
{
	if(topo == 0)
		printf("\n Underflow!");
	else
	{
		printf("\n Desempilhado o valor %d", pilha[topo - 1]);
		topo--;
	}//fim else
	getch();
}//fim desempilhar

void mostrar()
{
	int aux;
	for (aux=topo-1; aux>=0; aux--)
	{
		printf("\nPosicao %d = %d\n", aux, pilha[aux]);
	}
	getch();
}





