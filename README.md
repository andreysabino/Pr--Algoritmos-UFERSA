# Introdução a Linguagem C

A linguagem C é uma linguagem de programação de propósito geral, **imperativa** e de **alto desempenho**. Desenvolvida por Dennis Ritchie nos laboratórios Bell na década de 1970, ela se tornou a base para muitos sistemas operacionais (como o Linux) e outras linguagens de programação (como C++, Java e C#).

---

## Por Que Aprender C?

* **Controle:** C oferece um alto nível de controle sobre o hardware do computador, o que a torna ideal para programação de sistemas e embarcada.
* **Eficiência:** Programas em C são geralmente muito rápidos, pois a linguagem compila diretamente para código de máquina otimizado.
* **Base Sólida:** Entender C fornece uma compreensão fundamental de como os computadores funcionam, facilitando o aprendizado de outras linguagens de programação.
* **Amplamente Utilizada:** Apesar de sua idade, C ainda é extremamente relevante em diversas áreas, incluindo desenvolvimento de sistemas operacionais, drivers de dispositivo, jogos e sistemas embarcados.

---

## Estrutura Básica de um Programa C

Todo programa em C tem uma estrutura fundamental. Veja um exemplo simples:

```c
#include <stdio.h> // Inclui a biblioteca padrão de entrada e saída

int main() { // Função principal, onde a execução do programa começa
    printf("Olá, mundo!\n"); // Imprime "Olá, mundo!" no console
    return 0; // Indica que o programa foi executado com sucesso
}
```

* `#include <stdio.h>`: É uma **diretiva de pré-processador**. Ela "inclui" o conteúdo da biblioteca padrão de entrada e saída (`stdio.h`), que contém funções como `printf()` para imprimir texto na tela.
* `int main()`: Esta é a **função principal** do programa. Todo programa em C precisa de uma função `main()`, pois é a partir dela que a execução começa. O `int` indica que a função retornará um valor inteiro, e `return 0;` é o valor de retorno, que indica que o programa foi executado sem erros.
* `{ }`: As chaves definem o **bloco de código** da função `main()`.
* `printf("Olá, mundo!\n");`: Esta é uma **instrução**. `printf()` é uma função da biblioteca `stdio.h` que imprime uma string (texto) no console. O `\n` é um **caractere de escape** que representa uma nova linha.
* `;`: O **ponto e vírgula** é usado para terminar cada instrução em C.

---

## Declaração de Variáveis

Variáveis são como "caixinhas" na memória do computador que guardam valores. Antes de usar uma variável, você precisa **declarar** ela, informando o seu **tipo** e o seu **nome**.

### Sintaxe Básica

tipo nome_da_variavel;

| Tipo de Dado | Descrição                                        | Tamanho (típico) | Exemplo                       |
| :----------- | :----------------------------------------------- | :--------------- | :---------------------------- |
| `int`        | Números inteiros                                 | 4 bytes          | `int idade = 30;`             |
| `float`      | Números de ponto flutuante (com casas decimais)  | 4 bytes          | `float preco = 19.99f;`       |
| `double`     | Números de ponto flutuante de precisão dupla     | 8 bytes          | `double pi = 3.14159265;`     |
| `char`       | Um único caractere                               | 1 byte           | `char letra = 'A';`           |


## Exemplos de Declaração e Inicialização

```c
#include <stdio.h>

int main() {
    // Declaração de variáveis
    int quantidade;
    float altura;
    char inicial;

    // Inicialização (atribuição de valor)
    quantidade = 100;
    altura = 1.75f; // O 'f' indica que é um float literal
    inicial = 'J';

    // Declaração e inicialização na mesma linha
    double peso = 75.5;
    int ano_atual = 2024;
    char status = 'A';

    printf("Quantidade: %d\n", quantidade);
    printf("Altura: %.2f metros\n", altura); // .2f formata para 2 casas decimais
    printf("Inicial: %c\n", inicial);
    printf("Peso: %.1lf kg\n", peso); // .1lf formata para 1 casa decimal para double
    printf("Ano atual: %d\n", ano_atual);
    printf("Status: %c\n", status);

    return 0;
}
```
Modificadores de Formato (`%d`, `%f`, `%c`, `%lf`): São usados com `printf()` para indicar o tipo de dado que você está imprimindo.

---

## Tipos de Condicionais

Condicionais permitem que seu programa tome decisões e execute blocos de código diferentes com base em certas condições.

### 1. if Declaração

A estrutura if executa um bloco de código se uma condição for verdadeira.

```c
if (condicao) {
    // Código a ser executado se a condição for verdadeira
}
```

Exemplo:

```c
#include <stdio.h>

int main() {
    int idade = 18;

    if (idade >= 18) {
        printf("Você é maior de idade.\n");
    }
    return 0;
}
```

> **Observação:** No VisualG, o equivalente ao `if` em C é o comando `se ... então`.

---

### 2. if-else Declaração

A estrutura if-else executa um bloco de código se a condição for verdadeira, e outro bloco se a condição for falsa.

```c
if (condicao) {
    // Código se a condição for verdadeira
} else {
    // Código se a condição for falsa
}
```

Exemplo:

```c
#include <stdio.h>

int main() {
    int nota = 7;

    if (nota >= 7) {
        printf("Aprovado!\n");
    } else {
        printf("Reprovado.\n");
    }
    return 0;
}
```

> **Observação:** No VisualG, o equivalente é `se ... então ... senao`.

---

### 3. if-else if-else Declaração (Múltiplas Condições)

Para testar múltiplas condições em sequência.

```c
if (condicao1) {
    // Código se a condição1 for verdadeira
} else if (condicao2) {
    // Código se a condição2 for verdadeira
} else {
    // Código se nenhuma das condições anteriores for verdadeira
}
```

Exemplo:

```c
#include <stdio.h>

int main() {
    int pontuacao = 85;

    if (pontuacao >= 90) {
        printf("Sua nota é A.\n");
    } else if (pontuacao >= 80) {
        printf("Sua nota é B.\n");
    } else if (pontuacao >= 70) {
        printf("Sua nota é C.\n");
    } else {
        printf("Sua nota é D ou F.\n");
    }
    return 0;
}
```

> **Observação:** No VisualG, você pode usar `se ... então ... senao se ... então ... senao` para múltiplas condições.

---

### 4. switch Declaração

A estrutura switch é usada para executar blocos de código diferentes com base no valor de uma única variável ou expressão. É útil quando você tem muitas opções para testar.

```c
switch (expressao) {
    case valor1:
        // Código se expressao for igual a valor1
        break; // Importante para sair do switch
    case valor2:
        // Código se expressao for igual a valor2
        break;
    default:
        // Código se nenhum dos casos anteriores for correspondido
        break;
}
```

A expressao deve ser de um tipo inteiro (ou um tipo que possa ser convertido para inteiro, como char).  
Cada case compara a expressao com um valor.  
O comando break; é crucial para sair do switch após um caso ser correspondido. Sem ele, o código continuará executando os cases seguintes (comportamento conhecido como "fall-through").  
default: é opcional e é executado se nenhum dos cases anteriores for correspondido.

Exemplo:

```c
#include <stdio.h>

int main() {
    char opcao = 'B';

    switch (opcao) {
        case 'A':
            printf("Você escolheu a opção A.\n");
            break;
        case 'B':
            printf("Você escolheu a opção B.\n");
            break;
        case 'C':
            printf("Você escolheu a opção C.\n");
            break;
        default:
            printf("Opção inválida.\n");
            break;
    }
    return 0;
}
```

> **Observação:** No VisualG, o equivalente ao `switch` em C é o comando `escolha ... caso ...`, usado para selecionar entre várias opções.

---

## Estruturas de Repetição

Estruturas de repetição permitem executar um bloco de código várias vezes, enquanto uma condição for verdadeira.

### 1. while

Executa o bloco enquanto a condição for verdadeira.

```c
while (condicao) {
    // Código a ser executado repetidamente
}
```

Exemplo:

```c
#include <stdio.h>

int main() {
    int i = 0;
    while (i < 5) {
        printf("%d\n", i);
        i++;
    }
    return 0;
}
```

> **Observação:** No VisualG, o equivalente ao `while` em C é o comando `enquanto ... faça`.

---

### 2. do-while

Semelhante ao `while`, mas garante que o bloco será executado pelo menos uma vez.

```c
do {
    // Código a ser executado pelo menos uma vez
} while (condicao);
```

Exemplo:

```c
#include <stdio.h>

int main() {
    int i = 0;
    do {
        printf("%d\n", i);
        i++;
    } while (i < 5);
    return 0;
}
```

> **Observação:** No VisualG, o equivalente é `repita ... até`.

---

### 3. for

Usado quando se sabe exatamente quantas vezes o bloco deve ser executado.

```c
for (inicializacao; condicao; incremento) {
    // Código a ser executado
}
```

Exemplo:

```c
#include <stdio.h>

int main() {
    for (int i = 0; i < 5; i++) {
        printf("%d\n", i);
    }
    return 0;
}
```

> **Observação:** No VisualG, o equivalente ao `for` em C é o comando `para ... de ... até ... faça`.

---

> **Aviso:**  
> Todos os exemplos deste material usam apenas uma função, a `main`. Ainda não utilizamos funções próprias (como procedimentos no VisualG).  
> Se você já conhece procedimentos/funções do VisualG e quiser se aventurar em funções em C, fique a vontade para perguntar ou pesquisar mais sobre o assunto!

## Referências

- **Livro:** *Introdução a Estruturas de Dados - Com Técnicas de Programação em C* (2ª Edição)  
  Waldemar Celes, Renato Cerqueira, José Lucas Rangel  
- [Linguagem C: Guia Completo – Embarcados](https://embarcados.com.br/linguagem-c-guia-completo/)
- [Introdução à Linguagem C – PUCRS](https://www.inf.pucrs.br/~pinho/LaproI/IntroC/IntroC.htm)
- [O Manual do Iniciante em C – freeCodeCamp](https://www.freecodecamp.org/portuguese/news/o-manual-do-iniciante-em-c-aprenda-o-basico-sobre-a-linguagem-de-programacao-c-em-apenas-algumas-horas/)

---

> **Colabore!**  
> Se você deseja contribuir com este material, fique a vontade para sugerir melhorias, correções ou adicionar novos conteúdos. 

> Basta fazer um pull request que irei avaliar e, se estiver de acordo, aceitarei com prazer. Assim, podemos construir juntos um material cada vez melhor.
