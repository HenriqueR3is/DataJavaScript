Minhas anotações da vídeoaula recomendada pelo professor.

Date
Ela e representada por milissegundos desde a Era Unix que comecou em 1 de janeiro de 1970 as 00:00:00 do UTC (sistema de referencia que calcula fuso horario do mundo inteiro)

Existem 4 maneiras de criar uma data:
1 - A partir de funcao construtora Date, sem parametros: 
ex: var hoje = new Date();
obs: getTime mostra o tempo em milissegundos

2 - Criando uma data passando como parametro o tempo em milissegundos
ex: var natal = new Date(1419465600000);
obs: o calculo e feito a partir do UTC (Z ou Zulu Time). Por isso sai -2, pois estamos no horario Brasileiro (de verao).

3 - Criando uma data passando como parametro uma String
ex: No JS nao temos o simple date format para editar mascara. Mas temos o Date.parse que passa o tempo em milissegundos com base na data colocada, por exemplo Date.parse("2014/12/25"); retorna 1419472800000. e se usamos new Date com esses numeros ele retorna exatamente a data passada.
new Date("2014/12/25"); 
new Date("12/25/2014"); 

// new Date("25/12/2014"); O formato que usamos no Brasil nao funciona

Oficialmente os formatos aceitos sao RFC 2822 ou ISO 8601

RFC: Dia da semana - Mes - Dia - Ano - Hora ...
Podemos criar uma data passando como parametro uma String RFC

ISO: Ano - Mes - Dia ...
Podemos criar uma data passando como parametro uma String ISO
Obs: esse formato e sensivel a time zone, entao como estamos no Brasil o tempo fica em -2.  Para resolver podemos usar no final da String o -02:00, por exemplo: new Date("2014-12-25T10:30:00-02:00"); se nao usarmos o -2 ele retornaria 8:30 e nao 10:30.

4 - Criando uma data passando como parametro a propria data
ex: var natal = new Date(2014, 11, 25, 10, 30, 0);
Obs: Se atentar ao mes que comeca em 0, entao se quiser passar o mes 12 precisamos colocar 11. So se aplica o desconto de -2 quando usamos o tempo em milissegundos, quando especificamos a data ele respeita.

Date API
getDate - Retorna o dia
getDay - Retorna o dia da semana
getFullYear - Retorna o ano
getHours - Retorna as horas
getMilliseconds - Retorna os milissegundos
getMinutes - Retorna os minutos
getMonth - Retorna o mes
getSeconds - Retorna os segundos
getTime - Retorna o tempo em milissegundos
getString - Retorna a data em String

Obs: JavaScript e uma linguagem da decada de 90, entao o getYear se comporta como antes, entao se quiser ver 2014, use o getFullYear. 
O getMonth comeca em 0 entao vai de 0 a 11. 
O getDay se refere ao dia da semana, comecando em domingo que e 0. 
O getDate sim retorna o dia normalmente.
