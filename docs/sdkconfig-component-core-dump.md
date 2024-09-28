# 9.50 Core dump
Core dumpの設定を記載。

- [9.50 Core dump](#950-core-dump)
  - [9.50.1 Data destination](#9501-data-destination)
  - [9.50.2 Core dump data format](#9502-core-dump-data-format)
  - [9.50.3 Core dump data integrity check](#9503-core-dump-data-integrity-check)
  - [9.50.4 Include while .bss and .data sections and heap data into core dump file](#9504-include-while-bss-and-data-sections-and-heap-data-into-core-dump-file)
  - [9.50.5 Check core dump data integrity on boot](#9505-check-core-dump-data-integrity-on-boot)
  - [9.50.6 Enable core dump logs for debugging](#9506-enable-core-dump-logs-for-debugging)
  - [9.50.7 Maximum number of tasks](#9507-maximum-number-of-tasks)
  - [9.50.8 Delay before print to UART](#9508-delay-before-print-to-uart)
  - [9.50.9 Don't overwrite existing core dump](#9509-dont-overwrite-existing-core-dump)
  - [9.50.10 Reserved stack size](#95010-reserved-stack-size)
  - [9.50.11 Size of the stack dump buffer](#95011-size-of-the-stack-dump-buffer)
  - [9.50.12 Handling of UART core dumps in IDF Monitor](#95012-handling-of-uart-core-dumps-in-idf-monitor)

## 9.50.1 Data destination
- Flash
- UART
- None
## 9.50.2 Core dump data format
- Binary format
- ELF format
## 9.50.3 Core dump data integrity check
- Use CRC32 for integrity verification
- Use SHA256 for integrity verification
## 9.50.4 Include while .bss and .data sections and heap data into core dump file
## 9.50.5 Check core dump data integrity on boot
## 9.50.6 Enable core dump logs for debugging
## 9.50.7 Maximum number of tasks
## 9.50.8 Delay before print to UART
## 9.50.9 Don't overwrite existing core dump
## 9.50.10 Reserved stack size
## 9.50.11 Size of the stack dump buffer
## 9.50.12 Handling of UART core dumps in IDF Monitor
- Decode and show summary (info_corefile)
- Don't decode
