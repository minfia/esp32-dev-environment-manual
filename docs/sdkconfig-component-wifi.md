# 9.49 Wi-Fi
Wi-Fiの設定を記載。

- [9.49 Wi-Fi](#949-wi-fi)
  - [9.49.1 Host WiFi Enable](#9491-host-wifi-enable)
  - [9.49.2 Max number of WiFI static RX buffers](#9492-max-number-of-wifi-static-rx-buffers)
  - [9.49.3 Max number of WiFI dynamic RX buffers](#9493-max-number-of-wifi-dynamic-rx-buffers)
  - [9.49.4 Type of WiFi TX buffers](#9494-type-of-wifi-tx-buffers)
  - [9.49.5 Max number of WiFI static TX buffers](#9495-max-number-of-wifi-static-tx-buffers)
  - [9.49.6 Max number of WiFI cache TX buffers](#9496-max-number-of-wifi-cache-tx-buffers)
  - [9.49.7 Max number of WiFI dynamic TX buffers](#9497-max-number-of-wifi-dynamic-tx-buffers)
  - [9.49.8 Type of WiFi RX MGMT buffers](#9498-type-of-wifi-rx-mgmt-buffers)
  - [9.49.9 Max number of WiFi RX MGMT buffers](#9499-max-number-of-wifi-rx-mgmt-buffers)
  - [9.49.10 WiFi CSI(Channel State Information)](#94910-wifi-csichannel-state-information)
  - [9.49.11 WiFi AMPDU TX](#94911-wifi-ampdu-tx)
    - [9.49.11.1 WiFi AMPDU TX BA window size](#949111-wifi-ampdu-tx-ba-window-size)
  - [9.49.12 WiFi AMPDU RX](#94912-wifi-ampdu-rx)
    - [9.49.12.1 WiFi AMPDU RX BA window size](#949121-wifi-ampdu-rx-ba-window-size)
  - [9.49.13 WiFi AMSDU TX](#94913-wifi-amsdu-tx)
  - [9.49.14 WiFi NVS flash](#94914-wifi-nvs-flash)
  - [9.49.15 WiFi Task Core ID](#94915-wifi-task-core-id)
  - [9.49.16 Max length of WiFi SoftAP Beacon](#94916-max-length-of-wifi-softap-beacon)
  - [9.49.17 WiFi mgmt short buffer number](#94917-wifi-mgmt-short-buffer-number)
  - [9.49.18 WiFi IRAM speed optimization](#94918-wifi-iram-speed-optimization)
  - [9.49.19 WiFi EXTRA IRAM speed optimization](#94919-wifi-extra-iram-speed-optimization)
  - [9.49.20 WiFi RX IRAM speed optimization](#94920-wifi-rx-iram-speed-optimization)
  - [9.49.21 Enable WPA3-Personal](#94921-enable-wpa3-personal)
    - [9.49.21.1 Enable SAE-PK](#949211-enable-sae-pk)
    - [9.49.21.2 Enable WPA3 Personal(SAE) SoftAP](#949212-enable-wpa3-personalsae-softap)
  - [9.49.22 Enable OWE STA](#94922-enable-owe-sta)
  - [9.49.23 WiFi SLP IRAM speed optimization](#94923-wifi-slp-iram-speed-optimization)
  - [9.49.24 Minimum active time](#94924-minimum-active-time)
  - [9.49.25 Maximum keep alive time](#94925-maximum-keep-alive-time)
  - [9.49.26 Minimum wait broadcast data time](#94926-minimum-wait-broadcast-data-time)
  - [9.49.27 WiFi FTM](#94927-wifi-ftm)
    - [9.49.27.1 FTM Initiator support](#949271-ftm-initiator-support)
    - [9.49.27.2 FTM Responder support](#949272-ftm-responder-support)
  - [9.49.28 Power Management for station at disconnected](#94928-power-management-for-station-at-disconnected)
  - [9.49.29 WiFi GCMP Support(GCMP128 and GCMP256)](#94929-wifi-gcmp-supportgcmp128-and-gcmp256)
  - [9.49.30 WiFi GMAC Support(GMAC128 and GMAC256)](#94930-wifi-gmac-supportgmac128-and-gmac256)
  - [9.49.31 WiFi SoftAP Support](#94931-wifi-softap-support)
  - [9.49.32 WiFi modem automatically receives the beacon](#94932-wifi-modem-automatically-receives-the-beacon)
  - [9.49.33 WiFi sleep optimize when beacon lost](#94933-wifi-sleep-optimize-when-beacon-lost)
    - [9.49.33.1 Beacon loss timeout](#949331-beacon-loss-timeout)
    - [9.49.33.2 Maximum number of consecutive lost beacons allowed](#949332-maximum-number-of-consecutive-lost-beacons-allowed)
    - [9.49.33.3 Delta early time for RF PHY on](#949333-delta-early-time-for-rf-phy-on)
    - [9.49.33.4 Delta timeout time for RF PHY off](#949334-delta-timeout-time-for-rf-phy-off)
  - [9.49.34 Maximum espnow encrypt peers number](#94934-maximum-espnow-encrypt-peers-number)
  - [9.49.35 WiFi Aware](#94935-wifi-aware)
  - [9.49.36 Use MbedTLS crypto APIs](#94936-use-mbedtls-crypto-apis)
    - [9.49.36.1 Use MbedTLS TLS client for WiFi Enterprise connection](#949361-use-mbedtls-tls-client-for-wifi-enterprise-connection)
      - [9.49.36.1.1 Enable EAP-TLS v1.3 Support for WiFi Enterprise connection](#9493611-enable-eap-tls-v13-support-for-wifi-enterprise-connection)
  - [9.49.37 Enable WAPI PSK support](#94937-enable-wapi-psk-support)
  - [9.49.38 Enable NSA suite B support with 192 bit key](#94938-enable-nsa-suite-b-support-with-192-bit-key)
  - [9.49.39 Enable 802.11k, 802.11v APIs Support](#94939-enable-80211k-80211v-apis-support)
    - [9.49.39.1 Keep scan results in cache](#949391-keep-scan-results-in-cache)
  - [9.49.40 Enable Multi Band Operation Certification Support](#94940-enable-multi-band-operation-certification-support)
  - [9.49.41 Advanced support for Wi-Fi Roaming (Experimental)](#94941-advanced-support-for-wi-fi-roaming-experimental)
    - [9.49.41.1 Configure roaming App](#949411-configure-roaming-app)
      - [9.49.41.1.1 Roaming triggers](#9494111-roaming-triggers)
        - [9.49.41.1.1.1 Use Low RSSI to trigger roaming](#94941111-use-low-rssi-to-trigger-roaming)
          - [9.49.41.1.1.1.1 WiFi RSSI threshold to trigger roaming](#949411111-wifi-rssi-threshold-to-trigger-roaming)
          - [9.49.41.1.1.1.2 Offset by which to reset the RSSI Threshold after attempt to roam](#949411112-offset-by-which-to-reset-the-rssi-threshold-after-attempt-to-roam)
        - [9.49.41.1.1.2 Conduct periodic scans to check if a better AP is available](#94941112-conduct-periodic-scans-to-check-if-a-better-ap-is-available)
          - [9.49.41.1.1.2.1 Threshold at which to begin periodic scanning for better AP](#949411121-threshold-at-which-to-begin-periodic-scanning-for-better-ap)
          - [9.49.41.1.1.2.2 Time intervals (in seconds) at which station will initiate a scan](#949411122-time-intervals-in-seconds-at-which-station-will-initiate-a-scan)
          - [9.49.41.1.1.2.3 RSSI difference b/w current AP and candidate AP to initiate connection](#949411123-rssi-difference-bw-current-ap-and-candidate-ap-to-initiate-connection)
      - [9.49.41.1.2 Roaming Methods](#9494112-roaming-methods)
        - [9.49.41.1.2.1 Support Legacy roaming approach](#94941121-support-legacy-roaming-approach)
        - [9.49.41.1.2.2 Support Network Assisted roaming using 802.11kv](#94941122-support-network-assisted-roaming-using-80211kv)
          - [9.49.41.1.2.2.1 Retry count after which to switch to legacy roaming](#949411221-retry-count-after-which-to-switch-to-legacy-roaming)
      - [9.49.41.1.3 Scan Configuration](#9494113-scan-configuration)
      - [9.49.41.1.4 Default time to wait between subsequent roaming attempts](#9494114-default-time-to-wait-between-subsequent-roaming-attempts)
      - [9.49.41.1.5 Send periodic neighbor report request to AP for internal list updation](#9494115-send-periodic-neighbor-report-request-to-ap-for-internal-list-updation)
        - [9.49.41.1.5.1 Time interval (in seconds) between neighbor report requests to an AP](#94941151-time-interval-in-seconds-between-neighbor-report-requests-to-an-ap)
        - [9.49.41.1.5.2 Threshold for sending periodic neighbor report requests](#94941152-threshold-for-sending-periodic-neighbor-report-requests)
  - [9.49.42 Enable DPP support](#94942-enable-dpp-support)
  - [9.49.43 Enable 802.11R (Fast Transition) Support](#94943-enable-80211r-fast-transition-support)
  - [9.49.44 Add WPS Register support in SoftAP mode](#94944-add-wps-register-support-in-softap-mode)
  - [9.49.45 Enable Wi-Fi transmission statistics](#94945-enable-wi-fi-transmission-statistics)
  - [9.49.46 Enable Wi-Fi reception statistics](#94946-enable-wi-fi-reception-statistics)
    - [9.49.46.1 Enable w\\Wi-Fi DL MU-MIMO and DL OFDMA reception statistics](#949461-enable-wwi-fi-dl-mu-mimo-and-dl-ofdma-reception-statistics)
  - [9.49.47 WiFi TX HE TB QUEUE number for STA HE TB PPDU transmission](#94947-wifi-tx-he-tb-queue-number-for-sta-he-tb-ppdu-transmission)
  - [9.49.48 Enable Wi-Fi dump HE-SIGB which is contained in DL HE MU PPDUs](#94948-enable-wi-fi-dump-he-sigb-which-is-contained-in-dl-he-mu-ppdus)
  - [9.49.49 Enable Wi-Fi dump MU CFO](#94949-enable-wi-fi-dump-mu-cfo)
  - [9.49.50 Enable Wi-Fi dump NDPA frames](#94950-enable-wi-fi-dump-ndpa-frames)
  - [9.49.51 Enable Wi-Fi dump BFRP frame](#94951-enable-wi-fi-dump-bfrp-frame)
  - [9.49.52 WPS Configuration Options](#94952-wps-configuration-options)
    - [9.49.52.1 Strictly validate all WPS attributes](#949521-strictly-validate-all-wps-attributes)
    - [9.49.52.2 Get WPA2 passphrase in WPS config](#949522-get-wpa2-passphrase-in-wps-config)
  - [9.49.53 Print debug messages from WPA Supplicant](#94953-print-debug-messages-from-wpa-supplicant)
  - [9.49.54 Add DPP testing code](#94954-add-dpp-testing-code)
  - [9.49.55 Enable enterprize option](#94955-enable-enterprize-option)
    - [9.49.55.1 Free dynamic buffers during WiFi enterprise connection](#949551-free-dynamic-buffers-during-wifi-enterprise-connection)

## 9.49.1 Host WiFi Enable
## 9.49.2 Max number of WiFI static RX buffers
## 9.49.3 Max number of WiFI dynamic RX buffers
## 9.49.4 Type of WiFi TX buffers
- Static
- Dynamic
## 9.49.5 Max number of WiFI static TX buffers
## 9.49.6 Max number of WiFI cache TX buffers
## 9.49.7 Max number of WiFI dynamic TX buffers
## 9.49.8 Type of WiFi RX MGMT buffers
- Static
- Dynamic
## 9.49.9 Max number of WiFi RX MGMT buffers
## 9.49.10 WiFi CSI(Channel State Information)
## 9.49.11 WiFi AMPDU TX
### 9.49.11.1 WiFi AMPDU TX BA window size
## 9.49.12 WiFi AMPDU RX
### 9.49.12.1 WiFi AMPDU RX BA window size
## 9.49.13 WiFi AMSDU TX
## 9.49.14 WiFi NVS flash
## 9.49.15 WiFi Task Core ID
- Core 0
- Core 1
## 9.49.16 Max length of WiFi SoftAP Beacon
## 9.49.17 WiFi mgmt short buffer number
## 9.49.18 WiFi IRAM speed optimization
## 9.49.19 WiFi EXTRA IRAM speed optimization
## 9.49.20 WiFi RX IRAM speed optimization
## 9.49.21 Enable WPA3-Personal
### 9.49.21.1 Enable SAE-PK
### 9.49.21.2 Enable WPA3 Personal(SAE) SoftAP
## 9.49.22 Enable OWE STA
## 9.49.23 WiFi SLP IRAM speed optimization
## 9.49.24 Minimum active time
## 9.49.25 Maximum keep alive time
## 9.49.26 Minimum wait broadcast data time
## 9.49.27 WiFi FTM
### 9.49.27.1 FTM Initiator support
### 9.49.27.2 FTM Responder support
## 9.49.28 Power Management for station at disconnected
## 9.49.29 WiFi GCMP Support(GCMP128 and GCMP256)
## 9.49.30 WiFi GMAC Support(GMAC128 and GMAC256)
## 9.49.31 WiFi SoftAP Support
## 9.49.32 WiFi modem automatically receives the beacon
## 9.49.33 WiFi sleep optimize when beacon lost
### 9.49.33.1 Beacon loss timeout
### 9.49.33.2 Maximum number of consecutive lost beacons allowed
### 9.49.33.3 Delta early time for RF PHY on
### 9.49.33.4 Delta timeout time for RF PHY off
## 9.49.34 Maximum espnow encrypt peers number
## 9.49.35 WiFi Aware
## 9.49.36 Use MbedTLS crypto APIs
### 9.49.36.1 Use MbedTLS TLS client for WiFi Enterprise connection
#### 9.49.36.1.1 Enable EAP-TLS v1.3 Support for WiFi Enterprise connection
## 9.49.37 Enable WAPI PSK support
## 9.49.38 Enable NSA suite B support with 192 bit key
## 9.49.39 Enable 802.11k, 802.11v APIs Support
### 9.49.39.1 Keep scan results in cache
## 9.49.40 Enable Multi Band Operation Certification Support
## 9.49.41 Advanced support for Wi-Fi Roaming (Experimental)
### 9.49.41.1 Configure roaming App
#### 9.49.41.1.1 Roaming triggers
##### 9.49.41.1.1.1 Use Low RSSI to trigger roaming
###### 9.49.41.1.1.1.1 WiFi RSSI threshold to trigger roaming
###### 9.49.41.1.1.1.2 Offset by which to reset the RSSI Threshold after attempt to roam
##### 9.49.41.1.1.2 Conduct periodic scans to check if a better AP is available
###### 9.49.41.1.1.2.1 Threshold at which to begin periodic scanning for better AP
###### 9.49.41.1.1.2.2 Time intervals (in seconds) at which station will initiate a scan
###### 9.49.41.1.1.2.3 RSSI difference b/w current AP and candidate AP to initiate connection
#### 9.49.41.1.2 Roaming Methods
##### 9.49.41.1.2.1 Support Legacy roaming approach
##### 9.49.41.1.2.2 Support Network Assisted roaming using 802.11kv
###### 9.49.41.1.2.2.1 Retry count after which to switch to legacy roaming
#### 9.49.41.1.3 Scan Configuration
- Minimum duration (in milliseconds) of station's per channel active scan
- Maximum duration (in milliseconds) of station's per channel active scan time
- Home channel dwell time scanning between consecutive channels
- Preferred channel list for scanning
- Scan results expiry window(in seconds)
- Max Candidates in the network
#### 9.49.41.1.4 Default time to wait between subsequent roaming attempts
#### 9.49.41.1.5 Send periodic neighbor report request to AP for internal list updation
##### 9.49.41.1.5.1 Time interval (in seconds) between neighbor report requests to an AP
##### 9.49.41.1.5.2 Threshold for sending periodic neighbor report requests
## 9.49.42 Enable DPP support
## 9.49.43 Enable 802.11R (Fast Transition) Support
## 9.49.44 Add WPS Register support in SoftAP mode
## 9.49.45 Enable Wi-Fi transmission statistics
## 9.49.46 Enable Wi-Fi reception statistics
### 9.49.46.1 Enable w\Wi-Fi DL MU-MIMO and DL OFDMA reception statistics
## 9.49.47 WiFi TX HE TB QUEUE number for STA HE TB PPDU transmission
## 9.49.48 Enable Wi-Fi dump HE-SIGB which is contained in DL HE MU PPDUs
## 9.49.49 Enable Wi-Fi dump MU CFO
## 9.49.50 Enable Wi-Fi dump NDPA frames
## 9.49.51 Enable Wi-Fi dump BFRP frame
## 9.49.52 WPS Configuration Options
### 9.49.52.1 Strictly validate all WPS attributes
### 9.49.52.2 Get WPA2 passphrase in WPS config
## 9.49.53 Print debug messages from WPA Supplicant
## 9.49.54 Add DPP testing code
## 9.49.55 Enable enterprize option
### 9.49.55.1 Free dynamic buffers during WiFi enterprise connection
