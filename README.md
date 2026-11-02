# robobuggy-rtk-pcb
RTK base station PCB

## Layout

- `old-lora-setup/` — KiCad project for the base station radio: Teensy 4.1 + SparkFun LoRa 1W Breakout 915MHz (SPX-18572). Pinout matches `lora_rtcm_broadcast` in [robobuggy-firmware](https://github.com/CMU-Robotics-Club/robobuggy-firmware).
- `library/` — shared project library, registered in the project's `sym-lib-table` / `fp-lib-table` as `robobuggy_rtk` via `${KIPRJMOD}/../library/...`.
  - `robobuggy_rtk.kicad_sym` — `Teensy_4.1`, `SparkFun_LoRa_1W_Breakout_915MHz`
  - `robobuggy_rtk.pretty` — matching footprints (Teensy outer 48 pins; SparkFun breakout headers + 3.3 mm standoff holes)

## Teensy 4.1 ↔ LoRa breakout pinout

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

The +5V and GND buses are fed by an external supply through J1 (2-pin 5.08 mm screw terminal: pin 1 = +5V, pin 2 = GND). The bus also feeds the Teensy's VIN pin, so cut the VUSB–VIN trace on the Teensy underside before connecting USB; otherwise the external supply back-feeds the host's USB port.
