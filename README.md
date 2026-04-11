# tdf8546-library

Driver for the NXP TDF8546 four-channel I2C audio amplifier, targeting STM32F4 with the ST HAL. Writes the five TDF8546 instruction bytes (IB1-IB5) via the `stm32f4xx_hal` I2C API; the bytes are defined as bitfield unions in the header.

## Hardware

- STM32F4 MCU (`stm32f4xx_hal.h`)
- TDF8546 over I2C at address `0xD8`

## Layout

```
Inc/
  tdf8546.h              driver API and IB1-IB5 bitfield definitions
  main.h, stm32f4xx_*    HAL/project headers
Src/
  tdf8546.c              driver implementation
  main.c                 example entry
  stm32f4xx_*            HAL/project sources
```

## Usage

Copy `Inc/tdf8546.h` and `Src/tdf8546.c` into an existing STM32CubeMX/HAL project, ensure an `I2C_HandleTypeDef hi2c1` is available, then call `tdf8546_init()` to configure the amplifier.
