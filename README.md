# miniApp
 creating a mini App to convert a moment between second/minute/hour/day, with Javascript and the moment.js library
O moment nada mais faz do que transferir ou transformar a data em milissegundos

Para criar esse App usamos a biblioteca moment.js para datas link -> (https://momentjs.com/) 
após baixado colar dentro de outro arquivo ".js" no caso moment.min.js 

- no arquivo index.html colocar o moment.min.js antes do script do javascript pra ele rodar primeiro

- criado uma variavel para guardar o valor da data pedida 
let departureDateEntry = prompt('Digite a data de partida (formato DD/MM/YYYY)')

- criado uma variavel para armazenar a conversão do que foi digitado (em modo texto) utilizando o moment para converter modo string para numeros formato date
let departureDate = moment(departureDateEntry, 'DD/MM/YYYY')

- chamando o moment para retornar a data atual
let today = moment()

- agora fazer o calculo da diferença da data de hoje e a data de partida da nave
let dateDif = today - departureDate
( subtraindo os milissegundos passados até hoje, pelos milissegundos que passaram na data de partida da nave, o resultante é os milissegundos que passaram da data que a nave partiu at� hoje)

- Sendo isso para converter o resultado em segundos/minutos/horas/dias.
1 sec = 1000 milissegundos 
1 min = 60 sec
1 hora = 3600 sec
1 dia = 3600 *24sec

- perguntar para o usuario qual formato ele quer converter 
let chosenOption = prompt('Escolha como gostaria de exibir o tempo de partida\n1- Segundos\n2- Minutos\n3- Horas\n4- Dias'
)

- depois verificar qual formato ele escolheu e fazer o calculo correto que o mesmo requeriu

if (chosenOption == '1') {
let secondsOfDeparture = Math.round(dateDif / 1000)
alert( 'Tempo de vôo: ' + secondsOfDeparture + ' segundos' )
} else if (chosenOption == '2') {
let minutesOfDeparture = Math.round(dateDiff / 1000 / 60)
alert( 'Tempo de vôo: ' + minutesOfDeparture + ' minutos' )
} else if (chosenOption == '3') {
let hoursOfDeparture = Math.round(dateDif / 1000 / 3600)
alert( 'Tempo de vôo: ' + hoursOfDeparture + ' horas' )
} else if (chosenOption == '4') {
let daysOfDeparture = Math.round(dateDif / 1000 / 3600 / 24)
alert( 'Tempo de vôo: ' + daysOfDeparture + ' dias' )
} else {
alert( 'opção inválida' )

}

- para evitar numeros quebrados usamos a biblioteca Math nativa do Js
que tem um recurso chamado round que é um recurso que arredonda pra cima ou pra baixa um valor quebrado
