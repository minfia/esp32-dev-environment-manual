# 9.52 FreeRTOS
FreeRTOSの設定を記載。

- [9.52 FreeRTOS](#952-freertos)
  - [9.52.1 Kernel](#9521-kernel)
    - [9.52.1.1 Run the Amazon SMP FreeRTOS kernel instead (FEATURE UNDER DEVELOPMENT)](#95211-run-the-amazon-smp-freertos-kernel-instead-feature-under-development)
    - [9.52.1.2 Run FreeRTOS only on first core](#95212-run-freertos-only-on-first-core)
    - [9.52.1.3 configTICK\_RATE\_HZ](#95213-configtick_rate_hz)
    - [9.52.1.4 configUSE\_PORT\_OPTIMISED\_TASK\_SELECTION](#95214-configuse_port_optimised_task_selection)
    - [9.52.1.5 configCHECK\_FOR\_STACK\_OVERFLOW](#95215-configcheck_for_stack_overflow)
    - [9.52.1.6 configNUM\_THREAD\_LOCAL\_STORAGE\_POINTERS](#95216-confignum_thread_local_storage_pointers)
    - [9.52.1.7 configMINIMAL\_STACK\_SIZE (Idle task stack size)](#95217-configminimal_stack_size-idle-task-stack-size)
    - [9.52.1.8 configUSE\_IDLE\_HOOK](#95218-configuse_idle_hook)
    - [9.52.1.9 Use FreeRTOS minimal idle hook](#95219-use-freertos-minimal-idle-hook)
    - [9.52.1.10 configUSE\_TICK\_HOOK](#952110-configuse_tick_hook)
    - [9.52.1.11 configMAX\_TASK\_NAME\_LEN](#952111-configmax_task_name_len)
    - [9.52.1.12 configENABLE\_BACKWARD\_COMPATIBILITY](#952112-configenable_backward_compatibility)
    - [9.52.1.13 configTIMER\_SERVICE\_TASK\_NAME](#952113-configtimer_service_task_name)
    - [9.52.1.14 configTIMER\_SERVICE\_TASK\_CORE\_AFFINITY](#952114-configtimer_service_task_core_affinity)
    - [9.52.1.15 configTIMER\_TASK\_PRIORITY](#952115-configtimer_task_priority)
    - [9.52.1.16 configTIMER\_TASK\_STACK\_DEPTH](#952116-configtimer_task_stack_depth)
    - [9.52.1.17 configTIMER\_QUEUE\_LENGTH](#952117-configtimer_queue_length)
    - [9.52.1.18 configQUEUE\_REGISTRY\_SIZE](#952118-configqueue_registry_size)
    - [9.52.1.19 configTASK\_NOTIFICATION\_ARRAY\_ENTRIES](#952119-configtask_notification_array_entries)
    - [9.52.1.20 configUSE\_TRACE\_FACILITY](#952120-configuse_trace_facility)
      - [9.52.1.20.1 configUSE\_STATS\_FORMATTING\_FUNCTIONS](#9521201-configuse_stats_formatting_functions)
    - [9.52.1.21 configUSE\_LIST\_DATA\_INTEGRITY\_CHECK\_BYTES](#952121-configuse_list_data_integrity_check_bytes)
    - [9.52.1.22 Enable display of xCoreID in vTaskList](#952122-enable-display-of-xcoreid-in-vtasklist)
    - [9.52.1.23 configGENERATE\_RUN\_TIME\_STATS](#952123-configgenerate_run_time_stats)
      - [9.52.1.23.1 configRUN\_TIME\_COUNTER\_TYPE](#9521231-configrun_time_counter_type)
    - [9.52.1.24 configUSE\_TICKLESS\_IDLE](#952124-configuse_tickless_idle)
      - [9.52.1.24.1 configEXPECTED\_IDLE\_TIME\_BEFORE\_SLEEP](#9521241-configexpected_idle_time_before_sleep)
    - [9.52.1.25 configUSE\_APPLICATION\_TASK\_TAG](#952125-configuse_application_task_tag)
  - [9.52.2 Port](#9522-port)
    - [9.52.2.1 Wrap task functions](#95221-wrap-task-functions)
    - [9.52.2.2 Enable stack overflow debug watchpoint](#95222-enable-stack-overflow-debug-watchpoint)
    - [9.52.2.3 Enable thread local storage pointers deletion callbacks](#95223-enable-thread-local-storage-pointers-deletion-callbacks)
    - [9.52.2.4 Enable task pre-deletion hook](#95224-enable-task-pre-deletion-hook)
    - [9.52.2.5 Enable static task clean up hook (DEPRECATED)](#95225-enable-static-task-clean-up-hook-deprecated)
    - [9.52.2.6 Check that mutex semaphore is given by owner task](#95226-check-that-mutex-semaphore-is-given-by-owner-task)
    - [9.52.2.7 ISR stack size](#95227-isr-stack-size)
    - [9.52.2.8 Enable backtrace form interrupt to task context](#95228-enable-backtrace-form-interrupt-to-task-context)
    - [9.52.2.9 Use float in Level 1 ISR](#95229-use-float-in-level-1-isr)
    - [9.52.2.10 Tick timer source (Xtensa Only)](#952210-tick-timer-source-xtensa-only)
    - [9.52.2.11 Choose the clock source for run time stats](#952211-choose-the-clock-source-for-run-time-stats)
    - [9.52.2.12 Place FreeRTOS functions into Flash](#952212-place-freertos-functions-into-flash)
    - [9.52.2.13 Tests compliance with Vanilla FreeRTOS port\*\_CRITICAL calls](#952213-tests-compliance-with-vanilla-freertos-port_critical-calls)

## 9.52.1 Kernel
### 9.52.1.1 Run the Amazon SMP FreeRTOS kernel instead (FEATURE UNDER DEVELOPMENT)
### 9.52.1.2 Run FreeRTOS only on first core
### 9.52.1.3 configTICK_RATE_HZ
### 9.52.1.4 configUSE_PORT_OPTIMISED_TASK_SELECTION
### 9.52.1.5 configCHECK_FOR_STACK_OVERFLOW
- No checking
- Check by stack pointer value (Method 1)
- Check using canary bytes (Method 2)
### 9.52.1.6 configNUM_THREAD_LOCAL_STORAGE_POINTERS
### 9.52.1.7 configMINIMAL_STACK_SIZE (Idle task stack size)
### 9.52.1.8 configUSE_IDLE_HOOK
### 9.52.1.9 Use FreeRTOS minimal idle hook
### 9.52.1.10 configUSE_TICK_HOOK
### 9.52.1.11 configMAX_TASK_NAME_LEN
### 9.52.1.12 configENABLE_BACKWARD_COMPATIBILITY
### 9.52.1.13 configTIMER_SERVICE_TASK_NAME
### 9.52.1.14 configTIMER_SERVICE_TASK_CORE_AFFINITY
- CPU0
- CPU1
- No affinity
### 9.52.1.15 configTIMER_TASK_PRIORITY
### 9.52.1.16 configTIMER_TASK_STACK_DEPTH
### 9.52.1.17 configTIMER_QUEUE_LENGTH
### 9.52.1.18 configQUEUE_REGISTRY_SIZE
### 9.52.1.19 configTASK_NOTIFICATION_ARRAY_ENTRIES
### 9.52.1.20 configUSE_TRACE_FACILITY
#### 9.52.1.20.1 configUSE_STATS_FORMATTING_FUNCTIONS
### 9.52.1.21 configUSE_LIST_DATA_INTEGRITY_CHECK_BYTES
### 9.52.1.22 Enable display of xCoreID in vTaskList
### 9.52.1.23 configGENERATE_RUN_TIME_STATS
#### 9.52.1.23.1 configRUN_TIME_COUNTER_TYPE
- uint32_t
- uint64_t
### 9.52.1.24 configUSE_TICKLESS_IDLE
#### 9.52.1.24.1 configEXPECTED_IDLE_TIME_BEFORE_SLEEP
### 9.52.1.25 configUSE_APPLICATION_TASK_TAG
## 9.52.2 Port
### 9.52.2.1 Wrap task functions
### 9.52.2.2 Enable stack overflow debug watchpoint
### 9.52.2.3 Enable thread local storage pointers deletion callbacks
### 9.52.2.4 Enable task pre-deletion hook
### 9.52.2.5 Enable static task clean up hook (DEPRECATED)
### 9.52.2.6 Check that mutex semaphore is given by owner task
### 9.52.2.7 ISR stack size
### 9.52.2.8 Enable backtrace form interrupt to task context
### 9.52.2.9 Use float in Level 1 ISR
### 9.52.2.10 Tick timer source (Xtensa Only)
- Timer 0 (int 6, level 1)
- Timer 1 (int 15, level 3)
- SYSTIMER 0 (level 1)
- SYSTIMER 0 (level 3)
### 9.52.2.11 Choose the clock source for run time stats
- Use ESP TIMER for tun time stats
- Use CPU Clock for tun time stats
### 9.52.2.12 Place FreeRTOS functions into Flash
### 9.52.2.13 Tests compliance with Vanilla FreeRTOS port*_CRITICAL calls
