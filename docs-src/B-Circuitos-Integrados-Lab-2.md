# B - CI - Lab 1

!!! note
    Deve ser realizado para a entrega do projeto B.

## Referenciando a raiz

!!! warning
    Somente o **mediador**. Todos devem acompanhar!

- https://gist.github.com/CristinaSolana/1885435
- https://help.github.com/articles/syncing-a-fork/

Uma vez clonado o repositório, você deve entrar na pasta via o terminal:

``` bash
$ cd Z01.1-NomeDoGrupo
```

Uma vez na pasta do repositório precisamos agora indicar para o repositório original na qual o repositório que deu origem a esse fork, para isso devemos executar a seguinte linha de código: 

``` bash
$ git remote add upstream https://github.com/insper/Z01.1
```

Para verificar se deu certo, execute:

``` bash
$ git remote -v
```

E deve aparecer além do link para o repositório de vocês a referência ao repositório original:

``` bash
upstream	https://github.com/insper/Z01.1 (fetch)
upstream	https://github.com/insper/Z01.1 (push)
```

## Atualizando repositório

Para atualizar o repositório do grupo de vocês com as novas atualizações inseridas no repositório da disciplina basta executar:

Atualize o repositório raiz para o `branch upstream`

``` bash
$ git fetch upstream
```

Agora precisamos realizar um merge desse branch (que contém as atualizações do repositório da disciplin) com o master:

``` bash
$ git checkout master
$ git merge upstream/master
```

Agora precisamos submeter essa atualização para o repositório remoto a fim de todos do grupo terem acesso a versão mais nova.

``` bash
$ git push origin master
```

# Github 

!!! tip "git"
    GitHub Inc. is a web-based hosting service for version control using Git. It is mostly used for computer code. It offers all of the distributed version control and source code management functionality of Git as well as adding its own features. [Wikipedia](https://en.wikipedia.org/wiki/GitHub)
    
    - [http://github.com](http://github.com)

Nessa disciplina iremos utilizar não só a ferramenta principal do github, que é o servidor de repositórios git mas todas as outras ferramentas já integradas na plataforma para gestão e acompanhamento de projeto. Para isso será alteramos algumas configurações no repositório:

!!! example "Execute"
    Na página do seu repositório vá em: `Settings -> Features ->` e ative `Issues ` e `Project`.

A seguir alguns termos que serão utilizados nesse lab e é importante revisar/conhecer:

- **Github Project**: Ferramenta do github para gerenciamento de projetos (estilo Kambam), cada repositório pode ter N projetos, e o github automatiza o processo de todo/doing/done deixando de maneira visual as tarefas.

- **github issues**: Plataforma do github para criação de tarefas/ reportar erros. As tarefas aqui criadas serão associadas a um projeto específico e a um grupo de pessoas específicas.

- **Branch**: Ramo criado para implementar um feature/ correção de bug que será futuramente incorporado no master (merge)

- **Master**: Ramo principal do projeto, gerenciado pelo Scrum Master

- **Pull-request**: Maneira de um lider de projeto receber alterações a um projeto e ter controle do que será aceito ou não. Na maioria dos casos o pull-request é criado por um usuário e revisado por outro. Quem for fazer a eletiva de [`Desenvolvimento Aberto`](https://igordsm.github.io/dev-aberto/aulas.html) do [Prof. Igor](https://github.com/igordsm) verá bem a fundo essa questão. 

![Pull-Request](figs/B-CI/pull-request.png)

## Adicionando nomes ao `INTEGRANTES.json`

!!! warning
    Deve ser realizado individualmente!  

> - [ ] Gerar mudanças no repositório local
> - [ ] Enviar mudanças para o repositório remoto
> - [ ] Gerar pull-request


**Cada integrante** do grupo deve editar o documento com na raiz do projeto com nome `INTEGRANTES.json` 
e adicionar a esse arquivo o seu nome, e-mail (insper) e usuário gituhb. Conforme o exemplo a seguir:

``` json
{
  "aluno-1": {
    "nome": "Rafae Corsi",
    "email-insper": "rafael.corsi@insper.edu.br",
    "user-github": "rafaelcorsi"
  },
```

!!! warning 
    Uma única pessoa não deve editar o documento com todos os nomes.

-----------
> - [x] Gerar mudanças no repositório local
> - [ ] Enviar mudanças para o repositório remoto
> - [ ] Gerar pull-request
-----------

## Criando um branch para fazer o commit.

A fim de realizarmos um pull-request ao mediador do projeto é preciso salvarmos essas modificações em um novo branch. O comando a seguir faz isso:

``` bash
$ # criando um novo branch
$ git checkout -B $NOME
```

!!! tip "git"
    Substitua nos comandos o termo `$NOME` pelo seu nome.

Agora vamos fazer um commit com o seu nome nesse novo branch:

``` bash
$ git commit -am "Adicionado meu $NOME ao arquivo"
```

Será necessário enviarmos esse branch ao servidor (github) antes de realizarmos o `pull-request`:

``` bash
$ # enviando o branch para o repositório remoto
$ git push origin $NOME
```

!!! tip "git"
    Esse comando diz para o git que é para enviar o branch `$NOME` 
    para o repositório remoto `origin`. Aquele que aparece no comando `$ git remote -v`.

-----------
> - [x] Gerar mudanças no repositório local
> - [x] Enviar mudanças para o repositório remoto
> - [ ] Gerar pull-request
-----------

## Realizando pull-request

Uma vez enviando o branch para o servidor, podemos via a interface **web** do `github` realizar o `pull-request`. Abra a pagína do github do repositório do seu grupo. 

!!! tip "git"
    Se tiver instalado o software [`hub`](https://github.com/github/hub) digite na linha de comando: `$ hub browser`.

Vamos agora gerar o pull-request na interface do github, de forma similar ao exemplo a seguir:

!!! warning
    Cuidado! Escolher o seu repositório no momento de realizar o pullrequest.

![](figs/B-CI/pullrequest.gif)

-----------
> - [x] Gerar mudanças no repositório local
> - [x] Enviar mudanças para o repositório remoto
> - [x] Gerar pull-request
-----------

## Aceitando pull-request

O **mediador** do projeto deve revisar os pull-requests (e corrigir eventuais erros de merge) 
e aceitar ou negar o pedido. 

![](figs/B-CI/pullrequest-accept.gif)
