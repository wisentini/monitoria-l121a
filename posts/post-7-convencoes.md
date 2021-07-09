# Convenções na linguagem C

Aqui estão algumas dicas de como escrever um código minimamente legível em C. Eu sei que parece perda de tempo, mas um código mal escrito pode custar um tempo precioso na hora de sua análise. É claro que você não precisa seguir o que está descrito aqui a risca, afinal, são apenas dicas; no entanto, tente se basear nelas.

## Recomendação

Recomendo fortemente tirar 30 minutos do seu dia para ler isso: [C Coding Standard][ccs].

## Funções

Tente limitar o número de linhas das suas funções entre 20 e 25, no máximo. Se ultrapassar muito além disso, é certo que ela pode ser dividida em duas ou mais funções. Lembre-se, uma função deve resolver um problema específico.

## Nomes

Procure nomear variáveis e funções de modo que seja possível identificar o que elas representam/fazem apenas pela leitura do seu nome.

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

Opte sempre por indentar seu código com 4 espaços, para facilitar a legibilidade.

❌
```c
double divide(double a, double b)
{
if (b!=0){
return NAN;
}else{
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

## Espaçamento

### Operandos/operadores e estruturas

Coloque sempre espaços entre operandos/operadores e estruturas da linguagem (com exceção de chamadas de funções, em que o nome da função deve estar junto ao `{`) .

❌
```c
void inicializa_matriz(int n_lin,int n_col,int mat[n_lin][n_col])
{
    for(int i=0;i<n_lin;i++){
        for(int j=0;j<n_col;j++){
            mat[i][j]=0;
        }
    }
}
```

✔️
```c
void inicializa_matriz(int n_lin, int n_col, int mat[n_lin][n_col])
{
    for (int i = 0; i < n_lin; i++) {
        for (int j = 0; j < n_col; j++) {
            mat[i][j] = 0;
        }
    }
}
```

### Linhas

Procure separar com espaço os blocos de código que são do mesmo "contexto". No exemplo abaixo, qual código fica mais fácil de ser lido?! Observe que no exemplo corrigido, as linhas são organizadas de acordo com um padrão.

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

## "{}"

Com exceção da declaração de funções, sempre use o `{` ao lado da estrutura em questão e não na linha abaixo dela.

❌
```c
void inicializa_matriz(int n_lin,int n_col,int mat[n_lin][n_col])
{
    for(int i=0;i<n_lin;i++)
    {
        for(int j=0;j<n_col;j++)
        {
            if (mat[i][j]!=0)
            {
                mat[i][j]=0;
            }
        }
    }
}
```

✔️
```c
void inicializa_matriz(int n_lin, int n_col, int mat[n_lin][n_col])
{
    for (int i = 0; i < n_lin; i++) {
        for (int j = 0; j < n_col; j++) {
            if (mat[i][j] != 0) {
                mat[i][j] = 0;
            }
        }
    }
}
```

## `switch`

❌
```c
bool quer_sair_do_jogo(char opcao)
{
    switch(opcao)
    {
    case 'S':
    case 's':
        return true;
        break;
    case 'N':
    case 'n':
        return false;
        break;
    default:
        exit(1);
        break;
    }
}
```

✔️
```c
bool quer_sair_do_jogo(char opcao)
{
    switch (opcao) {
        case 'S':
        case 's':
            return true;
        case 'N':
        case 'n':
            return false;
        default:
            exit(1);
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
