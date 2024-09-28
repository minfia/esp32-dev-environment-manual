# 9.71 Ultra Low Power Co-processor
Ultra Low Power Co-processorの設定を記載。

- [9.71 Ultra Low Power Co-processor](#971-ultra-low-power-co-processor)
  - [9.71.1 Enable Ultra Low Power (ULP Co-processor)](#9711-enable-ultra-low-power-ulp-co-processor)
    - [9.71.1.1 ULP Co-processor type](#97111-ulp-co-processor-type)
  - [9.71.2 ULP RISC-V Settings](#9712-ulp-risc-v-settings)
  - [9.71.3 Enable print utilities from LP ROM](#9713-enable-print-utilities-from-lp-rom)
  - [9.71.4 ULP Debugging Options](#9714-ulp-debugging-options)
    - [9.71.4.1 Enable panic handler which outputs over LP UART](#97141-enable-panic-handler-which-outputs-over-lp-uart)
    - [9.71.4.2 Route lp\_core\_printf to the console HP-UART](#97142-route-lp_core_printf-to-the-console-hp-uart)

## 9.71.1 Enable Ultra Low Power (ULP Co-processor)
### 9.71.1.1 ULP Co-processor type
- ULP FSM (Finite State Machine)
- ULP RISC-V
- LP core RISC-V
## 9.71.2 ULP RISC-V Settings
-Enable ULP RISC-V interrupts 
- Baudrate used by the bitbanged ULP RISC-V UART driver
- Set timeout for ULP RISC-V I2C transaction timeout in ticks.
## 9.71.3 Enable print utilities from LP ROM
## 9.71.4 ULP Debugging Options
### 9.71.4.1 Enable panic handler which outputs over LP UART
### 9.71.4.2 Route lp_core_printf to the console HP-UART
