# Relatório 1 - AmpOp

## Parte 3: Amplificador Não-Inversor

###### Objetivo:

Medir o ganho de um amplificador não-inversor e verificar o efeito da saturação

###### Experimento:

Utilizando um Amp.OP. LM324N e o TL082 monte dois amplificadores não-inversores.
Utilize o resistor de realimentação com valor 20 kΩ e o outro resistor igual à 2kΩ.
Utilize a alimentação simétrica de +/-12V.

###### Procedimento:

1 - Simular o circuito utilizando como tensão de entrada um sinal senoidal com 0,5 Vp e 1kHz.

2 - Mostrar os resultados da tensão de saída.

3 - Verificar o valor do ganho obtido.

4 - Ir aumentando o valor da tensão de entrada e verificar para qual valor da tensão de entrada ocorre a saturação do sinal.

5 - Verificar qual o valor da queda de tensão com relação à tensão de alimentação.

6 - Discutir os resultados.

### Resultados calculados
Utilizando um AmpOp ideal, fez-se o cálculo do ganho de tensão "Av" do circuito.

![p3conta](/resources/images/relat1/p3conta.jpg)

O ganho calculado foi de 11 V/V.

### Formato de onda da tensão de entrada
![tensoafonte](/resources/images/relat1/p2fonte.jpg)

### Simulação: Circuito com LM324N
Circuito montado no LTspice, utilizando o modelo da Texas Instruments:

![p3circ1](/resources/images/relat1/p3circ1.jpg)

Tensão de entrada e tensão de saída do circuito:

![p3onda1](/resources/images/relat1/p3onda1.jpg)

A amplitude do sinal de saída foi de 5,51V, o que corresponde a um ganho de aproximadamente 11 vezes o valor de entrada.

### Simulação: Circuito com TL082
Circuito montado no LTspice, utilizando o modelo da Texas Instruments:

![p3circ2](/resources/images/relat1/p3circ2.jpg)

Tensão de entrada e tensão de saída do circuito:

![p3onda2](/resources/images/relat1/p3onda2.jpg)

A amplitude do sinal de saída foi de 5,48V, o que corresponde novamente a um ganho de aproximadamente 11 vezes o valor de entrada.

Após comparar os sinais de entrada e saída dos circuitos, aumentou-se gradativamente o valor da amplitude do sinal de entrada até que ocorresse a saturação do sinal de saída em cada circuito.

### Análise de saturação: Circuito com LM324N
O sinal de saída do circuito com o LM324N teve saturação positiva quando a amplitude do sinal de entrada atingiu 0,99V e saturação negativa (e positiva) quando atingiu 1,04V.

Tensão de saída do circuito com 0,99V de amplitude na tensão de entrada:

![p3onda3](/resources/images/relat1/p3onda3.jpg)
![p3onda31](/resources/images/relat1/p3onda31.jpg)

O valor da tensão no ponto de saturação positivo foi de 10,77V e portanto o valor da queda de tensão foi de 1,23V.


Tensão de saída do circuito com 1,04V de amplitude na tensão de entrada:

![p3onda4](/resources/images/relat1/p3onda4.jpg)
![p3onda41](/resources/images/relat1/p3onda41.jpg)
![p3onda42](/resources/images/relat1/p3onda42.jpg)

O valor de tensão no ponto de saturação negativo foi de -11,33V e portanto o valor da queda de tensão foi de -0,67V (a tensão no ponto de saturação positivo continuou sendo 10,77V).

### Análise de saturação: Circuito com TL082
O sinal de saída do circuito com o TL082 começou a apresentar saturação positiva e negativa quando a amplitude do sinal de entrada atingiu 1,40V.

Tensão de saída do circuito com 1,40V de amplitude na tensão de entrada:
![p3onda5](/resources/images/relat1/p3onda5.jpg)
![p3onda51](/resources/images/relat1/p3onda51.jpg)
![p3onda52](/resources/images/relat1/p3onda52.jpg)

O valor de tensão no ponto de saturação foi de 10,47 e -10,47 volts, portanto o valor da queda de tensão foi de 1,53 e -1,53 volts.

### Resultados
Comparando o formato de onda da tensão de entrada e de saída foi possível observar como o sinal é reproduzido de forma amplificada utilizando o circuito do AmpOp Não-Inversor. Nesta simulação foi possível verificar que o sinal de saída tinha a amplitude onze vezes maior do que o sinal de entrada, e os ciclos positivos e negativos do sinal de saída coincidiam com os do sinal de entrada.

Como a máxima amplitude do sinal da tensão de saída depende da tensão de alimentação do ampop, 12V neste caso, o maior valor de tensão esperado para o sinal saturado era de +-11,99V. Ao testarmos a situação de saturação, o ampop LM324N apresentou dois valores diferentes de tensão de saturação, 10,77V para o ciclo positivo e 11,33V para o ciclo negativo, enquanto que o ampop TL082 apresentou o valor de 10,47V para ambos ciclos.
