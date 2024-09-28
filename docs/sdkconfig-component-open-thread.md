# 9.63 OpenThread
OpenThreadの設定を記載。

- [9.63 OpenThread](#963-openthread)
  - [9.63.1 OpenThread](#9631-openthread)
    - [9.63.1.1 Enable dynamic log level control](#96311-enable-dynamic-log-level-control)
    - [9.63.1.2 OpenThread console type](#96312-openthread-console-type)
      - [9.63.1.2.1 OpenThread console type UART](#963121-openthread-console-type-uart)
      - [9.63.1.2.2 OpenThread console type USB Serial/JTAG Controller](#963122-openthread-console-type-usb-serialjtag-controller)
    - [9.63.1.3 OpenThread log verbosity](#96313-openthread-log-verbosity)
  - [9.63.2 Thread Operational Dataset](#9632-thread-operational-dataset)
    - [9.63.2.1 OpenThread network name](#96321-openthread-network-name)
    - [9.63.2.2 OpenThread mesh local prefix, format /](#96322-openthread-mesh-local-prefix-format-)
    - [9.63.2.3 OpenThread network channel](#96323-openthread-network-channel)
    - [9.63.2.4 OpenThread network pan id](#96324-openthread-network-pan-id)
    - [9.63.2.5 OpenThread extended pan id](#96325-openthread-extended-pan-id)
    - [9.63.2.6 OpenThread network key](#96326-openthread-network-key)
    - [9.63.2.7 OpenThread pre-shared commissioner key](#96327-openthread-pre-shared-commissioner-key)
  - [9.63.3 Config the Thread radio type](#9633-config-the-thread-radio-type)
  - [9.63.4 Config the Thread device type](#9634-config-the-thread-device-type)
  - [9.63.5 The RCP transport type](#9635-the-rcp-transport-type)
  - [9.63.6 OpenThread version message](#9636-openthread-version-message)
  - [9.63.7 Enable vendor command for RCP](#9637-enable-vendor-command-for-rcp)
  - [9.63.8 Enable OpenThread Command-Line Interface](#9638-enable-openthread-command-line-interface)
  - [9.63.9 Enable diag](#9639-enable-diag)
  - [9.63.10 Enable Commissioner](#96310-enable-commissioner)
    - [9.63.10.1 The size of max commissioning joiner entries](#963101-the-size-of-max-commissioning-joiner-entries)
  - [9.63.11 aEnable Joiner](#96311-aenable-joiner)
  - [9.63.12 Enable SRP Client](#96312-enable-srp-client)
    - [9.63.12.1 Specifies number of service entries in the SRP client service pool](#963121-specifies-number-of-service-entries-in-the-srp-client-service-pool)
  - [9.63.13 Enable DNS Client](#96313-enable-dns-client)
  - [9.63.14 Enable Border Router](#96314-enable-border-router)
  - [9.63.15 Allocate message pool buffer from PSRAM](#96315-allocate-message-pool-buffer-from-psram)
  - [9.63.16 The number of openthread message buffers](#96316-the-number-of-openthread-message-buffers)
  - [9.63.17 The size of  openthread spinel rx frame buffer](#96317-the-size-of--openthread-spinel-rx-frame-buffer)
  - [9.63.18 Maximum backoffs times before declaring a channel access failure.](#96318-maximum-backoffs-times-before-declaring-a-channel-access-failure)
  - [9.63.19 The size of max MLE children entries](#96319-the-size-of-max-mle-children-entries)
  - [9.63.20 Use dns64 client](#96320-use-dns64-client)
    - [9.63.20.1 DNS server address (IPv4)](#963201-dns-server-address-ipv4)
  - [9.63.21 The uart received buffer size of openthread](#96321-the-uart-received-buffer-size-of-openthread)
  - [9.63.22 Enable link metrics feature](#96322-enable-link-metrics-feature)
  - [9.63.23 Enable mac filter feature](#96323-enable-mac-filter-feature)
  - [9.63.24 Enable CSL feature](#96324-enable-csl-feature)
  - [9.63.25 The accuracy of the XTAL](#96325-the-accuracy-of-the-xtal)
  - [9.63.26 The current CSL rx/tx scheduling drift, in units of +/- ppm](#96326-the-current-csl-rxtx-scheduling-drift-in-units-of---ppm)
  - [9.63.27 The CSL Uncertainty in units of 10 us.](#96327-the-csl-uncertainty-in-units-of-10-us)
  - [9.63.28 Enable CSL debug](#96328-enable-csl-debug)
  - [9.63.29 Enable Domain Unicast Address feature](#96329-enable-domain-unicast-address-feature)
  - [9.63.30 Enable the time synchronization service feature](#96330-enable-the-time-synchronization-service-feature)
  - [9.63.31 Enable Radio Statistics feature](#96331-enable-radio-statistics-feature)
  - [9.63.32 Enable OpenThread External Radio Spinel feature](#96332-enable-openthread-external-radio-spinel-feature)
  - [9.63.33 Enable OpenThread radio capability rx on when idle](#96333-enable-openthread-radio-capability-rx-on-when-idle)
  - [9.63.34 Thread Address Query Config](#96334-thread-address-query-config)

## 9.63.1 OpenThread
### 9.63.1.1 Enable dynamic log level control
### 9.63.1.2 OpenThread console type
#### 9.63.1.2.1 OpenThread console type UART
#### 9.63.1.2.2 OpenThread console type USB Serial/JTAG Controller
### 9.63.1.3 OpenThread log verbosity
- No logs
- Error logs
- WArning logs
- Notice logs
- Info logs
- Debug logs
## 9.63.2 Thread Operational Dataset
### 9.63.2.1 OpenThread network name
### 9.63.2.2 OpenThread mesh local prefix, format <address>/<plen>
### 9.63.2.3 OpenThread network channel
### 9.63.2.4 OpenThread network pan id
### 9.63.2.5 OpenThread extended pan id
### 9.63.2.6 OpenThread network key
### 9.63.2.7 OpenThread pre-shared commissioner key
## 9.63.3 Config the Thread radio type
- Native 15.4 radio
- Connect via UART
- Connect via SPI
## 9.63.4 Config the Thread device type
- Full Thread Device
- Minimal Thread Device
- Radio Only Device
## 9.63.5 The RCP transport type
- UART RCP
- SPI RCP
## 9.63.6 OpenThread version message
- OpenThread package name
- platform information
## 9.63.7 Enable vendor command for RCP
## 9.63.8 Enable OpenThread Command-Line Interface
## 9.63.9 Enable diag
## 9.63.10 Enable Commissioner
### 9.63.10.1 The size of max commissioning joiner entries
## 9.63.11 aEnable Joiner
## 9.63.12 Enable SRP Client
### 9.63.12.1 Specifies number of service entries in the SRP client service pool
## 9.63.13 Enable DNS Client
## 9.63.14 Enable Border Router
## 9.63.15 Allocate message pool buffer from PSRAM
## 9.63.16 The number of openthread message buffers
## 9.63.17 The size of  openthread spinel rx frame buffer
## 9.63.18 Maximum backoffs times before declaring a channel access failure.
## 9.63.19 The size of max MLE children entries
## 9.63.20 Use dns64 client
### 9.63.20.1 DNS server address (IPv4)
## 9.63.21 The uart received buffer size of openthread
## 9.63.22 Enable link metrics feature
## 9.63.23 Enable mac filter feature
## 9.63.24 Enable CSL feature
## 9.63.25 The accuracy of the XTAL
## 9.63.26 The current CSL rx/tx scheduling drift, in units of +/- ppm
## 9.63.27 The CSL Uncertainty in units of 10 us.
## 9.63.28 Enable CSL debug
## 9.63.29 Enable Domain Unicast Address feature
## 9.63.30 Enable the time synchronization service feature
## 9.63.31 Enable Radio Statistics feature
## 9.63.32 Enable OpenThread External Radio Spinel feature
## 9.63.33 Enable OpenThread radio capability rx on when idle
## 9.63.34 Thread Address Query Config
- Timeout value (in seconds) for a address notification response after sending an address query.
- Initial retry delay for address query (in seconds).
- Maximum retry delay for address query (in seconds).
