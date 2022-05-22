// C++ code

//VARIAVEIS
const byte led = 13;
const byte botao = 2;

const int ledL = 12;
const int botaoL = 4;
const int ledR = 8;
const int botaoR = 7;

int estadoBotao = 0;
int estadoBotaoL = 0;
int estadoBotaoR = 0;

int cronometro = 0;

volatile byte state = LOW;

void setup() {

  //PINOS LED VERMELHO
  pinMode(led, OUTPUT);
  pinMode(botao, INPUT_PULLUP);
  attachInterrupt(digitalPinToInterrupt(botao), blink, FALLING);

  //PINOS LED ESQUERDO
  pinMode(ledL, OUTPUT);
  pinMode(botaoL, INPUT);

  //PINOS LED DIREITO
  pinMode(ledR, OUTPUT);
  pinMode(botaoR, INPUT);
}

void loop() {
  estadoBotao = digitalRead(botao);
  estadoBotaoL = digitalRead(botaoL);
  estadoBotaoR = digitalRead(botaoR);

  //LED VERMELHO
  if (estadoBotao == state) {
    digitalWrite(led, state);
    if (estadoBotao == HIGH) {

      //LED ESQUERDO
      if (estadoBotaoL == LOW) {
        delay(500);
        while (cronometro != 10) {
          digitalWrite(ledL, HIGH);
          delay(320);
          digitalWrite(ledL, LOW);
          delay(320);
          cronometro++;
          delay(10);

          //PARAR SETA MODO1
          if (state == LOW) {
            break;
            delay(10);
          }
        }
        //
        state = HIGH;
        cronometro = 0;
      }

      //LED DIREITO
      if (estadoBotaoR == LOW) {
        delay(500);
        while (cronometro != 10) {
          digitalWrite(ledR, HIGH);
          delay(320);
          digitalWrite(ledR, LOW);
          delay(320);
          cronometro++;
          delay(10);

          //PARAR SETA MODO1
          if (state == LOW) {
            break;
            delay(10);
          }
        } 
      	//
        state = HIGH;
        cronometro = 0;
      }
    }
  }
}
//
void blink() {
  state  = !state;
}
