# Gerenciar os recursos da AWS.

<p align=justify>Todos os recursos da AWS são consumidos por meio de APIs. Você pode, por exemplo, você pode iniciar uma instância EC2 ou criar uma função do Lambda. Vc pode usar o console de gerenciamento da AWS - CLI para utilizar linhas de comando. Pode utilizar, também, as SDKs com linguaggens como java, C++, Python, etc. Ou usar a <b>AWS Cloud Formation</b> para criar ambientes inteiros de forma centralizada utilizando chamadas de API da AWS para criar e gerenciar esses recursos</p>

## Console de Gerenciamento da AWS

<p align=justify>A interação com a console é feita pelo navegador e possui uma interface gráfica onde você pode gerenciar seus recursos da AWS de forma simples e intuitiva. Também é útil para criar ambientes de teste, visualizar contas da AWS e checar o monitoramento dos seus recurso. É aqui onde você aprenderar sobre AWS.</p>

<p align=justify>Contudo, gerenciar esses serviços de forma manual exigiria diversos cliques, o que tornaria o processo sucetível a erro. Dessa forma, a melhor forma pra evitar qualquer problema é a utilização de ferramentas que lhe permite criar scripts ou chamadas de API. A <b>Interface de Linha de Coando da AWS - CLI</b>, que permite que você faça chamadas diretamente do seu terminal. Ao iniciar uma instância EC2 dessa forma, caso seja necessário realizar o mesmo procedimento novamente você pode simplesmente executar o comando pré-escrito.</p>

<p align=justify>Outra maneira de interagir com a AWS é por meio dos Kits de desenvolvimento de software - SDKs. As SDKs permitem que você interaja com os recursos da AWS por meio de várias linguagens de programação(A AWS fornece documentação e códigos de exemplo). Isso torna mais fácil para os desenvolvedores criarem aplicações que usam as AWS sem utilizar APIs de baixo nível, bem como evitar a criação manual de recursos como descrito acima.</p>

## AWS Elastic Beanstalk

<p align=justify>É um serviço que lhe auxilia na administração dos recursos da AWS. com ele você fornece definições de código e configuração, e o Elastic Beanstalk implanta os recursos necessários para executar as seguintes tarefas:</p>

* Ajustar capacidade
* Balanceamento de carga
* Escalabilidade automática
* Monitoramento da integridade da aplicação

<p align=justify>Com o AWS Elastic Beanstalk console ou escrever vários comandos para criar sua rede, instâncias EC2, escalabilidade e os load balances, você vai fornecer o seu código da aplicação com as configurações desejadas no Beanstalk e, em seguida, ele cria o seu ambiente e faz o seu deploy. O Elastic Beanstalk também permite salvar as configurações do ambiente para que elas possam ser implantadas novamente.</p>

## AWS CloudFormation

<p align=justify>Outro serviço que pode auxiliar na automação é o <b>AWS CloudFormation</b>. O AWS CloudFormation é uma ferramenta que trata a infraestrutura como código, permitindo que você defina uma ampla variedade de recursos da AWS usando JSON ou Yaml, chamados de Templates do CloudFormation.  o CloudFormation te permite definir o que você deseja e o mecanismo dele vai se preocupar com os detalhes sobre como chamar as APIs para fazer essa criação</p>

<p align=justify>O CloudFormation é compatível com diversos recursos diferentes da AWS, como armazenamento, banco de dados, machine learning etc. O CloudFormation gerencia todas as chamadas de API para o back end da AWS. Você pode executar o mesmo template do CloudFormation em várias contas ou em várias regiões e ele criará ambientes idênticos</p>