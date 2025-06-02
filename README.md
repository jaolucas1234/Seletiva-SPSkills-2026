# Seletiva-SPSkills-2026

link do Figma: https://www.figma.com/proto/F70StyXugGgIpFrida0NTP/Untitled?node-id=1-136&t=uB6mNvBc0wmfWhAZ-0&scaling=scale-down&content-scaling=fixed&page-id=0%3A1&starting-point-node-id=1%3A3

Codigo C:

``` 
#include <stdio.h>
#include <string.h>

#define MAX 100


typedef struct {
    short horas;
    short minutos;
} tempo;



typedef struct {
    char descricao[100];
    tempo horario;
    int concluida;
} Tarefas;

concluida = 0;

Tarefas tarefas[MAX];
int total;



void criar() {
    if(total >= MAX) {
        printf("Você chegou ao limite de tarefas");
        return;
    }
    
    printf("Descrição: ");
    getchar();
    scanf("%s", tarefas[total].descricao);
    printf("Horario:\n");
    printf("Horas: ");
    scanf("%hd", &tarefas[total].horario.horas);
    printf("Minutos: ");
    scanf("%hd", &tarefas[total].horario.minutos);
    total++;
    printf("Tarefa adicionada com suçesso!\n");
}
void listar() {
    if(total == 0) {
        printf("Nunhuma tarefa cadastrada");
        return;
    }
    for(int i = 0; i < total; i++) {
        printf("[%d] Descrição: %s | Horario: %hd:%hd | statos: %s \n",
        i, tarefas[i].descricao, tarefas[i].horario.horas, tarefas[i].horario.minutos, 
        tarefas[i].concluida ? "Concluida" : "A-fazer" );
    }
}
void atualizar() {
    int i;
    printf("Digite o ID da tarefa que deseja concluir: ");
    scanf("%d", &i);
    if(i <  0 || i >= total){
        printf("ID invalido");
        return;
    }
    tarefas[i].concluida = 1;
    printf("Tarefa concluida com sucesso!\n");
}


int main() {
    int opcao;
    do{
    printf("Bem Vindo!\n");
    printf("1-Adicionar Tarefa\n");
    printf("2-Listar Tarefas\n");
    printf("3-Concluir Tarefa\n");
    printf("0-Sair\n");
    scanf("%d", &opcao);
    switch (opcao){
        case 1: criar(); break;
        case 2: listar(); break;
        case 3: atualizar(); break;
        case 0: printf("saindo...\n"); break;
        default: printf("opção invalida\n"); break;
    }
    } while (opcao != 0);
    return 0;[Uploading Documentação do Projeto.pdf…]()

}
```


