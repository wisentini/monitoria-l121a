# Convenções na linguagem C

A sintaxe C é escrever código de uma forma que permita a sua compilação. Convenções são coisas que não afetam a compilação do código, mas são geralmente aceitas como parte da escrita de um bom código C, e são coisas que você deve aderir para garantir que está escrevendo um código bom e legível.

## Funções

Tente limitar o número de linhas das suas funções entre 20 e 25, no máximo. Se ultrapassar muito além disso, é certo que ela pode ser dividida em duas ou mais funções. Lembre-se, uma função deve resolver um problema específico.

## Nomeação

### Convenções

Existem certas convenções para a forma como nomeamos as coisas em C:

#### Funções e variáveis

Estes devem ser `snake_case`, uma convenção onde os espaços são substituídos por `_`. Por exemplo, `salario_mensal`.

#### Constantes

Estes também devem ser da forma `SNAKE_CASE`, porém com a diferença de que todas as letras são maiúsculas. Por exemplo, `NUMERO_DE_ALUNOS`.

### Nomes descritivos

O nome de uma variável deve descrever o valor que ela armazena e o que ela representa. Da mesma forma, o nome de uma função deve descrever a tarefa da função. Em geral, nomes de variáveis devem ser substantivos, e nomes de funções devem ser verbos. Abreviações não devem ser usadas a menos que sejam abreviações geralmente aceitas ou muito óbvias, como `num` para número.

❌
```c
int main(void)
{
    double s = 1254.78;
    double a = 13/100;
    double ns = cns(s, a);
    
    printf("%lf", ns);
}
```

✔️
```c
int main(void)
{
    double salario = 1254.78;
    double porcentagem_aumento = 13/100;
    double novo_salario = calcula_novo_salario(salario, porcentagem_aumento);
    
    printf("%lf", novo_salario);
}
```

## Indentação

A indentação é uma forma importante de ajudar a distinguir blocos de código. Você deve indentar seu programa um <kbd>tab</kbd> além toda vez que abrir um `{` e indentar um <kbd>tab</kbd> a menos toda vez que fechar um `}`.

> Um <kbd>tab</kbd> geralmente deve ter 4 espaços. Esse tamanho pode ser configurado no seu editor de preferência.

❌
```c
double divide(double a, double b)
{
if (b!=0){
return NAN;
}
else{
return a/b;
}
}
```

✔️
```c
double divide(double a, double b)
{
    if (b != 0) {
        return a / b;
    } else {
        return NAN;
    }
}
```

A indentação torna o código mais fácil de ler. Ela ajuda o leitor a ver qual código está aninhado e onde, e também onde estruturas como declarações `if` e loops começam e terminam.

## Espaçamento

Pode parecer trivial, mas manter um bom espaçamento ao longo do seu programa ajuda a que seu código seja mais legível para os olhos humanos. A maioria dos programadores segue as convenções de espaçamento abaixo para seus programas:

| Código                     | Bom                             | Ruim                        |
| -------------------------: | ------------------------------- | --------------------------- |
| Cabeçalho de função        | `int funcao(int a, char *b)`   | `int funcao (int a,char *b){` |
| Chamada de função          | `teste(107, 3, "string");`      | `teste(107,3,"string");`    |
| Loop `for`                 | `for (int i = 0; i < 5; i++) {` | `for(int i=0;i<5;i++){`     |
| Loop `while`               | `while (condicao) {`            | `while(condicao){`          |
| Inicialização de variáveis | `int x = -5 * j + y % 2;`       | `int x=-5*j+y%2;`          |   

Observe o espaçamento nas expressões. Geralmente, deve-se sempre deixar um espaço de cada lado de um operador (+, -, =, etc.). As únicas exceções são ++, --, e usar - para expressar números negativos (isto é, -5).

### Espaçamento entre funções

Semelhante ao espaçamento dentro de linhas de código, queremos garantir que tenhamos espaçamento na estrutura de nosso código para manter nosso código com aspecto legível. Você deve sempre incluir uma linha em branco entre funções para garantir a legibilidade de seu código.

```c
int soma(int a, int b)
{

}

int subtrai(int a, int b)
{

}
```

### Espaçamento entre linhas

Procure separar com espaço os blocos de código que são do mesmo "contexto". No exemplo abaixo, qual código fica mais fácil de ser lido?!

❌
```c
int main(void)
{
    int idade_pessoa_b = 4;
    char nome_pessoa_a[] = "Frederico Vampiro";
    char nome_pessoa_b[] = "Luca";
    printf("\n%s tem %d anos.", nome_pessoa_b, idade_pessoa_b);
    int idade_pessoa_a = 485;
    printf("\n%s tem %d anos.", nome_pessoa_a, idade_pessoa_a);
    int idade_pessoa_c = -99;
    char nome_pessoa_c[] = "Marciano";
    printf("\n%s tem %d anos.", nome_pessoa_c, idade_pessoa_c);
}
```

✔️
```c
int main(void)
{
    char nome_pessoa_a[] = "Frederico Vampiro";
    int idade_pessoa_a = 485;
    printf("\n%s tem %d anos.", nome_pessoa_a, idade_pessoa_a);
    
    char nome_pessoa_b[] = "Luca";
    int idade_pessoa_b = 4;
    printf("\n%s tem %d anos.", nome_pessoa_b, idade_pessoa_b);
    
    char nome_pessoa_c[] = "Marciano";
    int idade_pessoa_c = -99;
    printf("\n%s tem %d anos.", nome_pessoa_c, idade_pessoa_c);
}
```

## Chaves

Com exceção da declaração de funções, um `{` deve ser colocado no final da linha que o abriu; já um `}` deve ser colocado em uma linha sozinha no mesmo nível de indentação que a linha com o `{`, somente se esse `}` terminar uma declaração ou terminar o corpo de uma função. Por exemplo, não há quebra de linha após o `}` se este for seguido por `else`.

❌
```c
void inicializa_matriz_com_val(int n_lin,int n_col,int mat[n_lin][n_col],int val){
    for(int i=0;i<n_lin;i++)
    {
        for(int j=0;j<n_col;j++)
        {
            if (mat[i][j]!=val)
            {
                mat[i][j]=val;
            }
            else {
                printf("\nA posição <%d, %d> da matriz já possui o valor %d!",i,j,val);
            }
        }
    }
}
```

✔️
```c
void inicializa_matriz_com_val(int n_lin, int n_col, int mat[n_lin][n_col], int val)
{
    for (int i = 0; i < n_lin; i++) {
        for (int j = 0; j < n_col; j++) {
            if (mat[i][j] != val) {
                mat[i][j] = val;
            } else {
                printf("\nA posição <%d, %d> da matriz já possui o valor %d!", i, j, val);
            }
        }
    }
}
```

Ficou com alguma dúvida? Entre em contato comigo pelo [Discord][discord-monitoria] ou pelo e-mail [mvisentini@inf.ufsm.br][email-monitor].

[Voltar para a página inicial][pagina-inicial]

<!-- Links -->

[ccs]:               https://users.ece.cmu.edu/~eno/coding/CCodingStandard.html              "C Coding Standard"
[discord-monitoria]: https://discord.gg/kSBnGsRvnB                                           "Servidor da monitoria da disciplina no Discord"
[email-monitor]:     mailto:mvisentini@inf.ufsm.br                                           "E-mail do monitor"
[pagina-inicial]:    ../README.md                                                            "Voltar para a página inicial"
