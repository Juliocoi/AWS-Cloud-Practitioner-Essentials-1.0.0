# Direcionamento de tráfego

## Elastic Load Balancing

<p align=justify><b>Elastic Load Balancing</b> é o serviço da AWS que distribui automaticamente o tráfego de entrada de aplicações entre vários recursos, como instâncias do Amazon EC2. Assim, à medida que você adiciona ou remove instâncias no EC2, em resposta à quantidade de tráfego de entrada, o <b>elastic load balancing</b>, que recebe essa informação primeiro, redireciona o fluxo para as novas instâncias automaticamente, fazendo o redirecionamento das informações para impedir que uma instância fique sobrecarregada enquanto outra está vazia. Quando o trafégo diminuir e determinada instancia ficar inativa o <b>elatic load balancing</b> fara uma nova redistribuição, com base no número restante de instâncias, tudo isso sem interromper o serviço.</p>

![Exemplo 1](/IMG/Elastic-load-balancing1.png)
![Exemplo 2](/IMG/Elastic-load-balancing2.png)

# Mensagens e filas

## Aplicações monolíticas e microsserviços

<p align=justify>As aplicações são feitas de vários componentes que se comunicam entre si para transmitir dados, atender solicitações e manter a aplicação em execução. </p>


<p align=justify>Em uma aplicação de componentes bem aclopados (esses componentes podem incluir bancos de dados, servidores, interfaca do usuário, lpogica de negócios etc.), caso um único complemento falhe, todos os outros também falharão. Esse tipo de arquitetura é chamada de <b>Estrutura monolítica.</b></p>

<p align=justify>Em uma abordagem de <mark>microsserviços</mark>, os componentes da aplicação são acoplados vagamente. Nesse caso, se um único componente falhar, os outros componentes continuarão a funcionar porque eles estarão se comunicando uns com os outros. O baixo acoplamento evita que toda a aplicação falhe. </p>

<p align=justify>Ao projetar aplicações na AWS, você pode adotar uma abordagem de <mark>microsserviços</mark> com serviços e componentes que cumprem funções diferentes. Dois serviços facilitam a integração de aplicações: <b>Amazon Simple Notification Service (Amazon SNS)</b> e <b>Amazon Simple Queue Service (Amazon SQS)</b>.</p>



## Amazon Simple Notification Service (Amazon SNS)

<p align=justify><b>Amazon Simple Notification Service (Amazon SNS)</b> é um serviço de publicação/assinatura. Usando tópicos do Amazon SNS, um editor publica mensagens para assinantes. Isso é semelhante ao café; o caixa fornece pedidos de café para o barista que faz as bebidas. No Amazon SNS, os assinantes podem ser servidores Web, endereços de e-mail, funções do <b>AWS Lambda</b> ou várias outras opções.</p>

## Amazon Simple Queue Service (Amazon SQS)

<p align=justify><b>Amazon Simple Queue Service (Amazon SQS)</b> é um serviço de enfileiramento de mensagens.</p> 

<p align=justify>Use o Amazon SQS para enviar, armazenar e receber mensagens entre componentes de software, sem perder mensagens ou precisar que outros serviços estejam disponíveis. No Amazon SQS, uma aplicação envia mensagens para uma fila. Um usuário ou serviço recupera uma mensagem da fila, a processa e a exclui da fila.</p>