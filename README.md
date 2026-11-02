# robobuggy-rtk-pcb
RTK base station PCB

## Layout

- `old-lora-setup/` - KiCad project for the base station radio: Teensy 4.1 + SparkFun LoRa 1W Breakout 915MHz (SPX-18572). Pinout matches `lora_rtcm_broadcast` in [robobuggy-firmware](https://github.com/CMU-Robotics-Club/robobuggy-firmware).
- `library/` — shared project library, registered in the project's `sym-lib-table` / `fp-lib-table` as `robobuggy_rtk` via `${KIPRJMOD}/../library/...`.
  - `robobuggy_rtk.kicad_sym` — `Teensy_4.1`, `SparkFun_LoRa_1W_Breakout_915MHz`
  - `robobuggy_rtk.pretty` — matching footprints (Teensy outer 48 pins; SparkFun breakout headers + 3.3 mm standoff holes)
