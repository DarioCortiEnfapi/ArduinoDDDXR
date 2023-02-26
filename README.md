# ArduinoDDDXR
code for arduino display with x written and with the emojis moving and flashing
#include <Wire.h>
#include <LiquidCrystal_I2C.h>

LiquidCrystal_I2C lcd(0x27,16,2);

void setup() {
  lcd.init();                      // Inizializza il display
  lcd.backlight();                 // Accendi la retroilluminazione del display
  lcd.setCursor(0, 0);             // Imposta il cursore sulla prima riga
  lcd.print("Ciao Mondo ");        // Mostra "Ciao Mondo" seguito da uno spazio
  lcd.write(byte(0));              // Mostra un'icona di faccina sorridente
  lcd.write(byte(1));              // Mostra un'icona di cuore
  lcd.write(byte(2));              // Mostra un'icona di stella
  lcd.write(byte(3));              // Mostra un'icona di nota musicale
}

void loop() {
  for (int i = 0; i < 15; i++) {   // Scorre il messaggio verso sinistra per 15 volte
    lcd.scrollDisplayLeft();       // Scrolla il display verso sinistra
    delay(250);                    // Attende per 250 millisecondi
  }

  lcd.clear();                     // Pulisce il display
  delay(250);                      // Attende per 250 millisecondi
  
  lcd.setCursor(0, 0);             // Imposta il cursore sulla prima riga
  lcd.print("Corti Dario");        // Mostra "Ciao Mondo" seguito da uno spazio
  lcd.write(byte(0));              // Mostra un'icona di faccina sorridente
  lcd.write(byte(1));              // Mostra un'icona di cuore
  lcd.write(byte(2));              // Mostra un'icona di stella
  lcd.write(byte(3));              // Mostra un'icona di nota musicale
  
  delay(500);                      // Attende per 500 millisecondi
  
  for (int i = 0; i < 15; i++) {   // Scorre il messaggio verso sinistra per 15 volte
    lcd.scrollDisplayLeft();       // Scrolla il display verso sinistra
    delay(250);                    // Attende per 250 millisecondi
  }
  
  lcd.clear();                     // Pulisce il display
  delay(250);                      // Attende per 250 millisecondi
}
