# Solução do [desafio 1][desafio-1] :heavy_check_mark:

Ver solução do desafio no Online GDB: [https://onlinegdb.com/wtdoQEt9E][codigo-gdb].

```c
#include <stdio.h>

void mostrar_mensagem_erro(char opcao)
{
    printf("\nA opção \"%c\" é inválida. Tente novamente...\n", opcao);
}

int calcular_n_segundos(char opcao)
{
    switch (opcao) {
        case 'd':
            return 24 * 60 * 60;
        case 'm':
            return 30 * 24 * 60 * 60;
        case 'a':
            return 12 * 30 * 24 * 60 * 60;
        default:
            mostrar_mensagem_erro(opcao);
            return 0;
    }
}

int calcular_n_minutos(char opcao)
{
    switch (opcao) {
        case 'd':
            return 24 * 60;
        case 'm':
            return 30 * 24 * 60;
        case 'a':
            return 12 * 30 * 24 * 60;
        default:
            mostrar_mensagem_erro(opcao);
            return 0;
    }
}

int calcular_n_horas(char opcao)
{
    switch (opcao) {
        case 'd':
            return 24;
        case 'm':
            return 30 * 24;
        case 'a':
            return 12 * 30 * 24;
        default:
            mostrar_mensagem_erro(opcao);
            return 0;
    }
}

void mostrar_segundos(int dia, int mes, int ano)
{
    printf("\nEm um dia há %8d segundos.", dia);
    printf("\nEm um mês há %8d segundos.", mes);
    printf("\nEm um ano há %8d segundos.\n", ano);
}

void mostrar_minutos(int dia, int mes, int ano)
{
    printf("\nEm um dia há %8d minutos.", dia);
    printf("\nEm um mês há %8d minutos.", mes);
    printf("\nEm um ano há %8d minutos.\n", ano);
}

void mostrar_horas(int dia, int mes, int ano)
{
    printf("\nEm um dia há %8d horas.", dia);
    printf("\nEm um mês há %8d horas.", mes);
    printf("\nEm um ano há %8d horas.\n", ano);
}

int main(void)
{
    char dia = 'd';
    char mes = 'm';
    char ano = 'a';
    
    int n_segundos_dia = calcular_n_segundos(dia);
    int n_segundos_mes = calcular_n_segundos(mes);
    int n_segundos_ano = calcular_n_segundos(ano);
    
    int n_minutos_dia = calcular_n_minutos(dia);
    int n_minutos_mes = calcular_n_minutos(mes);
    int n_minutos_ano = calcular_n_minutos(ano);
    
    int n_horas_dia = calcular_n_horas(dia);
    int n_horas_mes = calcular_n_horas(mes);
    int n_horas_ano = calcular_n_horas(ano);
    
    mostrar_segundos(n_segundos_dia, n_segundos_mes, n_segundos_ano);
    mostrar_minutos(n_minutos_dia, n_minutos_mes, n_minutos_ano);
    mostrar_horas(n_horas_dia, n_horas_mes, n_horas_ano);
    
    return 0;
}
```

Ficou com alguma dúvida? Entre em contato comigo pelo [Discord][discord-monitoria] ou pelo e-mail [mvisentini@inf.ufsm.br][email-monitor].

[Voltar para a página inicial][pagina-inicial]

<!-- Links -->

[desafio-1]:         post-2-segundos-minutos-horas.md "Desafio 1"
[codigo-gdb]:        https://onlinegdb.com/wtdoQEt9E  "Solução do desafio no Online GDB"
[discord-monitoria]: https://discord.gg/kSBnGsRvnB    "Servidor da monitoria da disciplina no Discord"
[email-monitor]:     mailto:mvisentini@inf.ufsm.br    "E-mail do monitor"
[pagina-inicial]:    ../README.md                     "Voltar para a página inicial"
