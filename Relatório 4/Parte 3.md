# Relatório 4 - Circuitos com Transistores do tipo MOS

## Parte 3: Inversor com transistor do tipo NMOS (NMOS Inverter)
Os parâmetros utilizados (W, L, Vt, Kp) e modelo SPICE são do transistor 2N7002 do fabricante DIODES Incorporated.

![f1](/resources/images/relat4/p2model.jpg)

Simular o circuito a seguir com os seguintes valores: R1 = 10 kΩ e VCC= 5,0 V.VIN =  forma de onda quadrada com 1 kHz e amplitude de 5,0 Vpp (sem valor negativo, ou seja de0 a 5V ). Após isso simular o mesmo circuito, mas alterar VIN para ter uma amplitude de 2,5 Vpp.

![f2](/resources/images/relat4/p4circ1.jpg)

### Resultados calculados

![f2](/resources/images/relat4/p4calculo1.jpg)

O Rds calculado com Vin igual a 5V foi de 0,755 ohms e para Vin igual a 2,5V foi de 6,21 ohms.

A tensão de saída, Vout, acaba dependendo de Rds. Sendo de 377,47µV para Vin igual a 5V e 1,55mV para Vin igual a 2,5V.

Quando Vin é igual a zero, Vg e Vs são iguais a zero, e portanto Vout acaba sendo igual a Vcc.

### Simulando o circuito

![f3](/resources/images/relat4/p4circ2.jpg)

### Comparando os sinais da tensão de entrada e tensão de saída
#### Com Vin tendo 5Vpp
![f4](/resources/images/relat4/p4onda1.jpg)
##### Valores de Vout
![f4](/resources/images/relat4/p4onda2.jpg)

#### Com Vin tendo 2,5Vpp
![f4](/resources/images/relat4/p4onda3.jpg)
##### Valores de Vout
![f4](/resources/images/relat4/p4onda4.jpg)

Como esperado Vout apresenta o mesmo valor de Vcc quando Vin é igual a 0. Os valores calculados de Vout foram menores do que os valores obtidos pelo gráfico da simulação.
