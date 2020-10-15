# Projeto da Fonte

## Parte 2

### Circuito referência de tensão zener (R1 e D3): Ver roteiro 03. Podemos melhorar esse circuito? Quais problemas podemos identificar nesta topologia?

Usando o circuito de referência da [parte 1](https://github.com/GabrielMassuy/ifsc_eletronica_2020/blob/master/Projeto%20fonte/Parte%201.md):

![f1](/resources/images/fonte/circ7.jpg)

Com Vin igual a 17V, se a tensão sobre o resistor R1 for maior que 7V o diodo zener não estará polarizado e o regulador de tensão não terá mais a tensão de referência. Utilizando dois transistores PNP é possível construir uma fonte de corrente, assim o diodo zener não fica dependente da corrente que passa sobre o resistor R1 para ser polarizado.

### Adicionar o circuito proposto à fonte:

![f2](/resources/images/fonte/figura5.jpg)

### Fazendo o cálculo dos valores de R1 e R6

 ![f3](/resources/images/fonte/calculo6.jpg)

### Aplicando circuito ao projeto da fonte

Os transistores PNP utilizados são do tipo 2N3906 da fabricante NXP. O valor escolhido para R5 foi de 30k ohms.

![f4](/resources/images/fonte/circ8.jpg)

#### Tensão de saída com carga de 15 ohms
![f5](/resources/images/fonte/curva11.jpg)

A tensão de saída foi de 14,97V.

![f6](/resources/images/fonte/curva12.jpg)

A tensão de ripple foi de 505uV.

#### Tensão e corrente sobre o diodo zener D6, com carga de 15 ohms

![f7](/resources/images/fonte/curva13.jpg)

A tensão sobre o diodo zener ficou em 10V e a corrente sobre o diodo zener ficou oscilando entre 1,8 e 2 mA aproximadamente.
