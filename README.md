#define BLYNK_PRINT Serial


#include <ESP8266WiFi.h>
#include <BlynkSimpleEsp8266.h>

// You should get Auth Token in the Blynk App.
// Go to the Project Settings (nut icon).
char auth[] = "5628DSigkkeEW3WdyKcF6npxeTU6dO6K";

// Your WiFi credentials.
// Set password to "" for open networks.
char ssid[] = "HUAWEI-A3A8";
char pass[] = "74042685";

void setup()
{ /*To avoid relays chatters when connected to blynk, set the pin to HIGH (for Relays that turns OFF at HIGH) before blynk.begin function. Eg. for D3 Given Below */ //
  pinMode(D3, OUTPUT);//digitalWrite(D3, HIGH);
  Serial.begin(9600);
  Blynk.begin(auth, ssid, pass);
  Blynk.syncAll(); //This will sync the last state of your device
  }
  void loop()
  {
    Blynk.run();
  }
