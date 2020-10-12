# Relatório 3

## Parte 1: Circuito dobrador de tensão
Projetar um circuito dobrador de tensão para alimentar um Ampop utilizando como tensão de entrada um transformador com tap central de 12Vrms e no máximo 200ms de tempo de inicialização do circuito. Considerar uma corrente de saída do Ampop de 10mA.

### Análise do Circuito
![f1](/resources/images/relat3/p1calculo1.jpg)

Pela análise, conclui-se que a tensão de saída do circuito dobrador (Vc2) será de duas vezes a tensão de pico da entrada (Vp) menos a queda de tensão sobre os dois diodos.

### Dimensionamento do Capacitor
![f2](/resources/images/relat3/p1calculo2.jpg)

Utilizando o valor de pico da tensão de entrada e a corrente de saída do Ampop, e considerando uma tensão de ripple de 10%, foi calculado o valor dos capacitores para serem utilizados no circuito dobrador de tensão. O valor escolhido para o capacitor foi de 47µF por se tratar de um valor comercial fácil de se encontrar.

### Simulação do Circuito

#### Tempo de inicialização
![f2](/resources/images/relat3/p1curva1.jpg)
O circuito demorou cerca de 171ms para inicializar

#### Tensão de ripple
![f2](/resources/images/relat3/p1curva2.jpg)
A tensão de ripple foi de 60mV
