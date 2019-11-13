Vamos agora fazer a implementação do comando `push constant 3` no VMtranslator.

1. Crie o projeto no IntelliJ da mesma maneira que do projeto `H-Assembler`
    - o arquivo maven está na pasta `J-VMTranslator/VMtranslator`

Nesse projeto vocês terão que mexer apenas no `code.java`, os demais módulos já estão prontos (similar ao projeto do Assembler, temos nesse o `parser`, `VMTranslator`, ...).

## Editando o `code.java`

No `code.java` encontre a implementação do método `push` , linha 119

```java

public void writePushPop(Parser.CommandType command, String segment, Integer index) {
...
...
...
 else if (command == Parser.CommandType.C_PUSH) {
            commands.add(String.format("; %d - PUSH %s %d", lineCode++ ,segment, index));

            if (segment.equals("constant")) {
            
            }

```

Essa método é chamado sempre que um comando `push/pop` for ser interpretado, exemplo:

- `push constant 3`
- command: `C_PUSH`
- segment: `constant`
- Index: `3`

Precisamos agora traduzir a execução desse comando em `vm` para `nasm`, seguindos os passos a seguir:

1. Carregar o valor da constante em um registrador disponível
2. Busca no StackPointer(SP) o endereço da posição vazia da stack
3. Move o valor do Index (no caso 3) para essa posição vazia
4. Incrementa SP em um

Exemplo de implementação do segundo, deve se adicionar as instruções na lista de comandos
```java
commands.add("leaw $SP,%A");
commands.add("movw (%A),%A");
```

Para testar o projeto VMtranslator, não há testes unitários disponíveis, no entanto, podemos já realizar o teste de integração direto (simulação), usando o `testeVMtranslator.py`. No caso do `push constant`, temos o teste SimplePushConst, bastando apenas habilitar este teste na config (`tests/config.txt`). Se observar o arquivo, irá perceber que existem diversos outros testes básicos, como `SimplePushLocal`, `SimplePopLocal` e outros ([lista](https://github.com/Insper/Z01.1/wiki/J-VMtranslator-Lab-2#teste)) que podem ser habilitados conforme forem implementado estes recursos no seu VMtranslator.
