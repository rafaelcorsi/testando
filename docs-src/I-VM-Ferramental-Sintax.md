# Linguagem VM




São suportadas as seguintes operações aritméticas na pilha:

- add 
     - executa: X + Y
     
- sub 
     - executa: X - Y
     
- neg
     - executa: $- Y$  (complemento de dois)
     
- eq 
     - compara X == Y 
          - True : resulta em b"11111111111111111", 0xFFFF
          - False: resulta em b"0000000000000000"", 0x0000
          
- gt
     - compara X > Y 
          - True : resulta em b"11111111111111111", 0xFFFF
          - False: resulta em b"0000000000000000"", 0x0000
          
- lt 
     - compara X < Y 
          - True : resulta em b"11111111111111111", 0xFFFF
          - False: resulta em b"0000000000000000"", 0x0000
          
- and 
     - executa: X and Y (bit a bit)
     
- or
     - executa: X or Y (bit a bit)
     
- not
     - executa: not Y (bit a bit)

## Label

Labels são definidos pelo keyword **label** seguido de seu **nome** :

> label **nome**

São utilizados para endereçar o código em uma condição de goto.

## Goto

Existem dois tipos de GOTO, condicional (**if-goto**) e incondicional (**goto**). No condicional o salto é realizado caso a condição não for Falsa (verifica sempre o último valor da pilha).

> goto **nome**

> if-goto **nome**


## Função

A seguir definições de funções :

### Declaração de função 

Uma função é definida pelo keyword **function** seguido do seu **nome** e quantidade de variáveis locais **n** na estrutura a seguir :

> function **nome** **n**

Toda função em VM deve possuir um retorno, definido pelo keyword **return**

### Chamada de função

Uma função em VM é chamada pelo keyword: **call** seguido do **nome** da função e da quantidade **m** de parâmetros passados para essa função.

> call **nome** **m**

### Parâmetros

Os parâmetros de uma função são passados na própria pilha.
