# 9.44 ESP PSRAM
ESP PSRAMの設定を記載。

- [9.44 ESP PSRAM](#944-esp-psram)
  - [9.44.1 Support for external, SPI-connected RAM](#9441-support-for-external-spi-connected-ram)
    - [9.44.1.1 SPI RAM config](#94411-spi-ram-config)
      - [9.44.1.1.1 Type of SPI RAM ship in use](#944111-type-of-spi-ram-ship-in-use)
      - [9.44.1.1.2 Set RAM Clock speed](#944112-set-ram-clock-speed)
      - [9.44.1.1.3 Initialize SPI RAM during startup](#944113-initialize-spi-ram-during-startup)
        - [9.44.1.1.3.1 Ignore PSRAM when not found](#9441131-ignore-psram-when-not-found)
      - [9.44.1.1.4 SPI RAM access method](#944114-spi-ram-access-method)
      - [9.44.1.1.5 Run memory test on SPI RAM initialization](#944115-run-memory-test-on-spi-ram-initialization)
      - [9.44.1.1.6 Maximum malloc() size, in bytes, to always put in internal memory](#944116-maximum-malloc-size-in-bytes-to-always-put-in-internal-memory)
      - [9.44.1.1.7 Try to allocate memories of WiFi and LWIP in SPIRAM firstly. If failed, allocate internal memory](#944117-try-to-allocate-memories-of-wifi-and-lwip-in-spiram-firstly-if-failed-allocate-internal-memory)
      - [9.44.1.1.8 Reserve this amount of bytes for data that specifically needs to be in DMA or internal memory](#944118-reserve-this-amount-of-bytes-for-data-that-specifically-needs-to-be-in-dma-or-internal-memory)
      - [9.44.1.1.9 Allow .bss segment placed in external memory](#944119-allow-bss-segment-placed-in-external-memory)
      - [9.44.1.1.10 Allow .noinit segment placed in external memory](#9441110-allow-noinit-segment-placed-in-external-memory)
      - [9.44.1.1.11 Enable workaround for bug in sPI RAM cache for Rev1 ESP32s](#9441111-enable-workaround-for-bug-in-spi-ram-cache-for-rev1-esp32s)
      - [9.44.1.1.12 SPIRAM cache workaround debugging](#9441112-spiram-cache-workaround-debugging)
      - [9.44.1.1.12.1 Workaround strategy](#94411121-workaround-strategy)
      - [9.44.1.1.13 SPIRAM workaround libraries placement](#9441113-spiram-workaround-libraries-placement)
      - [9.44.1.1.14 Enable bank switching for \>4MiB external RAM](#9441114-enable-bank-switching-for-4mib-external-ram)
      - [9.44.1.1.15 Allow external memory as an argument to xTaskCreateStatic](#9441115-allow-external-memory-as-an-argument-to-xtaskcreatestatic)
      - [9.44.1.1.16 SPI host to use for 32MBit PSRAM](#9441116-spi-host-to-use-for-32mbit-psram)
      - [9.44.1.1.17 PSRAM clock and cs IO for ESP32-DOWD](#9441117-psram-clock-and-cs-io-for-esp32-dowd)
      - [9.44.1.1.18 PSRAM clock and cs IO for ESP32-D2WD](#9441118-psram-clock-and-cs-io-for-esp32-d2wd)
      - [9.44.1.1.19 PSRAM clock and cs IO for ESP32-PICO-D4](#9441119-psram-clock-and-cs-io-for-esp32-pico-d4)
      - [9.44.1.1.20 Use custom SPI PSRAM WP(SD3) Pin when flash pins set in eFuse (read help)](#9441120-use-custom-spi-psram-wpsd3-pin-when-flash-pins-set-in-efuse-read-help)
      - [9.44.1.1.21 Custom SPI PSRAM WP(SD3) Pin](#9441121-custom-spi-psram-wpsd3-pin)
      - [9.44.1.1.22 Enable SPI PSRAM 2T mode](#9441122-enable-spi-psram-2t-mode)

## 9.44.1 Support for external, SPI-connected RAM
### 9.44.1.1 SPI RAM config
#### 9.44.1.1.1 Type of SPI RAM ship in use
- Auto-detect
- ESP-PSRAM16 or APS1604
- ESP-PSRAM32
- ESP-PSRAM64 or LY68L6400
#### 9.44.1.1.2 Set RAM Clock speed
- 40 MHz clock speed
- 80 MHz clock speed
#### 9.44.1.1.3 Initialize SPI RAM during startup
##### 9.44.1.1.3.1 Ignore PSRAM when not found
#### 9.44.1.1.4 SPI RAM access method
- Integrate RAM into memory map
- Make RAM allocatable using heap_caps_malloc(..., MALLOC_CAP_SPIRAM)
- Make RAM allocatable using malloc() as well
#### 9.44.1.1.5 Run memory test on SPI RAM initialization
#### 9.44.1.1.6 Maximum malloc() size, in bytes, to always put in internal memory
#### 9.44.1.1.7 Try to allocate memories of WiFi and LWIP in SPIRAM firstly. If failed, allocate internal memory
#### 9.44.1.1.8 Reserve this amount of bytes for data that specifically needs to be in DMA or internal memory
#### 9.44.1.1.9 Allow .bss segment placed in external memory
#### 9.44.1.1.10 Allow .noinit segment placed in external memory
#### 9.44.1.1.11 Enable workaround for bug in sPI RAM cache for Rev1 ESP32s
#### 9.44.1.1.12 SPIRAM cache workaround debugging
#### 9.44.1.1.12.1 Workaround strategy
- Insert memw after vulnerable instructions (default)
- Duplicate LD/ST for 32-bit, memw for 8./16 bit
- Insert nops between vulnerable loads/stores (old strategy, obsolete)
#### 9.44.1.1.13 SPIRAM workaround libraries placement
- Put libc's jump related functions in IRAM
- Put libc's math related functions in IRAM
- Put libc's number parsing related functions in IRAM
- Put libc's I/O related functions in IRAM
- Put libc's time related functions in IRAM
- Put libc's characters related functions in IRAM
- Put libc's memory related functions in IRAM
- Put libc's string related functions in IRAM
- Put libc's random related functions in IRAM
- Put libc's environment related functions in IRAM
- Put libc's file related functions in IRAM
- Put libc's miscellaneous functions in IRAM, see help
#### 9.44.1.1.14 Enable bank switching for >4MiB external RAM
#### 9.44.1.1.15 Allow external memory as an argument to xTaskCreateStatic
#### 9.44.1.1.16 SPI host to use for 32MBit PSRAM
- HSPI host (SPI2)
- VSPI host (SPI3)
- Will not try to use any host, will abort if not able to use the PSRAM
#### 9.44.1.1.17 PSRAM clock and cs IO for ESP32-DOWD
- PSRAM CLK IO number
- PSRAM CS IO number
#### 9.44.1.1.18 PSRAM clock and cs IO for ESP32-D2WD
- PSRAM CLK IO number
- PSRAM CS IO number
#### 9.44.1.1.19 PSRAM clock and cs IO for ESP32-PICO-D4
- PSRAM CS IO number
#### 9.44.1.1.20 Use custom SPI PSRAM WP(SD3) Pin when flash pins set in eFuse (read help)
#### 9.44.1.1.21 Custom SPI PSRAM WP(SD3) Pin
#### 9.44.1.1.22 Enable SPI PSRAM 2T mode
