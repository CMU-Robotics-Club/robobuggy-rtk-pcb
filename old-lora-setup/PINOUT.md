
## Teensy 4.1 <-> LoRa breakout pinout

| Signal | Teensy pin | Breakout pin |
| --- | --- | --- |
| NSS / CS | 10 | CS |
| SPI MOSI | 11 | SDI |
| SPI MISO | 12 | SDO |
| SPI SCK | 13 | SCK |
| RESET | 25 | RST |
| DIO0 | 26 | D0 |
| DIO1 | 27 | D1 |
| RXEN | 8 | RXEN |
| TXEN | 9 | TXEN |
| +5V bus | VIN | 5V |
| +3V3 | 3.3V | 3V3 (pull-ups only) |
| GND bus | GND | GND |

## Power

The USB line should ideally be data only to avoid two sources of +5V