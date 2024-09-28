# 9.68 SPI Flash driver
SPI Flash driverの設定を記載。

- [9.68 SPI Flash driver](#968-spi-flash-driver)
  - [9.68.1 Verify SPI flash writes](#9681-verify-spi-flash-writes)
  - [9.68.1.1 Log errors if verification fails](#96811-log-errors-if-verification-fails)
  - [9.68.1.2 Log warning if writing zero bits to ones](#96812-log-warning-if-writing-zero-bits-to-ones)
  - [9.68.2 Enable operation counters](#9682-enable-operation-counters)
  - [9.68.3 Enable SPI flash ROM driver patched functions](#9683-enable-spi-flash-rom-driver-patched-functions)
  - [9.68.4 Use rsp\_flash implementation in ROM](#9684-use-rsp_flash-implementation-in-rom)
  - [9.68.5 Writing to dangerous flash regions](#9685-writing-to-dangerous-flash-regions)
  - [9.68.6 Support other devices attached to SPI1 bus](#9686-support-other-devices-attached-to-spi1-bus)
  - [9.68.7 Bypass a block erase and always do sector erase](#9687-bypass-a-block-erase-and-always-do-sector-erase)
  - [9.68.8 Enable yield operation during flash erase](#9688-enable-yield-operation-during-flash-erase)
    - [9.68.8.1 Duration of erasing to yield CPUs (ms)](#96881-duration-of-erasing-to-yield-cpus-ms)
    - [9.68.8.2 CPU release time (tick) for an erase operation](#96882-cpu-release-time-tick-for-an-erase-operation)
  - [9.68.9 Flash write chunk size](#9689-flash-write-chunk-size)
  - [9.68.10 Override flash size in bootloader header by ESPTOOLPY\_FLASHSIZE](#96810-override-flash-size-in-bootloader-header-by-esptoolpy_flashsize)
  - [9.68.11 Flash timeout checkout disabled](#96811-flash-timeout-checkout-disabled)
  - [9.68.12 Override default chip driver list](#96812-override-default-chip-driver-list)
  - [9.68.13 Auto-detect flash chips](#96813-auto-detect-flash-chips)
    - [9.68.13.1 ISSI](#968131-issi)
    - [9.68.13.2 MXIC](#968132-mxic)
    - [9.68.13.3 GigaDevice](#968133-gigadevice)
    - [9.68.13.4 Winbond](#968134-winbond)
    - [9.68.13.5 BOYA](#968135-boya)
    - [9.68.13.6 TH](#968136-th)
    - [9.68.13.7 mxic (opi)](#968137-mxic-opi)
  - [9.68.14 Enable encrypted partition read/write operation](#96814-enable-encrypted-partition-readwrite-operation)

## 9.68.1 Verify SPI flash writes
## 9.68.1.1 Log errors if verification fails
## 9.68.1.2 Log warning if writing zero bits to ones
## 9.68.2 Enable operation counters
## 9.68.3 Enable SPI flash ROM driver patched functions
## 9.68.4 Use rsp_flash implementation in ROM
## 9.68.5 Writing to dangerous flash regions
- Aborts
- Fails
- Allowed
## 9.68.6 Support other devices attached to SPI1 bus
## 9.68.7 Bypass a block erase and always do sector erase
## 9.68.8 Enable yield operation during flash erase
### 9.68.8.1 Duration of erasing to yield CPUs (ms)
### 9.68.8.2 CPU release time (tick) for an erase operation
## 9.68.9 Flash write chunk size
## 9.68.10 Override flash size in bootloader header by ESPTOOLPY_FLASHSIZE
## 9.68.11 Flash timeout checkout disabled 
## 9.68.12 Override default chip driver list
## 9.68.13 Auto-detect flash chips
### 9.68.13.1 ISSI
### 9.68.13.2 MXIC
### 9.68.13.3 GigaDevice
### 9.68.13.4 Winbond
### 9.68.13.5 BOYA
### 9.68.13.6 TH
### 9.68.13.7 mxic (opi)
## 9.68.14 Enable encrypted partition read/write operation
