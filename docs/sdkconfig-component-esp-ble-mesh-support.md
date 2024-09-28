# 9.3 ESP BLE Mesh Support
ESP BLE Mesh Supportの設定を記載。

- [9.3 ESP BLE Mesh Support](#93-esp-ble-mesh-support)
  - [9.3.1 Support sending 20ms non-connectable adv packets](#931-support-sending-20ms-non-connectable-adv-packets)
  - [9.3.2 Support using random adv interval for mesh packets](#932-support-using-random-adv-interval-for-mesh-packets)
  - [9.3.3 Support Duplicate Scan in BLE Mesh](#933-support-duplicate-scan-in-ble-mesh)
  - [9.3.4 Memory allocation strategy](#934-memory-allocation-strategy)
  - [9.3.5 Enable FreeRTOS static allocation](#935-enable-freertos-static-allocation)
    - [9.3.5.1 Memory allocation for FreeRTOS objects](#9351-memory-allocation-for-freertos-objects)
  - [9.3.6 Support de-initialize BLE Mesh stack](#936-support-de-initialize-ble-mesh-stack)
  - [9.3.7 BLE Mesh and BLE coexistance support](#937-ble-mesh-and-ble-coexistance-support)
    - [9.3.7.1 Support sending normal BLE advertising packets](#9371-support-sending-normal-ble-advertising-packets)
      - [9.3.7.1.1 Number of advertising buffers of BLE advertising packets](#93711-number-of-advertising-buffers-of-ble-advertising-packets)
    - [9.3.7.2 Support scanning normal BLE advertising packets](#9372-support-scanning-normal-ble-advertising-packets)
  - [9.3.8 Enable BLE Mesh Fast Provisioning](#938-enable-ble-mesh-fast-provisioning)
  - [9.3.9 Support for BLE Mesh Node](#939-support-for-ble-mesh-node)
  - [9.3.10 Support for BLE Mesh Provisioner](#9310-support-for-ble-mesh-provisioner)
    - [9.3.10.1 Maximum number of unprovisioned devices that can be added to device queue](#93101-maximum-number-of-unprovisioned-devices-that-can-be-added-to-device-queue)
    - [9.3.10.2 Maximum number of devices that can be provisioned by Provisioner](#93102-maximum-number-of-devices-that-can-be-provisioned-by-provisioner)
    - [9.3.10.3 Maximum number of PB-ADV running at the same time by Provisioner](#93103-maximum-number-of-pb-adv-running-at-the-same-time-by-provisioner)
    - [9.3.10.4 Maximum number of PB-GATT running at the same time by Provisioner](#93104-maximum-number-of-pb-gatt-running-at-the-same-time-by-provisioner)
    - [9.3.10.5 Maximum number of mesh subnets that can be created by Provisioner](#93105-maximum-number-of-mesh-subnets-that-can-be-created-by-provisioner)
    - [9.3.10.6 Maximum number of application keys that can be owned by Provisioner](#93106-maximum-number-of-application-keys-that-can-be-owned-by-provisioner)
    - [9.3.10.7 Support receiving Heartbeat messages](#93107-support-receiving-heartbeat-messages)
      - [9.3.10.7.1 Maximum number of filter entries for receiving Heartbeat messages](#931071-maximum-number-of-filter-entries-for-receiving-heartbeat-messages)
  - [9.3.11 BLE Mesh Provisioning support](#9311-ble-mesh-provisioning-support)
    - [9.3.11.1 BLE Mesh enhanced provisioning authentication](#93111-ble-mesh-enhanced-provisioning-authentication)
    - [9.3.11.2 Support Certificate-based provisioning](#93112-support-certificate-based-provisioning)
      - [9.3.11.2.1 Maximum size of the provisioning record fragment that Provisioner can receive](#931121-maximum-size-of-the-provisioning-record-fragment-that-provisioner-can-receive)
  - [9.3.12 Provisioning support using the advertising bearer](#9312-provisioning-support-using-the-advertising-bearer)
    - [9.3.12.1 Internal between two consecutive Unprovisioned Device Beacon](#93121-internal-between-two-consecutive-unprovisioned-device-beacon)
  - [9.3.13 Provisioning support using GATT](#9313-provisioning-support-using-gatt)
  - [9.3.14 BLE Mesh Proxy protocol support](#9314-ble-mesh-proxy-protocol-support)
  - [9.3.15 BLE Mesh GATT Proxy Server](#9315-ble-mesh-gatt-proxy-server)
    - [9.3.15.1 Node Identity advertising timeout](#93151-node-identity-advertising-timeout)
    - [9.3.15.2 Maximum number of filter entries per Proxy Client](#93152-maximum-number-of-filter-entries-per-proxy-client)
    - [9.3.15.3 Support Proxy Privacy](#93153-support-proxy-privacy)
    - [9.3.15.4 Support receiving Proxy Solicitation PDU](#93154-support-receiving-proxy-solicitation-pdu)
      - [9.3.15.4.1 Maximum capacity of solicitation replay protection list](#931541-maximum-capacity-of-solicitation-replay-protection-list)
  - [9.3.16 BLE Mesh GATT Proxy Client](#9316-ble-mesh-gatt-proxy-client)
    - [9.3.16.1 Support sending Proxy Solicitation PDU](#93161-support-sending-proxy-solicitation-pdu)
      - [9.3.16.1.1 Maximum number of SSRC that cant be used by Proxy Client](#931611-maximum-number-of-ssrc-that-cant-be-used-by-proxy-client)
  - [9.3.17 Store BLE MEsh configuration Persistently](#9317-store-ble-mesh-configuration-persistently)
    - [9.3.17.1 Delay (in seconds) before string anything persistently](#93171-delay-in-seconds-before-string-anything-persistently)
    - [9.3.17.2 How often the sequence number gets updated in storage](#93172-how-often-the-sequence-number-gets-updated-in-storage)
    - [9.3.17.3 Minimum frequency that the RPL gets updated in storage](#93173-minimum-frequency-that-the-rpl-gets-updated-in-storage)
    - [9.3.17.4 A specific option for settings backward compatibility](#93174-a-specific-option-for-settings-backward-compatibility)
    - [9.3.17.5 Use a specific NVS partition for BLE Mesh](#93175-use-a-specific-nvs-partition-for-ble-mesh)
      - [9.3.17.5.1 Name of the NVS partition for BLE Mesh](#931751-name-of-the-nvs-partition-for-ble-mesh)
    - [9.3.17.6 Support using multiple NVS namespaces by Provisioner](#93176-support-using-multiple-nvs-namespaces-by-provisioner)
      - [9.3.17.6.1 Maximum number of NVS namespaces](#931761-maximum-number-of-nvs-namespaces)
  - [9.3.18 Maximum number of mesh subnets per network](#9318-maximum-number-of-mesh-subnets-per-network)
  - [9.3.19 Maximum number of application keys per network](#9319-maximum-number-of-application-keys-per-network)
  - [9.3.20 Maximum number of application keys per model](#9320-maximum-number-of-application-keys-per-model)
  - [9.3.21 Maximum number of group address subscriptions per model](#9321-maximum-number-of-group-address-subscriptions-per-model)
  - [9.3.22 maximum number of Label UUIDs used for Virtual Addresses](#9322-maximum-number-of-label-uuids-used-for-virtual-addresses)
  - [9.3.23 Maximum capacity of the replay protection list](#9323-maximum-capacity-of-the-replay-protection-list)
    - [9.3.23.1 Not relay replayed message in a mesh network](#93231-not-relay-replayed-message-in-a-mesh-network)
  - [9.3.24 Not relay replayed messages in a mesh network](#9324-not-relay-replayed-messages-in-a-mesh-network)
  - [9.3.25 Network message cache size](#9325-network-message-cache-size)
  - [9.3.26 Number of advertising buffers](#9326-number-of-advertising-buffers)
  - [9.3.27 Divider for IV Update state refresh timer](#9327-divider-for-iv-update-state-refresh-timer)
  - [9.3.28 Recovery for IV index when the latest whole IV update procedure is missed](#9328-recovery-for-iv-index-when-the-latest-whole-iv-update-procedure-is-missed)
  - [9.3.29 Segmentation and reassembly enhancement](#9329-segmentation-and-reassembly-enhancement)
  - [9.3.30 Maximum number of simultaneous outgoing segmented message](#9330-maximum-number-of-simultaneous-outgoing-segmented-message)
  - [9.3.31 Maximum number of simultaneous incoming segmented message](#9331-maximum-number-of-simultaneous-incoming-segmented-message)
  - [9.3.32 Maximum incoming Upper Transport Access PDU length](#9332-maximum-incoming-upper-transport-access-pdu-length)
  - [9.3.33 Maximum number of segments in outgoing messages](#9333-maximum-number-of-segments-in-outgoing-messages)
  - [9.3.34 Relay support](#9334-relay-support)
    - [9.3.34.1 Use separate advertising buffers for relay packets](#93341-use-separate-advertising-buffers-for-relay-packets)
      - [9.3.34.1.1 Number of advertising buffers for relay packets](#933411-number-of-advertising-buffers-for-relay-packets)
  - [9.3.35 Support for Low Power features](#9335-support-for-low-power-features)
    - [9.3.35.1 Perform Friendship establishment using low power](#93351-perform-friendship-establishment-using-low-power)
    - [9.3.35.2 Automatically start looking for Friend nodes once provisioned](#93352-automatically-start-looking-for-friend-nodes-once-provisioned)
      - [9.3.35.2.1 Time from last received message before going to LPN mode](#933521-time-from-last-received-message-before-going-to-lpn-mode)
    - [9.3.35.3 Retry timeout for Friend requests](#93353-retry-timeout-for-friend-requests)
    - [9.3.35.4 RSSIFactor, used in Friend Offer Delay calculation](#93354-rssifactor-used-in-friend-offer-delay-calculation)
    - [9.3.35.5 ReceiveWindowFactor, used in Friend Offer Delay calculation](#93355-receivewindowfactor-used-in-friend-offer-delay-calculation)
    - [9.3.35.6 Minimum size of the acceptable friend queue(MinQueueSizeLog)](#93356-minimum-size-of-the-acceptable-friend-queueminqueuesizelog)
    - [9.3.35.7 Receive delay requested by the local node](#93357-receive-delay-requested-by-the-local-node)
    - [9.3.35.8 The value of the PoolTimeout timer](#93358-the-value-of-the-pooltimeout-timer)
    - [9.3.35.9 The starting value of the PoolTimeout timer](#93359-the-starting-value-of-the-pooltimeout-timer)
    - [9.3.35.10 Latency for enabling scanning](#933510-latency-for-enabling-scanning)
    - [9.3.35.11 Number of groups the LPN can subscribe to](#933511-number-of-groups-the-lpn-can-subscribe-to)
    - [9.3.35.12 Automatically subscribe all nodes address](#933512-automatically-subscribe-all-nodes-address)
  - [9.3.36 Support for Friend feature](#9336-support-for-friend-feature)
    - [9.3.36.1 Friend Receive Window](#93361-friend-receive-window)
    - [9.3.36.2 Minimum number of buffers supported per Friend Queue](#93362-minimum-number-of-buffers-supported-per-friend-queue)
    - [9.3.36.3 Friend Subscription List Size](#93363-friend-subscription-list-size)
    - [9.3.36.4 Number of supported LPN nodes](#93364-number-of-supported-lpn-nodes)
    - [9.3.36.5 Number of incomplete segment lists per LPN](#93365-number-of-incomplete-segment-lists-per-lpn)
  - [9.3.37 Disable BLE Mesh debug logs](#9337-disable-ble-mesh-debug-logs)
  - [9.3.38 BLE Mesh STACK DEBUG LOG LEVEL](#9338-ble-mesh-stack-debug-log-level)
    - [9.3.38.1 BLE\_MESH\_STACK](#93381-ble_mesh_stack)
  - [9.3.39 BLE Mesh NET BUG DEBUG LOG LEVEL](#9339-ble-mesh-net-bug-debug-log-level)
  - [9.3.39.1 BLE\_MESH\_NET\_BUF](#93391-ble_mesh_net_buf)
  - [9.3.40 Timeout for client message response](#9340-timeout-for-client-message-response)
  - [9.3.41 Support for BLE Mesh Foundation models](#9341-support-for-ble-mesh-foundation-models)
    - [9.3.41.1 Configuration Client model](#93411-configuration-client-model)
    - [9.3.41.2 Health Client model](#93412-health-client-model)
    - [9.3.41.3 Health Server model](#93413-health-server-model)
    - [9.3.41.4 Bridge Configuration Client model](#93414-bridge-configuration-client-model)
    - [9.3.41.5 Bridge Configuration Server model](#93415-bridge-configuration-server-model)
      - [9.3.41.5.1 Maximum number of Bridging Table entries](#934151-maximum-number-of-bridging-table-entries)
      - [9.3.41.5.2 Maximum capacity of bridge replay protection list](#934152-maximum-capacity-of-bridge-replay-protection-list)
    - [9.3.41.6 Mesh Private Beacon Client model](#93416-mesh-private-beacon-client-model)
    - [9.3.41.7 Mesh Private Beacon Server model](#93417-mesh-private-beacon-server-model)
    - [9.3.41.8 Solicitation PDU RPL Configuration Client model](#93418-solicitation-pdu-rpl-configuration-client-model)
    - [9.3.41.9 Solicitation PDU RPL Configuration Server model](#93419-solicitation-pdu-rpl-configuration-server-model)
    - [9.3.41.10 Opcodes Aggregator Client model](#934110-opcodes-aggregator-client-model)
    - [9.3.41.11 Opcodes Aggregator Server model](#934111-opcodes-aggregator-server-model)
    - [9.3.41.12 SAR Configuration Client model](#934112-sar-configuration-client-model)
    - [9.3.41.13 SAR Configuration Server model](#934113-sar-configuration-server-model)
    - [9.3.41.14 Support Composition Data Page 1](#934114-support-composition-data-page-1)
    - [9.3.41.15 Support Composition Data Page 128](#934115-support-composition-data-page-128)
    - [9.3.41.16 Support Models Metadata Page 0](#934116-support-models-metadata-page-0)
    - [9.3.41.16.1 Support Models Metadata Page 128](#9341161-support-models-metadata-page-128)
    - [9.3.41.17 Large Composition Data Client model](#934117-large-composition-data-client-model)
    - [9.3.41.18 Large Composition Data Server model](#934118-large-composition-data-server-model)
    - [9.3.41.19 Remote Provisioning Client model](#934119-remote-provisioning-client-model)
      - [9.3.41.19.1 Maximum number of PB-Remote running at the same time by Provisioner](#9341191-maximum-number-of-pb-remote-running-at-the-same-time-by-provisioner)
    - [9.3.41.20 Remote Provisioning Server model](#934120-remote-provisioning-server-model)
    - [9.3.41.20.1 Maximum number of device information can be scanned](#9341201-maximum-number-of-device-information-can-be-scanned)
    - [9.3.41.20.2 Support Active Scan for remote provisioning](#9341202-support-active-scan-for-remote-provisioning)
    - [9.3.41.20.3 Maximum number of extended scan procedures](#9341203-maximum-number-of-extended-scan-procedures)
    - [9.3.41.21 Directed Forwarding Configuration Client model](#934121-directed-forwarding-configuration-client-model)
    - [9.3.41.22 Directed Forwarding Configuration Server model](#934122-directed-forwarding-configuration-server-model)
    - [9.3.41.22.1 Maximum number of discovery table entries in a given subnet](#9341221-maximum-number-of-discovery-table-entries-in-a-given-subnet)
    - [9.3.41.22.2 Maximum number of forward table entries in a given subnet](#9341222-maximum-number-of-forward-table-entries-in-a-given-subnet)
    - [9.3.41.22.3 Maximum number of dependent nodes per path](#9341223-maximum-number-of-dependent-nodes-per-path)
    - [9.3.41.22.4 Enable Path Monitoring test mode](#9341224-enable-path-monitoring-test-mode)
    - [9.3.41.22.5 Enable Directed Proxy functionality](#9341225-enable-directed-proxy-functionality)
  - [9.3.42 Support for BLE Mesh Client/Server models](#9342-support-for-ble-mesh-clientserver-models)
    - [9.3.42.1 Generic OnOff Client model](#93421-generic-onoff-client-model)
    - [9.3.42.2 Generic Level Client model](#93422-generic-level-client-model)
    - [9.3.42.3 Generic Default Transition Time Client model](#93423-generic-default-transition-time-client-model)
    - [9.3.42.4 Generic Power OfOff Client model](#93424-generic-power-ofoff-client-model)
    - [9.3.42.5 Generic Power Level Client model](#93425-generic-power-level-client-model)
    - [9.3.42.6 Generic Battery Client model](#93426-generic-battery-client-model)
    - [9.3.42.7 Generic Location Client model](#93427-generic-location-client-model)
    - [9.3.42.8 Generic Property Client model](#93428-generic-property-client-model)
    - [9.3.42.9 Sensor Client model](#93429-sensor-client-model)
    - [9.3.42.10 Time Client model](#934210-time-client-model)
    - [9.3.42.11 Scene Client model](#934211-scene-client-model)
    - [9.3.42.12 Scheduler Client model](#934212-scheduler-client-model)
    - [9.3.42.13 Light Lightness Client model](#934213-light-lightness-client-model)
    - [9.3.42.14 Light CTL Client model](#934214-light-ctl-client-model)
    - [9.3.42.15 Light HSL Client model](#934215-light-hsl-client-model)
    - [9.3.42.16 Light XYL Client model](#934216-light-xyl-client-model)
    - [9.3.42.17 Light LC Client model](#934217-light-lc-client-model)
    - [9.3.42.18 Generic server models](#934218-generic-server-models)
    - [9.3.42.19 Sensor server models](#934219-sensor-server-models)
    - [9.3.42.20 Time and Scenes server models](#934220-time-and-scenes-server-models)
    - [9.3.42.21 Lighting server models](#934221-lighting-server-models)
    - [9.3.42.22 BLOB Transfer Client model](#934222-blob-transfer-client-model)
      - [9.3.42.22.1 Maximum number of simultaneous blob receivers](#9342221-maximum-number-of-simultaneous-blob-receivers)
    - [9.3.42.23 BLOB Transfer Server model](#934223-blob-transfer-server-model)
  - [9.3.43 Test the IV Update Procedure](#9343-test-the-iv-update-procedure)
  - [9.3.44 BLE Mesh specific test option](#9344-ble-mesh-specific-test-option)
    - [9.3.44.1 Perform BLE Mesh self-test](#93441-perform-ble-mesh-self-test)
    - [9.3.44.2 Enable BLE Mesh specific internal test](#93442-enable-ble-mesh-specific-internal-test)
    - [9.3.44.3 unprovisioned device enters mesh network automatically](#93443-unprovisioned-device-enters-mesh-network-automatically)
    - [9.3.44.4 Use white list to filter mesh advertising packets](#93444-use-white-list-to-filter-mesh-advertising-packets)
    - [9.3.44.5 Enable BLE Mesh shell](#93445-enable-ble-mesh-shell)
    - [9.3.44.6 Enable BLE Mesh debug logs](#93446-enable-ble-mesh-debug-logs)
      - [9.3.44.6.1 Network layer debug](#934461-network-layer-debug)
      - [9.3.44.6.2 Transport layer debug](#934462-transport-layer-debug)
      - [9.3.44.6.3 Beacon debug](#934463-beacon-debug)
      - [9.3.44.6.4 Crypto debug](#934464-crypto-debug)
      - [9.3.44.6.5 Provisioning debug](#934465-provisioning-debug)
      - [9.3.44.6.6 Access layer debug](#934466-access-layer-debug)
      - [9.3.44.6.7 Foundation model debug](#934467-foundation-model-debug)
      - [9.3.44.6.8 Advertising debug](#934468-advertising-debug)
      - [9.3.44.6.9 Low Power debug](#934469-low-power-debug)
      - [9.3.44.6.10 Friend debug](#9344610-friend-debug)
      - [9.3.44.6.11 Proxy debug](#9344611-proxy-debug)
  - [9.3.45 Make BLE experimental features visible](#9345-make-ble-experimental-features-visible)

## 9.3.1 Support sending 20ms non-connectable adv packets
## 9.3.2 Support using random adv interval for mesh packets
## 9.3.3 Support Duplicate Scan in BLE Mesh
## 9.3.4 Memory allocation strategy
- Internal DRAM
- External SPIRAM
- Default alloc mode
- Internal IRAM
## 9.3.5 Enable FreeRTOS static allocation
### 9.3.5.1 Memory allocation for FreeRTOS objects
- External SPIRAM
- Internal IRAM
## 9.3.6 Support de-initialize BLE Mesh stack
## 9.3.7 BLE Mesh and BLE coexistance support
### 9.3.7.1 Support sending normal BLE advertising packets
#### 9.3.7.1.1 Number of advertising buffers of BLE advertising packets
### 9.3.7.2 Support scanning normal BLE advertising packets
## 9.3.8 Enable BLE Mesh Fast Provisioning
## 9.3.9 Support for BLE Mesh Node
## 9.3.10 Support for BLE Mesh Provisioner
### 9.3.10.1 Maximum number of unprovisioned devices that can be added to device queue
### 9.3.10.2 Maximum number of devices that can be provisioned by Provisioner
### 9.3.10.3 Maximum number of PB-ADV running at the same time by Provisioner
### 9.3.10.4 Maximum number of PB-GATT running at the same time by Provisioner
### 9.3.10.5 Maximum number of mesh subnets that can be created by Provisioner
### 9.3.10.6 Maximum number of application keys that can be owned by Provisioner
### 9.3.10.7 Support receiving Heartbeat messages
#### 9.3.10.7.1 Maximum number of filter entries for receiving Heartbeat messages
## 9.3.11 BLE Mesh Provisioning support
### 9.3.11.1 BLE Mesh enhanced provisioning authentication
### 9.3.11.2 Support Certificate-based provisioning
#### 9.3.11.2.1 Maximum size of the provisioning record fragment that Provisioner can receive
## 9.3.12 Provisioning support using the advertising bearer
### 9.3.12.1 Internal between two consecutive Unprovisioned Device Beacon
## 9.3.13 Provisioning support using GATT
## 9.3.14 BLE Mesh Proxy protocol support
## 9.3.15 BLE Mesh GATT Proxy Server
### 9.3.15.1 Node Identity advertising timeout
### 9.3.15.2 Maximum number of filter entries per Proxy Client
### 9.3.15.3 Support Proxy Privacy
### 9.3.15.4 Support receiving Proxy Solicitation PDU
#### 9.3.15.4.1 Maximum capacity of solicitation replay protection list
## 9.3.16 BLE Mesh GATT Proxy Client
### 9.3.16.1 Support sending Proxy Solicitation PDU
#### 9.3.16.1.1 Maximum number of SSRC that cant be used by Proxy Client
## 9.3.17 Store BLE MEsh configuration Persistently
### 9.3.17.1 Delay (in seconds) before string anything persistently
### 9.3.17.2 How often the sequence number gets updated in storage
### 9.3.17.3 Minimum frequency that the RPL gets updated in storage
### 9.3.17.4 A specific option for settings backward compatibility
### 9.3.17.5 Use a specific NVS partition for BLE Mesh
#### 9.3.17.5.1 Name of the NVS partition for BLE Mesh
### 9.3.17.6 Support using multiple NVS namespaces by Provisioner
#### 9.3.17.6.1 Maximum number of NVS namespaces
## 9.3.18 Maximum number of mesh subnets per network
## 9.3.19 Maximum number of application keys per network
## 9.3.20 Maximum number of application keys per model
## 9.3.21 Maximum number of group address subscriptions per model
## 9.3.22 maximum number of Label UUIDs used for Virtual Addresses
## 9.3.23 Maximum capacity of the replay protection list
### 9.3.23.1 Not relay replayed message in a mesh network
## 9.3.24 Not relay replayed messages in a mesh network
## 9.3.25 Network message cache size
## 9.3.26 Number of advertising buffers
## 9.3.27 Divider for IV Update state refresh timer
## 9.3.28 Recovery for IV index when the latest whole IV update procedure is missed
## 9.3.29 Segmentation and reassembly enhancement
## 9.3.30 Maximum number of simultaneous outgoing segmented message
## 9.3.31 Maximum number of simultaneous incoming segmented message
## 9.3.32 Maximum incoming Upper Transport Access PDU length
## 9.3.33 Maximum number of segments in outgoing messages
## 9.3.34 Relay support
### 9.3.34.1 Use separate advertising buffers for relay packets
#### 9.3.34.1.1 Number of advertising buffers for relay packets
## 9.3.35 Support for Low Power features
### 9.3.35.1 Perform Friendship establishment using low power
### 9.3.35.2 Automatically start looking for Friend nodes once provisioned
#### 9.3.35.2.1 Time from last received message before going to LPN mode
### 9.3.35.3 Retry timeout for Friend requests
### 9.3.35.4 RSSIFactor, used in Friend Offer Delay calculation
### 9.3.35.5 ReceiveWindowFactor, used in Friend Offer Delay calculation
### 9.3.35.6 Minimum size of the acceptable friend queue(MinQueueSizeLog)
### 9.3.35.7 Receive delay requested by the local node
### 9.3.35.8 The value of the PoolTimeout timer
### 9.3.35.9 The starting value of the PoolTimeout timer
### 9.3.35.10 Latency for enabling scanning
### 9.3.35.11 Number of groups the LPN can subscribe to
### 9.3.35.12 Automatically subscribe all nodes address
## 9.3.36 Support for Friend feature
### 9.3.36.1 Friend Receive Window
### 9.3.36.2 Minimum number of buffers supported per Friend Queue
### 9.3.36.3 Friend Subscription List Size
### 9.3.36.4 Number of supported LPN nodes
### 9.3.36.5 Number of incomplete segment lists per LPN
## 9.3.37 Disable BLE Mesh debug logs
## 9.3.38 BLE Mesh STACK DEBUG LOG LEVEL
### 9.3.38.1 BLE_MESH_STACK
- NONE
- ERROR
- WARNING
- IFO
- DEBUG
- VERBOSE
## 9.3.39 BLE Mesh NET BUG DEBUG LOG LEVEL
## 9.3.39.1 BLE_MESH_NET_BUF
- NONE
- ERROR
- WARNING
- IFO
- DEBUG
- VERBOSE
## 9.3.40 Timeout for client message response
## 9.3.41 Support for BLE Mesh Foundation models
### 9.3.41.1 Configuration Client model
### 9.3.41.2 Health Client model
### 9.3.41.3 Health Server model
### 9.3.41.4 Bridge Configuration Client model
### 9.3.41.5 Bridge Configuration Server model
#### 9.3.41.5.1 Maximum number of Bridging Table entries
#### 9.3.41.5.2 Maximum capacity of bridge replay protection list
### 9.3.41.6 Mesh Private Beacon Client model
### 9.3.41.7 Mesh Private Beacon Server model
### 9.3.41.8 Solicitation PDU RPL Configuration Client model
### 9.3.41.9 Solicitation PDU RPL Configuration Server model
### 9.3.41.10 Opcodes Aggregator Client model
### 9.3.41.11 Opcodes Aggregator Server model
### 9.3.41.12 SAR Configuration Client model
### 9.3.41.13 SAR Configuration Server model
### 9.3.41.14 Support Composition Data Page 1
### 9.3.41.15 Support Composition Data Page 128
### 9.3.41.16 Support Models Metadata Page 0
### 9.3.41.16.1 Support Models Metadata Page 128
### 9.3.41.17 Large Composition Data Client model
### 9.3.41.18 Large Composition Data Server model
### 9.3.41.19 Remote Provisioning Client model
#### 9.3.41.19.1 Maximum number of PB-Remote running at the same time by Provisioner
### 9.3.41.20 Remote Provisioning Server model
### 9.3.41.20.1 Maximum number of device information can be scanned
### 9.3.41.20.2 Support Active Scan for remote provisioning
### 9.3.41.20.3 Maximum number of extended scan procedures
### 9.3.41.21 Directed Forwarding Configuration Client model
### 9.3.41.22 Directed Forwarding Configuration Server model
### 9.3.41.22.1 Maximum number of discovery table entries in a given subnet
### 9.3.41.22.2 Maximum number of forward table entries in a given subnet
### 9.3.41.22.3 Maximum number of dependent nodes per path
### 9.3.41.22.4 Enable Path Monitoring test mode
### 9.3.41.22.5 Enable Directed Proxy functionality
## 9.3.42 Support for BLE Mesh Client/Server models
### 9.3.42.1 Generic OnOff Client model
### 9.3.42.2 Generic Level Client model
### 9.3.42.3 Generic Default Transition Time Client model
### 9.3.42.4 Generic Power OfOff Client model
### 9.3.42.5 Generic Power Level Client model
### 9.3.42.6 Generic Battery Client model
### 9.3.42.7 Generic Location Client model
### 9.3.42.8 Generic Property Client model
### 9.3.42.9 Sensor Client model
### 9.3.42.10 Time Client model
### 9.3.42.11 Scene Client model
### 9.3.42.12 Scheduler Client model
### 9.3.42.13 Light Lightness Client model
### 9.3.42.14 Light CTL Client model
### 9.3.42.15 Light HSL Client model
### 9.3.42.16 Light XYL Client model
### 9.3.42.17 Light LC Client model
### 9.3.42.18 Generic server models
### 9.3.42.19 Sensor server models
### 9.3.42.20 Time and Scenes server models
### 9.3.42.21 Lighting server models
### 9.3.42.22 BLOB Transfer Client model
#### 9.3.42.22.1 Maximum number of simultaneous blob receivers
### 9.3.42.23 BLOB Transfer Server model
## 9.3.43 Test the IV Update Procedure
## 9.3.44 BLE Mesh specific test option
### 9.3.44.1 Perform BLE Mesh self-test
### 9.3.44.2 Enable BLE Mesh specific internal test
### 9.3.44.3 unprovisioned device enters mesh network automatically
### 9.3.44.4 Use white list to filter mesh advertising packets
### 9.3.44.5 Enable BLE Mesh shell
### 9.3.44.6 Enable BLE Mesh debug logs
#### 9.3.44.6.1 Network layer debug
#### 9.3.44.6.2 Transport layer debug
#### 9.3.44.6.3 Beacon debug
#### 9.3.44.6.4 Crypto debug
#### 9.3.44.6.5 Provisioning debug
#### 9.3.44.6.6 Access layer debug
#### 9.3.44.6.7 Foundation model debug
#### 9.3.44.6.8 Advertising debug
#### 9.3.44.6.9 Low Power debug
#### 9.3.44.6.10 Friend debug
#### 9.3.44.6.11 Proxy debug
## 9.3.45 Make BLE experimental features visible
