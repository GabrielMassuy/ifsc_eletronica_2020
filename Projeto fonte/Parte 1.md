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

Conforme foi visto na [parte 1 do relatório 3](https://github.com/GabrielMassuy/ifsc_eletronica_2020/blob/master/Relat%C3%B3rio%203/Parte%201.md), a tensão VCC esperada é de 32,54 V, porém a tensão de ripple irá aumentar significativamente com a adição de uma carga na saída VCC. Essa variação do valor de VCC irá se refletir na tensão de saída do ampop. Para diminuir essa tensão de ripple pode-se utilizar um circuito regulador do tipo série após o circuito dobrador de tensão, conforme a  imagem abaixo:

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

Como foi visto na [parte 1 do relatório 3](https://github.com/GabrielMassuy/ifsc_eletronica_2020/blob/master/Relat%C3%B3rio%203/Parte%201.md), a tensão de saída esperada do circuito dobrador, considerando 12Vrms de entrada, é de 32,54V. O cálculo do valor dos capacitores para o circuito dobrador foi feito considerando a corrente de alimentação do ampop de 0,1A e Tensão de ripple de 10%.

![f12](/resources/images/fonte/calculo2.jpg)

![f13](/resources/images/fonte/circ2.jpg)

#### Tensão de saída do dobrador

![f14](/resources/images/fonte/curva5.jpg)

Leva cerca de 200 ms para a tensão de saída do dobrador atingir o valor esperado.

#### Circuito regulador do dobrador
Para evitar oscilações que possam vir a ocorrer na saída Vc2 com a alimentação do ampop, utilizou-se um circuito regulador do tipo série na saída do dobrador de tensão. Como o LM324 (ON semiconductor) aceita alimentação singular de 3 a 32V foi utilizado o diodo Zener UMZ27K (27V, 5mA, 200mW) da fabricante ROHM Semiconductor e o transistor utilizado foi o 2N3904 da NXP, por ter um hfe alto.

A tensão esperada na saída é de 26,3V (Vz - VBE).

![f15](/resources/images/fonte/circ3.jpg)

O método do cálculo da resistência em série com o diodo Zener foi apresentada na [parte 2 do relatório 3](https://github.com/GabrielMassuy/ifsc_eletronica_2020/blob/master/Relat%C3%B3rio%203/Parte%202.md).
#### Nova tensão de saída do dobrador

![f16](/resources/images/fonte/curva7.jpg)

A tensão Vcc teve um valor de 26,5V

### Circuito regulador do tipo série com ampop

Agora que o ampop já tem a alimentação Vcc, o circuito que irá regular a tensão pode ser construído.

![f17](/resources/images/fonte/circ4.jpg)

Para esse bloco a tensão de saída depende do valor de D6 e a relação entre R3 e R4. Como a tensão de saída já esta definida (15V), basta atribuir um valor para D6 e achar a relação entre R3 e R4.

![f18](/resources/images/fonte/calculo5.jpg)

No cálculo da relação, utilizou-se Vz como 10V e os resistores escolhidos foram de 5k e 10k ohms.

### Circuito proposto montado

O diodo zener D6 utilizado foi o UMZ10K (10V, 5mA, 200mW) da ROHM Semiconductor, o transistor NMOS utilizado é da fabricante Vishay e o ampop utilizado é da fabricante ON Semiconductor

![f18](/resources/images/fonte/circ5.jpg)

#### Tensão de saída Vout
Tensão de saída sem carga:
![f19](/resources/images/fonte/curva10.jpg)


O circuito demorou cerca de 27ms para inicializar e a tensão de saída permaneceu praticamente constante em 14,98V sem carga e com carga de 15, 1k e 100k ohms.

![f19](/resources/images/fonte/circ6.jpg)

Com a carga de 15 ohms a tensão de ripple foi de 1,30mV.
