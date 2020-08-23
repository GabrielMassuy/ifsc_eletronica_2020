# Relatório 1 - AmpOp

## Parte 4: Amplificador Subtrator

###### Objetivo:

Verificar as não idealidades dos ampops aplicadas em um circuito subtrator.

###### Experimento:

Utilizando um Amp.OP. Lm324N e o TL082 monte dois amplificadores subtratores.
Use o resistor de realimentação  com valor 510kΩ e ganho igual á 10V/V.
Utilize a alimentação simétrica de +/-12V.

###### Procedimento:

1 - Simular os circuitos utilizando como sinal de entrada uma tensão contínua de 12V.

2 - Comparar os resultados da tensão de saída dos dois circuitos.

3 - Verificar o valor da tensão de saída se a tensão de entrada for igual a 0.

4 - Verificar o que acontece se um resistor extra de 10kΩ for adicionado em série com a entrada V1.

5 - Discutir os resultados e justificar as dissimilaridades encontradas utilizando os dados do datasheet.

### Resultados calculados
**EDITAR**
Utilizando um AmpOp ideal, fez-se o cálculo dos resistores R1 considerando que os resistores R2 deveriam ter o valor de 510kΩ e o ganho deveria ser de 10.

[p4conta](/resources/images/relat1/p4conta.jpg)

O valor calculado dos resistores R1 foi de 51kΩ.

### Simulação: Circuito com LM324N
Circuito montado no LTspice, utilizando o modelo da Texas Instruments:

![p4circ1](/resources/images/relat1/p4circ1.jpg)

### Simulação: Circuito com TL082
Circuito montado no LTspice, utilizando o modelo da Texas Instruments:

![p4circ2](/resources/images/relat1/p4circ2.jpg)

### Simulação: Comparação do sinal de saída dos circuitos com LM324N E TL082

![p4onda1](/resources/images/relat1/p4onda1.jpg)

A tensão de saída do circuito com o LM324N teve um valor de 10,91V, enquanto que a tensão de saída com o circuito com o TL082 foi de 0,98V.

### Simulação: Adição do resistor de 10kΩ

![p4onda2](/resources/images/relat1/p4onda2.jpg)

Após adicionar o resistor de 10kΩ, a tensão de saída do circuito com o LM324N teve um valor de 10,82V, enquanto que a tensão de saída com o circuito com o TL082 foi de 10,47V.

### Resultados
