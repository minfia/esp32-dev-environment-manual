# 9.5 Driver Configurations
Driver Configurationsの設定を記載。

- [9.5 Driver Configurations](#95-driver-configurations)
  - [9.5.1 TWAI Configuration](#951-twai-configuration)
  - [9.5.2 Legacy ADC Driver Configuration](#952-legacy-adc-driver-configuration)
    - [9.5.2.1 Disable DAC when ADC2 is used on GPIO 25 and 26](#9521-disable-dac-when-adc2-is-used-on-gpio-25-and-26)
    - [9.5.2.2 Suppress legacy driver deprecated warning](#9522-suppress-legacy-driver-deprecated-warning)
    - [9.5.2.3 Legacy ADC Calibration Configuration](#9523-legacy-adc-calibration-configuration)
  - [9.5.3 Legacy DAC Driver Configurations](#953-legacy-dac-driver-configurations)
  - [9.5.4 Legacy MCPWM Driver Configurations](#954-legacy-mcpwm-driver-configurations)
  - [9.5.5 Legacy Timer Group Driver Configurations](#955-legacy-timer-group-driver-configurations)
  - [9.5.6 Legacy RTM Driver Configurations](#956-legacy-rtm-driver-configurations)
  - [9.5.7 Legacy I2S Driver Configurations](#957-legacy-i2s-driver-configurations)
  - [9.5.8 Legacy PCNT Driver Configurations](#958-legacy-pcnt-driver-configurations)
  - [9.5.9 Legacy SDM Driver Configurations](#959-legacy-sdm-driver-configurations)
  - [9.5.10 Legacy Temperature Sensor Driver Configurations](#9510-legacy-temperature-sensor-driver-configurations)

## 9.5.1 TWAI Configuration
- Place TWAI ISR function into IRAM
- Add SW workaround for REC change during bus-off
- Add SW workaround for RX interrupt lost errata
- Add SW workaround for invalid RX frame errata
- Add SW workaround for RX FIFO corruption errata
- Add SW workaround for listen only transmits dominant bit errata
## 9.5.2 Legacy ADC Driver Configuration
### 9.5.2.1 Disable DAC when ADC2 is used on GPIO 25 and 26
### 9.5.2.2 Suppress legacy driver deprecated warning
### 9.5.2.3 Legacy ADC Calibration Configuration
- Use Two Point Values
- Use eFuse Vref
- Use Lookup Tables
- Suppress legacy driver deprecated warning
## 9.5.3 Legacy DAC Driver Configurations
- Suppress legacy driver deprecated warning
## 9.5.4 Legacy MCPWM Driver Configurations
- Suppress legacy driver deprecated warning
## 9.5.5 Legacy Timer Group Driver Configurations
- Suppress legacy driver deprecated warning
## 9.5.6 Legacy RTM Driver Configurations
- Suppress legacy driver deprecated warning
## 9.5.7 Legacy I2S Driver Configurations
- Suppress legacy driver deprecated warning
## 9.5.8 Legacy PCNT Driver Configurations
- Suppress legacy driver deprecated warning
## 9.5.9 Legacy SDM Driver Configurations
- Suppress legacy driver deprecated warning
## 9.5.10 Legacy Temperature Sensor Driver Configurations
- Suppress legacy driver deprecated warning
