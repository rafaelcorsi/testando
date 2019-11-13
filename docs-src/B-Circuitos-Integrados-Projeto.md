> Esse é o único projeto que irá ter sobreposição de prazo de entrega, a ideia é que o grupo faça a divisão de trabalho para maximizar a produtividade.

# Descrição 

Esse projeto tem como objetivo trabalhar com os conceitos básicos de portas lógicas feitas em circuitos integrados. Cada grupo receberá uma equação lógica que deverá implementar e caberá ao grupo decidir a melhor forma de separação de trabalho que privilegie a distribuição de tarefas.

## Instruções

Deve-se implementar a mesma equação **lógica recebida no projeto A** (individual por grupo) via os circuitos integrados da família 40xx lógicos recebidos em sala. O circuito deve ser realizado na protoboard.

### Materiais extras

Cada grupo recebeu os seguintes CIs:

- 2x 4001 – NOR
- 2x 4013 – FF D Type
- 2x 4070 – XOR
- 2x 4073 – AND
- 2x 4075 – OR
- 2x 4072 – OR 4

Poderão utilizar a quantidade que material recebido que acharem necessário para realizarem a equação lógica, não podendo superar a quantidade aqui descrita.

> Vocês podem substituir possíveis CIs / transistores queimados.

### Entradas

Pode-se utilizar como entrada do sistema (A,B,C,...) *jumpers* que estarão hora conectados em `GND (0)` ou `VCC (1)`. 

> A cada entrada um LED de cor diferente pode ser utilizado para de forma fácil saber quais são as entradas do sistema.

## Saída

A saída final do sistema deve ser representada com um LED, sendo aceso indicando lógica 1 e apagado lógica 0.

## Documentação

Um documento descrevendo a solução empregada deve ser apresentando. O documento deve conter : A equação lógica original, diagrama de blocos lógico ( contendo as portas lógicas) e o diagrama de elétrico/montagem (quais pinos de quais componentes foram utilizados).

**O documento deve descrever como foi feito a divisão do trabalho em grupo.**

### Validação

Uma tabela verdade do circuito deve ser apresentada e em aula e uma demonstração que o circuito representa a tabela deve ser feita.

## Entrega 

A entrega da documentação deve ser realizada via github no fork realizado na disciplina [(verifique o lab 2 do projeto A)](A-Transistores-Lab-2).

O documento deve ser colocado na pasta do repositório do grupo: `Z01.1/B-CircuitosIntegrados/Documentacao.pdf`

``` diff
- Na entrega todos os integrantes do grupo já 
- devem fazer parte do repositório.
```

##### Rubricas

As rubricas são progressivas A(B(C())).

| Nota máxima | Descritivo                                             |
|-------------|--------------------------------------------------------|
| A+          | - Adicionado botão na entrada do sistema (A,B,C)       |
|             |                                                        |
| B           | - Documentação correta                                 |
|             |                                                        |
| C           | - Circuito funcionado                                  |
|             | - Um item da documentação errado/faltando              |
|             | - Entregue fora do prazo original                      |
|             |                                                        |
| D           | - Entregue fora do prazo máximo                        |
|             | - Circuito não funcionando                             |
|             | - Documentação com mais de dois itens errados/faltando |
|             |                                                        |
| I           | - Não entregue                                         |

