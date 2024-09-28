# 9.46 ESP System Settings
ESP System Settingsの設定を記載。

- [9.46 ESP System Settings](#946-esp-system-settings)
  - [9.46.1 CPU frequency](#9461-cpu-frequency)
  - [9.46.2 Memory](#9462-memory)
    - [9.46.2.1 Use fixed static RAM size](#94621-use-fixed-static-ram-size)
      - [9.46.2.1.1 Fixed Static RAM size](#946211-fixed-static-ram-size)
    - [9.46.2.2 Enable IRAM as 8 bit accessible memory](#94622-enable-iram-as-8-bit-accessible-memory)
    - [9.46.2.3 Non-backward compatible options](#94623-non-backward-compatible-options)
    - [9.46.2.3.1 Reserve parts of SRAM1 for app IRAM](#946231-reserve-parts-of-sram1-for-app-iram)
  - [9.46.3 Trace memory](#9463-trace-memory)
    - [9.46.3.1 Use TRAX tracing feature](#94631-use-trax-tracing-feature)
      - [9.46.3.1.1 Reserve memory for tracing both pro as well as app cpu execution](#946311-reserve-memory-for-tracing-both-pro-as-well-as-app-cpu-execution)
  - [9.46.4 Panic handler behaviour](#9464-panic-handler-behaviour)
  - [9.46.5 Panic reboot delay](#9465-panic-reboot-delay)
  - [9.46.6 Bootstrap cycles for external 32kHz crystal](#9466-bootstrap-cycles-for-external-32khz-crystal)
  - [9.46.7 Enable RTC fast memory for dynamic allocations](#9467-enable-rtc-fast-memory-for-dynamic-allocations)
  - [9.46.8 Generate and use eh\_frame for backtracing](#9468-generate-and-use-eh_frame-for-backtracing)
  - [9.46.9 Memory protection](#9469-memory-protection)
  - [9.46.9.1 Enable IRAM/DRAM split protection](#94691-enable-iramdram-split-protection)
  - [9.46.9.2 Enable memory protection](#94692-enable-memory-protection)
  - [9.46.9.2.1 Lock memory protection settings](#946921-lock-memory-protection-settings)
  - [9.46.10 System event queue size](#94610-system-event-queue-size)
  - [9.46.11 Event loop task stack size](#94611-event-loop-task-stack-size)
  - [9.46.12 Main task stack size](#94612-main-task-stack-size)
  - [9.46.13 Main task core affinity](#94613-main-task-core-affinity)
  - [9.46.14 Minimal allowed size for shared stack](#94614-minimal-allowed-size-for-shared-stack)
  - [9.46.15 Channel for console output](#94615-channel-for-console-output)
  - [9.46.16 Interrupt watchdog](#94616-interrupt-watchdog)
    - [9.46.16.1 Channel for console secondary output](#946161-channel-for-console-secondary-output)
  - [9.46.17 UART peripheral to use for console output](#94617-uart-peripheral-to-use-for-console-output)
  - [9.46.18 UART TX on GPIO#](#94618-uart-tx-on-gpio)
  - [9.46.19 UART RX on GPIO#](#94619-uart-rx-on-gpio)
  - [9.46.20 UART console baud rate](#94620-uart-console-baud-rate)
  - [9.46.21 Size of USB CDC RX buffer](#94621-size-of-usb-cdc-rx-buffer)
  - [9.46.22 Enable esp\_rom\_printf / ESP\_EARLY\_LOG via USB CDC](#94622-enable-esp_rom_printf--esp_early_log-via-usb-cdc)
  - [9.46.23 Interrupt watchdog](#94623-interrupt-watchdog)
    - [9.46.23.1 Interrupt watchdog timeout](#946231-interrupt-watchdog-timeout)
    - [9.46.23.2 Also watch CPU1 tick interrupt](#946232-also-watch-cpu1-tick-interrupt)
  - [9.46.24 Enable Task Watchdog Timer](#94624-enable-task-watchdog-timer)
    - [9.46.24.1 Initialize Task Watchdog Timer on startup](#946241-initialize-task-watchdog-timer-on-startup)
      - [9.46.24.1.1 Invoke panic handler on Task Watchdog timeout](#9462411-invoke-panic-handler-on-task-watchdog-timeout)
      - [9.46.24.1.2 Task Watchdog timeout period](#9462412-task-watchdog-timeout-period)
      - [9.46.24.1.3 Watch CPU0 Idle Task](#9462413-watch-cpu0-idle-task)
      - [9.46.24.1.4 Watch CPU1 Idle Task](#9462414-watch-cpu1-idle-task)
  - [9.46.25 Initialize XTAL32K watchdog timer on startup](#94625-initialize-xtal32k-watchdog-timer-on-startup)
    - [9.46.25.1 XTAL32K watchdog timeout period](#946251-xtal32k-watchdog-timeout-period)
    - [9.46.25.2 Automatically switch to BACKUP32K\_CLK when timer expires](#946252-automatically-switch-to-backup32k_clk-when-timer-expires)
  - [9.46.26 Place panic handler code in IRAM](#94626-place-panic-handler-code-in-iram)
  - [9.46.27 OpenOCD debug stubs](#94627-openocd-debug-stubs)
  - [9.46.28 Make exception and panic handlers JTAG/OCD aware](#94628-make-exception-and-panic-handlers-jtagocd-aware)
  - [9.46.29 Interrupt level to use for Interrupt Watchdog and other system checks](#94629-interrupt-level-to-use-for-interrupt-watchdog-and-other-system-checks)
  - [9.46.30 Brownout Detector](#94630-brownout-detector)
  - [9.46.30.1 Hardware brownout detect \& reset](#946301-hardware-brownout-detect--reset)
  - [9.46.30.1.1 Brownout voltage level](#9463011-brownout-voltage-level)
  - [9.46.31 Permanently disable BASIC ROM Console](#94631-permanently-disable-basic-rom-console)
  - [9.46.32 Hardware stack guard](#94632-hardware-stack-guard)
  - [9.46.33 Re-calibration BBPLL at startup](#94633-re-calibration-bbpll-at-startup)
  - [9.46.34 Hardware PC recording](#94634-hardware-pc-recording)


## 9.46.1 CPU frequency
- 40 MHz
- 80 MHz
- 160 MHz
- 240 MHz
## 9.46.2 Memory
### 9.46.2.1 Use fixed static RAM size
#### 9.46.2.1.1 Fixed Static RAM size
### 9.46.2.2 Enable IRAM as 8 bit accessible memory
### 9.46.2.3 Non-backward compatible options
### 9.46.2.3.1 Reserve parts of SRAM1 for app IRAM
## 9.46.3 Trace memory
### 9.46.3.1 Use TRAX tracing feature
#### 9.46.3.1.1 Reserve memory for tracing both pro as well as app cpu execution
## 9.46.4 Panic handler behaviour
- Print registers and halt
- Print registers and reboot
- Silent reboot
- GDBStub on panic
## 9.46.5 Panic reboot delay
## 9.46.6 Bootstrap cycles for external 32kHz crystal
## 9.46.7 Enable RTC fast memory for dynamic allocations
## 9.46.8 Generate and use eh_frame for backtracing
## 9.46.9 Memory protection
## 9.46.9.1 Enable IRAM/DRAM split protection
## 9.46.9.2 Enable memory protection
## 9.46.9.2.1 Lock memory protection settings
## 9.46.10 System event queue size
## 9.46.11 Event loop task stack size
## 9.46.12 Main task stack size
## 9.46.13 Main task core affinity
- CPU0
- CPU1
- No affinity
## 9.46.14 Minimal allowed size for shared stack
## 9.46.15 Channel for console output
- Default: UART0
- USB CDC
- USB Serial/JTAG Controller
- Custom UART
- None
## 9.46.16 Interrupt watchdog
### 9.46.16.1 Channel for console secondary output
- No secondary console
- USB_SERIAL_JTAG PORT
## 9.46.17 UART peripheral to use for console output
- UART0
- UART1
## 9.46.18 UART TX on GPIO#
## 9.46.19 UART RX on GPIO#
## 9.46.20 UART console baud rate
## 9.46.21 Size of USB CDC RX buffer
## 9.46.22 Enable esp_rom_printf / ESP_EARLY_LOG via USB CDC
## 9.46.23 Interrupt watchdog
### 9.46.23.1 Interrupt watchdog timeout
### 9.46.23.2 Also watch CPU1 tick interrupt
## 9.46.24 Enable Task Watchdog Timer
### 9.46.24.1 Initialize Task Watchdog Timer on startup
#### 9.46.24.1.1 Invoke panic handler on Task Watchdog timeout
#### 9.46.24.1.2 Task Watchdog timeout period
#### 9.46.24.1.3 Watch CPU0 Idle Task
#### 9.46.24.1.4 Watch CPU1 Idle Task
## 9.46.25 Initialize XTAL32K watchdog timer on startup
### 9.46.25.1 XTAL32K watchdog timeout period
### 9.46.25.2 Automatically switch to BACKUP32K_CLK when timer expires
## 9.46.26 Place panic handler code in IRAM
## 9.46.27 OpenOCD debug stubs
## 9.46.28 Make exception and panic handlers JTAG/OCD aware
## 9.46.29 Interrupt level to use for Interrupt Watchdog and other system checks
- Level 5 interrupt
- Level 4 interrupt
## 9.46.30 Brownout Detector
## 9.46.30.1 Hardware brownout detect & reset
## 9.46.30.1.1 Brownout voltage level
- 2.43V +/- 0.05
- 2.48V +/- 0.05
- 2.58V +/- 0.05
- 2.62V +/- 0.05
- 2.67V +/- 0.05
- 2.70V +/- 0.05
- 2.77V +/- 0.05
- 2.80V +/- 0.05
## 9.46.31 Permanently disable BASIC ROM Console
## 9.46.32 Hardware stack guard
## 9.46.33 Re-calibration BBPLL at startup
## 9.46.34 Hardware PC recording
