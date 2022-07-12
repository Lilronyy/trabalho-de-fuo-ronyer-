# trabalho-de-fup-ronyer-
caixa eletronico em c para um trabalho de fup


#include<stdio.h>
#include<ctype.h>
#include<stdlib.h>
#include<string.h>
#include<locale.h>

struct criarconta {
char cpf[11];
char rg[9];
char nome[50];
char end[30];
char cidade[30];
char bairro[15];
char cep[8];
char uf[2];
char telefone[10];
};
void addconta();
void salvar(struct criar conta);
void listarconta();
void remover();


int main (){
    int op;
    float depositar, saque, saldo = 500;


setlocale(LC_ALL, "Portuguese");

printf ( "|-----Bem vindo ao Cbank-| \n " ) ;
printf ( "|-----MENU---------------| \n " ) ;
printf ( "|-----PRINCIPAL----------| \n " ) ;
printf ( "| (|1|) Criar Conta      | \n " ) ;
printf ( "| (|2|) Listar Contas    | \n " ) ;
printf ( "| (|3|) Remover Conta    | \n " ) ;
printf ( "| (|4|) Consultar Saldo  | \n " ) ;
printf ( "| (|5|) Fazer Deposito   | \n " ) ;
printf ( "| (|6|) Fazer Saque      | \n " ) ;
printf ( "| (|7|) Listar Contas    | \n " ) ;
printf ( "| (|8|) Sair do Sistema  | \n " ) ;
printf ( "|------------------------| \n " ) ;

printf("Digite a opção que deseja realizar!!\n");
scanf("%d%*c",&op);

switch (op)
{
    case 1 :
    printf("Criar Conta \n");
       addconta();
    break;

    case 2 :
    printf (" Listar Contas \n");
    break;

    case 3 :
    printf ("Remover Conta\n");
    break;

    case 4 :
    printf ("Consultar Saldo\n");
    break;

    case 5 :
    printf ("Deposito\n");

    printf("Informe o valor a ser depositado na sua conta?\n");
            scanf("%f", &depositar);
            saldo = saldo + depositar;
            printf("Deposito realizado com sucesso seu saldo agora e %.2f reais", saldo);


    break;

    case 6 :
    printf ("Sacar\n");
       printf("informe o valor do saque ?\n");
            scanf("%f", &saque);

            if(saque > saldo){

                printf("saldo insulficiente\n");


                }else{

                    saldo = saldo - saque;
                    printf("Vocé sacou %.2f reais", saque);

            }
            break;

    case 7 :
    printf("Listar Contas");
    break;

    case 8 :
    printf("Sair do Sistema ");
    break;

    default:
    printf("\n ATENÇÃO Opção não existente !!!");
    break;
}
}

void addconta(){
/* fprintf(f, "%d\n", i); */



   FILE *f = fopen("nconta.txt", "a");
    if (f == 0) { printf("Erro ao abrir arquivo."); exit(0); }

    struct criarconta c;
    printf("\nPreencha os dados a seguir :\n");

    fflush(stdin);
	printf("\nDigite o CPF: ");
    gets(c.cpf);

    fflush(stdin);
	printf("\nDigite o RG: ");
    gets(c.rg);

    fflush(stdin);
	printf("\nDigite o NOME: ");
	gets(c.nome);

    fflush(stdin);
	printf("\nDigite o ENDEREÇO: ");
	gets(c.end);

	fflush(stdin);
    printf("\nDigite a CIDADE: ");
	gets(c.cidade);

    fflush(stdin);
	printf("\nDigite o BAIRRO: ");
	gets(c.bairro);

	fflush(stdin);
	printf("\nDigite o CEP: ");
	gets(c.cep);

	fflush(stdin);
    printf("\nDigite a UF: ");
	gets(c.uf);

	fflush(stdin);
	printf("\nDigite o TELEFONE: ");
	gets(c.telefone);





    fclose(f);
}

/*void listarconta(){
        FILE *f = fopen("nconta.txt", "r");
        if (f == 0) { printf("Erro ao abrir arquivo."); exit(0); }

        while(!feof(arquivo)){
		fscanf(f,"%s %s %s %s %s %s %s %s %s\n",&nome.c);
	}



}*/
