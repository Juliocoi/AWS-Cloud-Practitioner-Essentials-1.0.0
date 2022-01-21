# Infraestrutura global da AWS

## Seleção da região

<p align=justify>A AWS possui infraestrutura em várias partes do globo e todas elas podem ser usada para rodar sua aplicação. Apesar de tudo é importante salientar que os dados nunca saem do local onde a aplicação está hospedada, sem a prévia autorização do responsável pela aplicação. Para determinar a região certa para rodar sua aplicação você deve levar em consideração alsuns fatores. </p>

1. A lei local onde está localizada a empresa (que pode exigir que os dados do usuário não saiam do país onde a empresa está sediada);

2. Proximidade com o cliente;

3. Seviços disponível na região (Nem todos os serviços oferecidos pela AWS estão disponível em todas as regiões.);

4. Definição de preço. (Cada região possui sua própria tabela de preços. Os preços dos serviços levam considerações fatores locais, como a carga tributária etc.)

## Zonas de disponibilidade.

<p align=justify>A AWS possui vários datas center em cada região em que opera, cada datacenter é chamado de <b>zona de disponibilidade</b>. Cada <b>zona de disponibilidade</b> é composta por um ou mais data center, que possuem alimentação redundante, redes e conectividade e ficam a dezenas de quilômetros uma das outras, mas estão próximas o suficiente para ter baixa latência. Assim, caso um acidente natural ocorra em alguma região onde há um data center, os outros estarão longes o suficientes para não serem atingidos. Por isso é uma boa ideia não rodar a aplicação em uma única <b>zona de disponibilidade</b>. A AWS recomenda que a aplicação seja rodada ao menos em duas zonas de disponibilidade em uma região.</p>

# Pontos de presença.

## Redes de entregas de conteúdo - CDN

### Amazon CloudFront

<p align=justify id= "cloudFront">Um ponto de presença é um site que a <b>Amazon CloudFront</b> usa para armazenar cópias armazenadas em cash de seu conteúdo em Zonas de disponibilidades distintas das que você hospeda sua aplicação. Facilitando a entrega do conteúdo para clientes que estão em um local distante do local onde a aplicação está hospedada</p>

<p align=justify>O <b>Amazon CloudFront</b> usa o chamado <b>Edge locations</b> que são pontos de presenças espalhadas pelo mundo. As <b>edge locations</b> são separadas da regiões, assim você pode enviar um conteúdo de uma região para uma coleção desses pontos de presença em todo mundo. As <b>edge location</b> da AWS também executam um serviço de DNS, chamado <b>Amazon Route 53</b>. </p>

<p align=justify>Você também pode usar os serviços da AWS dentro do seu próprio prédio através do serviço <b>AWS Outposts, assim, você pode manter suas aplicações dentro de seu próprio prédio.</b></p>


