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

Conforme foi visto na parte 2 do relatório 4, a tensão VCC esperada é de 32,54 V, porém a tensão de ripple irá aumentar significativamente com a adição de uma carga na saída VCC. Essa variação do valor de VCC irá se refletir na tensão de saída do ampop. Para diminuir essa tensão de ripple pode-se utilizar um circuito regulador do tipo série após o circuito dobrador de tensão, conforme a  imagem abaixo:

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
- Queda de tensão nos diosos = 0,7V
