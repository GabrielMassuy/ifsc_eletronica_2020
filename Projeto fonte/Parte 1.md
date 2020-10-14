# Projeto da Fonte

## Parte 1
Considerando o circuito da figura 01 que representa uma fonte linear com regulador MOSFET, temos o seguinte problema:  Qual relação entre a tensão de alimentação do ampop e a tensão de saída? O que devemos considerar para esse circuito operar como um LDO? Como obter as tensões de alimentação para o AmpOp (VCC e VEE)

#### figura 01
![f1](/resources/images/fonte/figura1.jpg)

### Relação entre tensão de alimentação do ampop e a tensão de saída
A tensão de saída é limitada pela tensão de alimentação do ampop (saturação). Nos casos em que ela acaba sendo limitada a tensão de saída sempre irá ter um valor um pouco menor do que a tensão de alimentação.

### O que devemos considerar para esse circuito operar como um LDO?
Para o circuito operar como um LDO, a tensão de saída deve ter um valor baixo. No bloco do regulador do tipo série com ampop, temos que Vout = Vz[1+(R2/R3)], portanto a tensão de saída vai depender da tensão de referência zener e da relação entre os resistores R2 e R3.

### Como obter as tensões de alimentação para o AmpOp (VCC e VEE)
Os valores de tensões de alimentação do ampop estão presentes em seu datasheet. Para fazer essa alimentação pode-se utilizar duas fontes independentes para alimentar VCC e VEE ou utilizar um dobrador de tensão para alimentar VCC (VEE ligado ao GND). Por se tratar de um projeto de fonte, seria inviável ter que utilizar duas fontes independentes, portanto o dobrador de tensão é a melhor opção.

### Conforme a figura 02, utilizando o circuito dobrador de tensão, qual valor de VCC você obtêm para um sinal Vin+ de 12 Vrms? Quais problemas apresentam esse circuito? Podemos melhorar?
#### figura 02
![f2](/resources/images/fonte/figura2.jpg)

Conforme foi visto na parte 1 do relatório 3, a tensão VCC esperada é de 32,54 V, porém a tensão de ripple irá aumentar significativamente com a adição de uma carga na saída VCC. Essa variação do valor de VCC irá se refletir na tensão de saída do ampop. Para diminuir essa tensão de ripple pode-se utilizar um circuito regulador do tipo série após o circuito dobrador de tensão, conforme a  imagem abaixo:

![f3](/resources/images/fonte/figura3.jpg)

### Projetar o seguinte circuito

![f4](/resources/images/fonte/figura4.jpg)


#### Considerar:
- AmpOp LM324
- MOSFET IRF540
- Vout = 15V
- Iout = 1A
- Vin+ = 12Vrms
- Vripple (pós retificador) = 1V
- Queda de tensão nos diodos = 0,7V

### Transformador e Circuito Retificador
O transformador vai fazer a transformação de 220V para 12V (RMS). A frequência utilizada será a mesma de nossa rede elétrica (60Hz).

O retificador que será utilizado é do tipo de onda completa com transformador em derivação. Considerando a queda de tensão em cada diodo de 0,7V, o valor de pico da tensão de saída do retificador será de aproximadamente 16,3V.

#### Circuito do retificador
![f5](/resources/images/fonte/bloco1.jpg)

Os diodos utilizados na simulação são do modelo 1N4007. Na saída do circuito foi utilizado um resistor de 16,3 ohms para simular a corrente máxima de 1 A.

#### Sinal da tensão no enrolamento primário (Vs)
![f6](/resources/images/fonte/curva1.jpg)

#### Sinal da tensão no enrolamento secundário (Vin+) e na saída do circuito (Vout)
![f7](/resources/images/fonte/curva2.jpg)

A tensão de pico na saída do circuito foi de 16,07V, portanto a corrente de pico da saída será de 1A quando a resistência R1 tiver o valor de 16,07 ohms.

### Filtro a Capacitor

Para o valor da tensão de saída (Vout) tornar-se mais constante, utiliza-se um filtro a capacitor. Para o cálculo do valor do capacitor foi considerado que a corrente máxima da carga será de 1A e a corrente total para outros componentes (como ampop's) será de 0,1A.

![f8](/resources/images/fonte/calculo1.jpg)

O valor calculado para o capacitor foi de 9,17mF.

#### Circuito com o filtro a capacitor

![f9](/resources/images/fonte/bloco2.jpg)

#### Sinal da tensão de saída (Vout)
![f10](/resources/images/fonte/curva3.jpg)
![f11](/resources/images/fonte/curva4.jpg)

Com a adição do filtro, a tensão ficou variando entre 15,88V e 15,15V, portanto a tensão de ripple foi de 0,73V.

### Circuito dobrador de tensão

Antes de adicionar o regulador de tensão ao circuito principal, é necessário usar um dobrador de tensão para alimentar o ampop que será utilizado.

Como foi visto na parte 1 do relatório 3, a tensão de saída esperada do circuito dobrador, considerando 12Vrms de entrada, é de 32,54V. O cálculo do valor dos capacitores para o circuito dobrador foi feito considerando a corrente de alimentação do ampop de 0,1A e Tensão de ripple de 10%.

![f12](/resources/images/fonte/calculo2.jpg)

![f13](/resources/images/fonte/circ2.jpg)

#### Tensão de saída do dobrador

![f14](/resources/images/fonte/curva5.jpg)

Leva cerca de 200 ms para a tensão de saída do dobrador atingir o valor esperado.

Pelo datasheet do LM324 da fabricante Texas Instruments, a tensão de alimentação singular do ampop deve ser de 3 a 32V. Como a tensão de saída do circuito dobrador ultrapassar esse valor, pode-se utilizar um diodo zener para ser a referência de tensão de alimentação do ampop.

 ![f15](/resources/images/fonte/datasheet1.jpg)

#### Adicionando referência com diodo zener ao circuito dobrador
