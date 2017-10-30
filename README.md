# telota2.c
teplota.c
#include <LiquidCrystal.h>
#include <LiquidCrystal_I2C.h>
#include <OneWire.h>
#include <DallasTemperature.h>

#define ONE_WIRE_BUS 2

LiquidCrystal_I2C lcd(0x20,20,4);

const int pinCidlaDS = 4;

OneWire oneWireDS(pinCidlaDS);

DallasTemperature senzoryDS(&oneWireDS);

void setup() 
{
senzoryDS.begin();

  
  lcd.backlight();
  lcd.print("Teplota je ");
  lcd.print("senzoryDS.getTempCByIndex(0)");
  lcd.print("oC");
  
}

void loop() 
{
   senzoryDS.requestTemperatures();
 
   

   delay (50);
}
