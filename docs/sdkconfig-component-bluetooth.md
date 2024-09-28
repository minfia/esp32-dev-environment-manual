# 9.2 Bluetooth
Bluetoothの設定を記載。

- [9.2 Bluetooth](#92-bluetooth)
  - [9.2.1 Bluetooth](#921-bluetooth)
    - [9.2.1.1 Host](#9211-host)
    - [9.2.1.2 Controller](#9212-controller)
  - [9.2.2 Bluedroid Options](#922-bluedroid-options)
    - [9.2.2.1 Bluetooth event (callback to application) task stack size](#9221-bluetooth-event-callback-to-application-task-stack-size)
    - [9.2.2.2 The cpu core which Bluedroid run](#9222-the-cpu-core-which-bluedroid-run)
    - [9.2.2.3 Bluetooth Bluedroid Host Stack task stack size](#9223-bluetooth-bluedroid-host-stack-task-stack-size)
    - [9.2.2.4 Bluedroid memory debug](#9224-bluedroid-memory-debug)
    - [9.2.2.5 Enable Espressif Vendor-specific HCI commands for coexist status configuration](#9225-enable-espressif-vendor-specific-hci-commands-for-coexist-status-configuration)
    - [9.2.2.6 Classic Bluetooth](#9226-classic-bluetooth)
      - [9.2.2.6.1 configure encryption key size](#92261-configure-encryption-key-size)
      - [9.2.2.6.2 Host Qualification support for Classic Bluetooth](#92262-host-qualification-support-for-classic-bluetooth)
      - [9.2.2.6.3 A2DP](#92263-a2dp)
      - [9.2.2.6.4 SPP](#92264-spp)
      - [9.2.2.6.5 BT L2CAP](#92265-bt-l2cap)
      - [9.2.2.6.6 Hands Free/Handset Profile](#92266-hands-freehandset-profile)
        - [9.2.2.6.6.1 Hands Free Unit](#922661-hands-free-unit)
        - [9.2.2.6.6.2 Audio Gateway](#922662-audio-gateway)
        - [9.2.2.6.6.3 audio data path](#922663-audio-data-path)
    - [9.2.2.7 Wide Band Speech](#9227-wide-band-speech)
    - [9.2.2.8 Classic BT HID](#9228-classic-bt-hid)
      - [9.2.2.8.1 Classic BT HID Host](#92281-classic-bt-hid-host)
      - [9.2.2.8.2 Classic BT HID Device](#92282-classic-bt-hid-device)
    - [9.2.2.9 Bluetooth Low Energy](#9229-bluetooth-low-energy)
      - [9.2.2.9.1 Include GATT server module](#92291-include-gatt-server-module)
        - [9.2.2.9.1.1 Enable Peripheral Preferred Connection Parameters characteristic in GAP service](#922911-enable-peripheral-preferred-connection-parameters-characteristic-in-gap-service)
        - [9.2.2.9.1.2 Include blufi function](#922912-include-blufi-function)
        - [9.2.2.9.1.3 Max GATT Server Profiles](#922913-max-gatt-server-profiles)
        - [9.2.2.9.1.4 Max GATT Service Attributes](#922914-max-gatt-service-attributes)
        - [9.2.2.9.1.5 GATTS Service Change Mode](#922915-gatts-service-change-mode)
        - [9.2.2.9.1.6 Enable Robust Caching on Server Side](#922916-enable-robust-caching-on-server-side)
        - [9.2.2.9.1.7 Allow to write device name by GATT clients](#922917-allow-to-write-device-name-by-gatt-clients)
        - [9.2.2.9.1.8 Allow to write appearance by Gatt clients](#922918-allow-to-write-appearance-by-gatt-clients)
      - [9.2.2.9.2 Include GATT client module](#92292-include-gatt-client-module)
        - [9.2.2.9.2.1 Max gattc change characteristic for discover](#922921-max-gattc-change-characteristic-for-discover)
        - [9.2.2.9.2.2 Max gattc notify(indication) register number](#922922-max-gattc-notifyindication-register-number)
        - [9.2.2.9.2.3 Save gattc cache data to nvs flash](#922923-save-gattc-cache-data-to-nvs-flash)
        - [9.2.2.9.2.4 The number of attempts reconnect if the connection establishment failed](#922924-the-number-of-attempts-reconnect-if-the-connection-establishment-failed)
      - [9.2.2.9.3 Include BLE security module](#92293-include-ble-security-module)
        - [9.2.2.9.3.1 Slave enable connection parameters update during pairing](#922931-slave-enable-connection-parameters-update-during-pairing)
        - [9.2.2.9.3.2 Reset device identity when all bonding records are deleted](#922932-reset-device-identity-when-all-bonding-records-are-deleted)
    - [9.2.2.10 Disable BT debug logs](#92210-disable-bt-debug-logs)
    - [9.2.2.11 BT DEBUG LOG LEVEL](#92211-bt-debug-log-level)
    - [9.2.2.12 BT/BLE MAX ACK CONNECTIONS](#92212-btble-max-ack-connections)
    - [9.2.2.13 Enable BLE multi-connections](#92213-enable-ble-multi-connections)
    - [9.2.2.14 BT/BLE will first malloc the memory from the PSRAM](#92214-btble-will-first-malloc-the-memory-from-the-psram)
    - [9.2.2.15 Use dynamic memory allocation in BT/BLE stack](#92215-use-dynamic-memory-allocation-in-btble-stack)
    - [9.2.2.16 BLE queue congestion check](#92216-ble-queue-congestion-check)
    - [9.2.2.17 BT/BLE maximum bond device count](#92217-btble-maximum-bond-device-count)
    - [9.2.2.18 Report adv data and scan response individually when BLE active scan](#92218-report-adv-data-and-scan-response-individually-when-ble-active-scan)
    - [9.2.2.19 Timeout of BLE connection establishment](#92219-timeout-of-ble-connection-establishment)
    - [9.2.2.20 length of bluetooth device name](#92220-length-of-bluetooth-device-name)
    - [9.2.2.21 Update RPA to Controller](#92221-update-rpa-to-controller)
    - [9.2.2.22 Timeout of resolvable private address](#92222-timeout-of-resolvable-private-address)
    - [9.2.2.23 Enable BLE 5.0 features](#92223-enable-ble-50-features)
    - [9.2.2.24 Enable BLE 4.2 features](#92224-enable-ble-42-features)
    - [9.2.2.25 Enable BLE periodic advertising sync transfer feature](#92225-enable-ble-periodic-advertising-sync-transfer-feature)
    - [9.2.2.26 Enable periodic adv enhancements](#92226-enable-periodic-adv-enhancements)
    - [9.2.2.27 Enable create sync enhancements](#92227-enable-create-sync-enhancements)
    - [9.2.2.28 Enable BLE high duty advertising interval feature](#92228-enable-ble-high-duty-advertising-interval-feature)
  - [9.2.3 NimBLE Options](#923-nimble-options)
    - [9.2.3.1 Memory allocation strategy](#9231-memory-allocation-strategy)
    - [9.2.3.2 NimBLE Host log verbosity](#9232-nimble-host-log-verbosity)
    - [9.2.3.3 Maximum number of concurrent connections](#9233-maximum-number-of-concurrent-connections)
    - [9.2.3.4 Maximum number of bonds to save across reboots](#9234-maximum-number-of-bonds-to-save-across-reboots)
    - [9.2.3.5 Maximum number of CCC descriptors to save across reboots](#9235-maximum-number-of-ccc-descriptors-to-save-across-reboots)
    - [9.2.3.6 Maximum number of connection oriented channels](#9236-maximum-number-of-connection-oriented-channels)
    - [9.2.3.7 The CPU core on which NumBLE host will run](#9237-the-cpu-core-on-which-numble-host-will-run)
    - [9.2.3.8 NimBLE Host task stack size](#9238-nimble-host-task-stack-size)
    - [9.2.3.9 Enable BLE Central role](#9239-enable-ble-central-role)
    - [9.2.3.10 Enable BLE Peripheral role](#92310-enable-ble-peripheral-role)
    - [9.2.3.11 Enable BLE Broadcaster role](#92311-enable-ble-broadcaster-role)
    - [9.2.3.12 Enable BLE Observer role](#92312-enable-ble-observer-role)
    - [9.2.3.13 Persist the BLE Bonding keys in NVS](#92313-persist-the-ble-bonding-keys-in-nvs)
    - [9.2.3.14 Reset device identity when all bonding records are deleted](#92314-reset-device-identity-when-all-bonding-records-are-deleted)
    - [9.2.3.15 Enable BLE SM feature](#92315-enable-ble-sm-feature)
      - [9.2.3.15.1 Security manager legacy pairing](#923151-security-manager-legacy-pairing)
      - [9.2.3.15.2 Security manager secure connections](#923152-security-manager-secure-connections)
        - [9.2.3.15.2.1 Use predefined public-private key pair](#9231521-use-predefined-public-private-key-pair)
      - [9.2.3.15.3 Enable LE encryption](#923153-enable-le-encryption)
      - [9.2.3.15.4 Security level](#923154-security-level)
    - [9.2.3.16 Enable extra runtime asserts and host debugging](#92316-enable-extra-runtime-asserts-and-host-debugging)
    - [9.2.3.17 Enable dynamic services](#92317-enable-dynamic-services)
    - [9.2.3.18 BLE GAP default device name](#92318-ble-gap-default-device-name)
    - [9.2.3.19 Maximum length of BLE device name in octets](#92319-maximum-length-of-ble-device-name-in-octets)
    - [9.2.3.20 Preferred MTU size in octets](#92320-preferred-mtu-size-in-octets)
    - [9.2.3.21 External appearance of the device](#92321-external-appearance-of-the-device)
    - [9.2.3.22 Memory Settings](#92322-memory-settings)
      - [9.2.3.22.1 MSYS\_1 Block Count](#923221-msys_1-block-count)
      - [9.2.3.22.2 MSYS\_1 Block Size](#923222-msys_1-block-size)
      - [9.2.3.22.3 MSYS\_2 Block Count](#923223-msys_2-block-count)
      - [9.2.3.22.4 MSYS\_2 Block Size](#923224-msys_2-block-size)
      - [9.2.3.22.5 Get Msys Mbuf from heap](#923225-get-msys-mbuf-from-heap)
      - [9.2.3.22.6 ACL Buffer count](#923226-acl-buffer-count)
      - [9.2.3.22.7 Transport ACL Buffer size](#923227-transport-acl-buffer-size)
      - [9.2.3.22.8 Transport Event Buffer size](#923228-transport-event-buffer-size)
      - [9.2.3.22.9 Transport Event Buffer count](#923229-transport-event-buffer-count)
      - [9.2.3.22.10 Discardable Transport Event Buffer count](#9232210-discardable-transport-event-buffer-count)
      - [9.2.3.22.11 L2cap coc Service Data Unit Buffer count](#9232211-l2cap-coc-service-data-unit-buffer-count)
    - [9.2.3.23 Maximum number of GATT client procedures](#92323-maximum-number-of-gatt-client-procedures)
    - [9.2.3.24 Enable Host Flow control](#92324-enable-host-flow-control)
      - [9.2.3.24.1 Host Flow control interval](#923241-host-flow-control-interval)
      - [9.2.3.24.2 Host Flow control threshold](#923242-host-flow-control-threshold)
      - [9.2.3.24.3 Host Flow control on disconnect](#923243-host-flow-control-on-disconnect)
    - [9.2.3.25 RPA timeout in seconds](#92325-rpa-timeout-in-seconds)
    - [9.2.3.26 Enable BLE mesh functionality](#92326-enable-ble-mesh-functionality)
      - [9.2.3.26.1 Enable mesh proxy functionality](#923261-enable-mesh-proxy-functionality)
      - [9.2.3.26.2 Enable BLE mesh provisioning](#923262-enable-ble-mesh-provisioning)
        - [9.2.3.26.2.1 Enable mesh provisioning over advertising bearer](#9232621-enable-mesh-provisioning-over-advertising-bearer)
        - [9.2.3.26.2.2 Enable mesh provisioning over GATT bearer](#9232622-enable-mesh-provisioning-over-gatt-bearer)
      - [9.2.3.26.3 Enable GATT Proxy functionality](#923263-enable-gatt-proxy-functionality)
      - [9.2.3.26.4 Enable mesh relay functionality](#923264-enable-mesh-relay-functionality)
      - [9.2.3.26.5 Enable mesh low power mode](#923265-enable-mesh-low-power-mode)
      - [9.2.3.26.6 Enable mesh friend functionality](#923266-enable-mesh-friend-functionality)
      - [9.2.3.26.7 Set mesh device name](#923267-set-mesh-device-name)
      - [9.2.3.26.8 Set mesh node count](#923268-set-mesh-node-count)
      - [9.2.3.26.9 Enable BLE mesh provisioner](#923269-enable-ble-mesh-provisioner)
    - [9.2.3.27 Override TinyCrypt with mbedTLS for crypto computations](#92327-override-tinycrypt-with-mbedtls-for-crypto-computations)
    - [9.2.3.28 BLE host stop timeout in msec](#92328-ble-host-stop-timeout-in-msec)
    - [9.2.3.29 Enable host based privacy for random address.](#92329-enable-host-based-privacy-for-random-address)
    - [9.2.3.30 Enable connection reattempts on connection establishment error](#92330-enable-connection-reattempts-on-connection-establishment-error)
      - [9.2.3.30.1 Maximum number connection reattempts](#923301-maximum-number-connection-reattempts)
    - [9.2.3.31 Enable BLE 5 feature](#92331-enable-ble-5-feature)
      - [9.2.3.31.1 Enable 2M Phy](#923311-enable-2m-phy)
      - [9.2.3.31.2 Enable coded Phy](#923312-enable-coded-phy)
      - [9.2.3.31.3 Enable extended advertising](#923313-enable-extended-advertising)
        - [9.2.3.31.3.1 Maximum number of extended advertising instances.](#9233131-maximum-number-of-extended-advertising-instances)
        - [9.2.3.31.3.2 Maximum length of the advertising data.](#9233132-maximum-length-of-the-advertising-data)
        - [9.2.3.31.3.3 Enable periodic advertisement.](#9233133-enable-periodic-advertisement)
          - [9.2.3.31.3.3.1 Enable Transfer Sync Events](#92331331-enable-transfer-sync-events)
        - [9.2.3.31.3.4 Maximum number of periodic advertising syncs](#9233134-maximum-number-of-periodic-advertising-syncs)
        - [9.2.3.31.3.5 Maximum number of periodic advertiser list](#9233135-maximum-number-of-periodic-advertiser-list)
        - [9.2.3.31.3.6 Enable support for BLE Power Control](#9233136-enable-support-for-ble-power-control)
        - [9.2.3.31.3.7 Periodic adv enhancements(adi support)](#9233137-periodic-adv-enhancementsadi-support)
        - [9.2.3.31.3.8 Enable GATT caching](#9233138-enable-gatt-caching)
    - [9.2.3.32 BLE white list size](#92332-ble-white-list-size)
    - [9.2.3.33 Throughput Test Mode enable](#92333-throughput-test-mode-enable)
    - [9.2.3.34 Enable blufi functionality](#92334-enable-blufi-functionality)
    - [9.2.3.35 Enable Esp Timer for Nimble](#92335-enable-esp-timer-for-nimble)
    - [9.2.3.36 Blob transfer](#92336-blob-transfer)
    - [9.2.3.37 GAP Service](#92337-gap-service)
      - [9.2.3.37.1 GAP Appearance write permissions](#923371-gap-appearance-write-permissions)
        - [9.2.3.37.1.1 Write](#9233711-write)
      - [9.2.3.37.2 GAP Characteristic - Central Address Resolution](#923372-gap-characteristic---central-address-resolution)
      - [9.2.3.37.3 GAP device name write permissions](#923373-gap-device-name-write-permissions)
        - [9.2.3.37.3.1 Write](#9233731-write)
      - [9.2.3.37.4 PPCP Connection Interval Max](#923374-ppcp-connection-interval-max)
      - [9.2.3.37.5 PPCP Connection Interval Min](#923375-ppcp-connection-interval-min)
      - [9.2.3.37.6 PPCP Slave Latency](#923376-ppcp-slave-latency)
      - [9.2.3.37.7 PPCP Supervision Timeout](#923377-ppcp-supervision-timeout)
    - [9.2.3.38 BLE Services](#92338-ble-services)
      - [9.2.3.38.1 HID service](#923381-hid-service)
        - [9.2.3.38.1.1 Maximum HID service instances](#9233811-maximum-hid-service-instances)
        - [9.2.3.38.1.2 Maximum HID Report characteristic per service instance](#9233812-maximum-hid-report-characteristic-per-service-instance)
    - [9.2.3.39 Enable support for VSC and VSE](#92339-enable-support-for-vsc-and-vse)
    - [9.2.3.40 Encrypted Advertising Data](#92340-encrypted-advertising-data)
      - [9.2.3.40.1 Maximum number of EAD devices to save across reboots](#923401-maximum-number-of-ead-devices-to-save-across-reboots)
    - [9.2.3.41 Enable BLE high duty advertising interval feature](#92341-enable-ble-high-duty-advertising-interval-feature)
    - [9.2.3.42 BLE queue congestion check](#92342-ble-queue-congestion-check)
    - [9.2.3.43 Host-controller Transport](#92343-host-controller-transport)
      - [9.2.3.43.1 Enable Uart Transport](#923431-enable-uart-transport)
        - [9.2.3.43.1.1 Uart port](#9234311-uart-port)
        - [9.2.3.43.1.2 Uart Hci Baud Rate](#9234312-uart-hci-baud-rate)
        - [9.2.3.43.1.3 Uart PARITY](#9234313-uart-parity)
        - [9.2.3.43.1.4 UART Rx pin](#9234314-uart-rx-pin)
        - [9.2.3.43.1.5 UART Tx pin](#9234315-uart-tx-pin)
      - [9.2.3.43.2 Uart Flow Control](#923432-uart-flow-control)
      - [9.2.3.43.3 UART Rts Pin](#923433-uart-rts-pin)
      - [9.2.3.43.4 UART Cts Pin](#923434-uart-cts-pin)
  - [9.2.4 Controller Options](#924-controller-options)
    - [9.2.4.1 Bluetooth controller mode](#9241-bluetooth-controller-mode)
    - [9.2.4.2 BLE Max Conections](#9242-ble-max-conections)
    - [9.2.4.3 BR/EDR ACL Max Connections](#9243-bredr-acl-max-connections)
    - [9.2.4.4 BR/EDR Sync(SCO/eSCO) Max Connections](#9244-bredr-syncscoesco-max-connections)
    - [9.2.4.5 BR/EDR Sync(SCO/eSCO) default data path](#9245-bredr-syncscoesco-default-data-path)
    - [9.2.4.6 PCM Signal Config](#9246-pcm-signal-config)
      - [9.2.4.6.1 PCM Role](#92461-pcm-role)
      - [9.2.4.6.2 PCM Polar](#92462-pcm-polar)
    - [9.2.4.7 Auto Latency](#9247-auto-latency)
    - [9.2.4.8 Legacy Authentication Vender Specific Event Enable](#9248-legacy-authentication-vender-specific-event-enable)
    - [9.2.4.9 The cpu core which bluetooth controller run](#9249-the-cpu-core-which-bluetooth-controller-run)
    - [9.2.4.10 HCI mode](#92410-hci-mode)
    - [9.2.4.11 HCI UART(H4) mode](#92411-hci-uarth4-mode)
      - [9.2.4.11.1 UART Number for HCI](#924111-uart-number-for-hci)
      - [9.2.4.11.2 UART Baudrate for HCI](#924112-uart-baudrate-for-hci)
      - [9.2.4.11.3 Enable Uart flow control](#924113-enable-uart-flow-control)
    - [9.2.4.12 MODEM SLEEP Options](#92412-modem-sleep-options)
      - [9.2.4.12.1 Bluetooth modem sleep](#924121-bluetooth-modem-sleep)
        - [9.2.4.12.1.1 Bluetooth modem sleep mode](#9241211-bluetooth-modem-sleep-mode)
      - [9.2.4.12.2 Bluetooth low power clock](#924122-bluetooth-low-power-clock)
    - [9.2.4.13 BLE Sleep Clock Accuracy](#92413-ble-sleep-clock-accuracy)
    - [9.2.4.14 BLE Scan Duplicate Options](#92414-ble-scan-duplicate-options)
      - [9.2.4.14.1 Scan Duplicate Type](#924141-scan-duplicate-type)
      - [9.2.4.14.2 Maximum number of devices in scan duplicate filter](#924142-maximum-number-of-devices-in-scan-duplicate-filter)
      - [9.2.4.14.3 Duplicate scan list refresh period](#924143-duplicate-scan-list-refresh-period)
      - [9.2.4.14.4 Special duplicate scan mechanism for BLE Mesh scan](#924144-special-duplicate-scan-mechanism-for-ble-mesh-scan)
        - [9.2.4.14.4.1 Maximum number of Mesh adv packets in scan duplicate filter](#9241441-maximum-number-of-mesh-adv-packets-in-scan-duplicate-filter)
    - [9.2.4.15 BLE full scan feature supported](#92415-ble-full-scan-feature-supported)
    - [9.2.4.16 Disable active scan backoff](#92416-disable-active-scan-backoff)
    - [9.2.4.17 BLE adv report flow control supported](#92417-ble-adv-report-flow-control-supported)
      - [9.2.4.17.1 BLE adv report flow control number](#924171-ble-adv-report-flow-control-number)
      - [9.2.4.17.2 BLE adv lost event threshold value](#924172-ble-adv-lost-event-threshold-value)
    - [9.2.4.18 High level interrupt](#92418-high-level-interrupt)
  - [9.2.5 Release Bluetooth text](#925-release-bluetooth-text)
  - [9.2.6 Common Options](#926-common-options)
    - [9.2.6.1 Maximum number of Bluetooth alarms](#9261-maximum-number-of-bluetooth-alarms)
  - [9.2.7 Enable Bluetooth HCI debug mode](#927-enable-bluetooth-hci-debug-mode)
    - [9.2.7.1 size of the cache used for HCI data in Bluetooth HCI debug mode](#9271-size-of-the-cache-used-for-hci-data-in-bluetooth-hci-debug-mode)
    - [9.2.7.2 size of the cache used for adv report in Bluetooth HCI debug mode](#9272-size-of-the-cache-used-for-adv-report-in-bluetooth-hci-debug-mode)

## 9.2.1 Bluetooth
### 9.2.1.1 Host
- Bluedroid - Dual-mode
- NimBLE - BLE only
- Disable
### 9.2.1.2 Controller
- Enable
- Disable
## 9.2.2 Bluedroid Options
"[Bluetooth](#921-bluetooth)"を有効かつ"[Host](#9211-host)"を"Bluedroid"以外で表示
### 9.2.2.1 Bluetooth event (callback to application) task stack size
### 9.2.2.2 The cpu core which Bluedroid run
- Core 0 (PRO CPU)
- Core 1 (APP CPU)
### 9.2.2.3 Bluetooth Bluedroid Host Stack task stack size
### 9.2.2.4 Bluedroid memory debug
### 9.2.2.5 Enable Espressif Vendor-specific HCI commands for coexist status configuration
### 9.2.2.6 Classic Bluetooth
#### 9.2.2.6.1 configure encryption key size
- Supported by standard HCI command
- Supported by Vender-specific HCI command
- Not Supported
#### 9.2.2.6.2 Host Qualification support for Classic Bluetooth
#### 9.2.2.6.3 A2DP
#### 9.2.2.6.4 SPP
#### 9.2.2.6.5 BT L2CAP
#### 9.2.2.6.6 Hands Free/Handset Profile
"[Hands Free/Handset Profile](#92266-hands-freehandset-profile)"を有効で設定可能
##### 9.2.2.6.6.1 Hands Free Unit
##### 9.2.2.6.6.2 Audio Gateway
##### 9.2.2.6.6.3 audio data path
- PCM
- HCI
### 9.2.2.7 Wide Band Speech
"[Hands Free/Handset Profile](#92266-hands-freehandset-profile)"を有効で表示
### 9.2.2.8 Classic BT HID
"[Classic Bluetooth](#9226-classic-bluetooth)"の有効で表示
"[Classic BT HID](#9228-classic-bt-hid)"を有効で設定可能
#### 9.2.2.8.1 Classic BT HID Host
#### 9.2.2.8.2 Classic BT HID Device
### 9.2.2.9 Bluetooth Low Energy
#### 9.2.2.9.1 Include GATT server module
##### 9.2.2.9.1.1 Enable Peripheral Preferred Connection Parameters characteristic in GAP service
##### 9.2.2.9.1.2 Include blufi function
##### 9.2.2.9.1.3 Max GATT Server Profiles
##### 9.2.2.9.1.4 Max GATT Service Attributes
##### 9.2.2.9.1.5 GATTS Service Change Mode
- GATTS manually send service change indication
- GATTS automatically send service change indication
##### 9.2.2.9.1.6 Enable Robust Caching on Server Side
##### 9.2.2.9.1.7 Allow to write device name by GATT clients
##### 9.2.2.9.1.8 Allow to write appearance by Gatt clients
#### 9.2.2.9.2 Include GATT client module
##### 9.2.2.9.2.1 Max gattc change characteristic for discover
##### 9.2.2.9.2.2 Max gattc notify(indication) register number
##### 9.2.2.9.2.3 Save gattc cache data to nvs flash
##### 9.2.2.9.2.4 The number of attempts reconnect if the connection establishment failed
#### 9.2.2.9.3 Include BLE security module
##### 9.2.2.9.3.1 Slave enable connection parameters update during pairing
##### 9.2.2.9.3.2 Reset device identity when all bonding records are deleted
### 9.2.2.10 Disable BT debug logs
### 9.2.2.11 BT DEBUG LOG LEVEL
以下の設定を各layerで行う。
- NONE
- ERROR
- WARNING
- API
- EVENT
- DEBUG
- VERBOSE

1. HCI layer
1. BTM layer
1. L2CAP layer
1. RFCOMM layer
1. SDP layer
1. GAP layer
1. BNEP layer
1. PAN layer
1. A2D layer
1. AVDT layer
1. AVCT layer
1. AVRC layer
1. MCA layer
1. HID layer
1. APPL layer
1. GATT layer
1. SMP layer
1. BTIF layer
1. BTC layer
1. OSI layer
1. BLUFI layer
### 9.2.2.12 BT/BLE MAX ACK CONNECTIONS
### 9.2.2.13 Enable BLE multi-connections
### 9.2.2.14 BT/BLE will first malloc the memory from the PSRAM
### 9.2.2.15 Use dynamic memory allocation in BT/BLE stack
### 9.2.2.16 BLE queue congestion check
### 9.2.2.17 BT/BLE maximum bond device count
### 9.2.2.18 Report adv data and scan response individually when BLE active scan
### 9.2.2.19 Timeout of BLE connection establishment
### 9.2.2.20 length of bluetooth device name
### 9.2.2.21 Update RPA to Controller
### 9.2.2.22 Timeout of resolvable private address
### 9.2.2.23 Enable BLE 5.0 features
"[Controller](#9212-controller)"を無効で表示
### 9.2.2.24 Enable BLE 4.2 features
### 9.2.2.25 Enable BLE periodic advertising sync transfer feature
"[Enable BLE 5.0 features](#92222-enable-ble-50-features)"を有効で表示
### 9.2.2.26 Enable periodic adv enhancements
"[Enable BLE 5.0 features](#92222-enable-ble-50-features)"を有効で表示
### 9.2.2.27 Enable create sync enhancements
"[Enable BLE 5.0 features](#92222-enable-ble-50-features)"を有効で表示
### 9.2.2.28 Enable BLE high duty advertising interval feature
## 9.2.3 NimBLE Options
"[Bluetooth](#921-bluetooth)"を有効かつ"[Host](#9211-host)"を"NimBLE"以外で表示
### 9.2.3.1 Memory allocation strategy
- Internal memory
- External SPIRAM
- Default alloc mode
- Internal IRAM
### 9.2.3.2 NimBLE Host log verbosity
- No logs
- Error logs
- Warning logs
- Info logs
- Debug logs
### 9.2.3.3 Maximum number of concurrent connections
### 9.2.3.4 Maximum number of bonds to save across reboots
### 9.2.3.5 Maximum number of CCC descriptors to save across reboots
### 9.2.3.6 Maximum number of connection oriented channels
### 9.2.3.7 The CPU core on which NumBLE host will run
- Core 0 (PRO CPU)
- Core 1 (APP CPU)
### 9.2.3.8 NimBLE Host task stack size
### 9.2.3.9 Enable BLE Central role
### 9.2.3.10 Enable BLE Peripheral role
### 9.2.3.11 Enable BLE Broadcaster role
### 9.2.3.12 Enable BLE Observer role
### 9.2.3.13 Persist the BLE Bonding keys in NVS
### 9.2.3.14 Reset device identity when all bonding records are deleted
### 9.2.3.15 Enable BLE SM feature
"[Enable BLE SM feature](#92315-enable-ble-sm-feature)"の有効で設定可能
#### 9.2.3.15.1 Security manager legacy pairing
#### 9.2.3.15.2 Security manager secure connections
##### 9.2.3.15.2.1 Use predefined public-private key pair
"[Security manager secure connections](#923152-security-manager-secure-connections)"の有効で表示
#### 9.2.3.15.3 Enable LE encryption
#### 9.2.3.15.4 Security level
### 9.2.3.16 Enable extra runtime asserts and host debugging
### 9.2.3.17 Enable dynamic services
### 9.2.3.18 BLE GAP default device name
### 9.2.3.19 Maximum length of BLE device name in octets
### 9.2.3.20 Preferred MTU size in octets
### 9.2.3.21 External appearance of the device
### 9.2.3.22 Memory Settings
#### 9.2.3.22.1 MSYS_1 Block Count
#### 9.2.3.22.2 MSYS_1 Block Size
#### 9.2.3.22.3 MSYS_2 Block Count
#### 9.2.3.22.4 MSYS_2 Block Size
#### 9.2.3.22.5 Get Msys Mbuf from heap
#### 9.2.3.22.6 ACL Buffer count
#### 9.2.3.22.7 Transport ACL Buffer size
#### 9.2.3.22.8 Transport Event Buffer size
#### 9.2.3.22.9 Transport Event Buffer count
#### 9.2.3.22.10 Discardable Transport Event Buffer count
#### 9.2.3.22.11 L2cap coc Service Data Unit Buffer count
### 9.2.3.23 Maximum number of GATT client procedures
### 9.2.3.24 Enable Host Flow control
#### 9.2.3.24.1 Host Flow control interval
"[Enable Host Flow control](#92324-enable-host-flow-control)"の有効で表示
#### 9.2.3.24.2 Host Flow control threshold
"[Enable Host Flow control](#92324-enable-host-flow-control)"の有効で表示
#### 9.2.3.24.3 Host Flow control on disconnect
"[Enable Host Flow control](#92324-enable-host-flow-control)"の有効で表示
### 9.2.3.25 RPA timeout in seconds
### 9.2.3.26 Enable BLE mesh functionality
#### 9.2.3.26.1 Enable mesh proxy functionality
"[Enable BLE mesh functionality](#92326-enable-ble-mesh-functionality)"の有効で設定可能
"[Enable GATT Proxy functionality](#923263-enable-gatt-proxy-functionality)"が有効で強制有効
#### 9.2.3.26.2 Enable BLE mesh provisioning
"[Enable BLE mesh functionality](#92326-enable-ble-mesh-functionality)"の有効で設定可能
##### 9.2.3.26.2.1 Enable mesh provisioning over advertising bearer
##### 9.2.3.26.2.2 Enable mesh provisioning over GATT bearer
#### 9.2.3.26.3 Enable GATT Proxy functionality
"[Enable BLE mesh functionality](#92326-enable-ble-mesh-functionality)"の有効で設定可能
#### 9.2.3.26.4 Enable mesh relay functionality
"[Enable BLE mesh functionality](#92326-enable-ble-mesh-functionality)"の有効で設定可能
#### 9.2.3.26.5 Enable mesh low power mode
"[Enable BLE mesh functionality](#92326-enable-ble-mesh-functionality)"の有効で設定可能
#### 9.2.3.26.6 Enable mesh friend functionality
"[Enable BLE mesh functionality](#92326-enable-ble-mesh-functionality)"の有効で設定可能
#### 9.2.3.26.7 Set mesh device name
"[Enable BLE mesh functionality](#92326-enable-ble-mesh-functionality)"の有効で設定可能
#### 9.2.3.26.8 Set mesh node count
"[Enable BLE mesh functionality](#92326-enable-ble-mesh-functionality)"の有効で設定可能
#### 9.2.3.26.9 Enable BLE mesh provisioner
"[Enable BLE mesh functionality](#92326-enable-ble-mesh-functionality)"の有効で設定可能
### 9.2.3.27 Override TinyCrypt with mbedTLS for crypto computations
### 9.2.3.28 BLE host stop timeout in msec
### 9.2.3.29 Enable host based privacy for random address.
### 9.2.3.30 Enable connection reattempts on connection establishment error
#### 9.2.3.30.1 Maximum number connection reattempts
### 9.2.3.31 Enable BLE 5 feature
"[Enable BLE 5 feature](#92331-enable-ble-5-feature)"の有効で設定可能
#### 9.2.3.31.1 Enable 2M Phy
#### 9.2.3.31.2 Enable coded Phy
#### 9.2.3.31.3 Enable extended advertising
##### 9.2.3.31.3.1 Maximum number of extended advertising instances.
##### 9.2.3.31.3.2 Maximum length of the advertising data.
##### 9.2.3.31.3.3 Enable periodic advertisement.
###### 9.2.3.31.3.3.1 Enable Transfer Sync Events
##### 9.2.3.31.3.4 Maximum number of periodic advertising syncs
##### 9.2.3.31.3.5 Maximum number of periodic advertiser list
##### 9.2.3.31.3.6 Enable support for BLE Power Control
##### 9.2.3.31.3.7 Periodic adv enhancements(adi support)
##### 9.2.3.31.3.8 Enable GATT caching
"[Enable GATT caching](#9233135-enable-gatt-caching)"の有効で設定可能
- Maximum connections to be cached
- Maximum number of services per connection
- Maximum number of characteristics per connection
- Maximum number of descriptors per connection
### 9.2.3.32 BLE white list size
### 9.2.3.33 Throughput Test Mode enable
### 9.2.3.34 Enable blufi functionality
### 9.2.3.35 Enable Esp Timer for Nimble
### 9.2.3.36 Blob transfer
### 9.2.3.37 GAP Service
#### 9.2.3.37.1 GAP Appearance write permissions
##### 9.2.3.37.1.1 Write
- Write with encryption
"[Write](#9233711-write)"の有効で表示
- Write with authentication
"[Write](#9233711-write)"の有効で表示
- Write with authorisation
"[Write](#9233711-write)"の有効で表示
#### 9.2.3.37.2 GAP Characteristic - Central Address Resolution
- Characteristic not supported
- Central Address Resolution not supported
- Central Address Resolution supported
#### 9.2.3.37.3 GAP device name write permissions
##### 9.2.3.37.3.1 Write
- Write with encryption
"[Write](#9233731-write)"の有効で表示
- Write with authentication
"[Write](#9233731-write)"の有効で表示
- Write with authorisation
"[Write](#9233731-write)"の有効で表示
#### 9.2.3.37.4 PPCP Connection Interval Max
#### 9.2.3.37.5 PPCP Connection Interval Min
#### 9.2.3.37.6 PPCP Slave Latency
#### 9.2.3.37.7 PPCP Supervision Timeout
### 9.2.3.38 BLE Services
#### 9.2.3.38.1 HID service
"[HID service](#923381-hid-service)"の有効で設定可能
##### 9.2.3.38.1.1 Maximum HID service instances
##### 9.2.3.38.1.2 Maximum HID Report characteristic per service instance
### 9.2.3.39 Enable support for VSC and VSE
### 9.2.3.40 Encrypted Advertising Data
#### 9.2.3.40.1 Maximum number of EAD devices to save across reboots
"[Encrypted Advertising Data](#92340-encrypted-advertising-data)"の有効で表示
### 9.2.3.41 Enable BLE high duty advertising interval feature
### 9.2.3.42 BLE queue congestion check
### 9.2.3.43 Host-controller Transport
#### 9.2.3.43.1 Enable Uart Transport
##### 9.2.3.43.1.1 Uart port
##### 9.2.3.43.1.2 Uart Hci Baud Rate
- 115200
- 230400
- 460800
- 921600
##### 9.2.3.43.1.3 Uart PARITY
- None
- Odd
- Even
##### 9.2.3.43.1.4 UART Rx pin
##### 9.2.3.43.1.5 UART Tx pin
#### 9.2.3.43.2 Uart Flow Control
- Disable
- Enable hardware flow control
#### 9.2.3.43.3 UART Rts Pin
#### 9.2.3.43.4 UART Cts Pin
## 9.2.4 Controller Options
"[Bluetooth](#921-bluetooth)"を有効かつ"[Controller](#9212-controller)"を"Enable"で表示で表示
### 9.2.4.1 Bluetooth controller mode
- BLE Only
- BR/EDR Only
- Bluetooth Dual Mode
### 9.2.4.2 BLE Max Conections
"[Bluetooth controller mode](#9241-bluetooth-controller-mode)"の"BR/EDR Only"以外有効で表示
### 9.2.4.3 BR/EDR ACL Max Connections
"[Bluetooth controller mode](#9241-bluetooth-controller-mode)"の"BLE Only"以外有効で表示
### 9.2.4.4 BR/EDR Sync(SCO/eSCO) Max Connections
"[Bluetooth controller mode](#9241-bluetooth-controller-mode)"の"BLE Only"以外有効で表示
### 9.2.4.5 BR/EDR Sync(SCO/eSCO) default data path
"[Bluetooth controller mode](#9241-bluetooth-controller-mode)"の"BLE Only"以外有効で表示
- HCI
- PCM
### 9.2.4.6 PCM Signal Config
"[Bluetooth controller mode](#9241-bluetooth-controller-mode)"の"BLE Only"以外有効で表示
#### 9.2.4.6.1 PCM Role
- PCM Master
- PCM Slave
#### 9.2.4.6.2 PCM Polar
- Falling Edge
- Rising Edge
### 9.2.4.7 Auto Latency
"[Bluetooth controller mode](#9241-bluetooth-controller-mode)"の"Bluetooth Dual Mode"有効で表示
### 9.2.4.8 Legacy Authentication Vender Specific Event Enable
"[Bluetooth controller mode](#9241-bluetooth-controller-mode)"の"BLE Only"以外有効で表示
### 9.2.4.9 The cpu core which bluetooth controller run
- Core 0 (PRO CPU)
- Core 1 (APP CPU)
### 9.2.4.10 HCI mode
- VHCI
- UART(H4)
### 9.2.4.11 HCI UART(H4) mode
#### 9.2.4.11.1 UART Number for HCI
#### 9.2.4.11.2 UART Baudrate for HCI
#### 9.2.4.11.3 Enable Uart flow control
### 9.2.4.12 MODEM SLEEP Options
#### 9.2.4.12.1 Bluetooth modem sleep
##### 9.2.4.12.1.1 Bluetooth modem sleep mode
"[Bluetooth modem sleep](#924111-bluetooth-modem-sleep)"の有効で表示
- ORIG Mode(sleep with low power clock)
- EVED Mode(For internal test only)
#### 9.2.4.12.2 Bluetooth low power clock
"[Bluetooth modem sleep](#924111-bluetooth-modem-sleep)"の有効かつ"[Bluetooth modem sleep mode](#9241111-bluetooth-modem-sleep-mode)"を"ORIG Mode(sleep with low power clock)"の有効で表示
- Main crystal
- External 32kHz crystal
### 9.2.4.13 BLE Sleep Clock Accuracy
"[Bluetooth controller mode](#9241-bluetooth-controller-mode)"の"BR/EDR Only"以外有効で表示
- 251ppm to 500ppm
- 151ppm to 250ppm
### 9.2.4.14 BLE Scan Duplicate Options
"[Bluetooth controller mode](#9241-bluetooth-controller-mode)"の"BR/EDR Only"以外有効で表示
#### 9.2.4.14.1 Scan Duplicate Type
"[BLE Scan Duplicate Options](#92413-ble-scan-duplicate-options)"の有効で表示
- Scan Duplicate By Device Address
- Scan Duplicate By Advertising Data
- Scan Duplicate By Device Address And Advertising Data
#### 9.2.4.14.2 Maximum number of devices in scan duplicate filter
"[BLE Scan Duplicate Options](#92413-ble-scan-duplicate-options)"の有効で表示
#### 9.2.4.14.3 Duplicate scan list refresh period
"[BLE Scan Duplicate Options](#92413-ble-scan-duplicate-options)"の有効で表示
#### 9.2.4.14.4 Special duplicate scan mechanism for BLE Mesh scan
"[BLE Scan Duplicate Options](#92413-ble-scan-duplicate-options)"の有効で表示
##### 9.2.4.14.4.1 Maximum number of Mesh adv packets in scan duplicate filter
"[Special duplicate scan mechanism for BLE Mesh scan](#924134-special-duplicate-scan-mechanism-for-ble-mesh-scan)"の有効で表示
### 9.2.4.15 BLE full scan feature supported
"[Bluetooth controller mode](#9241-bluetooth-controller-mode)"の"BR/EDR Only"以外有効で表示
### 9.2.4.16 Disable active scan backoff
### 9.2.4.17 BLE adv report flow control supported
"[Bluetooth controller mode](#9241-bluetooth-controller-mode)"の"BR/EDR Only"以外有効で表示
#### 9.2.4.17.1 BLE adv report flow control number
"[BLE adv report flow control supported](#92416-ble-adv-report-flow-control-supported)"の有効で表示
#### 9.2.4.17.2 BLE adv lost event threshold value
"[BLE adv report flow control supported](#92416-ble-adv-report-flow-control-supported)"の有効で表示
### 9.2.4.18 High level interrupt
## 9.2.5 Release Bluetooth text
## 9.2.6 Common Options
"[Bluetooth](#921-bluetooth)"を有効かつ"[Host](#9211-host)"を"Disable"以外で表示
### 9.2.6.1 Maximum number of Bluetooth alarms
## 9.2.7 Enable Bluetooth HCI debug mode
"[Bluetooth](#921-bluetooth)"を有効かつ"[Host](#9211-host)"を"Disable"以外で表示
### 9.2.7.1 size of the cache used for HCI data in Bluetooth HCI debug mode
### 9.2.7.2 size of the cache used for adv report in Bluetooth HCI debug mode
