#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// DefiniÃ§Ã£o da estrutura para armazenar as respostas do visitante
typedef struct {
    char nome[50];
    int idade;
    char sentimento[200];
    char melhorias[200];
    char voltaria[10];
} RespostaVisitante;

// FunÃ§Ã£o para exibir informaÃ§Ãµes sobre as exposiÃ§Ãµes
void exibirExposicao(char nomeExposicao[], int ano) {
    printf("Bem-vindo à exposição '%s'!\n", nomeExposicao);
    printf("Esta exposição celebra eventos importantes da história:\n");
    printf("- Ano: %d\n", ano);
    printf("\n");
}

// FunÃ§Ã£o para vender um bilhete (implemente esta funÃ§Ã£o)
void venderBilhete() {
    // ImplementaÃ§Ã£o da venda de bilhetes
    printf("Bilhete vendido!\n");
}

// FunÃ§Ã£o para mostrar os bilhetes vendidos (implemente esta funÃ§Ã£o)
void mostrarBilhetes() {
    // ImplementaÃ§Ã£o para mostrar bilhetes vendidos
    printf("Bilhetes vendidos:\n");
}

int main() {
    printf("Museu MultitemÃ¡tico - ExposiÃ§Ãµes em Destaque\n\n");

    // Exibindo informaÃ§Ãµes sobre cada exposiÃ§Ã£o
    const char *exposicao1 = "100 anos da semana de arte moderna";
    const char *exposicao2 = "150 anos de Santos Dumont";
    const char *exposicao3 = "Jogos Olímpicos de Paris 2024";
    const char *exposicao4 = "Evolução da Comunicação";

    printf("Esperamos que vocÃª aproveite sua visita ao nosso museu!\n");

    int escolhaSobre = 0;
    int escolha = 0;

    do {
        // Exibe o menu principal
        printf("\nMenu:\n");
        printf("1. Vender Bilhete\n");
        printf("2. Mostrar Bilhetes Vendidos\n");
        printf("3. Sobre\n");
        printf("4. Sala de Exposicao\n");
        printf("5. Idade Minima para Ingressar\n");
        printf("6. Sair\n");
        printf("Escolha uma opcao: ");
        scanf("%d", &escolha);

        // Limpa o buffer do teclado
        while (getchar() != '\n');

        switch (escolha) {
        case 1:
            venderBilhete();
            break;
        case 2:
            mostrarBilhetes();
            break;
        case 3:
            // Exibe o submenu para a opÃ§Ã£o "Sobre"

            do {
                printf("\nSobre:\n");
                printf("1. 100 anos da Semana de Arte Moderna\n");
                printf("2. 150 anos de Santos Dumont\n");
                printf("3. Jogos Olimpicos de Paris 2024\n");
                printf("4. Evolucao da comunicacao\n");
                printf("5. Voltar ao menu principal\n");
                printf("Escolha uma opcao: ");
                scanf("%d", &escolhaSobre);

                // Limpa o buffer do teclado
                while (getchar() != '\n');

                switch (escolhaSobre) {
                case 1:
                    printf("\n100 anos da Semana de Arte Moderna: Informacoes sobre este evento.\n\n");
                    break;
                case 2:
                    printf("\n150 anos de Santos Dumont: Informacoes sobre o pioneiro da aviacao.\n\n");
                    break;
                case 3:
                    printf("\nJogos Olimpicos de Paris 2024: Detalhes sobre os proximos Jogos Olimpicos.\n\n");
                    break;
                case 4:
                    printf("\nEvolucao da comunicacao: Como a comunicacao mudou ao longo do tempo.\n\n");
                    break;
                case 5:
                    printf("\nVoltando ao menu principal...\n\n");
                    break;
                default:
                    printf("\nOpÃ§Ã£o invalida. Tente novamente.\n\n");
                }
            } while (escolhaSobre != 5); // Permite voltar ao menu principal

            break;
        case 4:
            printf("\nSala de Exposicao: Aqui voce encontrara obras de arte maravilhosas!\n\n"); // Explicar sobre as salas e obras
            break;
        case 5:
            printf("\nIdade Minima para Ingressar: A idade minima para entrar nas salas de exposiÃ§Ãµes Ã© 6 anos.\n\n");
            break;
        case 6:
            printf("\nSaindo do Menu. Obrigado!\n");
            break;
        default:
            printf("\nOpcao invalida. Tente novamente.\n\n");
        }
    } while (escolha != 6);

    return 0;
}


// DefiniÃ§Ã£o da estrutura para armazenar as respostas do visitante
typedef struct {
    char nome[50];
    int idade;
    char sentimento[200];
    char melhorias[200];
    char voltaria[10];
}

int main() {
    int num_entrevistados;

    printf("Bem-vindo ao questionÃ¡rio sobre a visita ao museu multitemÃ¡tico!\n\n");

    printf("Quantos visitantes foram entrevistados? ");
    scanf("%d", &num_entrevistados);

    // Cria um array de estruturas para armazenar as respostas de cada visitante
        RespostaVisitante* respostas = malloc(num_entrevistados * sizeof(RespostaVisitante));

    // Coleta as respostas de cada visitante
    for (int i = 0; i < num_entrevistados; i++) {
        printf("\nEntrevistado %d:\n", i + 1);

        printf("Nome: ");
        scanf(" %[^\n]s", respostas[i].nome);

        printf("Idade: ");
        scanf("%d", &respostas[i].idade);

        printf("Como vocÃª se sentiu observando a exposiÃ§Ã£o? (atÃ© 200 caracteres)\n");
        scanf(" %[^\n]s", respostas[i].sentimento);

        printf("O que poderia ser melhorado na exposiÃ§Ã£o? (atÃ© 200 caracteres)\n");
        scanf(" %[^\n]s", respostas[i].melhorias);

        printf("VocÃª voltaria para uma nova visita? (Sim/NÃ£o): ");
        scanf(" %[^\n]s", respostas[i].voltaria);
    }

    // Gerar relatÃ³rio
    printf("\nRelatÃ³rio de Visitantes:\n");
    printf("---------------------------------------------------\n");
    printf("| %-15s | %-5s | %-15s | %-15s | %-10s |\n", "Nome", "Idade", "Sentimento", "Melhorias", "Voltaria");
    printf("---------------------------------------------------\n");

    for (int i = 0; i < num_entrevistados; i++) {
        printf("| %-15s | %-5d | %-15s | %-15s | %-10s |\n", respostas[i].nome, respostas[i].idade, respostas[i].sentimento, respostas[i].melhorias, respostas[i].voltaria);
    }
    printf("---------------------------------------------------\n");

    // Libera a memÃ³ria alocada
    free(respostas);

    return 0;
}
