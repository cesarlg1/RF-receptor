#include <SPI.h>
#include <nRF24L01.h>
#include <RF24.h>

RF24 radio(9, 10); // CE, CSN

const byte addresses[][6] = {"00001", "00002"};

//*************  Controle de Contagem  *************************
   int sensor1_rf = 0;
   int sensor2_rf = 0;
   int sensor3_rf = 0;
   int sensor4_rf = 0;
   int sensor5_rf = 0;
   int sensor6_rf = 0;
   int sensor7_rf = 0;
   int sensor8_rf = 0;
   int sensor9_rf = 0;

    //*************  Controle de estado dos pinos de contagem  *******************
   
int buttonState1;
int buttonState2;
int buttonState3;
int buttonState4;
int buttonState5;
int buttonState6;
int buttonState7;
int buttonState8;
int buttonState9;

void setup() {

  radio.begin();
  Serial.begin(115200);

  radio.openWritingPipe(addresses[0]); // 00002
  radio.openReadingPipe(1, addresses[1]); // 00001
  radio.setPALevel(RF24_PA_MIN);
}

void loop() {
 
  radio.startListening();
 // if (radio.available()) {
    while (radio.available()) {
      
      radio.read(&sensor1_rf, sizeof(sensor1_rf));
      radio.read(&sensor2_rf, sizeof(sensor2_rf));
      radio.read(&sensor3_rf, sizeof(sensor3_rf));
      radio.read(&sensor4_rf, sizeof(sensor4_rf));
      radio.read(&sensor5_rf, sizeof(sensor5_rf));
      radio.read(&sensor6_rf, sizeof(sensor6_rf));
      radio.read(&sensor7_rf, sizeof(sensor7_rf));
      radio.read(&sensor8_rf, sizeof(sensor8_rf));
      radio.read(&sensor9_rf, sizeof(sensor9_rf));
     //  }
   
   }
    Serial.print("sensor1_rf : ");                              //imprime
    Serial.println(sensor1_rf);                                 //imprime variavel
    Serial.print("sensor2_rf : ");                              //imprime
    Serial.println(sensor2_rf);                                 //imprime variavel
    Serial.print("sensor3_rf : ");                              //imprime
    Serial.println(sensor3_rf);                                 //imprime variavel
    Serial.print("sensor4_rf : ");                              //imprime
    Serial.println(sensor4_rf);                                 //imprime variavel
    Serial.print("sensor5_rf : ");                              //imprime
    Serial.println(sensor5_rf);                                 //imprime variavel
    Serial.print("sensor6_rf : ");                              //imprime
    Serial.println(sensor6_rf);                                 //imprime variavel
    Serial.print("sensor7_rf : ");                              //imprime
    Serial.println(sensor7_rf);                                 //imprime variavel
    Serial.print("sensor8_rf : ");                              //imprime
    Serial.println(sensor8_rf);                                 //imprime variavel
    Serial.print("sensor9_rf : ");                              //imprime
    Serial.println(sensor9_rf);                                 //imprime variavel
        
    Serial.print("estado sensor1 : ");                              //imprime
    Serial.println(buttonState1);                                 //imprime variavel
    Serial.print("estado sensor2 : ");                              //imprime
    Serial.println(buttonState2);                                 //imprime variavel
    Serial.print("estado sensor3 : ");                              //imprime
    Serial.println(buttonState3);                                 //imprime variavel
    Serial.print("estado sensor4 : ");                              //imprime
    Serial.println(buttonState4);                                 //imprime variavel
    Serial.print("estado sensor5 : ");                              //imprime
    Serial.println(buttonState5);                                 //imprime variavel
    Serial.print("estado sensor6 : ");                              //imprime
    Serial.println(buttonState6);                                 //imprime variavel
    Serial.print("estado sensor7 : ");                              //imprime
    Serial.println(buttonState7);                                 //imprime variavel
    Serial.print("estado sensor8 : ");                              //imprime
    Serial.println(buttonState8);                                 //imprime variavel
    Serial.print("estado sensor9 : ");                              //imprime
    Serial.println(buttonState9);                                 //imprime variavel
    delay(500);
}
