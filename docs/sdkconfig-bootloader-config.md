# 2 Bootloader config
Bootloader configの設定を記載。

- [2 Bootloader config](#2-bootloader-config)
  - [2.1 Bootloader manager](#21-bootloader-manager)
  - [2.2 Bootloader optimization Level](#22-bootloader-optimization-level)
  - [2.3 Bootloader log verbosity](#23-bootloader-log-verbosity)
  - [2.4 Serial Flash Configurations](#24-serial-flash-configurations)
  - [2.5 VDDSDIO LDO voltage](#25-vddsdio-ldo-voltage)
  - [2.6 GPIO triggers factory reset](#26-gpio-triggers-factory-reset)
    - [2.6.1 Number of the GPIO input for factory reset](#261-number-of-the-gpio-input-for-factory-reset)
    - [2.6.2 Clear OTA data on factory reset](#262-clear-ota-data-on-factory-reset)
    - [2.6.3 Comma-separated names of partitions to clear on factory reset](#263-comma-separated-names-of-partitions-to-clear-on-factory-reset)
  - [2.7 GPIO triggers boot from test app partition](#27-gpio-triggers-boot-from-test-app-partition)
    - [2.7.1 Number of the GPIO input to boot TEST partition](#271-number-of-the-gpio-input-to-boot-test-partition)
    - [2.7.2 App test GPIO level](#272-app-test-gpio-level)
    - [2.7.3 Hold time of GPIO for reset/test mode](#273-hold-time-of-gpio-for-resettest-mode)
  - [2.8 Enable protection for unmapped memory regions](#28-enable-protection-for-unmapped-memory-regions)
  - [2.9 Use RTC watchdog in start code](#29-use-rtc-watchdog-in-start-code)
    - [2.9.1 Allows RTC watchdog disable in user code](#291-allows-rtc-watchdog-disable-in-user-code)
    - [2.9.2 Timeout for RTC watchdog](#292-timeout-for-rtc-watchdog)
  - [2.10 Enable app rollback support](#210-enable-app-rollback-support)
    - [2.10.1 Enable app anti-rollback support](#2101-enable-app-anti-rollback-support)
      - [2.10.1.1 eFuse secure version of app](#21011-efuse-secure-version-of-app)
      - [2.10.1.2 Size of the efuse secure version field](#21012-size-of-the-efuse-secure-version-field)
      - [2.10.1.3 Emulate operations with efuse secure version](#21013-emulate-operations-with-efuse-secure-version)
  - [2.11 Skip image validation when exiting deep sleep](#211-skip-image-validation-when-exiting-deep-sleep)
  - [2.12 Skip image validation from power on reset](#212-skip-image-validation-from-power-on-reset)
  - [2.13 Skip image validation always](#213-skip-image-validation-always)
  - [2.14 Reserve RTC FAST memory for custom purposes](#214-reserve-rtc-fast-memory-for-custom-purposes)
    - [2.14.1 Include custom memory in the CRC calculation](#2141-include-custom-memory-in-the-crc-calculation)
    - [2.14.2 Size in bytes for custom purposes](#2142-size-in-bytes-for-custom-purposes)

## 2.1 Bootloader manager
- Use time/date stamp for bootloader
- Project version
## 2.2 Bootloader optimization Level
- Size (-Os)
- Debug (-Og)
- Optimize for performance (-O2)
- Debug without optimization (-O0)
## 2.3 Bootloader log verbosity
- No output
- Error
- Warning
- Info
- Debug
- Verbose
## 2.4 Serial Flash Configurations
- Allow app adjust Dummy Cycle bits in SPI Flash for higher frequency (READ HELP FIRST)
- Enable the support for flash chips of XMC (READ DOCS FIRST)
## 2.5 VDDSDIO LDO voltage
- 1.8V
- 1.9V
## 2.6 GPIO triggers factory reset
### 2.6.1 Number of the GPIO input for factory reset
- Reset on GPIO low
- Reset on GPIO high
### 2.6.2 Clear OTA data on factory reset
### 2.6.3 Comma-separated names of partitions to clear on factory reset
## 2.7 GPIO triggers boot from test app partition
### 2.7.1 Number of the GPIO input to boot TEST partition
### 2.7.2 App test GPIO level
- Enter test app on GPIO low
- Enter test app on GPIO high
### 2.7.3 Hold time of GPIO for reset/test mode
## 2.8 Enable protection for unmapped memory regions
## 2.9 Use RTC watchdog in start code
### 2.9.1 Allows RTC watchdog disable in user code
### 2.9.2 Timeout for RTC watchdog
## 2.10 Enable app rollback support
### 2.10.1 Enable app anti-rollback support
有効にすると"[GPIO triggers boot from test app partition](#227-gpio-triggers-boot-from-test-app-partition)"の項目が消える
#### 2.10.1.1 eFuse secure version of app
#### 2.10.1.2 Size of the efuse secure version field
#### 2.10.1.3 Emulate operations with efuse secure version
## 2.11 Skip image validation when exiting deep sleep
## 2.12 Skip image validation from power on reset
## 2.13 Skip image validation always
有効にすると以下の2つが有効になる。\
- [Skip image validation when exiting deep sleep](#2211-skip-image-validation-when-exiting-deep-sleep)
- [Skip image validation from power on reset](#2212-skip-image-validation-from-power-on-reset)
## 2.14 Reserve RTC FAST memory for custom purposes
### 2.14.1 Include custom memory in the CRC calculation
### 2.14.2 Size in bytes for custom purposes
