# 9.54 Heap memory debugging
Heap memory debuggingの設定を記載。

- [9.54 Heap memory debugging](#954-heap-memory-debugging)
  - [9.54.1 Heap corruption detection](#9541-heap-corruption-detection)
  - [9.54.2 Heap tracing](#9542-heap-tracing)
  - [9.54.3 Heap tracing stack depth](#9543-heap-tracing-stack-depth)
  - [9.54.4 Use allocation and free hooks](#9544-use-allocation-and-free-hooks)
  - [9.54.5 Enable heap task tracing](#9545-enable-heap-task-tracing)
  - [9.54.6 Use hash map mechanism to access heap trace records](#9546-use-hash-map-mechanism-to-access-heap-trace-records)
    - [9.54.6.1 Place hash map in external RAM](#95461-place-hash-map-in-external-ram)
    - [9.54.6.2 The number of entries in the hash map](#95462-the-number-of-entries-in-the-hash-map)
  - [9.54.7 Abort if memory allocation fails](#9547-abort-if-memory-allocation-fails)
  - [9.54.8 Use ROM implementation of heap tlsf library](#9548-use-rom-implementation-of-heap-tlsf-library)
  - [9.54.9 Force the entire heap component to be placed in flash memory](#9549-force-the-entire-heap-component-to-be-placed-in-flash-memory)

## 9.54.1 Heap corruption detection
- Basic (no poisoning)
- Light impact
- Comprehensive
## 9.54.2 Heap tracing
- Disabled
- Standalone
- Host-based
## 9.54.3 Heap tracing stack depth
## 9.54.4 Use allocation and free hooks
## 9.54.5 Enable heap task tracing
## 9.54.6 Use hash map mechanism to access heap trace records
### 9.54.6.1 Place hash map in external RAM
### 9.54.6.2 The number of entries in the hash map
## 9.54.7 Abort if memory allocation fails
## 9.54.8 Use ROM implementation of heap tlsf library
## 9.54.9 Force the entire heap component to be placed in flash memory
