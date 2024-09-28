# 1 Build type
Build typeの設定を記載。

- [1 Build type](#1-build-type)
  - [1.1 Application build type](#11-application-build-type)
  - [1.2 Build app without SPI\_FLASH/PSRAM support](#12-build-app-without-spi_flashpsram-support)
  - [1.3 Enable reproducible build](#13-enable-reproducible-build)
  - [1.4 No Binary Blobs](#14-no-binary-blobs)
  - [1.5 App compatible with bootloaders before ESP-IDF v2.1](#15-app-compatible-with-bootloaders-before-esp-idf-v21)
  - [1.6 App compatible with bootloader and partition table before ESP-IDF v3.1](#16-app-compatible-with-bootloader-and-partition-table-before-esp-idf-v31)

## 1.1 Application build type
- Default
アプリケーションと2ndステージ用ブートローダー
- Build app runs entirely in RAM
RAM向けにビルド(試験的実装)
## 1.2 Build app without SPI_FLASH/PSRAM support
"[Build app runs entirely in RAM](#2112-build-app-runs-entirely-in-ram)"有効時のみ設定可能
## 1.3 Enable reproducible build
## 1.4 No Binary Blobs
## 1.5 App compatible with bootloaders before ESP-IDF v2.1
## 1.6 App compatible with bootloader and partition table before ESP-IDF v3.1
