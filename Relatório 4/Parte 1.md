# Relatório 4 - Circuitos com Transistores do tipo MOS

## Parte 1: Determinar parâmetros do transistor de dois fabricantes

Os transistor utilizado foi o 2N7002, da nexperia e da ONsemiconductor

###### Procedimento:

Comparar o transistor 2N7002 de dois fabricantes

### Parâmetros L, W, uo, Cox, VA e Vt

![f1](/resources/images/relat4/p1tabela1.jpg)

Não foi encontrado o valor de Va de ambos transistores.

### Calcular o valor de RDS para as tensões VGS de 2V, 3V, 4V, 5V e 10V
![f2](/resources/images/relat4/p1formula1.jpg)
![f3](/resources/images/relat4/p1tabela2.jpg)

### Tensões máximas de operação

![f4](/resources/images/relat4/p1tabela3.jpg)

### Curva ID x VDS para as tensões VGS de 2V, 3V, 4V, 5V e 10V
#### DIODES

![f5](/resources/images/relat4/p1circ1.jpg)
![f6](/resources/images/relat4/p1curva1.jpg)
![f7](/resources/images/relat4/p1curva2.jpg)

#### nexperia

![f8](/resources/images/relat4/p1circ2.jpg)
![f9](/resources/images/relat4/p1curva4.jpg)
![f10](/resources/images/relat4/p1curva3.jpg)

As curvas dos gráficos plotados ficaram levemente diferentes dos gráficos apresentados no datasheet dos dois fabricantes. Essa diferença pode ser por conta de elementos não considerados na simulação virtual, como por exemplo a temperatura de operação.

### Valores de RDS obtidos com a curva ID x VDS

![f11](/resources/images/relat4/p1tabela4.jpg)

O cálculo dos valores de RDS foi feito pegando dois pontos da reta e calculando a sua inclinação. Como os gráficos plotados ficaram diferentes dos gráficos contidos no datasheet, os valores de RDS calculados e plotados também ficaram diferentes. 
