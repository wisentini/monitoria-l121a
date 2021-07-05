# Cores :art:

No [trabalho 2][t2] vocês devem manipular cores de caracteres na tela, então, aqui vai uma ajudinha!

O professor Benhur deixou na descrição do trabalho duas funções:

```c
// os próximos caracteres serão escritos na cor normal
void cor_normal(void)
{
  printf("%c[0m", 27);
}

// os próximos caracteres serão escritos na cor rl, gl, bl com fundo na cor rf, gf, bf
// Os valores r, g, b representam o nível de vermelho, verde e azul da cor desejada, e devem estar entre 0 e 255
void muda_cor(int rl, int gl, int bl, int rf, int gf, int bf)
{
  printf("%c[38;2;%d;%d;%d;48;2;%d;%d;%dm", 27, rl, gl, bl, rf, gf, bf);
}
```

A função `muda_cor()` serve, como o próprio nome já diz, para mudar a cor dos caracteres escritos após a chamada da função.

Já a função `cor_normal()` faz a cor dos caracteres voltar ao normal.

Sempre que você chamar `muda_cor()`, deve chamar também `cor_normal()` em algum momento do programa. Caso contrário, tudo
que vier pela frente terá sua cor modificada.

Exemplo:

```c
int main(void)
{
    // Define a cor da letra em RGB
    // A união dessas três cores produzirá
    // uma cor para a letra do caractere
    // Nesse exemplo, a cor da letra será roxa
    int cor_verm_letra = 128;
    int cor_verd_letra = 0;
    int cor_azul_letra = 128;
    
    // Define a cor do fundo em RGB
    // A união dessas três cores produzirá
    // uma cor para o fundo do caractere
    // Nesse exemplo, a cor do fundo será laranja
    int cor_verm_fundo = 255;
    int cor_verd_fundo = 165;
    int cor_azul_fundo = 0;
    
    // A mensagem que nós vamos usar para testar
    // as funções de manipulação de cores
    char mensagem[] = "Olá, isso é um teste!";
    
    // Aqui será impressa a mensagem sem formatação
    // como nós já estamos acostumados
    printf("%s", mensagem);
    
    // Mas, quando eu chamo a função `muda_cor()`,
    // ela muda a cor de todos os caracteres
    // que vierem pela frente, até encontrar a
    // função `cor_normal()`
    muda_cor(cor_verm_letra, cor_verd_letra, cor_azul_letra, cor_verm_fundo, cor_verd_fundo, cor_azul_fundo);
    
    // Agora, a nossa mensagem vai ser impressa
    // com as letras na cor roxa e o fundo na
    // cor laranja (combinação linda, eu sei)
    printf("%s", mensagem);
    
    // Como nós já mudamos a cor da mensagem, agora
    // podemos voltar à nossa cor original, então,
    // é chamada a função `cor_normal()`
    cor_normal();
}
```

Execute esse código no Online GDB para ver o resultado: [https://onlinegdb.com/auXECn2Ue][codigo-gdb].

Ficou com alguma dúvida? Entre em contato comigo pelo [Discord][discord-monitoria] ou pelo e-mail [mvisentini@inf.ufsm.br][email-monitor].

[Voltar para a página inicial][pagina-inicial]

<!-- Links -->

[t2]:                https://github.com/BenhurUFSM/l121a/blob/main/Assuntos/11.md#trabalho-2 "Trabalho 2"
[codigo-gdb]:        https://onlinegdb.com/auXECn2Ue                                         "Código no Online GDB"
[discord-monitoria]: https://discord.gg/kSBnGsRvnB                                           "Servidor da monitoria da disciplina no Discord"
[email-monitor]:     mailto:mvisentini@inf.ufsm.br                                           "E-mail do monitor"
[pagina-inicial]:    ../README.md                                                            "Voltar para a página inicial"
