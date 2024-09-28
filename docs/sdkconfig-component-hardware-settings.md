# 9.38 Hardware Settings
Hardware Settingsの設定を記載。

- [9.38 Hardware Settings](#938-hardware-settings)
  - [9.38.1 Chip revision](#9381-chip-revision)
    - [9.38.1.1 Minimum Supported ESP32 Revision](#93811-minimum-supported-esp32-revision)
    - [9.38.1.2 Internal test mode](#93812-internal-test-mode)
  - [9.38.2 MAC Config](#9382-mac-config)
    - [9.38.2.1 Number of universally administered MAC address](#93821-number-of-universally-administered-mac-address)
    - [9.38.2.2 Ignore MAC CRC error](#93822-ignore-mac-crc-error)
    - [9.38.2.3 Enable using custom mac as base mac](#93823-enable-using-custom-mac-as-base-mac)
  - [9.38.3 Sleep Config](#9383-sleep-config)
    - [9.38.3.1 Power down flash in light sleep when there is no SPIRAM](#93831-power-down-flash-in-light-sleep-when-there-is-no-spiram)
    - [9.38.3.2 Pull-up Flash CS pin in light sleep](#93832-pull-up-flash-cs-pin-in-light-sleep)
    - [9.38.3.3 Pull-up PSRAM CS pin in light sleep](#93833-pull-up-psram-cs-pin-in-light-sleep)
    - [9.38.3.4 Pull-up all SPI pins in light sleep](#93834-pull-up-all-spi-pins-in-light-sleep)
    - [9.38.3.5 light sleep GPIO reset workaround](#93835-light-sleep-gpio-reset-workaround)
    - [9.38.3.6 Extra delay after flash powerdown sleep wakeup to wait flash ready](#93836-extra-delay-after-flash-powerdown-sleep-wakeup-to-wait-flash-ready)
    - [9.38.3.7 Check the cache safety of the sleep wakeup code in sleep process](#93837-check-the-cache-safety-of-the-sleep-wakeup-code-in-sleep-process)
    - [9.38.3.8 esp sleep debug](#93838-esp-sleep-debug)
    - [9.38.3.9 Allow to enable internal pull-up/downs for the Deep-Sleep wakeup IOs](#93839-allow-to-enable-internal-pull-updowns-for-the-deep-sleep-wakeup-ios)
    - [9.38.3.10 Enable registration of sleep event callbacks](#938310-enable-registration-of-sleep-event-callbacks)
  - [9.38.4 RTC Clock Config](#9384-rtc-clock-config)
    - [9.38.4.1 RTC clock source](#93841-rtc-clock-source)
    - [9.38.4.2 Additional current for external 32kHz crystal](#93842-additional-current-for-external-32khz-crystal)
    - [9.38.4.3 Number of cycles for RTC\_SLOW\_CLK calibration](#93843-number-of-cycles-for-rtc_slow_clk-calibration)
    - [9.38.4.4 Number of attempts to repeat 32k XTAL calibration](#93844-number-of-attempts-to-repeat-32k-xtal-calibration)
  - [9.38.5 Peripheral Control](#9385-peripheral-control)
    - [9.38.5.1 Place peripheral control functions into IRAM](#93851-place-peripheral-control-functions-into-iram)
  - [9.38.6 ETM configuration](#9386-etm-configuration)
    - [9.38.6.1 Enable debug log](#93861-enable-debug-log)
  - [9.38.7 GDMA Configurations](#9387-gdma-configurations)
    - [9.38.7.1 Place GDMA control functions in IRAM](#93871-place-gdma-control-functions-in-iram)
    - [9.38.7.2 GDMA ISR IRAM-Safe](#93872-gdma-isr-iram-safe)
    - [9.38.7.3 Enable debug log](#93873-enable-debug-log)
  - [9.38.8 DW\_GDMA Configurations](#9388-dw_gdma-configurations)
  - [9.38.8.1 Enable debug log](#93881-enable-debug-log)
  - [9.38.9 2D-DMA Configurations](#9389-2d-dma-configurations)
  - [9.38.9.1 Place 2D-DMA operation functions into IRAM](#93891-place-2d-dma-operation-functions-into-iram)
  - [9.38.9.2 2D-DMA ISR IRAM-Safe](#93892-2d-dma-isr-iram-safe)
  - [9.38.10 Main XTAL Config](#93810-main-xtal-config)
    - [9.38.10.1 Main XTAL frequency](#938101-main-xtal-frequency)
  - [9.38.11 Crypto DPA Protection](#93811-crypto-dpa-protection)
    - [9.38.11.1 Enable crypto DPA protection at startup](#938111-enable-crypto-dpa-protection-at-startup)

## 9.38.1 Chip revision
### 9.38.1.1 Minimum Supported ESP32 Revision
 Rev v0.0
 Rev v1.0
 Rev v1.1
 Rev v2.0
 Rev v3.0
 Rev v3.1
### 9.38.1.2 Internal test mode
## 9.38.2 MAC Config
### 9.38.2.1 Number of universally administered MAC address
 Two
 Four
### 9.38.2.2 Ignore MAC CRC error
### 9.38.2.3 Enable using custom mac as base mac
## 9.38.3 Sleep Config
### 9.38.3.1 Power down flash in light sleep when there is no SPIRAM
### 9.38.3.2 Pull-up Flash CS pin in light sleep
### 9.38.3.3 Pull-up PSRAM CS pin in light sleep
### 9.38.3.4 Pull-up all SPI pins in light sleep
### 9.38.3.5 light sleep GPIO reset workaround
### 9.38.3.6 Extra delay after flash powerdown sleep wakeup to wait flash ready
### 9.38.3.7 Check the cache safety of the sleep wakeup code in sleep process
### 9.38.3.8 esp sleep debug
### 9.38.3.9 Allow to enable internal pull-up/downs for the Deep-Sleep wakeup IOs
### 9.38.3.10 Enable registration of sleep event callbacks
## 9.38.4 RTC Clock Config
### 9.38.4.1 RTC clock source
 Internal 150 kHz RC oscillator
 External 32kHz crystal
 External 32kHz oscillator at 32K_XN pin
 Internal 8.5MHz oscillator, divided by 256 (~33kHz)
### 9.38.4.2 Additional current for external 32kHz crystal
- None
- Method 1
- Method 2
### 9.38.4.3 Number of cycles for RTC_SLOW_CLK calibration
### 9.38.4.4 Number of attempts to repeat 32k XTAL calibration
## 9.38.5 Peripheral Control
### 9.38.5.1 Place peripheral control functions into IRAM
## 9.38.6 ETM configuration
### 9.38.6.1 Enable debug log
## 9.38.7 GDMA Configurations
### 9.38.7.1 Place GDMA control functions in IRAM
### 9.38.7.2 GDMA ISR IRAM-Safe
### 9.38.7.3 Enable debug log
## 9.38.8 DW_GDMA Configurations
## 9.38.8.1 Enable debug log
## 9.38.9 2D-DMA Configurations
## 9.38.9.1 Place 2D-DMA operation functions into IRAM
## 9.38.9.2 2D-DMA ISR IRAM-Safe
## 9.38.10 Main XTAL Config
### 9.38.10.1 Main XTAL frequency
- 24 MHz
- 26 MHz
- 32 MHz
- 40 MHz
- 48 MHz
- Autodetect
## 9.38.11 Crypto DPA Protection
### 9.38.11.1 Enable crypto DPA protection at startup
- Security level low
- Security level medium
- Security level high
