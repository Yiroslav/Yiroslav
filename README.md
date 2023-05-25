#include <Wire.h>
#include <LiquidCrystal_I2C.h>
LiquidCrystal_I2C lcd(0x27, 16, 2);
#include "DHT.h"

#define DHT11PIN 2
#define Relay A3
byte degree[8] = // кодируем символ градуса
{
  B00111,
  B00101,
  B00111,
  B00000,
  B00000,
  B00000,
  B00000,
};
void setup()
{
  lcd.init();
  lcd.backlight();
  lcd.createChar(1, degree); // Создаем символ под номером 1
}
void loop()
 {
  pinMode (Relay, OUTPUT); //Инициализируем режим работы порта в режиме выхода
 
  Serial.begin (9600);
}
void loop()
{
  int chk = sensor.read(DHT11PIN);
  lcd.setCursor(0, 0);
  lcd.print("Hum:          %");
  lcd.setCursor(11, 0);
  lcd.print(sensor.humidity);
  lcd.setCursor(0, 1);
  lcd.print("temp:         C");
  lcd.setCursor(11, 1);
  lcd.print(sensor.temperature);
  delay(2000);
}
if (t > 25) //Указываем условие, если переменная "h" (влажность) больше 40%
{
  digitalWrite (Relay, LOW); //то включаем наше реле, которое приводит в действие вентилятор
}
else //иначе
{
  digitalWrite (Relay, HIGH); //Реле будет выключено, вентилятор не работает
}
/*Вы можете изменить переменную на переменную . Мы привели вам самый простой пример, его идею можно использовать для создания качественного проекта! */
}
