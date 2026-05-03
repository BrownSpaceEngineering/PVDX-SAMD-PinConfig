# PVDX SAMD51-A Pin Config

## This repo serves as the official source of truth for the PVDX mission's pin configuration.

> [!NOTE]
> Any edits to the .atzip file at this project's root must be commuted to the README.
Commits must be clearly labeled with which pins were changed and for what purpose.

> [!NOTE]
> BEFORE YOU COMMIT, CHECK:
> 1. Does my PVDXosV2 compile with this ASF config?
> 2. Make sure there's only one .atzip file in the repo, delete the old one (it will be in version control)
> 3. Have I updated the README?


# Compute Board — SAMD51P20A Pin Mapping Reference

**MCU:** Microchip SAMD51P20A-AF (128-pin TQFP)
---

## SERCOM Peripheral Assignments

### SERCOM0 — SPI_MRAM

| Function | Pin  | Direction |
|----------|------|-----------|
| MOSI     | PB24 | Output    |
| SCK      | PB25 | Output    |
| MISO     | PC18 | Input     |

Directly-connected chip selects, resets, and write-protect lines:

| Signal    | Pin  | Direction      | Initial Level |
|-----------|------|----------------|---------------|
| MRAM1_CS  | PC04 | Output         | High          |
| MRAM1_RST | PC05 | Output         | High          |
| MRAM1_WP  | PB12 | Output         | High          |
| MRAM2_CS  | PC06 | Output         | High          |
| MRAM2_RST | PC07 | Output         | High          |
| MRAM2_WP  | PB13 | Output         | High          |
| MRAM3_CS  | PB10 | Output         | High          |
| MRAM3_RST | PB11 | Output         | High          |
| MRAM3_WP  | PB15 | Output         | High          |

### SERCOM1 — SPI_DISPLAY

| Function | Pin  | Direction |
|----------|------|-----------|
| MOSI     | PA00 | Output    |
| SCK      | PA01 | Output    |
| MISO     | PA18 | Input     |

| Signal      | Pin  | Direction | Initial Level |
|-------------|------|-----------|---------------|
| DISPLAY_CS  | PC11 | Output    | High          |
| DISPLAY_RST | PD11 | Output    | High          |
| DISPLAY_DC  | PD12 | Output    | High          |

### SERCOM2 — SPI_CAMERA

| Function | Pin  | Direction |
|----------|------|-----------|
| MOSI     | PB26 | Output    |
| SCK      | PB27 | Output    |
| MISO     | PA14 | Input     |

| Signal    | Pin  | Direction | Initial Level |
|-----------|------|-----------|---------------|
| CAMERA_CS | PC14 | Output    | High          |

### SERCOM3 — I2C_SBAND

| Function | Pin  | Direction |
|----------|------|-----------|
| SCL      | PA16 | I2C       |
| SDA      | PA17 | I2C       |

### SERCOM4 — SPI_MAGNETOMETER_GYRO

| Function | Pin  | Direction |
|----------|------|-----------|
| MOSI     | PA13 | Output    |
| SCK      | PA12 | Output    |
| MISO     | PB14 | Input     |

| Signal           | Pin  | Direction | Initial Level |
|------------------|------|-----------|---------------|
| MAGNETOMETER_CS  | PC19 | Output    | High          |
| MAGNETOMETER_DRDY| PC10 | Input     | High          |
| GYRO_CS          | PC20 | Output    | High          |
| GYRO_RST         | PC21 | Output    | High          |
| GYRO_DRDY        | PC22 | Input     | —             |

### SERCOM5 — SPI_SBAND

| Function | Pin  | Direction |
|----------|------|-----------|
| MOSI     | PB16 | Output    |
| SCK      | PB17 | Output    |
| MISO     | PB18 | Input     |

| Signal   | Pin  | Direction | Initial Level |
|----------|------|-----------|---------------|
| SBAND_CS | PB19 | Output    | High          |

### SERCOM6 — I2C_CAMERA

| Function | Pin  | Direction |
|----------|------|-----------|
| SCL      | PD08 | I2C       |
| SDA      | PD09 | I2C       |

### SERCOM7 — SPI_UHF

| Function | Pin  | Direction |
|----------|------|-----------|
| MOSI     | PC12 | Output    |
| SCK      | PC13 | Output    |
| MISO     | PD10 | Input     |

| Signal  | Pin  | Direction | Initial Level |
|---------|------|-----------|---------------|
| UHF_CS  | PC16 | Output    | High          |
| UHF_RST | PC17 | Output    | High          |

---

## ADC Channels

### ADC0

| Channel | Pin  |
|---------|------|
| AIN0    | PA02 |
| AIN1    | PA03 |
| AIN2    | PB08 |
| AIN3    | PB09 |
| AIN4    | PA04 |
| AIN5    | PA05 |
| AIN6    | PA06 |
| AIN7    | PA07 |
| AIN8    | PA08 |
| AIN9    | PA09 |
| AIN10   | PA10 |
| AIN11   | PA11 |
| AIN12   | PB00 |
| AIN13   | PB01 |
| AIN14   | PB02 |
| AIN15   | PB03 |

### ADC1

| Channel | Pin  |
|---------|------|
| AIN4    | PC02 |
| AIN5    | PC03 |
| AIN6    | PB04 |
| AIN7    | PB05 |
| AIN8    | PB06 |
| AIN9    | PB07 |
| AIN10   | PC00 |
| AIN11   | PC01 |
| AIN12   | PC30 |
| AIN13   | PC31 |
| AIN14   | PD00 |
| AIN15   | PD01 |

---

## LEDs

| Signal      | Pin  | Direction | Initial Level |
|-------------|------|-----------|---------------|
| LED_RED     | PA19 | Output    | High          |
| LED_ORANGE1 | PC15 | Output    | High          |
| LED_ORANGE2 | PA15 | Output    | High          |

---

## Magnetorquer (PWM)

### MAGNETORQUER_XY — TCC0 (X and Y axes)

| Signal     | Pin  | Direction |
|------------|------|-----------|
| MTQ_X_IN1  | PA20 | Output    |
| MTQ_X_IN2  | PA21 | Output    |
| MTQ_Y_IN1  | PA22 | Output    |
| MTQ_Y_IN2  | PA23 | Output    |

### MAGNETORQUER_Z — TCC1 (Z axis)

| Signal     | Pin  | Direction |
|------------|------|-----------|
| MTQ_Z_IN1  | PD20 | Output    |
| MTQ_Z_IN2  | PD21 | Output    |

---

## Debug (SWD)

| Function | Pin  |
|----------|------|
| SWCLK    | PA30 |
| SWDIO    | PA31 |

These are dedicated SWD pins on the SAMD51 and are not configured through Atmel START.

---

## System Peripherals

| Driver      | Hardware Block | Notes                 |
|-------------|----------------|-----------------------|
| TIMER_0     | RTC            | FreeRTOS tick source   |
| DELAY_0     | SysTick        | Blocking delay driver  |
| RAND_0      | TRNG           | Hardware RNG           |
| WDT_0       | WDT            | Watchdog timer         |
| CMCC        | CMCC           | Cortex cache controller|
| DMAC        | DMAC           | DMA controller         |

---

## Unmapped Pins

The following SAMD51P20A pins have no assignment in the Atmel START configuration.

### Port A

| Pin  | Notes |
|------|-------|
| PA24 | Unallocated |
| PA25 | Unallocated |
| PA27 | Unallocated |

### Port B

| Pin  | Notes |
|------|-------|
| PB20 | Unallocated |
| PB21 | Unallocated |
| PB22 | Unallocated |
| PB23 | Unallocated |
| PB28 | Unallocated |
| PB29 | Unallocated |
| PB30 | Unallocated |
| PB31 | Unallocated |

### Port C

| Pin  | Notes |
|------|-------|
| PC23 | Unallocated |
| PC24 | Unallocated |
| PC25 | Unallocated |
| PC26 | Unallocated |
| PC27 | Unallocated |
| PC28 | Unallocated |
