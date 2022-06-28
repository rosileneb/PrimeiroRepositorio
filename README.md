# PrimeiroRepositorio
## Pong no Java
// Posição da Bolinha
let xBolinha = 200;
let yBolinha = 200;
let diametro = 30;
let raio = diametro/2
// Velocidade da bolinha
let velocidadexBolinha = 5
let velocidadeyBolinha = 5
//Posição da Raquete
let xRaquete = 5
let yRaquete = 200
let compRaquete = 20
let alturaRaquete = 100
//Posição do Oponente
let xOponente = 575
let yOponente = 200
let compOponente = 20
let alturaOponente = 100
let colidiu = false
//placar do jogo
let meusPontos = 0;
let pontosDoOponente = 0;

function setup() {
createCanvas(600, 400);
}

function draw() {
background(0);
 incluirPlacar ()
 marcaPonto()

circle(xBolinha,yBolinha,diametro);

xBolinha += velocidadexBolinha;
yBolinha += velocidadeyBolinha;

// if = se

if (xBolinha+raio>600 || xBolinha-raio<0 ) {
velocidadexBolinha *= -1
}
if (yBolinha+raio>400 || yBolinha-raio<0 ) {
velocidadeyBolinha *= -1
}
rect(xRaquete, yRaquete, compRaquete, alturaRaquete);

if (keyIsDown(UP_ARROW)) {
yRaquete -= 5;
}

if (keyIsDown(DOWN_ARROW)) {
yRaquete += 5;
}

if (xBolinha - raio < xRaquete + compRaquete && yBolinha-raio< yRaquete+alturaRaquete && yBolinha+ raio>yRaquete) {
velocidadexBolinha *= -1
}
rect ( xOponente, yOponente, compOponente, alturaOponente)

yOponente = yBolinha -60

if (xBolinha + raio > xOponente)  {

velocidadexBolinha *= -1
}
  function incluiPlacar() {
    fill(255);
    text(meusPontos, 278, 26);
    text(pontosDoOponente, 321, 26);
}
function incluirPlacar(){
  fill(255)
  text(meusPontos, 278 ,26)
  text(pontosDoOponente,321,26)
 
}
  function marcaPonto() {
    if (xBolinha > 585) {
        meusPontos += 1;
    }
    if (xBolinha < 15) {
        pontosDoOponente += 1;
    }
}
}
