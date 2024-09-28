# 9.57 LWIP
LWIPの設定を記載。

- [9.57 LWIP](#957-lwip)
  - [9.57.1 Enable LwIP stack](#9571-enable-lwip-stack)
  - [9.57.2 Local netif hostname](#9572-local-netif-hostname)
  - [9.57.3 Enable usage of standard POSIX APIs LWIP](#9573-enable-usage-of-standard-posix-apis-lwip)
  - [9.57.4 Enable tcpip core locking](#9574-enable-tcpip-core-locking)
    - [9.57.4.1 Enable tcpip core locking input](#95741-enable-tcpip-core-locking-input)
  - [9.57.5 Checks that lwip aPI runs in expected context](#9575-checks-that-lwip-api-runs-in-expected-context)
  - [9.57.6 Enable mDNS queries in resolving host name](#9576-enable-mdns-queries-in-resolving-host-name)
  - [9.57.7 Enable copy between Layer2 and Layer3 packets](#9577-enable-copy-between-layer2-and-layer3-packets)
  - [9.57.8 Enable LWIP IRAM optimization](#9578-enable-lwip-iram-optimization)
  - [9.57.9 Enable LWIP IRAM optimization for TCP part](#9579-enable-lwip-iram-optimization-for-tcp-part)
  - [9.57.10 Enable LWIP Timers on demand](#95710-enable-lwip-timers-on-demand)
  - [9.57.11 LWIP NDP6 Enable/Disable](#95711-lwip-ndp6-enabledisable)
    - [9.57.11.1 LWIP Force Router Forwarding Enable/Disable](#957111-lwip-force-router-forwarding-enabledisable)
  - [9.57.12 Max number of open sockets](#95712-max-number-of-open-sockets)
  - [9.57.13 Support LWIP socket select() only (DEPRECATED)](#95713-support-lwip-socket-select-only-deprecated)
  - [9.57.14 Enable SO\_LINGER processing](#95714-enable-so_linger-processing)
  - [9.57.15 Enable SO\_REUSEADDR option](#95715-enable-so_reuseaddr-option)
    - [9.57.15.1 SO\_REUSEADDR copies broadcast/multicast to all matches](#957151-so_reuseaddr-copies-broadcastmulticast-to-all-matches)
  - [9.57.16 Enable SO\_RCVBUF option](#95716-enable-so_rcvbuf-option)
  - [9.57.17 Enable IP\_PKTINFO option](#95717-enable-ip_pktinfo-option)
  - [9.57.18 The value for Time-To-Live used by transport layers](#95718-the-value-for-time-to-live-used-by-transport-layers)
  - [9.57.19 Enable fragment outgoing IP4 packets](#95719-enable-fragment-outgoing-ip4-packets)
  - [9.57.20 Enable fragment outgoing IP6 packets](#95720-enable-fragment-outgoing-ip6-packets)
  - [9.57.21 Enable reassembly incoming fragmented IP4 packets](#95721-enable-reassembly-incoming-fragmented-ip4-packets)
  - [9.57.22 Enable reassembly incoming fragmented IP6 packets](#95722-enable-reassembly-incoming-fragmented-ip6-packets)
  - [9.57.23 The maximum amount of pbufs waiting to be reassembly](#95723-the-maximum-amount-of-pbufs-waiting-to-be-reassembly)
  - [9.57.24 Enable IP forwarding](#95724-enable-ip-forwarding)
    - [9.57.24.1 Enable NAT](#957241-enable-nat)
      - [9.57.24.1.1 Enable NAT Port Mapping](#9572411-enable-nat-port-mapping)
  - [9.57.25 Enable LWIP statistics](#95725-enable-lwip-statistics)
  - [9.57.26 Send gratuitous ARP periodically](#95726-send-gratuitous-arp-periodically)
    - [9.57.26.1 GARP timer interval(seconds)](#957261-garp-timer-intervalseconds)
  - [9.57.27 Send mldv6 report periodically](#95727-send-mldv6-report-periodically)
    - [9.57.27.1 mldv6 report timer interval(seconds)](#957271-mldv6-report-timer-intervalseconds)
  - [9.57.28 TCPIP task receive mail box size](#95728-tcpip-task-receive-mail-box-size)
  - [9.57.29 DHCP: Perform ARP check on any offered address](#95729-dhcp-perform-arp-check-on-any-offered-address)
  - [9.57.30 DHCP: Disable Use of HW address as client identification](#95730-dhcp-disable-use-of-hw-address-as-client-identification)
  - [9.57.31 DHCP: Disable Use of vendor class identification](#95731-dhcp-disable-use-of-vendor-class-identification)
  - [9.57.32 DHCP: Restore last UP obtained from DHCP](#95732-dhcp-restore-last-up-obtained-from-dhcp)
  - [9.57.33 DHCP total option length](#95733-dhcp-total-option-length)
  - [9.57.34 Number of clients store data in netif](#95734-number-of-clients-store-data-in-netif)
  - [9.57.35 DHCP coarse timer interval](#95735-dhcp-coarse-timer-interval)
  - [9.57.36 DHCP server](#95736-dhcp-server)
    - [9.57.36.1 DHCPS: Enable IPv4 Dynamic Host Configuration Protocol Server (DHCPS)](#957361-dhcps-enable-ipv4-dynamic-host-configuration-protocol-server-dhcps)
      - [9.57.36.1.1 Multiplier for lease time, in seconds](#9573611-multiplier-for-lease-time-in-seconds)
      - [9.57.36.1.2 Maximum number of stations](#9573612-maximum-number-of-stations)
      - [9.57.36.1.3 Enable ARP static entries](#9573613-enable-arp-static-entries)
  - [9.57.37 Enable IPV4 Link-Local Addressing](#95737-enable-ipv4-link-local-addressing)
    - [9.57.37.1 DHCP Probes before self-assigning IPv4 LL address](#957371-dhcp-probes-before-self-assigning-ipv4-ll-address)
    - [9.57.37.2 Max IP conflicts before rate limiting](#957372-max-ip-conflicts-before-rate-limiting)
    - [9.57.37.3 Rate limited interval (seconds)](#957373-rate-limited-interval-seconds)
  - [9.57.38 Enable IPv4](#95738-enable-ipv4)
  - [9.57.39 Enable IPv6](#95739-enable-ipv6)
    - [9.57.39.1 Enable IPV6 stateless address autoconfiguration (SLAAC)](#957391-enable-ipv6-stateless-address-autoconfiguration-slaac)
    - [9.57.39.2 Number of IPv6 addresses on each network interface](#957392-number-of-ipv6-addresses-on-each-network-interface)
    - [9.57.39.3 Enable IPv6 forwarding between interfaces](#957393-enable-ipv6-forwarding-between-interfaces)
  - [9.57.40 Use IPv6 Router Advertisement Recursive DNS ServerOption](#95740-use-ipv6-router-advertisement-recursive-dns-serveroption)
  - [9.57.41 Enable DHCPv6 stateless address autoconfiguration](#95741-enable-dhcpv6-stateless-address-autoconfiguration)
  - [9.57.42 Enable status callback for network interfaces](#95742-enable-status-callback-for-network-interfaces)
  - [9.57.43 Support per-interface loopback](#95743-support-per-interface-loopback)
    - [9.57.43.1 Max queued loopback packets per interface](#957431-max-queued-loopback-packets-per-interface)
  - [9.57.44 TCP](#95744-tcp)
    - [9.57.44.1 Maximum active TCP Connections](#957441-maximum-active-tcp-connections)
    - [9.57.44.2 Maximum listening TCP Connections](#957442-maximum-listening-tcp-connections)
    - [9.57.44.3 TCP high speed retransmissions](#957443-tcp-high-speed-retransmissions)
    - [9.57.44.4 Maximum number of retransmissions of data segments](#957444-maximum-number-of-retransmissions-of-data-segments)
    - [9.57.44.5 Maximum number of retransmissions of SYN segments](#957445-maximum-number-of-retransmissions-of-syn-segments)
    - [9.57.44.6 Maximum Segment Size (MSS)](#957446-maximum-segment-size-mss)
    - [9.57.44.7 TCP timer interval(ms)](#957447-tcp-timer-intervalms)
    - [9.57.44.8 Maximum segment lifetime (MSL)](#957448-maximum-segment-lifetime-msl)
    - [9.57.44.9 Maximum FIN segment lifetime](#957449-maximum-fin-segment-lifetime)
    - [9.57.44.10 Default send buffer size](#9574410-default-send-buffer-size)
    - [9.57.44.11 Default receive window size](#9574411-default-receive-window-size)
    - [9.57.44.12 Queue incoming out-of-order segments](#9574412-queue-incoming-out-of-order-segments)
      - [9.57.44.12.1 Timeout for each pbuf queued in TCP OOSEQ, in RTOs.](#95744121-timeout-for-each-pbuf-queued-in-tcp-ooseq-in-rtos)
      - [9.57.44.12.2 The maximum number of pbufs queued on OOSEQ per pcb](#95744122-the-maximum-number-of-pbufs-queued-on-ooseq-per-pcb)
      - [9.57.44.12.3 Support sending selective acknowledgements](#95744123-support-sending-selective-acknowledgements)
    - [9.57.44.13 Pre-allocate transmit PBUF size (MSS)](#9574413-pre-allocate-transmit-pbuf-size-mss)
    - [9.57.44.14 Support TCP window scale](#9574414-support-tcp-window-scale)
      - [9.57.44.14.1 Set TCP receiving window scaling factor](#95744141-set-tcp-receiving-window-scaling-factor)
    - [9.57.44.15 Default TCP rto time](#9574415-default-tcp-rto-time)
  - [9.57.45 UDP](#95745-udp)
    - [9.57.45.1 Maximum active UDP control blocks](#957451-maximum-active-udp-control-blocks)
    - [9.57.45.2 Default UDP receive mail box size](#957452-default-udp-receive-mail-box-size)
  - [9.57.46 Checksums](#95746-checksums)
  - [9.57.47 TCP/IP Task Stack Size](#95747-tcpip-task-stack-size)
  - [9.57.48 TCP/IP task affinity](#95748-tcpip-task-affinity)
  - [9.57.49 Enable PPP support](#95749-enable-ppp-support)
    - [9.57.49.1 Enable IPV6 support for PPP connections (IPV6CP)](#957491-enable-ipv6-support-for-ppp-connections-ipv6cp)
  - [9.57.50 Max number of IPv6 packets to queue during MAC resolution](#95750-max-number-of-ipv6-packets-to-queue-during-mac-resolution)
  - [9.57.51 Max number of entries in IPv6 neighbor cache](#95751-max-number-of-entries-in-ipv6-neighbor-cache)
  - [9.57.52 Enable Notify Phase Callback](#95752-enable-notify-phase-callback)
  - [9.57.53 Enable PAP support](#95753-enable-pap-support)
  - [9.57.54 Enable CHAP support](#95754-enable-chap-support)
  - [9.57.55 Enable MSCHAP support](#95755-enable-mschap-support)
  - [9.57.56 Enable MPPE support](#95756-enable-mppe-support)
  - [9.57.57 Enable PPP server support](#95757-enable-ppp-server-support)
  - [9.57.58 Enable VJ IP Header compression](#95758-enable-vj-ip-header-compression)
  - [9.57.59 Enable LCP ECHO](#95759-enable-lcp-echo)
    - [9.57.59.1 Echo interval (s)](#957591-echo-interval-s)
    - [9.57.59.2 Maximum echo failures](#957592-maximum-echo-failures)
  - [9.57.60 Enable PPP debug log output](#95760-enable-ppp-debug-log-output)
  - [9.57.61 Enable SLIP support](#95761-enable-slip-support)
    - [9.57.61.1 Enable SLIP debug log output](#957611-enable-slip-debug-log-output)
  - [9.57.62 ICMP](#95762-icmp)
    - [9.57.62.1 ICMP: Enable ICMP](#957621-icmp-enable-icmp)
    - [9.57.62.2 Respond to multicast pings](#957622-respond-to-multicast-pings)
    - [9.57.62.3 Respond to broadcast pings](#957623-respond-to-broadcast-pings)
  - [9.57.63 LWIP RAW API](#95763-lwip-raw-api)
    - [9.57.63.1 Maximum LWIP TAR PCBs](#957631-maximum-lwip-tar-pcbs)
  - [9.57.64 SNTP](#95764-sntp)
    - [9.57.64.1 Maximum number of NTP servers](#957641-maximum-number-of-ntp-servers)
    - [9.57.64.2 Request NTP servers from DHCP](#957642-request-ntp-servers-from-dhcp)
      - [9.57.64.2.1 Maximum number of NTP servers acquired via DHCP](#9576421-maximum-number-of-ntp-servers-acquired-via-dhcp)
    - [9.57.64.3 Request interval to update time (ms)](#957643-request-interval-to-update-time-ms)
    - [9.57.64.4 Enable SNTP startup delay](#957644-enable-sntp-startup-delay)
      - [9.57.64.4.1 Maximum startup delay (ms)](#9576441-maximum-startup-delay-ms)
  - [9.57.65 DNS](#95765-dns)
    - [9.57.65.1 Maximum number of DNS servers](#957651-maximum-number-of-dns-servers)
    - [9.57.65.2 Enable DSN fallback server support](#957652-enable-dsn-fallback-server-support)
      - [9.57.65.2.1 DSN fallback server address](#9576521-dsn-fallback-server-address)
  - [9.57.66 Maximum number of bridge ports](#95766-maximum-number-of-bridge-ports)
  - [9.57.67 Enable LWIP ASSERT checks](#95767-enable-lwip-assert-checks)
  - [9.57.68 Hooks](#95768-hooks)
    - [9.57.68.1 TCP ISN Hook](#957681-tcp-isn-hook)
    - [9.57.68.2 IPv6 route Hook](#957682-ipv6-route-hook)
    - [9.57.68.3 IPv6 get gateway Hook](#957683-ipv6-get-gateway-hook)
    - [9.57.68.4 IPv6 source address selection Hook](#957684-ipv6-source-address-selection-hook)
    - [9.57.68.5 Netconn external resolve Hook](#957685-netconn-external-resolve-hook)
    - [9.57.68.6 IPv6 packet input](#957686-ipv6-packet-input)
  - [9.57.69 Enable LWIP Debug](#95769-enable-lwip-debug)
    - [9.57.69.1 Route LWIP debugs through ESP\_LOG interface](#957691-route-lwip-debugs-through-esp_log-interface)
    - [9.57.69.2 Enable netif debug messages](#957692-enable-netif-debug-messages)
    - [9.57.69.3 Enable pbuf debug messages](#957693-enable-pbuf-debug-messages)
    - [9.57.69.4 Enable etharp debug messages](#957694-enable-etharp-debug-messages)
    - [9.57.69.5 Enable api lib debug messages](#957695-enable-api-lib-debug-messages)
    - [9.57.69.6 Enable socket debug messages](#957696-enable-socket-debug-messages)
    - [9.57.69.7 Enable IP debug messages](#957697-enable-ip-debug-messages)
    - [9.57.69.8 Enable ICMP debug messages](#957698-enable-icmp-debug-messages)
    - [9.57.69.9 Enable DHCP state tracking](#957699-enable-dhcp-state-tracking)
    - [9.57.69.10 Enable DHCP debug messages](#9576910-enable-dhcp-debug-messages)
    - [9.57.69.11 Enable IP6 debug messages](#9576911-enable-ip6-debug-messages)
    - [9.57.69.12 Enable ICMP6 debug messages](#9576912-enable-icmp6-debug-messages)
    - [9.57.69.13 Enable TCP debug messages](#9576913-enable-tcp-debug-messages)
    - [9.57.69.14 Enable UDP debug messages](#9576914-enable-udp-debug-messages)
    - [9.57.69.15 Enable SNTP debug messages](#9576915-enable-sntp-debug-messages)
    - [9.57.69.16 Enable DSN debug messages](#9576916-enable-dsn-debug-messages)
    - [9.57.69.17 Enable NAPT debug messages](#9576917-enable-napt-debug-messages)
    - [9.57.69.18 Enable bridge generic debug messages](#9576918-enable-bridge-generic-debug-messages)
    - [9.57.69.19 Enable bridge FDB debug messages](#9576919-enable-bridge-fdb-debug-messages)
    - [9.57.69.20 Enable bridge forwarding debug messages](#9576920-enable-bridge-forwarding-debug-messages)

## 9.57.1 Enable LwIP stack
## 9.57.2 Local netif hostname
## 9.57.3 Enable usage of standard POSIX APIs LWIP
## 9.57.4 Enable tcpip core locking
### 9.57.4.1 Enable tcpip core locking input
## 9.57.5 Checks that lwip aPI runs in expected context
## 9.57.6 Enable mDNS queries in resolving host name
## 9.57.7 Enable copy between Layer2 and Layer3 packets
## 9.57.8 Enable LWIP IRAM optimization
## 9.57.9 Enable LWIP IRAM optimization for TCP part
## 9.57.10 Enable LWIP Timers on demand
## 9.57.11 LWIP NDP6 Enable/Disable
### 9.57.11.1 LWIP Force Router Forwarding Enable/Disable
## 9.57.12 Max number of open sockets
## 9.57.13 Support LWIP socket select() only (DEPRECATED)
## 9.57.14 Enable SO_LINGER processing
## 9.57.15 Enable SO_REUSEADDR option
### 9.57.15.1 SO_REUSEADDR copies broadcast/multicast to all matches
## 9.57.16 Enable SO_RCVBUF option
## 9.57.17 Enable IP_PKTINFO option
## 9.57.18 The value for Time-To-Live used by transport layers
## 9.57.19 Enable fragment outgoing IP4 packets
## 9.57.20 Enable fragment outgoing IP6 packets
## 9.57.21 Enable reassembly incoming fragmented IP4 packets
## 9.57.22 Enable reassembly incoming fragmented IP6 packets
## 9.57.23 The maximum amount of pbufs waiting to be reassembly
## 9.57.24 Enable IP forwarding
### 9.57.24.1 Enable NAT
#### 9.57.24.1.1 Enable NAT Port Mapping
## 9.57.25 Enable LWIP statistics
## 9.57.26 Send gratuitous ARP periodically
### 9.57.26.1 GARP timer interval(seconds)
## 9.57.27 Send mldv6 report periodically
### 9.57.27.1 mldv6 report timer interval(seconds)
## 9.57.28 TCPIP task receive mail box size
## 9.57.29 DHCP: Perform ARP check on any offered address
## 9.57.30 DHCP: Disable Use of HW address as client identification
## 9.57.31 DHCP: Disable Use of vendor class identification
## 9.57.32 DHCP: Restore last UP obtained from DHCP
## 9.57.33 DHCP total option length
## 9.57.34 Number of clients store data in netif
## 9.57.35 DHCP coarse timer interval
## 9.57.36 DHCP server
### 9.57.36.1 DHCPS: Enable IPv4 Dynamic Host Configuration Protocol Server (DHCPS)
#### 9.57.36.1.1 Multiplier for lease time, in seconds
#### 9.57.36.1.2 Maximum number of stations
#### 9.57.36.1.3 Enable ARP static entries
## 9.57.37 Enable IPV4 Link-Local Addressing
### 9.57.37.1 DHCP Probes before self-assigning IPv4 LL address
### 9.57.37.2 Max IP conflicts before rate limiting
### 9.57.37.3 Rate limited interval (seconds)
## 9.57.38 Enable IPv4
## 9.57.39 Enable IPv6
### 9.57.39.1 Enable IPV6 stateless address autoconfiguration (SLAAC)
### 9.57.39.2 Number of IPv6 addresses on each network interface
### 9.57.39.3 Enable IPv6 forwarding between interfaces
## 9.57.40 Use IPv6 Router Advertisement Recursive DNS ServerOption
## 9.57.41 Enable DHCPv6 stateless address autoconfiguration
## 9.57.42 Enable status callback for network interfaces
## 9.57.43 Support per-interface loopback
### 9.57.43.1 Max queued loopback packets per interface
## 9.57.44 TCP
### 9.57.44.1 Maximum active TCP Connections
### 9.57.44.2 Maximum listening TCP Connections
### 9.57.44.3 TCP high speed retransmissions
### 9.57.44.4 Maximum number of retransmissions of data segments
### 9.57.44.5 Maximum number of retransmissions of SYN segments
### 9.57.44.6 Maximum Segment Size (MSS)
### 9.57.44.7 TCP timer interval(ms)
### 9.57.44.8 Maximum segment lifetime (MSL)
### 9.57.44.9 Maximum FIN segment lifetime
### 9.57.44.10 Default send buffer size
### 9.57.44.11 Default receive window size
### 9.57.44.12 Queue incoming out-of-order segments
#### 9.57.44.12.1 Timeout for each pbuf queued in TCP OOSEQ, in RTOs.
#### 9.57.44.12.2 The maximum number of pbufs queued on OOSEQ per pcb
#### 9.57.44.12.3 Support sending selective acknowledgements
### 9.57.44.13 Pre-allocate transmit PBUF size (MSS)
- MSS
- 25% MSS
- Disabled
### 9.57.44.14 Support TCP window scale
#### 9.57.44.14.1 Set TCP receiving window scaling factor
### 9.57.44.15 Default TCP rto time
## 9.57.45 UDP
### 9.57.45.1 Maximum active UDP control blocks
### 9.57.45.2 Default UDP receive mail box size
## 9.57.46 Checksums
- Enable LWIP IP checksums
- Enable LWIP UDP checksums
- Enable LWIP ICMP checksums
## 9.57.47 TCP/IP Task Stack Size
## 9.57.48 TCP/IP task affinity
- No affinity
- CPU0
- CPU1
## 9.57.49 Enable PPP support
### 9.57.49.1 Enable IPV6 support for PPP connections (IPV6CP)
## 9.57.50 Max number of IPv6 packets to queue during MAC resolution
## 9.57.51 Max number of entries in IPv6 neighbor cache
## 9.57.52 Enable Notify Phase Callback
## 9.57.53 Enable PAP support
## 9.57.54 Enable CHAP support
## 9.57.55 Enable MSCHAP support
## 9.57.56 Enable MPPE support
## 9.57.57 Enable PPP server support
## 9.57.58 Enable VJ IP Header compression
## 9.57.59 Enable LCP ECHO
### 9.57.59.1 Echo interval (s)
### 9.57.59.2 Maximum echo failures
## 9.57.60 Enable PPP debug log output
## 9.57.61 Enable SLIP support
### 9.57.61.1 Enable SLIP debug log output
## 9.57.62 ICMP
### 9.57.62.1 ICMP: Enable ICMP
### 9.57.62.2 Respond to multicast pings
### 9.57.62.3 Respond to broadcast pings
## 9.57.63 LWIP RAW API
### 9.57.63.1 Maximum LWIP TAR PCBs
## 9.57.64 SNTP
### 9.57.64.1 Maximum number of NTP servers
### 9.57.64.2 Request NTP servers from DHCP
#### 9.57.64.2.1 Maximum number of NTP servers acquired via DHCP
### 9.57.64.3 Request interval to update time (ms)
### 9.57.64.4 Enable SNTP startup delay
#### 9.57.64.4.1 Maximum startup delay (ms)
## 9.57.65 DNS
### 9.57.65.1 Maximum number of DNS servers
### 9.57.65.2 Enable DSN fallback server support
#### 9.57.65.2.1 DSN fallback server address
## 9.57.66 Maximum number of bridge ports
## 9.57.67 Enable LWIP ASSERT checks
## 9.57.68 Hooks
### 9.57.68.1 TCP ISN Hook
- No hook declared
- Default implementation
- Custom implementation
### 9.57.68.2 IPv6 route Hook
- No hook declared
- Default (weak) implementation
- Custom implementation
### 9.57.68.3 IPv6 get gateway Hook
- No hook declared
- Default (weak) implementation
- Custom implementation
### 9.57.68.4 IPv6 source address selection Hook
- No hook declared
- Default (weak) implementation
- Custom implementation
### 9.57.68.5 Netconn external resolve Hook
- No hook declared
- Default (weak) implementation
- Custom implementation
### 9.57.68.6 IPv6 packet input
- No hook declared
- Default (weak) implementation
- Custom implementation
## 9.57.69 Enable LWIP Debug
### 9.57.69.1 Route LWIP debugs through ESP_LOG interface
### 9.57.69.2 Enable netif debug messages
### 9.57.69.3 Enable pbuf debug messages
### 9.57.69.4 Enable etharp debug messages
### 9.57.69.5 Enable api lib debug messages
### 9.57.69.6 Enable socket debug messages
### 9.57.69.7 Enable IP debug messages
### 9.57.69.8 Enable ICMP debug messages
### 9.57.69.9 Enable DHCP state tracking
### 9.57.69.10 Enable DHCP debug messages
### 9.57.69.11 Enable IP6 debug messages
### 9.57.69.12 Enable ICMP6 debug messages
### 9.57.69.13 Enable TCP debug messages
### 9.57.69.14 Enable UDP debug messages
### 9.57.69.15 Enable SNTP debug messages
### 9.57.69.16 Enable DSN debug messages
### 9.57.69.17 Enable NAPT debug messages
### 9.57.69.18 Enable bridge generic debug messages
### 9.57.69.19 Enable bridge FDB debug messages
### 9.57.69.20 Enable bridge forwarding debug messages
