# Relatório 4 - Circuitos com Transistores do tipo MOS

## Parte 2a:  Polarização de transistores do tipo NMOS
Simular o seguinte circuito, onde Vcc = 9,0 V, R3 = R4 = 10 kΩ, R1 = 2 kΩ,R2 = 1 kΩ e responder em qual região o transistor se encontra polarizado.
![f1](/resources/images/relat4/p2circ1.jpg)

Os parâmetros utilizados (W, L, Vt, Kp) e modelo SPICE são do transistor 2N7002 do fabricante DIODES Incorporated.

![f3](/resources/images/relat4/p2model.jpg)

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

O curto-circuito do Gate com o Dreno faz com que a corrente ID1 que passa sobre o transistor Q1 seja igual a (Vcc - Vgs)/R. A tensão Vgs polariza o transistor Q2, e como a corrente do transistor Q2 depende dos parâmetros físicos W, L, Kp, Vt, Vgs é o mesmo nos dois transistores e Q1 e Q1 são iguais, a corrente que passa por Q2 será a mesma que passa sobre Q1, portanto ID1 = ID2.

### Traçar a curva ID2 x V2
