#include <LiquidCrystal_I2C_AvrI2C.h>
LiquidCrystal_I2C_AvrI2C lcd(0x3f,16,2); 
const int sensor =A0;
int sensor_deger ;
float voltaj_deger ;
float sicaklik;
void setup() {
 lcd.begin();
}
void loop() {
sensor_deger = analogRead(sensor);
  voltaj_deger = (sensor_deger / 1023.0 ) *5000;
  sicaklik = voltaj_deger / 10.0;
  lcd.home();  
  lcd.print("Sicaklik=");
  lcd.setCursor(9,0);
  lcd.print(sicaklik);
}
