# Project-250

#include "thingProperties.h"

int LEDpin = 23

void setup() {
  
  Serial.begin(9600);
 
  delay(1500); 

 
  initProperties();

  
  ArduinoCloud.begin(ArduinoIoTPreferredConnection);
  
 

  setDebugMessageLevel(2);
  ArduinoCloud.printDebugInfo();
}

void loop() {
  ArduinoCloud.update();
}

void onLedChange()  {
  if(led == 1){
    digitalWrite(LEDpin, HIGH);
    Serial.println("ON");
  }else{
    if(led == 0){
      digitalWrite(LEDpin, LOW);
      Serial.println("OFF");
    }
  }
}
