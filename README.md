# teste
Dia 16/11/2022
# Labirinto em JavaScript
## _SENAI 2022_

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

No curso de Desenvolvimento de Sistemas do SENAI Shunji Nishimura, na aula de JavaScript foi realizada uma atividade com o intuito de criar um labirinto para:

- Otimizar o tempo
- Facilitar a compra
- Tecnologia avançada

## Aqui encontrará:

- Imagem demonstrativa
- Exemplos dos códigos
- Conteúdo teórico
- Colaboradores

## Imagem demonstrativa
![imagem mapa1](https://github.com/ruthmegmat/Aula28/blob/main/mapa1.jpg?raw=true)
No primeiro mapa procuramos deixar o caminho mais rápido e com uma pequena diferença  no segundo corredor, mudando o posicionamento da fileira.

## Exemplos dos códigos

Aqui está todos os códigos de nosso mapa:

var labirinto = [
  [99, 99, 99, 99, 99, 33, 44, 99, 99, 99, 99, 99, 99, 44, 44, 99, 99, 99, 99, 99],
  [99, 88, 44, 44, 44, 44, 44, 44, 44, 44, 44, 88, 44, 44, 44, 44, 44, 44, 44, 99],
  [99, 44, 44, 44, 44, 44, 44, 44, 44, 44, 44, 44, 44, 44, 44, 44, 44, 44, 44, 99],
  [99, 44, 44, 44, 44, 44, 44, 44, 44, 44, 44, 44, 44, 44, 44, 44, 44, 44, 44, 99],
  [99, 44, 44, 99, 99, 44, 88, 99, 99, 44, 44, 99, 99, 44, 44, 99, 99, 44, 88, 99],
  [99, 44, 44, 99, 99, 44, 44, 99, 99, 44, 88, 99, 99, 44, 88, 99, 99, 44, 44, 99],
  [99, 44, 44, 99, 99, 44, 44, 99, 99, 44, 44, 99, 99, 44, 44, 99, 99, 44, 44, 99],
  [99, 44, 44, 99, 99, 44, 44, 99, 99, 44, 44, 99, 99, 44, 44, 99, 99, 44, 44, 99],
  [99, 88, 44, 99, 99, 44, 44, 44, 88, 44, 44, 99, 99, 44, 44, 99, 99, 44, 44, 99],
  [99, 44, 44, 99, 99, 44, 44, 44, 44, 44, 44, 99, 99, 44, 44, 99, 99, 44, 44, 99],
  [99, 44, 44, 99, 99, 44, 44, 99, 99, 44, 44, 99, 99, 44, 44, 99, 99, 44, 44, 99],
  [99, 44, 44, 99, 99, 44, 44, 99, 99, 44, 44, 99, 99, 44, 44, 99, 99, 44, 44, 99],
  [99, 44, 44, 99, 99, 44, 44, 99, 99, 44, 44, 99, 99, 44, 44, 99, 99, 44, 44, 99],
  [99, 44, 44, 99, 99, 44, 44, 99, 99, 44, 44, 99, 99, 44, 44, 99, 99, 44, 44, 99],
  [99, 44, 44, 99, 99, 44, 44, 99, 99, 44, 44, 99, 99, 44, 44, 99, 99, 44, 44, 99],
  [99, 44, 44, 88, 44, 44, 44, 44, 44, 44, 44, 44, 88, 44, 44, 44, 44, 44, 44, 99],
  [99, 88, 44, 44, 44, 44, 44, 44, 44, 44, 44, 44, 44, 44, 44, 44, 44, 44, 88, 99],
  [99, 99, 99, 99, 99, 99, 99, 99, 99, 99, 99, 99, 99, 99, 99, 99, 99, 99, 99, 99],
  [99, 99, 99, 99, 99, 99, 99, 99, 99, 99, 99, 99, 99, 99, 99, 99, 99, 99, 99, 99]
]

 var clc = require("cli-color");   

function colorir(text) {
  if(text == 99 ) {
    return clc.bgCyan	('   ');
  } else if (text == 44) {
     return clc.bgWhite( '   ');
  }  else if (text == 88) {
     return clc.bgMagenta(' $ ');
  } else {
    return clc.	bgBlueBright('😊');
  }
  }

function mostrarLabirinto() {
  console.clear();
for (let linha of labirinto) {
  var linhaFormatada = []
  for (let item of linha ) {
    linhaFormatada.push(colorir(item));
  }
console.log(linhaFormatada.toString().replaceAll(',',''));
}
}
var x = 0;
var y = 5;

function desce() {
  if(labirinto[x + 1][y] !== 99) {
  labirinto[x][y] = 44  
    x = x + 1;
    labirinto[x][y] = 33
    contador++
   }
  }
function sobe() {
  if(labirinto[x - 1][y] !== 99 && x - 1 > 0 ) {
    labirinto[x][y] = 44
    x = x - 1;
    labirinto[x][y] = 33
    contador++
  }
}
 function direita() {
   if(labirinto[x][y + 1] !== 99){
labirinto[x][y] = 44
    y = y + 1;
    labirinto[x][y] = 33
     contador++
  }
 }

function esquerda() {
  if(labirinto[x][y - 1] !== 99 && y - 1 >= 0){
   labirinto[x][y] = 44
    y = y - 1;
    labirinto[x][y] = 33
    contador++
  }
}
var contador = 0;
while(true) {
  mostrarLabirinto();
  console.log('contador de passos:', contador);
  var escolha = prompt ('wasd');
  if(escolha == 'w') {
    sobe();
  } else if(escolha == 'a') {
    esquerda();
  } else if(escolha == 's') {
    desce();
    
  } else if(escolha == 'd') {
    direita();
  }
}



## Conteúdo teórico

De início, criamos um mapa com produtos diversificados e espalhados. 
Por fim, codificamos o mapa para termos várias possibilidades de caminho e demonstrar qual seria o mais viável.

## Colaboradores

Essa atividade foi ministrada pelo Professor João Vitor Biston.
E foi criada pelas alunas:
- Ana Carolina de Souza Pereira
- Leticia Suffi Mariano
- Luana Fajoli
- Luana Moreira Santos
- Milena Sampaio Rodrigues
- Ruth Megumi Matunoshita
