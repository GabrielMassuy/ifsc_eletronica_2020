# Relatório 1 - AmpOp

## Parte 2: Amplificador Inversor

###### Objetivo:

Medir o ganho de um amplificador inversor e verificar o efeito da saturação

###### Experimento:

Utilizando um Amp.OP. LM324N e o TL082 monte dois amplificadores inversores utilize o resistor de realimentação com valor 20 kΩ e a resistência de entrada de 2kΩ. Utilize a alimentação simétrica de +/-12V.

###### Procedimento:

1 - Simular o circuito utilizando como tensão de entrada um sinal senoidal com 0,5 Vp e 1kHz.

2 - Mostrar os resultados da tensão de saída.

3 - Verificar o valor do ganho obtido.

4 - Ir aumentando o valor da tensão de entrada e verificar para qual valor da tensão de entrada ocorre a saturação do sinal.

5 - Verificar qual o valor da queda de tensão com relação à tensão de alimentação.

6 - Discutir os resultados.

### Resultados calculados
Utilizando um AmpOp ideal, fez-se o cálculo do ganho de tensão "Av" do circuito.

![p2conta](/resources/images/relat1/p2conta.jpg)

O ganho calculado foi de -10.

### Formato de onda da tensão de entrada
![tensoafonte](/resources/images/relat1/p2fonte.jpg)

### Simulação: Circuito com LM324N
Circuito montado no LTspice, utilizando o modelo da Texas Instruments:

![p2circ1](/resources/images/relat1/p2circ1.jpg)

Tensão de entrada e tensão de saída do circuito:

![p2onda1](/resources/images/relat1/p2onda1.jpg)

### Simulação: Circuito com TL082
Circuito montado no LTspice, utilizando o modelo da Texas Instruments:

![p2circ2](/resources/images/relat1/p2circ2.jpg)

Tensão de entrada e tensão de saída do circuito:

![p2onda2](/resources/images/relat1/p2onda2.jpg)

Em ambos circuitos o sinal da tensão de saída tem amplitude de 5V e seus ciclos positivos aparecem em conjunto com os ciclos negativos do sinal da tensão de entrada, o que demonstra um ganho de -10.

Após comparar os sinais de entrada e saída dos circuitos, aumentou-se gradativamente o valor da amplitude do sinal de entrada até que ocorresse a saturação do sinal de saída em cada circuito.

### Análise de saturação: Circuito com LM324N
O sinal de saída do circuito com o LM324N teve saturação positiva quando a amplitude do sinal de entrada atingiu 1,08V e saturação negativa (e positiva) quando atingiu 1,14V.

Tensão de saída do circuito com 1,08V de amplitude na tensão de entrada:

![p2onda3](/resources/images/relat1/p2onda3.jpg)
![p2onda31](/resources/images/relat1/p2onda31.jpg)

O valor da tensão no ponto de saturação positivo foi de 10,77V e portanto o valor da queda de tensão foi de 1,23V.


Tensão de saída do circuito com 1,14V de amplitude na tensão de entrada:

![p2onda4](/resources/images/relat1/p2onda4.jpg)
![p2onda41](/resources/images/relat1/p2onda41.jpg)
![p2onda42](/resources/images/relat1/p2onda42.jpg)

O valor de tensão no ponto de saturação negativo foi de -11,32V e portanto o valor da queda de tensão foi de -0,68V (a tensão no ponto de saturação positivo continuou sendo 10,77V).

### Análise de saturação: Circuito com TL082
O sinal de saída do circuito com o TL082 começou a apresentar saturação positiva e negativa quando a amplitude do sinal de entrada atingiu 1,05V. A imagem do sinal de saída a seguir foi feita com a amplitude da tensão de entrada em 1,06V pois a saturação fica mais visível.

Tensão de saída do circuito com 1,06V de amplitude na tensão de entrada:
![p2onda5](/resources/images/relat1/p2onda5.jpg)
![p2onda51](/resources/images/relat1/p2onda51.jpg)
![p2onda52](/resources/images/relat1/p2onda52.jpg)

O valor de tensão no ponto de saturação foi de 10,37 e -10,37 volts, portanto o valor da queda de tensão foi de 1,63 e -1,63.

### Resultados
Comparando o formato de onda da tensão de entrada e de saída foi possível observar como o sinal é amplificado e invertido utilizando o circuito do AmpOp Inversor. Nesta simulação foi possível verificar que o sinal de saída tinha a amplitude dez vezes maior do que o sinal de entrada, e os ciclos positivos do sinal de saída coincidiam com os ciclos negativos do sinal de entrada.

Como a máxima amplitude do sinal da tensão de saída depende da tensão de alimentação do ampop, 12V neste caso, o maior valor de tensão esperado para o sinal saturado era de +-11,99V. Ao testarmos a situação de saturação, o ampop LM324N apresentou dois valores diferentes de tensão de saturação, 10,77V para o ciclo positivo e 11,32V para o ciclo negativo, enquanto que o ampop TL082 apresentou o valor de 10,37V para ambos ciclos. Isso mostra a importância de conhecer as informações técnicas do ampop que venha a ser utilizado em algum projeto, pois modelos diferentes apresentam diferenças na zona de saturação.
