# Amazon Elastic Compute Cloud (Amazon EC2)

<p align=justify>O Amazon EC2 é o serviço que você utiliza para se conectar aos servidores virtuais da AWS. Ele fornece capacidade computacional segura e redimensionável na nuvem como instâncias do Amazon EC2 <br>
Um dos benefícios de usar o EC2 é a enconomia, pois você não precisará se preocupar com a compra de servidores locais, além de economisar no tempo gasto pela logística de entrega e instalação desses servidores, Também não precisará se preocupar com a capacidade do hardware, pois na AWS você paga apenas pelo tempo de computação usado quando uma instância está em execução, não quando ela é interrompida ou encerrada. Você pode poupar custo ao ter a capacidade ideal para sua aplicação.</p>


<p align=justify>As instancias EC2 são executados em hosting físicos, gerenciados pela AWS, usando tecnologia de virtualização</p>

## Tipos de instâncias

<p align=justify>Há vários tipos de instâncias no Amazon EC2, cada uma feita para uma necessidade específica que podem incluir requisitos para recurso de computação, memória ou armazenamento. Cada tipo de instância é agrupada em uma família que são otimizadas para determinados tipos de tarefa. Famílias abaixo:</p>

### Instância geral

<p align=justify>Fornecem um equilíbrio de recursos de computação, memória e rede. Ideal para aplicações onde as necessidades de recurso para computador, memória e rede sejam aproximadamente equivalentes. Onde não há necessidade de otimização em uma área área de recurso única. Ideais para:</p>

* servidores de aplicações;
* servidores de jogos;
* servudires de bach-end para aplicações corporatívas;
* banco de dados pequenos e médios.

### Instâncias otimizadas para computação

<p align=justify>São ideais para aplicações vinculadas à computação que se beneficiam de processadores de alta performace. São ideais para servidores web de alta performace, servidores de aplicações coputação intensiva e servidores de jogos dedicados.</p>

### Instâncias otimizadas para memória

<p align=justify>São projetadas para fornecer rápida performance para cargas de trabalho que processam grandes conjuntos de dados na memória. Como banco de dados de alta performance ou uma carga de trabalho que envolve a execução de processamento em tempo real de uma grande quatidade de dados não estruturados</p>

### Instâncias de computação acelerada

<p align=justify>usam aceleradores de hardware, ou coprocessadores, para executar algumas funções de forma mais eficiente do que é possível no software executado em CPUs. Exemplos dessas funções incluem cálculos de número de ponto flutuante, processamento de gráficos e correspondência de padrões de dados. são ideais para cargas de trabalho, como aplicações gráficas, streaming de jogos e streaming de aplicações.</p>

### Instâncias otimizadas para armazenamento

<p align=justify>ão projetadas para cargas de trabalho que exigem alto acesso sequencial de leitura e gravação a grandes conjuntos de dados no armazenamento local.  incluem sistemas de arquivos distribuídos, aplicações de data warehousing e sistemas de processamento de transações online de alta frequência (OLTP)</p>