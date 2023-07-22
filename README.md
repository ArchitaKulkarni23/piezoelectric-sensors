# piezoelectric-sensors
#include &lt;LiquidCrystal_I2C.h&gt;
#define PIEZO A0
LiquidCrystal_I2C lcd(0x27, 16, 2);
void setup()
{
pinMode(PIEZO, INPUT);
lcd.init();
lcd.backlight();
}
void loop()
{
int sensorValue=analogread(PIEZO);
float voltage=sensorValue*(5.0/1023.0);
lcd.clear();
lcs.setCursor(3,0);
lcd.print(“Voltage is”);
lcd.setCursor(0,1);
lcd.print(voltage);
delay(500);
}
