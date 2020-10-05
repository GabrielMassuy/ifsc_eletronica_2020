# Relatório 2 - Diodos

## Parte 1a: Circuito Retificador de Meia Onda

###### Experimento:

Montar um circuito retificador de meia onda utilizando resistores de 270Ω.
Utilizar capacitores de 330μF e 2200μF.

###### Procedimento:

1 - Simular o circuito do retificador de meia onda, inicialmente sem capacitor e anotar os valores da tensão de pico, eficaz e média, os valores da máxima tensão reversa e a corrente sobre os diodos em uma tabela.

2 - Em seguida, conectar um capacitor de 330μF e anotar os valores solicitados.

3 - Após isso, substituir o capacitor de 330μF por um de 2200μF, observar o formato da onda da tensão de saída e anotar os valores de solicitados.

4 - Responder o que são resistores shunt e como determinar o valor do resistor para o circuito.

### Simulação: Circuito retificador de meia onda sem capacitor

![p1circ1](/resources/images/relat2/p1circ1.jpg)

#### Formato de onda da tensão no enrolamento primário (Vf)

![p1onda1](/resources/images/relat2/p1onda1.jpg)

#### Formato de onda da tensão sobre o resistor (Vo1) e da tensão no enrolamento secundário (Vin1)
![p1onda2](/resources/images/relat2/p1v01.jpg)
![p1onda2](/resources/images/relat2/p1onda2.jpg)
![p1onda21](/resources/images/relat2/p1onda21.jpg)

É possível perceber que a onda Vo1 tem amplitude um pouco menor do que a onda Vin1. Isso acontece por conta da queda de tensão sobre o diodo, neste caso cerca de 0,72V (pico), para que o mesmo seja polarizado diretamente. O valor do sinal de tensão Vo1 é zero nos ciclos negativos de Vin por conta da polarização inversa do diodo.

#### Valores de tensão média e eficaz sobre o enrolamento secundário (Vin1) e o resistor (Vo1)
![p1](/resources/images/relat2/p1media1.jpg)

#### Formato de onda da corrente sobre o diodo (D1)
![p1onda4](/resources/images/relat2/p1corrente1.jpg)
![p1onda41](/resources/images/relat2/p1media2.jpg)

O valor máximo da corrente foi de 60,14mA, o valor médio foi de 18,74mA e o valor eficaz foi de 29,76mA.

### Simulação: Circuito retificador de meia onda com capacitor de 330μF
O diodo utilizado nas simulações foi o disponibilizado pelo próprio LTspice.
![p1circ2](/resources/images/relat2/p1circ2.jpg)

#### Formato de onda da tensão no enrolamento secundário (Vin2) e da tensão sobre o resistor (Vo2)
![p1onda5](/resources/images/relat2/p1onda3.jpg)
![p1onda6](/resources/images/relat2/p1onda4.jpg)

A adição do capacitor no circuito faz com que a taxa de variação da tensão Vo sobre o resistor diminua consideravelmente, quando comparado com o circuito sem capacitor.

No ciclo positivo de Vin o capacitor é carregado, e então no seu ciclo negativo o capacitor vai descarregando, fazendo com que a tensão sobre o resistor não seja zero. Quando Vin entra no ciclo positivo o capacitor começa a carregar novamente.

A diferença entre a tensão máxima de Vo e a tensão de Vo quando o capacitor começa a carregar novamente é a tensão de ripple. Nesse caso a tensão de ripple é de 2,5V.

#### Valores de tensão média e eficaz sobre o resistor (Vo2)
![p1onda7](/resources/images/relat2/p1media3.jpg)

#### Formato de onda da corrente sobre o diodo (D2)
![p1onda8](/resources/images/relat2/p1onda5.jpg)
![p1onda9](/resources/images/relat2/p1media4.jpg)

O valor máximo da corrente foi de 2,09A, o valor médio foi de 147,29mA e o valor eficaz foi de 435,95mA.

### Simulação: Circuito retificador de meia onda com capacitor de 2200μF
![p1circ3](/resources/images/relat2/p1circ3.jpg)

#### Formato de onda da tensão no enrolamento secundário (Vin) e da tensão sobre o resistor (Vo)
![p1onda10](/resources/images/relat2/p1onda6.jpg)
![p1onda11](/resources/images/relat2/p1onda7.jpg)

Com o aumento da capacitância do capacitor o valor da tensão de ripple diminuiu, sendo de 0,38V com o capacitor de 2200μF.

#### Valores de tensão média e eficaz sobre o resistor (Vo)
![p1onda12](/resources/images/relat2/p1media5.jpg)

#### Formato de onda da corrente sobre o diodo (D1)
![p1onda13](/resources/images/relat2/p1onda8.jpg)
![p1onda14](/resources/images/relat2/p1media6.jpg)

O valor máximo da corrente foi de 13,67A, o valor médio foi de 751,82mA e o valor eficaz foi de 2,74A.

#### Preenchimento da tabela com os valores solicitados (V)

![p1tabela3](/resources/images/relat2/p1tabela.jpg)

### Resultados
![p1ondaresult](/resources/images/relat2/p1result1.jpg)

Nesta simulação foi observado que ao adicionarmos um capacitor conectado em paralelo ao circuito, é possível manter sobre o resistor um valor de tensão próximo á tensão de pico do enrolamento secundário, porém para diminuir a tensão de ripple é necessário que o valor de capacitância aumente. Deste modo é possível que o formato de onda da tensão do enrolamento secundário seja retificado.

![p1ondaresult2](/resources/images/relat2/p1result2.jpg)

Também foi visto que toda vez que o capacitor carrega existe um pico de corrente (sendo maior na primeira vez que é carregado) que aumenta dependendo do valor de capacitância do capacitor. Portanto é importante verificar se os demais componentes do circuito conseguem aguentar esses valores de corrente, mesmo sendo em um intervalo de tempo pequeno.

## Parte 1b:  Resistores Shunt
Resistores Shunt são resistores usados para desviar a corrente de certos componentes ou para a medição de tensão e corrente.

Para a medição de corrente do circuito deve-se conectar um resistor shunt com baixa resistência em série com a carga, assim a queda de tensão sobre o resistor shunt será pequena e a carga irá continuar com praticamente a mesma queda de tensão que havia antes.

Após verificar a tensão sobre o resistor shunt a corrente é medida de forma indireta, usando a lei de Ohm, onde I = V/R.
