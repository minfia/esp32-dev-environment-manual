# 9 Component config
Component configの設定の一覧。

- [9 Component config](#9-component-config)
  - [9.1 Application Level Tracing](#91-application-level-tracing)
  - [9.2 Bluetooth](#92-bluetooth)
  - [9.3 ESP BLE Mesh Support](#93-esp-ble-mesh-support)
  - [9.4 Console Library](#94-console-library)
  - [9.5 Driver Configurations](#95-driver-configurations)
  - [9.6 eFuse Bit Manager](#96-efuse-bit-manager)
  - [9.7 ESP-TLS](#97-esp-tls)
  - [9.8 ADC and ADC Calibration](#98-adc-and-adc-calibration)
  - [9.9 Wireless Coexistence](#99-wireless-coexistence)
  - [9.10 Common ESP-related](#910-common-esp-related)
  - [9.11 ESP-Driver:Analog Comparator Configurations](#911-esp-driveranalog-comparator-configurations)
  - [9.12 ESP-Driver:Camera Controller Configurations](#912-esp-drivercamera-controller-configurations)
  - [9.13 ESP-Driver:DAC Configurations](#913-esp-driverdac-configurations)
  - [9.14 ESP-Driver:GPIO Configurations](#914-esp-drivergpio-configurations)
  - [9.15 ESP-Driver:GPTimer Configurations](#915-esp-drivergptimer-configurations)
  - [9.16 ESP-Driver:I2C Configurations](#916-esp-driveri2c-configurations)
  - [9.17 ESP-Driver:I2S Configurations](#917-esp-driveri2s-configurations)
  - [9.18 ESP-Driver:ISP Configurations](#918-esp-driverisp-configurations)
  - [9.19 ESP-Driver:JPEG-Codec Configurations](#919-esp-driverjpeg-codec-configurations)
  - [9.20 ESP-Driver:LEDC Configurations](#920-esp-driverledc-configurations)
  - [9.21 ESP-Driver:MCPWM Configurations](#921-esp-drivermcpwm-configurations)
  - [9.22 ESP-Driver:Parallel IO Configurations](#922-esp-driverparallel-io-configurations)
  - [9.23 ESP-Driver:PCNT Configurations](#923-esp-driverpcnt-configurations)
  - [9.24 ESP-Driver:RMT Configurations](#924-esp-driverrmt-configurations)
  - [9.25 ESP-Driver:Sigma Delta Modulator Configurations](#925-esp-driversigma-delta-modulator-configurations)
  - [9.26 ESP-Driver:SPI Configurations](#926-esp-driverspi-configurations)
  - [9.27 ESP-Driver:Touch Sensor Configurations](#927-esp-drivertouch-sensor-configurations)
  - [9.28 ESP-Driver:Temperature Sensor Configurations](#928-esp-drivertemperature-sensor-configurations)
  - [9.29 ESP-Driver:UART Configurations](#929-esp-driveruart-configurations)
  - [9.30 ESP-Driver:USB Serial/JTAG Configuration](#930-esp-driverusb-serialjtag-configuration)
  - [9.31 Ethernet](#931-ethernet)
  - [9.32 Event Loop Library](#932-event-loop-library)
  - [9.33 GDB Stub](#933-gdb-stub)
  - [9.34 ESP HTTP client](#934-esp-http-client)
  - [9.35 HTTP Server](#935-http-server)
  - [9.36 ESP HTTPS OTA](#936-esp-https-ota)
  - [9.37 ESP HTTPS server](#937-esp-https-server)
  - [9.38 Hardware Settings](#938-hardware-settings)
  - [9.39 LCD and Touch Panel](#939-lcd-and-touch-panel)
  - [9.40 ESP NETIF Adapter](#940-esp-netif-adapter)
  - [9.41 Partition API Configuration](#941-partition-api-configuration)
  - [9.42 PHY](#942-phy)
  - [9.43 Power Management](#943-power-management)
  - [9.44 ESP PSRAM](#944-esp-psram)
  - [9.45 ESP Ringbuf](#945-esp-ringbuf)
  - [9.46 ESP System Settings](#946-esp-system-settings)
  - [9.47 IPC (Inter-Process Call)](#947-ipc-inter-process-call)
  - [9.48 ESP Timer](#948-esp-timer)
  - [9.49 Wi-Fi](#949-wi-fi)
  - [9.50 Core dump](#950-core-dump)
  - [9.51 FAT Filesystem support](#951-fat-filesystem-support)
  - [9.52 FreeRTOS](#952-freertos)
  - [9.53 Hardware Abstraction Layer (HAL) and Low Level (LL)](#953-hardware-abstraction-layer-hal-and-low-level-ll)
  - [9.54 Heap memory debugging](#954-heap-memory-debugging)
  - [9.55 IEEE 802.15.4](#955-ieee-802154)
  - [9.56 Log output](#956-log-output)
  - [9.57 LWIP](#957-lwip)
  - [9.58 mbedTLS](#958-mbedtls)
  - [9.59 ESP-MQTT Configuration](#959-esp-mqtt-configuration)
  - [9.60 Newlib](#960-newlib)
  - [9.61 NVS](#961-nvs)
  - [9.62 NVS Security Provider](#962-nvs-security-provider)
  - [9.63 OpenThread](#963-openthread)
  - [9.64 Protocomm](#964-protocomm)
  - [9.65 PThreads](#965-pthreads)
  - [9.66 SoC Settings](#966-soc-settings)
  - [9.67 Main Flash configuration](#967-main-flash-configuration)
  - [9.68 SPI Flash driver](#968-spi-flash-driver)
  - [9.69 SPIFFS Configuration](#969-spiffs-configuration)
  - [9.70 TCP Transport](#970-tcp-transport)
  - [9.71 Ultra Low Power Co-processor](#971-ultra-low-power-co-processor)
  - [9.72 Unity unit testing library](#972-unity-unit-testing-library)
  - [9.73 USB-OTG](#973-usb-otg)
  - [9.74 Virtual file system](#974-virtual-file-system)
  - [9.75 Wear Levelling](#975-wear-levelling)
  - [9.76 Wi-Fi Provisioning Manager](#976-wi-fi-provisioning-manager)

## 9.1 Application Level Tracing
[Application Level Tracing](./sdkconfig-component-application-level-tracing.md)を参照

## 9.2 Bluetooth
[Bluetooth](./sdkconfig-component-bluetooth.md)を参照

## 9.3 ESP BLE Mesh Support
"[Bluetooth](#92-bluetooth)"の有効で表示
[ESP BLE Mesh Support](./sdkconfig-component-esp-ble-mesh-support.md)を参照

## 9.4 Console Library
[Console Library](./sdkconfig-component-console-library.md)を参照

## 9.5 Driver Configurations
[Driver Configurations](./sdkconfig-component-driver-configuration.md)を参照

## 9.6 eFuse Bit Manager
[eFuse Bit Manager](./sdkconfig-component-efuse-bit-manager.md)を参照

## 9.7 ESP-TLS
[ESP-TLS](./sdkconfig-component-esp-tls.md)を参照

## 9.8 ADC and ADC Calibration
[ADC and ADC Calibration](./sdkconfig-component-adc-and-adc-calibration.md)を参照

## 9.9 Wireless Coexistence
[Wireless Coexistence](./sdkconfig-component-wireless-coexistence.md)を参照

## 9.10 Common ESP-related
[Common ESP-related](./sdkconfig-component-common-esp-related.md)を参照

## 9.11 ESP-Driver:Analog Comparator Configurations
[ESP-Driver:Analog Comparator Configurations](./sdkconfig-component-esp-driver-analog-comparator-configurations.md)を参照

## 9.12 ESP-Driver:Camera Controller Configurations
[ESP-Driver:Camera Controller Configurations](./sdkconfig-component-esp-driver-camera-controller-configurations.md)を参照

## 9.13 ESP-Driver:DAC Configurations
[ESP-Driver:DAC Configurations](./sdkconfig-component-esp-driver-dac-configuration.md)を参照

## 9.14 ESP-Driver:GPIO Configurations
[ESP-Driver:GPIO Configurations](./sdkconfig-component-esp-driver-gpio-configurations.md)を参照

## 9.15 ESP-Driver:GPTimer Configurations
[ESP-Driver:GPTimer Configurations](./sdkconfig-component-esp-driver-gptimer-configurations.md)を参照

## 9.16 ESP-Driver:I2C Configurations
[ESP-Driver:I2C Configurations](./sdkconfig-component-esp-driver-i2c-configurations.md)を参照

## 9.17 ESP-Driver:I2S Configurations
[ESP-Driver:I2S Configurations](./sdkconfig-component-esp-driver-i2s-configurations.md)を参照

## 9.18 ESP-Driver:ISP Configurations
[ESP-Driver:ISP Configurations](./sdkconfig-component-esp-driver-isp-configurations.md)を参照

## 9.19 ESP-Driver:JPEG-Codec Configurations
[ESP-Driver:JPEG-Codec Configurations](./sdkconfig-component-esp-driver-jpeg-codec-configurations.md)を参照

## 9.20 ESP-Driver:LEDC Configurations
[ESP-Driver:LEDC Configurations](./sdkconfig-component-esp-driver-ledc-configurations.md)を参照

## 9.21 ESP-Driver:MCPWM Configurations
[ESP-Driver:MCPWM Configurations](./sdkconfig-component-esp-driver-mcpwm-configurations.md)を参照

## 9.22 ESP-Driver:Parallel IO Configurations
[ESP-Driver:Parallel IO Configurations](./sdkconfig-component-esp-driver-parallel-io-configurations.md)を参照

## 9.23 ESP-Driver:PCNT Configurations
[ESP-Driver:PCNT Configurations](./sdkconfig-component-esp-driver-pcnt-configurations.md)を参照

## 9.24 ESP-Driver:RMT Configurations
[ESP-Driver:RMT Configurations](./sdkconfig-component-esp-driver-rmt-configurations.md)を参照

## 9.25 ESP-Driver:Sigma Delta Modulator Configurations
[ESP-Driver:Sigma Delta Modulator Configurations](./sdkconfig-component-esp-driver-sigma-delta-modulator-configurations.md)を参照

## 9.26 ESP-Driver:SPI Configurations
[ESP-Driver:SPI Configurations](./sdkconfig-component-esp-driver-spi-configurations.md)を参照

## 9.27 ESP-Driver:Touch Sensor Configurations
[ESP-Driver:Touch Sensor Configurations](./sdkconfig-component-esp-driver-touch-sensor-configurations.md)を参照

## 9.28 ESP-Driver:Temperature Sensor Configurations
[ESP-Driver:Temperature Sensor Configurations](./sdkconfig-component-esp-driver-temperature-sensor-configurations.md)を参照

## 9.29 ESP-Driver:UART Configurations
[ESP-Driver:UART Configurations](./sdkconfig-component-esp-driver-uart-configurations.md)を参照

## 9.30 ESP-Driver:USB Serial/JTAG Configuration
[ESP-Driver:USB Serial/JTAG Configuration](./sdkconfig-component-esp-driver-usb-serial-jtag-configurations.md)を参照

## 9.31 Ethernet
[Ethernet](./sdkconfig-component-ethernet.md)を参照

## 9.32 Event Loop Library
[Event Loop Library](./sdkconfig-component-event-loop-library.md)を参照

## 9.33 GDB Stub
[GDB Stub](./sdkconfig-component-gdb-stub.md)を参照

## 9.34 ESP HTTP client
[ESP HTTP client](./sdkconfig-component-esp-http-client.md)を参照

## 9.35 HTTP Server
[HTTP Server](./sdkconfig-component-http-server.md)を参照

## 9.36 ESP HTTPS OTA
[ESP HTTPS OTA](./sdkconfig-component-esp-https-ota.md)を参照

## 9.37 ESP HTTPS server
[ESP HTTPS server](./sdkconfig-component-esp-https-server.md)を参照

## 9.38 Hardware Settings
[Hardware Settings](./sdkconfig-component-hardware-settings.md)を参照

## 9.39 LCD and Touch Panel
[LCD and Touch Panel](./sdkconfig-component-lcd-and-touch-panel.md)を参照

## 9.40 ESP NETIF Adapter
[ESP NETIF Adapter](./sdkconfig-component-esp-netif-adapter.md)を参照

## 9.41 Partition API Configuration
[Partition API Configuration](./sdkconfig-component-partition-api-configuration.md)を参照

## 9.42 PHY
[PHY](./sdkconfig-component-phy.md)を参照

## 9.43 Power Management
[Power Management](./sdkconfig-component-power-management.md)を参照

## 9.44 ESP PSRAM
[ESP PSRAM](./sdkconfig-component-esp-psram.md)を参照

## 9.45 ESP Ringbuf
[ESP Ringbuf](./sdkconfig-component-esp-ringbuf.md)を参照

## 9.46 ESP System Settings
[ESP System Settings](./sdkconfig-component-esp-system-settings.md)を参照

## 9.47 IPC (Inter-Process Call)
[IPC (Inter-Process Call)](./sdkconfig-component-ipc-inter-process-call.md)を参照

## 9.48 ESP Timer
[ESP Timer](./sdkconfig-component-esp-timer.md)を参照

## 9.49 Wi-Fi
[Wi-Fi](./sdkconfig-component-wifi.md)を参照

## 9.50 Core dump
[Core dump](./sdkconfig-component-core-dump.md)を参照

## 9.51 FAT Filesystem support
[FAT Filesystem support](./sdkconfig-component-fat-filesytem-support.md)を参照

## 9.52 FreeRTOS
[FreeRTOS](./sdkconfig-component-freertos.md)を参照

## 9.53 Hardware Abstraction Layer (HAL) and Low Level (LL)
[Hardware Abstraction Layer (HAL) and Low Level (LL)](./sdkconfig-component-hardware-abstraction-layer-and-low-level.md)を参照

## 9.54 Heap memory debugging
[Heap memory debugging](./sdkconfig-component-heap-memory-debugging.md)を参照

## 9.55 IEEE 802.15.4
[IEEE 802.15.4](./sdkconfig-component-ieee-802.15.4.md)を参照

## 9.56 Log output
[Log output](./sdkconfig-component-log-output.md)を参照

## 9.57 LWIP
[LWIP](./sdkconfig-component-lwip.md)を参照

## 9.58 mbedTLS
[mbedTLS](./sdkconfig-component-mbed-tls.md)を参照

## 9.59 ESP-MQTT Configuration
[ESP-MQTT Configuration](./sdkconfig-component-esp-mqtt-configuration.md)を参照

## 9.60 Newlib
[Newlib](./sdkconfig-component-newlib.md)を参照

## 9.61 NVS
[NVS](./sdkconfig-component-nvs.md)を参照

## 9.62 NVS Security Provider
[NVS Security Provider](./sdkconfig-component-nvs-security-provider.md)を参照

## 9.63 OpenThread
[OpenThread](./sdkconfig-component-open-thread.md)を参照

## 9.64 Protocomm
[Protocomm](./sdkconfig-component-protocomm.md)を参照

## 9.65 PThreads
[PThreads](./sdkconfig-component-pthreads.md)を参照

## 9.66 SoC Settings
[SoC Settings](./sdkconfig-component-soc-settings.md)を参照

## 9.67 Main Flash configuration
[Main Flash configuration](./sdkconfig-component-main-flash-configuration.md)を参照

## 9.68 SPI Flash driver
[SPI Flash driver](./sdkconfig-component-spi-flash-driver.md)を参照

## 9.69 SPIFFS Configuration
[SPIFFS Configuration](./sdkconfig-component-spiffs-configuration.md)を参照

## 9.70 TCP Transport
[TCP Transport](./sdkconfig-component-tcp-transport.md)を参照

## 9.71 Ultra Low Power Co-processor
[Ultra Low Power Co-processor](./sdkconfig-component-ultra-low-power-co-processor.md)を参照

## 9.72 Unity unit testing library
[Unity unit testing library](./sdkconfig-component-unity-unit-testing-library.md)を参照

## 9.73 USB-OTG
[USB-OTG](./sdkconfig-component-usb-otg.md)を参照

## 9.74 Virtual file system
[Virtual file system](./sdkconfig-component-virtual-file-system.md)を参照

## 9.75 Wear Levelling
[Wear Levelling](./sdkconfig-component-wear-levelling.md)を参照

## 9.76 Wi-Fi Provisioning Manager
[Wi-Fi Provisioning Manager](./sdkconfig-component-wi-fi-provisioning-manager.md)を参照
