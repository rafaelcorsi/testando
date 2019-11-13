```diff
+ Realizar em dupla/trio (dois por grupo)
```

**Você é `Scrum Master` e não sabe por onde começar? De uma olhada nessas dicas: [Vixi! Sou Scrum Master](Vixi!-Sou-Scrum-Master)**

- [ ] [Atualize o Z01-Tools!](https://github.com/Insper/Z01.1/wiki/Dicas-GIT#atualizando-submodules) submodule antes de começar. Nesse projeto tivemos umas melhorias na infra do curso.

O objetivo desse laboratório é o de trabalharmos com o controle dos sinais da ULA para validarmos e entendermos as operações da unidade de processamento do nosso computador.

1. Programando FPGA com ULA
1. Entendendo funções das chaves e LEDs
1. Controlando ULA para realizar operações específicas (exercícios)

# Programando FPGA

Com a FPGA plugada no PC e ligada, execute o script `programFPGA.py` da pasta do projeto D. Esse script irá realizar a programação da FPGA com o hardware da Unidade Lógica Aritmética - ULA que vocês terão que implementar. 

Nesse os controles da ULA estão mapeados para as chaves da FPGA, a saída da ULA foi mapeada para LEDs: como ilustrado as figuras a seguir:

![ULA Z01](figs/D-ULA/D-ula-fpga-1.png)

![ULA FPGA map](figs/D-ULA/D-ula-fpga-2.png)

Como isso é feito em VHDL? De uma olhada no top level do projeto (`D-UnidadeLogicaAritmetica/src/TopLevel.vhd`)

``` vhd
  ula0: ALU port map (
    x                  => x,
    Y                  => y,
    Zx                 => SW(0),
    Nx                 => SW(1),
    Zy                 => SW(2),
    Ny                 => SW(3),
    F                  => SW(4),
    No                 => SW(5),
    Zr                 => LEDR(8),
    Ng                 => LEDR(9),
    Saida(7 downto 0)  => LEDR(7 downto 0),
    Saida(15 downto 8) => Open
    );
```

Note que ULA que iremos desenvolver no projeto D terá **16 bits** de largura, porém como temos um limite de LEDs e botões na FPGA, estamos ignorando os valores mais significativos, sem afetar o projeto.

# Controlando ULA

Com a FPGA programada podemos testar a ULA modificando seus sinais de controle. A seguir uma proposta de operações lógicas devem ser realizadas na FPGA, seus sinais de controle e resultado devem ser anotados nas tabelas.

> :warning: O projeto **FIXA** as entradas da ULA com os valores:
> 
> - X = 0x73  
> - Y = 0x5F

-----------

### Out = X

- Configure os controles da ULA para fazer com que a saída da ULA seja a entrada **X**

-----------

### Out = Y

- Configure os controles da ULA para fazer com que a saída da ULA seja a entrada Y

-----------

### Out = !Y

- Configure os controles da ULA para fazer com que a saída da ULA seja a entrada a entrada Y negada

-----------

### Out = 0

- Faça com que a saída da ULA seja 0

-----------

### Out = 1

- Faça com que a saída da ULA seja 1

-----------

### Out = X + Y

- Faça com que a saída da ULA seja a entrada X + a entrada Y

-----------

### (difícil) Out = X ou Y

- Faça com que a saída da ULA seja X ou Y

-----------

### (difícil) Out = X - Y

- Faça com que a saída da ULA seja a entrada X menos a entrada Y

-----------