# Projeto da Fonte

## Parte 3 - Adicionando um circuito de proteção de sobrecorrente ao regulador linear.

### Primeiramente reflita e pesquise sobre o que é sobrecorrente? Quais os impactos neste circuito? O que deve fazer um circuito de proteção de sobrecorrente? O que é a proteção foldback?

#### O que é sobrecorrente?
Sobrecorrente é o que ocorre quando um condutor é percorrido por uma corrente maior do que se esperava. Isso pode acabar danificando e diminuindo a vida útil de  componentes eletrônicos e da isolação de fios elétricos do circuito.

#### Quais os impactos neste circuito?
Caso ocorra sobrecorrente, diversos componentes do circuito podem acabar queimando (diodos, resistores, ampops, transistores).

#### O que deve fazer um circuito de proteção de sobrecorrente? O que é proteção foldback?
Uma das formas que o circuito de proteção de sobrecorrente pode agir é desviando parte da corrente quando ela atingir um valor maior do que o projetado.

Como a corrente sobre um condutor depende da diferença de potencial sobre o mesmo, outro modo de fazer a proteção de sobrecorrente é diminuindo a tensão sobre o condutor, assim a corrente acaba diminuindo também. O circuito foldback funciona desta maneira, ele reduz a tensão fornecida para a carga quando a corrente atinge certo valor, diminuindo o valor da tensão de saída e da corrente sobre a carga e protegendo a carga e o regulador de uma sobrecorrente.

Exemplo de circuito foldback:
![f1](/resources/images/fonte/figura6.jpg)

### Circuito limitador de corrente proposto

![f2](/resources/images/fonte/circ9.jpg)

Neste circuito foi utilizado parâmetros do transistor NMOS 2N7002 da fabricante DIODES Semiconductor. O Vds terá o mesmo valor de Vt (2,154) e a tensão de saída esperada é cerca de 4,4V. O circuito deverá entrar em ação diminuindo a tensão nos terminais quando a corrente da carga ultrapassar 1,2A. Foi dado um valor de 30m ohms para a resistência shunt.

### Cálculo de R7 e R9

![f3](/resources/images/fonte/calculo7.jpg)

### Projeto da fonte com o circuito limitador de corrente:

![f4](/resources/images/fonte/circ10.jpg)

### Tensão de saída sem carga
![f5](/resources/images/fonte/curva14.jpg)

A tensão de saída sem carga teve um valor de 14,97V após inicializar, o ripple teve valores muito baixos.

### Tensão e corrente de saída com carga de 2 ohms
![f6](/resources/images/fonte/x1.jpg)

A tensão teve um valor de 2,4 V e a corrente foi de 1,23A.

### Tensão e corrente de saída com carga de 10 ohms

![f6](/resources/images/fonte/x2.jpg)

A tensão teve um valor de 12,14V e a corrente foi de 1,21A.

### Tensão e corrente de saída com carga de 15 ohms

![f6](/resources/images/fonte/x3.jpg)

A tensão teve um valor de 14,97V e a corrente foi de 998,5 mA.

### Tensão e corrente de saída com carga de 100k ohms

![f6](/resources/images/fonte/x4.jpg)

A tensão teve um vaor de 14,97V e a corrente foi de 149uA.

## Resultados

Com a finalização do projeto da fonte, obteve-se valores muito próximos aos 15V de saída inicialmente requisitados. O regulador de tensão está funcionando e a fonte está apresentando 14,97V de saída com resistências de 15 a 100k ohms. O circuito de proteção contra sobrecorrente também atuou em cargas com valores abaixo de 15 ohms, abaixando a tensão de saída e mantendo a corrente perto dos 1,2A máximos.
