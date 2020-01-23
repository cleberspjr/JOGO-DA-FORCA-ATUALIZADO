#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <time.h>


int menu(){

printf("\n\t\t >>> JOGO DA FORCA: ESCOLHA UMA DAS OPÇÕES ABAIXO: <<<\n");
printf("\n\n  1) Novo Jogo   2) Mostrar Banco de Palavras    3) Sobre    4) Ajuda    5) Sair \n\n");


return 0;
}

int lebanco(char palavras[15][256]){
system("clear"); 
//char banco_de_palavras[15][256];
strcpy(palavras[0], "DIEGO ALVES");
strcpy(palavras[1], "RAFINHA");
strcpy(palavras[2], "PABLO MARI");
strcpy(palavras[3], "RODRIGO CAIO");
strcpy(palavras[4], "FILIPE LUIS");
strcpy(palavras[5], "ARAO");
strcpy(palavras[6], "GERSON");
strcpy(palavras[7], "ARRASCAETA");
strcpy(palavras[8], "DIEGO RIBAS");
strcpy(palavras[9], "EVERTON RIBEIRO");
strcpy(palavras[10], "BRUNO HENRIQUE");
strcpy(palavras[11], "GABRIEL BARBOSA");
strcpy(palavras[12], "REINIER");
strcpy(palavras[13], "MICHAEL");
strcpy(palavras[14], "GUSTAVO HENRIQUE");

return 0;
}

int imprimebanco(){
    int i;
    char palavras[15][256], ch;
    lebanco(palavras);

    printf("BANCO DE PALAVRAS:\n");
    for (i = 0; i < 15; i++)
    {
        printf("%d - ", i);
        puts(palavras[i]);
    }
    printf("\n");
    printf("PRESSIONE QUALQUER LETRA PARA CONTINUAR!\n");
    
    scanf(" %c",&ch);
    
    return 0;
    
}

int sobre(){
    char palavras[15][256], ch;
    lebanco(palavras);
    system("clear");    
    printf("\nSOBRE ESTE JOGO O JOGO DA FORCA:\n\n");
    printf("Programa desenvolvido por: Cleber dos Santos Pinto Júnior\n");
    printf("Propósito: Obtenção do V crédito na disciplina Linguagem de Programação 1\n");
    printf("UNIVERSIDADE ESTADUAL DE SANTA CRUZ\n");
    printf("CIÊNCIA DA COMPUTAÇÃO\n");
    

    printf("\n");
    printf("PRESSIONE QUALQUER LETRA PARA CONTINUAR!\n");
    
    scanf(" %c",&ch);
    
    return 0;
    
}

int ajuda(){
    char palavras[15][256], ch;
    lebanco(palavras);

    system("clear"); 
    printf("\nAJUDA PARA ESTE JOGO DA FORCA:\n\n");
    printf("* O jogo da forca é um jogo em que o jogador tem que acertar qual \né a palavra proposta.\n");
    printf("* O tema deste jogo é FUTEBOL\n* Mais especificamente: outro patamar de futebol (dica importante!). \n");
    printf("* Você deve digitar apenas letras maiúsculas.\n");
    printf("* Digite uma letra por vez e pressione enter.\n");
    printf("* Não existe limite de tentativas. Jogue à vontade e DIVIRTA-SE!\n");


    printf("\n");
    printf("PRESSIONE QUALQUER LETRA PARA CONTINUAR!\n");
    
    scanf(" %c",&ch);
    
    return 0;
    
}

int sorteia(int num_sorteados[15]){
    int i, k, flag_num_unico, num_sorteado;
    
    i = 0;
    srand((int)time(NULL));
    while(i < 14){
                
        num_sorteado = rand() % 15;
       // printf("i = %d Numero sorteado: %d\n", i, num_sorteado);
        flag_num_unico = 1;
        for(k = 0; k< 15; k++){
            if(num_sorteados[k] == num_sorteado){
                flag_num_unico = 0;
                break;
            }
        }

        if(flag_num_unico == 1){
            num_sorteados[i] = num_sorteado;
            i++;
        }
        

    }

    return 0;
}




int novojogo(){
    char letra;
    int num_palavra, i, count_erro, count_acertos, flag_acerto, flag_nome_composto, flag_continua_jogo, flag_novo_sorteio, num_sorteados[15], flag_chama_nova_palavra, k, j;
    
    //criando banco de palavras
    char banco_de_palavras[15][256];
    lebanco(banco_de_palavras);
    char buffer_game[256];
    
    for(i=0; i< 15; i++){
        num_sorteados[i] = 0;
    }
    sorteia(num_sorteados);

    for(k=0; k<15; k++){

        strcpy(buffer_game, "\0");   
        //puts(banco_de_palavras[num_sorteados[k]]);
        strcpy(buffer_game, "_");   
        //verificando se o nome é composto
        letra = ' ';
        flag_nome_composto = 0;        
        for (i = 1; i< strlen(banco_de_palavras[num_sorteados[k]]); i++){
            if( banco_de_palavras[num_sorteados[k]][i] == letra){
                 strcat(buffer_game, "-");        
                 flag_nome_composto = 1;
            }
            else strcat(buffer_game, "_");
        }

        //zerando flags da rodada atual
        count_erro = 0;
        count_acertos = 0;

        do{
            
            system("clear"); 
            menu();
            flag_chama_nova_palavra = 0;
            printf("\n--> Você já acertou %d palavras...\n\n", k);
            printf("--> Além disso, você já digitou %d letras erradas nesta rodada! \nFelizmente não temos limite de letras erradas! :) Continue tentando...\n", count_erro);
            printf("\n--> DIGITE UMA LETRA:\n\n");
           // puts(banco_de_palavras[num_sorteados[k]]);
            for(i = 0; i< strlen(buffer_game); i++)printf("%c ",buffer_game[i]);
            printf("\n");
            scanf(" %c",&letra);
            
            switch (letra)
            {
            case '1': 
                
                return(1);
                break;
             case '2': 

               return(2);
                // break;
             case '3': 
                return(3);
                 break;
            
             case '4':
             return(4);
                 break;
             case '5':
             return(5);
                 break;
            
            default: 

            flag_acerto = 0;
            for (i = 0; i< strlen(banco_de_palavras[num_sorteados[k]]); i++){
                if( banco_de_palavras[num_sorteados[k]][i] == letra){

                    buffer_game[i] = letra;
                    count_acertos++;
                    flag_acerto = 1;
                }
                 
            }  
            if(!flag_acerto){
                    count_erro++;
            }     

            
            if(flag_nome_composto == 1){
                if(count_acertos == strlen(banco_de_palavras[num_sorteados[k]]) - 1 ) {
                    flag_chama_nova_palavra = 1;
                }
            }
            else{
                if(count_acertos == strlen(banco_de_palavras[num_sorteados[k]])) {

                    flag_chama_nova_palavra = 1;
                }
            }
            break;                 
            }
        }while(!flag_chama_nova_palavra);        

    }

    printf("\n\n**** PARABÉNS! VOCÊ ACERTOU TODAS AS PALAVRAS DO JOGO ****\n\n");

    return 0;
}

int main(){
    menu();
    int op, saida;
    char ch;
    scanf("%d",&op);

    do{
        switch (op)
        {
        case 1: 
            
           op = novojogo();
            printf("\n");
            printf("PRESSIONE QUALQUER LETRA PARA CONTINUAR!\n");    
            scanf(" %c",&ch);
            menu();
            scanf("%d",&op);

            break;
        case 2: 
               printf("Banco de Palavras será mostrado\n");             
                 imprimebanco();        
                 
                 menu();
                scanf("%d",&op);
            break;
        case 3: 
            printf("Informações sobre o jogo serão exibidas\n");
            sobre();
                 
                 
                 menu();
                scanf("%d",&op);
            break;
        case 4: printf("Ajuda será exibida\n");
                ajuda();
                 
                 
                 menu();
                scanf("%d",&op);
            break;
        case 5: printf("O jogo será encerrado!\n");
            exit(0);
            break;
        
        default: 
            printf("Você precisa escolher uma opação válida!\n!!");
            op = 5;
            break;
        }

    }while(op != 0);

    return 0;
}
