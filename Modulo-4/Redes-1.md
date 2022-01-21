# Redes

## Amazon Vitual Private Cloud - VPC

<p align=justify>Uma VPC é um serviço que lhe permite provisionar uma seção logicamente isolada da nuvem da AWS em que você pode executar recursos da AWS em uma rede virtual definida por você, ou seja, te permite criar uma rede privada na AWS. Esses recursos podem ser voltados para o público, para que eles tenham acesso á internet, ou privados, sem acesso à internet.</p>

## Gateway da internet

<p align=justify>Para permitir que o trágedo público da internet acesse sua VPC, você anexa um <b>gateway da internet</b> à VPC. Um gateway da Internet é uma conexão entre uma VPC e a Internet.</p>

![Gateway-da-internet](/IMG/cliente-solicitacao-internet-vpc.png)

## Gateway privado virtual

<p align=justify>Para acessar recursos privados em uma VPC, você pode usar um gateway privado virtual, que permite estabelecer uma conexão VPN (rede virtual privada) entre a VPC e uma rede privada, como um datacenter on-premises ou uma rede corporativa interna. Um gateway privado virtual permitirá o tráfego na VPC somente se ele for proveniente de uma rede aprovada.</p>

![conexão VPN](/IMG/conexao-vpn.png)

## AWS Direct Connect

<p align=justify><b>AWS Direct Connect</b> é um serviço que permite estabelecer uma conexão privada dedicada entre seu datacenter on-promises e uma VPC. A conexão privada que o AWS Direct Connect fornece ajuda você a reduzir os custos de rede e a aumentar a quantidade de largura de banda que pode trafegar pela sua rede.  </p>

![AWS Direct Connect](/IMG/AWS-Direct-Connect.png)

# Sub-redes e listas de controle de acesso à rede.

<p align=justify>Uma sub-rede é uma seção de uma VPC na qual você pode agrupar recursos com base em necessidades operacionais ou de segurança. As sub-redes podem ser públicas ou privadas. Em uma VPC, as sub-redes podem se comunicar entre si. Por exemplo, você pode ter uma aplicação que envolve instâncias do Amazon EC2 em uma sub-rede pública se comunicando com bancos de dados localizados em uma sub-rede privada. Antes de um pacote poder entrar ou sair em uma sub-rede, ele verifica se há permissões. Essas permissões indicam quem enviou o pacote e como o pacote está tentando se comunicar com os recursos em uma sub-rede. </p>

<p align=justify><b>Sub-redes PUBLICAS</b> contêm recursos que precisam ser acessíveis pelo público, como o site de uma loja online.</p>

<p align=justify>As <b>sub-redes PRIVADAS</b> contêm recursos que devem ser acessíveis apenas pela sua rede privada, como um banco de dados que contém informações pessoais dos clientes e históricos de pedidos. </p>

![Sub-redes](/IMG/sub-redes.png)

<p align=justify>O componente da VPC que verifica as permissões de pacotes para sub-redes é uma <a href="https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html">lista de controle de acesso (ACL) à rede</a>.</p>

## Network ACLs (Listas de controle de acesso à rede)

<p align=justify>Uma<b>lista de controle de acesso à rede (ACL)</b> é um firewall virtual que controla o tráfego de entrada e saída no nível de sub-rede.</p>

<p align=justify>Cada conta da AWS inclui uma Network ACL padrão. Ao configurar sua VPC, você pode usar a <b>Network ACL</b> padrão da sua conta ou criar <b>Network ACLs</b> personalizadas. </p>

<p align=justify>Por padrão, a <b>Network ACL</b> da sua conta permite todo o tráfego de entrada e saída, mas isso pode ser alterado. Quando a <b>Network ACL</b>  é alterada, todo o tráfego, seja de entrada ou saída, é negado até que você adicione regras contendo as especificações as novas regras de tráfego. Além disso, todas as <b>Network ACLs</b> têm uma regra de negação explícita. Essa regra garante que se um pacote não corresponder a nenhuma das outras regras na lista, o pacote será negado</p>

## Filtragem de pacotes stateless

<p align=justify><b>Network ACLs</b> executam uma <b>filtragem de pacotes stateless</b>. Isso significa que elas verificam os pacotes que atravessam a borda da sub-rede em todos os sentidos: entrada e saída.</p>

<p align=justify>Observe que não é pq o pacote teve acesso a subrede, que ele poderá sair dela. como dito acima a verificações ocorre tanto na entrada quanto na saída, assim, o pacote pode ter sua saída negada, se não corresponder aos requisitos de segurança especificados.</p>

<p align=justify>A <b>Network ACLs</b> verificam tão somente as requisições de entrada e saída da Sub-rede, mas cada pacote deve, ainda, ser avaliado por uma nova camada de segurança, que vai validar seu acesso os recursos dentro da sub-rede, como as instâncias <b>Amazon EC2</b>.</p>

<p align=justify>O componente da VPC que verifica as permissões de pacote para uma instância do <b>Amazon EC2</b> é um <a href="https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html">grupo de segurança</a>.</p>

## Grupos de segurança

<p align=justify>Um grupo de segurança é um firewall virtual que controla o tráfego de entrada e saída de uma <mark>instância do Amazon EC2</mark>. Agindo como uma dupla camada de segurança, já que ele analizará a integridade do pacote independentemente da <b>lista de controle de acesso à rede (ACL)</b>, tratada acima. Que atua como segurança na <mark>entrada da Subrede</mark>. NÃO CONFUNDIR A ENTRADA DA SUB-REDE COM A ENTRADA EM UMA INSTÂNCIA EC2. A INTÂNCIA EC2 ESTÁ DENTRO DA SUBREDE</p>

<p align=justify>Por padrão, um grupo de segurança nega todo o tráfego de entrada e permite todo o tráfego de saída. Mas essas regras podem ser personalizadas. Aqui podemos notar mais uma diferença com a Lista de Controle de Acesso à Rede, que, por padrão</p>

## Filtragem de pacotes stateful

<p align=justify>Os <b>grupos de segurança</b> executam a filtragem de <b>pacotes <mark>stateful</mark></b>. Eles se lembram de decisões anteriores tomadas para pacotes recebidos.(Não confundir com a filtragem de pacotes <b><mark>stateless</mark></b> realizada no ambito da sub-rede. Aqui estamos falando das instâncias da Amazon EC2 que estão dentro da sub-rede)</p>

<p align=justify>Diferentemente das veríficações realizadas no ambito da sub-rede(feita pela filtragem Stateles), na filtragem Stateful a verificações ocorre apenas na entrada. Durante a saída os Grupos de Segurança "lembram" dos dados do pacote durante sua entrada e permitem sua saída sem a necessidade de nova verificação.</p>

![Estruturas da Núvem](/IMG/estrutura-nuvem.png)

# Redes Globais

## DNS

<p align=justify>O verdadeiro endereço de qualquer site é seu IP, a URL existe apenas para deixar a navegação mais amigável ao usuário. Ao digitar uma URL no navegador, antes do cliente procurar pelo servidor ele direciona sua requisição ao DNS, faz a consulta do endereço IP correspondente àquele site para em seguida fazer a requisição no servidor onde o site está hospedado. Conforme pode ser visto na IMG abaixo.</p>

![DNS](/IMG/DNS.png)

<p align=justify>OBS: Você pode acessar qualquer site digitando seu endereço IP diretamente no navegador. Existem serviços na WEB que te ajudam, de forma gratuíta, a identificar o IP dos sites.</p>

## Amazon Route 53

<p align=justify><b>Amazon Route 53</b> é um serviço Web DNS. Oferece aos desenvolvedores e empresas uma maneira confiável de rotear os usuários finais para aplicações da internet hospedadas na AWS. ele não apenas conecta solicitações de usuários à infraestrutura em execução na AWS, mas também pode rotear os usuário para outras infraestruturas fora da AWS</p>

<p align=justify>Outro recurso do Route 53 é a capacidade de gerenciar os registros DNS para nomes de domínio. Você pode registrar novos nomes de domínio diretamente no Route 53 ou transferir registros DNS gerenciados por outras empresas de registro de domínio. Isso permite que você gerencie todos os seus nomes de domínio em um único local.</p>

<p align=justify>No módulo anterior, vimos o <a href="/Módulo-3/6.Estruturas-globais-da-AWS.md#cloudFront">Amazon CloudFront</a>, um serviço de entrega de conteúdo. O exemplo a seguir descreve como o Route 53 e o Amazon CloudFront trabalham juntos para fornecer conteúdo aos clientes</p>

![exemplo](/IMG/Route33-CloudFront.png)

<p align=justify>Suponha que a aplicação da AnyCompany esteja em execução em várias instâncias do Amazon EC2. Essas instâncias estão em um grupo de Auto Scaling que é anexado a um Application Load Balancer. </p>

1. Um cliente solicita dados da aplicação acessando o site da AnyCompany;

2. O Amazon Route 53 usa a resolução para identificar o endereço IP correspondente da AnyCompany, 192.0.2.0. essas informações são enviadas de volta para o cliente;

3. A solicitação do cliente é enviada para o ponto de presença mais próximo por meio do Amazon CloudFront;

4. O Amazon CloudFront se conecata ao application load balance, que envia o pacote de entrada para uma instância do Amazon EC2.