# Relatório 1 - AmpOp

## Parte 4: Amplificador Subtrator

###### Objetivo:

Verificar as não idealidades dos ampops aplicadas em um circuito subtrator.

###### Experimento:

Utilizando um Amp.OP. LM324N e o TL082 monte dois amplificadores subtratores.
Use o resistor de realimentação  com valor 510kΩ e ganho igual á 10V/V.
Utilize a alimentação simétrica de +/-12V.

###### Procedimento:

1 - Depois de construir o circuito subtrator, simular os circuitos conforme os exemplos dados.

2 - Comparar os resultados da tensão de saída dos dois circuitos.

3 - Verificar o valor da tensão de saída se a tensão de entrada for igual a 0.

4 - Verificar o que acontece se os dois resistores de 620Ω forem colocados na mesma entrada.

### Resultados calculados
Utilizando um AmpOp ideal, fez-se o cálculo dos resistores R1 considerando que os resistores R2 deveriam ter o valor de 510kΩ e o ganho deveria ser de 10 V/V.

![p4conta](/resources/images/relat1/p4conta.jpg)

O valor calculado dos resistores R1 foi de 51kΩ.

### Simulação: Circuito com LM324N
Circuito montado no LTspice, utilizando o modelo da Texas Instruments:

![p4circ1](/resources/images/relat1/p4circ1.jpg)

### Simulação: Circuito com TL082
Circuito montado no LTspice, utilizando o modelo da Texas Instruments:

![p4circ2](/resources/images/relat1/p4circ2.jpg)

### Simulação: Comparação do sinal de saída dos circuitos com LM324N e TL082

![p4onda1](/resources/images/relat1/p4onda1.jpg)

A tensão de saída do circuito com o LM324N teve um valor de 130,01mV, enquanto que a tensão de saída com o circuito com o TL082 foi de 95,14mV.

### Simulação: Comparação do sinal de saída dos circuitos com LM324N e TL082, sendo a tensão de entrada 0V
![p4onda2](/resources/images/relat1/p4onda2.jpg)

Com a tensão de entrada igual a 0V, A tensão de saída do circuito com o LM324N foi de 31,43 mV e a tensão de saída do circuito com o TL082 foi de 0,12 mV.

### Simulação: Comparação do sinal de saída dos circuitos com LM324N e TL082, com os dois resistores de 620Ω na mesma entrada.
![p4circ3](/resources/images/relat1/p4circ3.jpg)
![p4onda3](/resources/images/relat1/p4onda3.jpg)

A tensão de saída do circuito com o LM324N foi de 128,11 mV e a tensão de saída do circuito com o TL082 foi de 96,80mV.

### Resultados

Nos casos simulados a tensão de saída deveria ser de 0V conforme a expressão da tensão de saída que foi calculada, mas por conta das não idealidades que os ampops apresentam, foi visto que as tensões de saída foram apenas próximas de zero, nunca chegando a este valor.
