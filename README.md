# CALCULADORA_ARDUINO_2.0
NUEVA_VERSION_PROBADA_DE_CALCULADORA_ARDUINO_TEAM_SAVE.THE.SEMESTER.COFFEE
#include <Keypad.h>
#include <LiquidCrystal.h>

const byte ROWS = 4;
const byte COLS = 4;

char hexaKeys[ROWS][COLS] = {
//{'1', '4', '3', '+'},
//{'4', '5', '6', '-'},
//{'7', '8', '9', '*'},
//{'X', '0', '=', '/'}
{'1', '4', '0', 'X'},
{'*', '9', '8', '7'},
{'7', '6', '5', '4'},
{'X', 'A', '=', '1'}
//{'1', '4', '7', '*'},
//{'2', '5', '8', '0'},
//{'3', '6', '9', 'X'},
//{'+', '-', '*', '/'}
};

byte rowPins[ROWS] = {3, 2, 1, 0};
byte colPins[COLS] = {7, 6, 5, 4};

LiquidCrystal lcd(13, 12, 11, 10, 9, 8);
Keypad myKeypad = Keypad( makeKeymap(hexaKeys), rowPins, colPins, ROWS, COLS); 

boolean valorActual = false;
boolean siguiente = false;
boolean final = false;
String num1, num2,num3;
int total;
int movimiento;
char op;

void setup(){
    lcd.begin(16,2);
    lcd.setCursor(0,0);
    lcd.print("CALCULADORA");
    lcd.setCursor(0,1);
    lcd.print("  + - x /  ");
    delay(2500);
    lcd.clear();
}
// PEÑA//
