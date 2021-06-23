# Números primos 🔢

Este desafio consiste na criação de um programa na linguagem de programação C que mostra na tela os `n` primeiros números naturais primos.

Para isso, você pode criar uma função para pedir ao usuário quantos números ele deseja que seja impresso na tela, uma outra função que determina se determinado número é primo e uma última função que imprime esses números:

```c
/*
 * Retorna a quantidade de números
 * naturais primos a ser impressa
 */
int pede_n_num_primos(void);

/*
 * Recebe um número e retorna se
 * ele é primo (`true`) ou não (`false`)
 */
bool eh_primo(int num);

/*
 * Recebe a quantidade de números naturais
 * primos a ser impressa e imprime esses
 * `n` números na tela
 */
void imprime_n_num_primos(int n_num_primos);
```

A função `main` pode ser estruturada da seguinte forma:

```c
int main(void)
{
    int n_num_primos = pede_n_num_primos();
    imprime_n_num_primos(n_num_primos);
    
    return 0;
}
```

Fique à vontade para modificar o nome das variáveis/funções, mas tente manter a estrutura original do programa.

## Observação :warning:

A resolução desse desafio (assim como de todos os outros que hão de surgir) não é obrigatória, não vale presença nem nota. Ainda assim, é fortemente recomendado que você ao menos tente resolvê-lo, a fim de descobrir e sanar suas dúvidas, além de aprimorar suas habilidades em programação.

Por favor, se você tiver qualquer dúvida, entre em contato comigo pelo [Discord][discord-monitoria] ou pelo e-mail [mvisentini@inf.ufsm.br][email-monitor], estou aqui para ajudá-lo! Lembre-se, para aprender a programar, basta programar. Boa sorte! :smile:

[Voltar para a página inicial][pagina-inicial]

[discord-monitoria]: https://discord.gg/kSBnGsRvnB "Servidor da monitoria da disciplina no Discord"
[email-monitor]:     mailto:mvisentini@inf.ufsm.br "E-mail do monitor"
[pagina-inicial]:    ../README.md                  "Voltar para a página inicial"
