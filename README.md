# Chip_Ordenador
Projeto de chip capaz de receber 4 palavras de 8 bits e ordená-los do maior ao menor

O projeto é composto pelos blocos:

##Ordenador

Bloco principal, composto de 5 blocos Max2 ordenados de forma que as comparações acabem ordenando os valores de entrada.

##Max2

Recebe 2 palavras de 8 bits e as ordena nas saídas MAX (pro valor maior) e MIN (pro valor menor)
É composto de 1 bloco Comparador e 2 Mux 2:1.

##Comparador

O bloco comparador, recebe 2 palavras de 8 bits e tem saída em valor lógico LOW (0) caso o primeiro valor seja maior e saída em valor lógico HIGH (1) caso o segundo valor seja maior. É usado para controlar os Mux.

É composto por 8 comparadores de 1 bit, os quais tem como entrada cada bit das 2 palavras recebidas juntamente com o ativador das suas saídas (En) e como saída, tem B_A, que tem saída em valor lógico LOW (0) caso o primeiro valor seja maior e saída em valor lógico HIGH (1) caso o segundo valor seja maior.

Os comparadores de 1 bit são ligados em cascata, onde o primeiro compara os MSB das palavras e caso os 2 sejam iguais, ele ativa o comparador do bit seguinte e assim sucessivamente até os LSB. Por fim, todas as saídas B_A são ligadas numa porta OR (apesar de que apenas uma estará ativa, foi necessária a inclusão da OR para a compilação do bloco) e na saída B_A, que finalmente indirará se a palavra B é maior que a palavra A ou não.

##Mux
Controlam qual das 2 palavras recebidas inicialmente irá para a saída MAX e qual irá para a MIN.
