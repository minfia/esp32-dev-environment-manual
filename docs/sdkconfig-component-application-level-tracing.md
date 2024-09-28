# 9.1 Application Level Tracing
Application Level Tracingの設定を記載。

- [9.1 Application Level Tracing](#91-application-level-tracing)
  - [9.1.1 Data Destination 1](#911-data-destination-1)
  - [9.1.2 Data Destination 2](#912-data-destination-2)
  - [9.1.3 UART TX on GPIO#](#913-uart-tx-on-gpio)
  - [9.1.4 UART RX on GPIO#](#914-uart-rx-on-gpio)
  - [9.1.5 UART baud rate](#915-uart-baud-rate)
  - [9.1.6 UART RX ring buffer size](#916-uart-rx-ring-buffer-size)
  - [9.1.7 UART TX ring buffer size](#917-uart-tx-ring-buffer-size)
  - [9.1.8 UART TX message size](#918-uart-tx-message-size)
  - [9.1.9 UART Task Priority](#919-uart-task-priority)
  - [9.1.10 Timeout for flushing last trace data to host on panic](#9110-timeout-for-flushing-last-trace-data-to-host-on-panic)
  - [9.1.11 Threshold for flushing last trace data to host on panic](#9111-threshold-for-flushing-last-trace-data-to-host-on-panic)
  - [9.1.12 Size of the pending data buffer](#9112-size-of-the-pending-data-buffer)
  - [9.1.13 FreeRTOS SystemView Tracing](#9113-freertos-systemview-tracing)
    - [9.1.13.1 SystemView Tracing Enable](#91131-systemview-tracing-enable)
      - [9.1.13.1.1 SystemView destination](#911311-systemview-destination)
    - [9.1.13.2 CPU to trace](#91132-cpu-to-trace)
    - [9.1.13.3 Timer to use as timestamp source](#91133-timer-to-use-as-timestamp-source)
    - [9.1.13.4 Maximum supported tasks](#91134-maximum-supported-tasks)
    - [9.1.13.5 Trace buffer wait timeout](#91135-trace-buffer-wait-timeout)
    - [9.1.13.6 Trace Buffer Overflow Event](#91136-trace-buffer-overflow-event)
    - [9.1.13.7 ISR Enter Event](#91137-isr-enter-event)
    - [9.1.13.8 ISR Exit Event](#91138-isr-exit-event)
    - [9.1.13.9 ISR Exit to Scheduler Event](#91139-isr-exit-to-scheduler-event)
    - [9.1.13.10 Task Start Execution Event](#911310-task-start-execution-event)
    - [9.1.13.11 Task Stop Execution Event](#911311-task-stop-execution-event)
    - [9.1.13.12 Task Start Ready State Event](#911312-task-start-ready-state-event)
    - [9.1.13.13 Task Stop Ready State Event](#911313-task-stop-ready-state-event)
    - [9.1.13.14 Task Create Event](#911314-task-create-event)
    - [9.1.13.15 Task Terminate Event](#911315-task-terminate-event)
    - [9.1.13.16 System Idle Event](#911316-system-idle-event)
    - [9.1.13.17 Timer Enter Event](#911317-timer-enter-event)
    - [9.1.13.18 Timer Exit Event](#911318-timer-exit-event)
  - [9.1.14 GCOV to Host Enable](#9114-gcov-to-host-enable)
    - [9.1.14.1 Gcov dump task stack size](#91141-gcov-dump-task-stack-size)

## 9.1.1 Data Destination 1
- JTAG
- None
## 9.1.2 Data Destination 2
- UART0
- UART1
- UART2
- USB_CDC
- None
## 9.1.3 UART TX on GPIO#
"[Data Destination 2](#912-data-destination-2)"を"UART1"または"UART2"に設定で表示
## 9.1.4 UART RX on GPIO#
"[Data Destination 2](#912-data-destination-2)"を"UART1"または"UART2"に設定で表示
## 9.1.5 UART baud rate
"[Data Destination 2](#912-data-destination-2)"を"UART1"または"UART2"に設定で表示
## 9.1.6 UART RX ring buffer size
"[Data Destination 2](#912-data-destination-2)"を"UART1"または"UART2"に設定で表示
## 9.1.7 UART TX ring buffer size
"[Data Destination 2](#912-data-destination-2)"を"UART1"または"UART2"に設定で表示
## 9.1.8 UART TX message size
"[Data Destination 2](#912-data-destination-2)"を"UART1"または"UART2"に設定で表示
## 9.1.9 UART Task Priority
"[Data Destination 2](#912-data-destination-2)"を"UART1"または"UART2"に設定で表示
## 9.1.10 Timeout for flushing last trace data to host on panic
"[Data Destination 1](#911-data-destination-1)"を"JTAG"に設定で表示
"[Data Destination 2](#912-data-destination-2)"を"UART1"または"UART2"に設定で表示
## 9.1.11 Threshold for flushing last trace data to host on panic
"[Data Destination 1](#911-data-destination-1)"を"JTAG"に設定で表示
"[Data Destination 2](#912-data-destination-2)"を"UART1"または"UART2"に設定で表示
## 9.1.12 Size of the pending data buffer
"[Data Destination 1](#911-data-destination-1)"を"JTAG"に設定で表示
## 9.1.13 FreeRTOS SystemView Tracing
"[Data Destination 1](#911-data-destination-1)"を"JTAG"に設定で表示
"[Data Destination 2](#912-data-destination-2)"を"UART1"または"UART2"に設定で表示
### 9.1.13.1 SystemView Tracing Enable
#### 9.1.13.1.1 SystemView destination
"[SystemView Tracing Enable](#91131-systemview-tracing-enable)"の有効で表示
- Data destination JTAG
- Data destination UART
### 9.1.13.2 CPU to trace
- CPU0
- CPU1
### 9.1.13.3 Timer to use as timestamp source
"[SystemView Tracing Enable](#91131-systemview-tracing-enable)"の有効で表示
- CPU cycle counter (CCOUNT)
- General Purpose Timer (Timer Group)
- esp_timer high resolution timer
### 9.1.13.4 Maximum supported tasks
"[SystemView Tracing Enable](#91131-systemview-tracing-enable)"の有効で表示
### 9.1.13.5 Trace buffer wait timeout
"[SystemView Tracing Enable](#91131-systemview-tracing-enable)"の有効で表示
### 9.1.13.6 Trace Buffer Overflow Event
"[SystemView Tracing Enable](#91131-systemview-tracing-enable)"の有効で表示
### 9.1.13.7 ISR Enter Event
"[SystemView Tracing Enable](#91131-systemview-tracing-enable)"の有効で表示
### 9.1.13.8 ISR Exit Event
"[SystemView Tracing Enable](#91131-systemview-tracing-enable)"の有効で表示
### 9.1.13.9 ISR Exit to Scheduler Event
"[SystemView Tracing Enable](#91131-systemview-tracing-enable)"の有効で表示
### 9.1.13.10 Task Start Execution Event
"[SystemView Tracing Enable](#91131-systemview-tracing-enable)"の有効で表示
### 9.1.13.11 Task Stop Execution Event
"[SystemView Tracing Enable](#91131-systemview-tracing-enable)"の有効で表示
### 9.1.13.12 Task Start Ready State Event
"[SystemView Tracing Enable](#91131-systemview-tracing-enable)"の有効で表示
### 9.1.13.13 Task Stop Ready State Event
"[SystemView Tracing Enable](#91131-systemview-tracing-enable)"の有効で表示
### 9.1.13.14 Task Create Event
"[SystemView Tracing Enable](#91131-systemview-tracing-enable)"の有効で表示
### 9.1.13.15 Task Terminate Event
"[SystemView Tracing Enable](#91131-systemview-tracing-enable)"の有効で表示
### 9.1.13.16 System Idle Event
"[SystemView Tracing Enable](#91131-systemview-tracing-enable)"の有効で表示
### 9.1.13.17 Timer Enter Event
"[SystemView Tracing Enable](#91131-systemview-tracing-enable)"の有効で表示
### 9.1.13.18 Timer Exit Event
"[SystemView Tracing Enable](#91131-systemview-tracing-enable)"の有効で表示
## 9.1.14 GCOV to Host Enable
"[SystemView Tracing Enable](#91131-systemview-tracing-enable)"の無効で表示
### 9.1.14.1 Gcov dump task stack size
