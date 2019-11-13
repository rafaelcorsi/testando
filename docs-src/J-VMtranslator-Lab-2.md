
O VMTranslator é um programa escrito em Java que faz a tradução de códigos escrito na linguagem VM definida no curso e traduz para linguagem Assembly do computador Z01.

## Testando



``` bash
$. /genJar.py
$ ./testeVMtraslator.py
```

Como o teste executa:

```
             genJAR.py
                 |   
                 |   
                 V
                 
            VMTranslator          Assembler            Z01-Simulator  ------------------
 arquivo.vm -------------> .nasm -----------> .hack  > ------------>  - Verifica saída -
                                                                      ------------------
                 ^
                 |   
                 |- Desenvolvido no projeto J 
                                                                    
```

1. Traduzir o arquivo `.vm` -> `.nasm`

Para isso foi criado alguns programas (`I-VM/src/vmExamples/`) em VM muito específicos que testam somente um comando, ou uma parte da tradução do `VMTranslator`. Por exemplo o teste `SimpleAdd` possui somente a seguinte linha :

```vm
add
```

Esse teste foi criado para testar o `Code.writeArithmetic` no caso de um comando `add`. Para isso, antes da execução desse código, o simulador faz a inicialização da RAM, simulando valores na pilha e já configurando o SP para uma situação real. A memória antes da execução da instrução add é a seguinte:

```
    0 : 0000000100000010;
  256 : 0000000000000010;
  257 : 0000000000000100;
  258 : 0000000000000000;
```

> `I-VM/tests/tst/SimpleAdd/SimpleAdd0_in.mif`

Espera-se o resultado final após a execução do comando add :

```
    0 : 0000000100000001
  256 : 0000000000000110
```

## teste:

A seguir uma lista de como cada parte do VMTranslator é testado:

### `code.writePushPop`

- pop
  - SimplePopTemp  : pop temp ...
  - SimplePopLocal : pop local ...
  - SimplePopThat  : pop that ...
  - SimplePopThis  : pop this ...
  
- push
  - SimplePushConst : push constant .... 
  - SimplePushTemp  : push tempo ....
  - SimplePushLocal : push local ....
  - SimplePushArg   : push argument ...
  - SimplePushThis  : push this ...
  - SimplePushThat  : push that ...

### code.writeArithmetic

- SimpleAdd : add
- SimpleNeg : neg
- SimpleSub : sub
- SimpleEq  : eq
- SimpleGt  : gt
- SimpleLt  : lt
- SimpleAnd : and
- SimpleOr  : or
