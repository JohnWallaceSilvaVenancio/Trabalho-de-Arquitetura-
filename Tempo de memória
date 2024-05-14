#include <stdio.h>
#include <stdlib.h>
#include <time.h>

void SalvarARQ(int sedd,int quantia){//Criei uma função para poder salvar os resultados das memórias em arquivos
	char Memoria[30];//uma variavel que vai armazenar o nome dos arquivos
	sprintf(Memoria,"Sedd %d: %d.txt",sedd,quantia);//aqui o nome do arquivo será guardado na variavel acima,mantendo as duas variaveis da função,além de tambem ser aonde é possivel manipular a Sedd
	FILE *arq; //cria o arquivo
	arq = fopen("Memoria.txt","wt");//Cria o tipo de arquivo
	if(arq == NULL){//caso o arquivo não exista,ou não seja possivel acessalo
		printf("Problema na existencia do arquivo!\n");//o mensagem a aparecer na tela em caso de algum erro
		fclose(arq);//fecha o arquivo altomaticamente
	}
	srand(sedd);//vai gerar os números aleatórios de acordo com a sedd
	clock_t inicio = clock();//incicia uma especie de temporizador,para podermos fazer o controle de tempo do programa
	int i;//valor a ser percorrido no laço de repetição
    int result;// variavel criada apenas no intuito de armazenar no arquivo a sedd
    printf("intervalo da rand: [0,%d]\n", RAND_MAX);//mostra o intervalo em que cada numero aleatório foi gerado
    for(i=1 ; i <= quantia ; i++){//feito para gerar os numeros de acordo com usuario e ir somando 1 numero aleatorio,até atender o que o usuario digitou
        printf("Numero %d: %d\n",i, rand());//mostra o número aleatorio gerado
		result = fprintf(arq,"SEDD %d: %d\n",i);//nessa linha a sedd também é colocada amostra no arquivo	
		if(result < 0){//caso a sedd não exista
 			printf("Erro ao tentar digitar no arquivo!");//essa mensagem aparecera na tela do usuario
 			fclose(arq);//fecha o arquivo altomaticamente
	 	}
 	}
 	clock_t fim = clock();//finaliza o cronômetro de tempo necessario para gerar o programa
 	double TempoNecessario;//variavel para anotar o tempo que foi gasto
 	TempoNecessario = (double)(fim-inicio);//operação necessario para se ter o tempo em segundos
 	printf("Memoria %s foi armazenado,tempo necessario:%.2f segundos \n",Memoria,TempoNecessario);//e aqui que o benchmark se concentra,depende do tempo a ser mostrado aqui
}
 
int main(){
	int sedd;//variavel que define a sedd
	int quantia;//variavel de numeros aleatórios
	printf("Sedd que vc deseja:\n");
	scanf("%d",&sedd);//le o numero desejado
	printf("Não exagere no valor a ser gerado abaixo!\n");//Só para não termos ploblemas
	printf("Digite a quantia de valores a serem gerados:\n");
	scanf("%d",&quantia);//le a quantia de numeros aleatórios
	SalvarARQ(sedd,quantia);//aqui é chamada toda a função acima
}
