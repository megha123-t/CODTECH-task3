//Interface the DHT11 Temp & Humidity sensor and display humidity and  temperature
//in Celsius, Fahrenheit, and Kelvin on a 20x4 character LCD

#include  <dht.h>
#include <LiquidCrystal.h>

//variable declarations
dht DHT;
double  tempF = 0;
double tempK = 0;
const int RS = 2, EN = 3, D4 = 4, D5 = 5, D6  = 6, D7 = 7;

LiquidCrystal lcd(RS,EN,D4,D5,D6,D7);   //set Uno pins that  are connected to LCD, 4-bit mode

void setup() {
  lcd.begin(20,4);    //set  20 columns and 4 rows of 16x2 LCD

}

void loop() {
  int readDHT  = DHT.read11(8);      //grab the 40-bit data packet from DHT sensor

  tempF  = DHT.temperature*9/5 + 32;   //convert temp to Fahrenheit
  tempK = DHT.temperature  + 273.15;   //convert temp to Kelvin
  lcd.print("Temp: ");
  lcd.print(DHT.temperature);     //display temp in C on LCD
  lcd.print("C");

  lcd.setCursor(0,1);
  lcd.print("Temp: ");
  lcd.print(tempF);     //display temp in F on LCD
  lcd.print("F");

  lcd.setCursor(0,2);
  lcd.print("Temp: ");
  lcd.print(tempK);     //display temp in Kelvin on LCD
  lcd.print("K");
    
  lcd.setCursor(0,3);
  lcd.print("Humidity: ");
  lcd.print(DHT.humidity);
  lcd.print("%");
  lcd.setCursor(0,0);
  delay(2000); 

}
