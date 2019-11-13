**SCRUM MASTER (todos devem acompanhar)**

Travis é um sistema de integração contínua que vai executar de forma automática alguns testes (criado por nós) no projeto e em caso de alguma falha irá notificar no github e por e-mail todos os integrantes.

Como ele funciona ? Ele fica verificando o repositório por alterações (você deve além de dar commit, dar push) e para cada novo commit ele faz o seguinte

1. Inicializa uma nova máquina virtual na nuvem (ubuntu, windows, mac)
2. Instala todo a infra necessária do projeto (no caso do Z01.1 : python, java, Quartus, ...)
3. Executa os scripts de teste localizados em cada parte do projeto 
      - No caso desse projeto : `Projetos/C-Logica-Combinacional/testeLogicaCombinacional.py`
4. Desliga e "deleta" a máquina virtual recém criada.

O arquivo de configuração do travis está localizado na raiz do repositório : [`Z01.1/.travis.yml`](https://github.com/Insper/Z01.1/blob/master/.travis.yml). Nele que estão feitas todas as definições de execução.

Na pagina do seu repositório em commits deve aparecer uma pequena bolinha em cada um dos commits novos que serão feitos no projeto, esse indicador será atualizado pelo travis sendo :

- Amarelo: O teste está em execução
- Verde: O teste passou
- Vermelho: O teste falhou

> Cada teste leva em torno de alguns minutos já que toda a infraestrutura é instalada sempre do zero, não utilize o sistema de Integração Contínua para validar as suas novas implementações, esse sistema deve ser utilizado para encontrar problemas mais amplos ou para o scrum master aceitar ou não um pull-request, já que o resultado do sucesso ou não dessa requisição é visível facilmente.

## Ativando no Travis

Será necessário acessar o site do travis :

- [https://travis-ci.org/](https://travis-ci.org/) e adicione o projeto forkado ao travis :

![Travis](figs/C-LogiComb/C-config-travis.gif)

```diff
+ Somente o usuário que realizou o fork do projeto
+ deve realizar essa etapa.
```

# Github 

> GitHub Inc. is a web-based hosting service for version control using Git. It is mostly used for computer code. It offers all of the distributed version control and source code management functionality of Git as well as adding its own features. [Wikipedia](https://en.wikipedia.org/wiki/GitHub)

Nessa disciplina iremos utilizar não só a ferramenta principal do github, que é o servidor de repositórios git mas todas as outras ferramentas já integradas na plataforma para gestão e acompanhamento de projeto.

- Github Project: Ferramenta do github para gerenciamento de projetos (estilo Kambam), cada repositório pode ter N projetos, e o github automatiza o processo de todo/doing/done deixando de maneira visual as tarefas.

- GitHub issues: Plataforma do github para criação de tarefas, as tarefas aqui criadas serão associadas a um projeto específico e a um grupo de pessoas específicas.

```diff
+ Você deverá ativar o issues no github.
+ Vá em Settings -> e clique em issues
```

- Pull-request: Maneira de um lider de projeto aceitar ou não atualizações em um código, o pull-request é criado por um usuário e revisado por outro.

- Branch: Ramo criado para implementar um feature/ correção de bug que será futuramente incorporado no master (merge)

- Master: Ramo principal do projeto, gerenciado pelo **Scrum Master**

# Tutorial

**O `Scrum Master` deve realizar as tarefas a seguir com todos acompanhando no monitor!**

- Criando um project no github

![Project](figs/C-LogiComb/C-2-project.gif)

- Adicionando issues

![Issues](figs/C-LogiComb/C-3-issues.gif)

Os issues devem ser [todos os módulos](https://github.com/Insper/Z01.1/wiki/C-Logica-Combinacional-Projeto#o-que-deve-ser-feito-) a serem implementados do projeto.

