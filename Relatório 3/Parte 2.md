## Parte 2: Circuito referência de tensão com diodo Zener
O cálculo de Vz foi feito conforme especificado pelo relatório.

![f6](/resources/images/relat3/p2calculo1.jpg)

O valor de tensão escolhido para o diodo zener foi de 30V, e o modelo utilizado foi o EDZV30B (150mW) da fabricante ROHM Semiconductor. O datasheet do modelo foi usado para saber o valor da corrente Iz (2mA).

![f7](/resources/images/relat3/p2tabela.jpg)

Com Iz, o valor do resistor que irá ser conectado em série com diodo zener foi calculado.

![f8](/resources/images/relat3/p2calculo2.jpg)

### Simulando o circuito
![f9](/resources/images/relat3/p2circ1.jpg)
![f10](/resources/images/relat3/p2curva1.jpg)

Com a inclusão do resistor e diodo zener a tensão de ripple da saída do dobrador de tensão foi de 0,51V, um aumento significativo quando comparado com a tensão de ripple da parte anterior do relatório.

![f11](/resources/images/relat3/p3curva2.jpg)

A tensão sobre o diodo zener foi de 29,93V.

![f12](/resources/images/relat3/p2curva3.jpg)

A corrente do diodo zener variou entre 1,36 e 1,75 mA, sem ultrapassar o valor de 2 mA.
