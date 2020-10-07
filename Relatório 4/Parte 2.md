# Relatório 4 - Circuitos com Transistores do tipo MOS

## Parte 2a:  Polarização de transistores do tipo NMOS
Os parâmetros utilizados (W, L, Vt, Kp) e modelo SPICE são do transistor 2N7002 do fabricante DIODES Incorporated.

![f3](/resources/images/relat4/p2model.jpg)

Simular o seguinte circuito, onde Vcc = 9,0 V, R3 = R4 = 10 kΩ, R1 = 2 kΩ,R2 = 1 kΩ e responder em qual região o transistor se encontra polarizado.
![f1](/resources/images/relat4/p2circ1.jpg)

### Resultados calculados

![f3](/resources/images/relat4/p2calculo1.jpg)

Pelos cálculos foi concluido que o transistor se encontra polarizado na região de saturação.

### Simulação do circuito

![f4](/resources/images/relat4/p2circ2.jpg)
![f5](/resources/images/relat4/p2circ2_result.jpg)

Os valores calculados ficaram bem próximos aos valores obtidos pela simulação, portanto o transistor está operando na região de saturação.

## Parte 2b: Espelho de corrente com transistores do tipo NMOS
Analise o seguinte circuito, onde R1 = 1,0 kΩ, VCC= 10,0 V. Para R2,variando entre 0 e 100kΩ.

![f6](/resources/images/relat4/p2circ3.jpg)

### Funcionamento do circuito

O curto-circuito do Gate com o Dreno faz com que a corrente ID1 que passa sobre o transistor Q1 seja igual a (Vcc - Vgs)/R1. A tensão Vgs polariza o transistor Q2, e como a corrente do transistor Q2 depende de seus parâmetros físicos W, L, Kp, Vt, Vgs que são os mesmos nos dois transistores (Q1 = Q2), a corrente que passa por Q2 será a mesma que passa sobre Q1, portanto ID1 = ID2.

### Traçar a curva ID2 x V2 (*tirar dúvida*)

### Cálculo do valor máximo de R2

![f6](/resources/images/relat4/p3calculo1.jpg)

Pelos valores calculados, as correntes ID1 e ID2 terão um valor de 7,66mA. Se o resistor R2 passar de 1023,88 ohms a tensão VGS irá ter um valor menor que Vt e o circuito não irá funcionar do modo que deve.

### Simulação do circuito
![f6](/resources/images/relat4/p3circ1.jpg)
![f6](/resources/images/relat4/p3resultados1.jpg)

Em um primeiro teste, as correntes que passam pelos resistores R1 e R2 apresentam o mesmo valor de 7,63 mA, valor bem próximo ao calculado.

#### Resposta das correntes variando o valor de R2

![f6](/resources/images/relat4/p3circ2.jpg)
![f6](/resources/images/relat4/p3curva1.jpg)
![f6](/resources/images/relat4/p3curva2.jpg)

Com o gráfico de corrente versus R2, é possível ver que as correntes continuam com os mesmos valores até 1203,60 ohms. O valor calculado da resistência máxima de R2 teve uma diferença de cerca de 180 ohms do valor obtido pela simulação.
