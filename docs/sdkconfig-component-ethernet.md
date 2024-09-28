# 9.31 Ethernet
Ethernetの設定を記載。

- [9.31 Ethernet](#931-ethernet)
  - [9.31.1 Support ESP32 internal EMAC controller](#9311-support-esp32-internal-emac-controller)
    - [9.31.1.1 PHY interface](#93111-phy-interface)
    - [9.31.1.2 RMII clock mode](#93112-rmii-clock-mode)
    - [9.31.1.3 Output RMII clock from GPIO0](#93113-output-rmii-clock-from-gpio0)
    - [9.31.1.4 RMII clock GPIO number](#93114-rmii-clock-gpio-number)
    - [9.31.1.5 Ethernet DMA buffer size](#93115-ethernet-dma-buffer-size)
    - [9.31.1.6 Amount of Ethernet DMA Rx buffers](#93116-amount-of-ethernet-dma-rx-buffers)
    - [9.31.1.7 Amount of Ethernet DMA Tx buffers](#93117-amount-of-ethernet-dma-tx-buffers)
    - [9.31.1.9 Enable software flow control](#93119-enable-software-flow-control)
    - [9.31.1.8 Enable IRAM optimization](#93118-enable-iram-optimization)
  - [9.31.2 Support SPI to Ethernet Module](#9312-support-spi-to-ethernet-module)
  - [9.31.3 Support OpenCores Ethernet MAC](#9313-support-opencores-ethernet-mac)
  - [9.31.4 Enable Transmit Mutex](#9314-enable-transmit-mutex)

## 9.31.1 Support ESP32 internal EMAC controller
### 9.31.1.1 PHY interface
- Reduced Media Independent Interface
### 9.31.1.2 RMII clock mode
- Input RMII clock from external 
- Output RMII clock from internal
### 9.31.1.3 Output RMII clock from GPIO0
### 9.31.1.4 RMII clock GPIO number
### 9.31.1.5 Ethernet DMA buffer size
### 9.31.1.6 Amount of Ethernet DMA Rx buffers
### 9.31.1.7 Amount of Ethernet DMA Tx buffers
### 9.31.1.9 Enable software flow control
### 9.31.1.8 Enable IRAM optimization
## 9.31.2 Support SPI to Ethernet Module
- Use DM9051
- Use W5500
- Use KSZ8851SNL
## 9.31.3 Support OpenCores Ethernet MAC
- Number of Ethernet DMA Rx buffers
- Number of Ethernet DMA Tx buffers
## 9.31.4 Enable Transmit Mutex
