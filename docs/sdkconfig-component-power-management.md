# 9.43 Power Management
Power Managementの設定を記載。

- [9.43 Power Management](#943-power-management)
  - [9.43.1 Support for power management](#9431-support-for-power-management)
  - [9.43.1.1 Enable dynamic frequency scaling (DFS) at startup](#94311-enable-dynamic-frequency-scaling-dfs-at-startup)
  - [9.43.1.2 Enable profiling counters for PM locks](#94312-enable-profiling-counters-for-pm-locks)
  - [9.43.1.3 Enable debug tracing of PM using GPIOs](#94313-enable-debug-tracing-of-pm-using-gpios)
  - [9.43.2 Put lightsleep related codes in internal RAM](#9432-put-lightsleep-related-codes-in-internal-ram)
  - [9.43.3 Put RTOS IDLE related codes in internal RAM](#9433-put-rtos-idle-related-codes-in-internal-ram)
  - [9.43.4 Calibrate the RTC\_FAST/SLOW clock every N times of light sleep](#9434-calibrate-the-rtc_fastslow-clock-every-n-times-of-light-sleep)
  - [9.43.5 Power down CPU in light sleep](#9435-power-down-cpu-in-light-sleep)
    - [9.43.5.1 Restore I/D-cache Peripheral in light sleep](#94351-restore-id-cache-peripheral-in-light-sleep)
  - [9.43.6 Enable registration of pm light sleep callbacks](#9436-enable-registration-of-pm-light-sleep-callbacks)

## 9.43.1 Support for power management
## 9.43.1.1 Enable dynamic frequency scaling (DFS) at startup
## 9.43.1.2 Enable profiling counters for PM locks
## 9.43.1.3 Enable debug tracing of PM using GPIOs
## 9.43.2 Put lightsleep related codes in internal RAM
## 9.43.3 Put RTOS IDLE related codes in internal RAM
## 9.43.4 Calibrate the RTC_FAST/SLOW clock every N times of light sleep
## 9.43.5 Power down CPU in light sleep
### 9.43.5.1 Restore I/D-cache Peripheral in light sleep
## 9.43.6 Enable registration of pm light sleep callbacks
