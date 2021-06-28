# Solução do [desafio 2][desafio-2] :heavy_check_mark:

Ver solução do desafio no Online GDB: [https://onlinegdb.com/2B00Yeozh][codigo-gdb].

## `pede_n_num_primos`

Esta função ~~como o próprio nome já diz~~ pede ao usuário a quantidade de números primos naturais a ser impressa na tela.

### Funcionamento

Dentro de uma estrutura de repetição `while` é pedida ao usuário a informação descrita acima. Caso essa quantidade informada seja menor ou igual a 0, o programa volta no início do laço e pede novamente a informação, por isso a palavra-chave `continue`. Esse processo tem duração infinita, pois a condição do laço `while` é `true` (`1`), ou seja, a condição é uma constante verdadeira. Por outro lado, se a quantidade informada é válida (`x > 0`), o programa não "entra" naquela condição (pois a condição se torna `false`) e vai para a próxima, que é `return x`, ou seja, retorna a quantidade lida do usuário, que agora é válida. O algorítmo simplificado seria algo como:

1. Lê uma quantidade
2. Se a quantidade for inválida, volte à instrução 1
3. Se a quantidade for válida, retorne-a

### Código da função

```c
int pede_n_num_primos(void)
{
    while (true) {
        int n_num_primos;

        printf("\nDigite a quantidade de números primos naturais a ser impressa na tela: ");
        scanf("%d", &n_num_primos);

        if (n_num_primos <= 0) {
            printf("\nQuantidade inválida. Tente novamente...\n");
            continue;
        }

        return n_num_primos;
    }   
}
```

## `eh_primo`

Esta função recebe um número inteiro natural e retorna `true` (`1`) caso ele seja primo; caso contrário, retorna `false` (`0`).

### Funcionamento

Se o número recebido pela função for menor ou igual a 1, é retornado `false` (`0`), pois sabemos que os números menores ou iguais a 1 não são considerados primos; se o número for igual a 2, é logo retornado `true` (`1`), a fim de facilitar os próximos cálculos, já que o 2 é o único número natural primo par. Após essas duas verificações, há um laço `for` que começa em `i = 2` e vai até `num - 1`, incrementando de 1 a 1. Dentro do laço é feita a seguinte verificação: se o resto da divisão de `num` por `i` é igual a `0`; caso positivo, é retornado `false` (`0`), pois se um número é divisível por outro além dele mesmo e 1, logo ele não pode ser primo. Se a função chegar até o final, sem ter retornado algo, significa que `num` não tem nenhum outro divisor além dele mesmo e 1, consequentemente, é primo e a função retorna `true` (`1`). O algorítmo simplificado seria algo como:

1. Se `num <= 1` retorne `false` (`0`)
2. Se `num == 2` retorne `true` (`1`)
3. Vá de `i` até `num - 1`
   1. Se `num % 2 == 0` retorne `false` (`0`)
   2. Incremente `i` em 1
   3. Volte à instrução 3
4. Retorne `true` (`1`)

### Código da função

```c
bool eh_primo(int num)
{
    if (num <= 1) return false;
    if (num == 2) return true;

    for (int i = 2; i < num; i++) {
        if (num % i == 0) return false;
    }

    return true;
}
```

## `imprime_n_num_primos`

Esta função recebe uma quantidade `n` que indica quantos números primos naturais serão impressos na tela e os imprime.

### Funcionamento

O primeiro número primo natural (2) é impresso na tela. A variável `cont` é criada e inicializada com o valor 1 (pois já imprimimos o primeiro número primo, 2). Essa variável será incrementada somente quando um número primo é impresso, para saber quando devemos parar de imprimir. Depois, a variável `num` é criada e inicializada com o valor 3, já que o primeiro número primo (2) já foi impresso. Ela representa os números que a gente vai testar. Ao contrário de `cont`, essa variável é incrementada em cada "laçada" em 2. Por que incrementar em 2 ao invés de 1? Bom, o número 2 é o único número par do conjunto dos primos, então como nós já imprimimos ele lá no início da função, não precisamos mais testar outros números pares, porque eles não podem ser primos. O algorítmo simplificado seria algo como:

1. Enquanto o número de primos impresso for menor que a quantidade que o usuário pediu
   1. Teste se o número é primo
   2. Caso positivo, imprima ele na tela e incremente o contador de números primos impressos
   3. Incremente o número em 2

### Código da função

```c
void imprime_n_num_primos(int n_num_primos)
{
    printf("\n%d ", 2);

    int cont = 1;
    int num = 3;

    while (cont < n_num_primos) {
        if (eh_primo(num)) {
            printf("%d ", num);
            cont++;
        }

        num += 2;
    }

    printf("\n\n");
}
```

## Código completo

```c
#include <stdio.h>
#include <stdbool.h>

int pede_n_num_primos(void)
{
    while (true) {
        int n_num_primos;

        printf("\nDigite a quantidade de números primos naturais a ser impressa na tela: ");
        scanf("%d", &n_num_primos);

        if (n_num_primos <= 0) {
            printf("\nQuantidade inválida. Tente novamente...\n");
            continue;
        }

        return n_num_primos;
    }   
}

bool eh_primo(int num)
{
    if (num <= 1) return false;
    if (num == 2) return true;

    for (int i = 2; i < num; i++) {
        if (num % i == 0) return false;
    }

    return true;
}

void imprime_n_num_primos(int n_num_primos)
{
    printf("\n%d ", 2);

    int cont = 1;
    int num = 3;

    while (cont < n_num_primos) {
        if (eh_primo(num)) {
            printf("%d ", num);
            cont++;
        }

        num += 2;
    }

    printf("\n\n");
}

int main(void)
{
    int n_num_primos = pede_n_num_primos();
    imprime_n_num_primos(n_num_primos);
    
    return 0;
}
```

Ficou com alguma dúvida? Entre em contato comigo pelo [Discord][discord-monitoria] ou pelo e-mail [mvisentini@inf.ufsm.br][email-monitor].

[Voltar para a página inicial][pagina-inicial]

<!-- Links -->

[desafio-2]:         post-4-numeros-primos.md         "Desafio 2"
[codigo-gdb]:        https://onlinegdb.com/2B00Yeozh  "Solução do desafio no Online GDB"
[discord-monitoria]: https://discord.gg/kSBnGsRvnB    "Servidor da monitoria da disciplina no Discord"
[email-monitor]:     mailto:mvisentini@inf.ufsm.br    "E-mail do monitor"
[pagina-inicial]:    ../README.md                     "Voltar para a página inicial"
