# AlphaFive-Control
An Arduino control library for the [Alpha Clock Five](https://wiki.evilmadscientist.com/Alpha_Clock_Five) by [Evil Mad Scientist Laboratories
](https://www.evilmadscientist.com/)


## Example
Using [wESP32](https://wesp32.com/) board wired to UART1 pins.

```
#include <HardwareSerial.h>
#include <AlphaFive-Control.h>

HardwareSerial ESPSerial(1);
AlphaClockFive FirstClock(&ESPSerial);
long RANDOM_NUM;

void setup()
{
  ESPSerial.begin(19200, SERIAL_8N1, 13, 12);
  FirstClock.writeWord("SETUP");
  delay(1000);
}

void loop()
{
  RANDOM_NUM = random(0,99999);
  FirstClock.writeNumber(RANDOM_NUM);
  delay(500);
}

```

## TODO
* Support daisy-chained units
