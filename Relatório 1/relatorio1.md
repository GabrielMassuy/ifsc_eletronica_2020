# Relatório 1 - AmpOp

## Parte 1: Seguidor de Tensão

###### Objetivo:

Verificar o funcionamento de um circuito seguidor de tensão

###### Experimento:

Utilizando um Amp.OP. LM324N e um TL082 monte dois circuitos na configuração de seguidor de tensão (Buffer), com uma resistência de realimentação de 10 kΩ em cada um dos circuitos. Utilize a alimentação simétrica de +/-12V.

###### Procedimento:

1 - Simular o circuito utilizando como tensão de entrada um sinal senoidal com 0,5 Vp e 1kHz.

2 - Discutir os resultados.

#### Resultados calculados
Utilizando um AmpOp ideal, faz-se o cálculo do ganho de tensão "Av" do circuito.

![p1conta1](/resources/images/relat1/p1conta.jpg)

#### Formato de onda da tensão de entrada
![tensaofonte](/resources/images/relat1/ondafonte.jpg)
#### Circuito com LM324N
Circuito montado no LTspice, utilizando o modelo da Texas Instruments.

![Circuito1p1](/resources/images/relat1/p1cir1.jpg)

Tensão de entrada e tensão de saída do circuito.

![p1onda1](/resources/images/relat1/p1onda1.jpg)

#### Circuito com TL082
Circuito montado no LTspice, utilizando o modelo da Texas Instruments.

![Circuito2p1](/resources/images/relat1/p1cir2.jpg)

Tensão de entrada e tensão de saída do circuito.

![p1onda2](/resources/images/relat1/p1onda2.jpg)

#### Resultados
Como o circuito é um **seguidor de tensão**, era esperado que o ganho do circuito fosse 1. Isso é confirmado pelo resultado da parte calculada com Av = 1 e pelo resultado da parte simulada, onde o formato de onda da tensão de saída é praticamente o mesmo da tensão de entrada.
