# 8 Compiler options
Compiler optionsの設定を記載。

- [8 Compiler options](#8-compiler-options)
  - [8.1 Optimization Level](#81-optimization-level)
  - [8.2 Assertion level](#82-assertion-level)
  - [8.3 Compiler float lib source](#83-compiler-float-lib-source)
  - [8.4 Disable messages in ESP\_RETURN\_ON\_\* and ESP\_EXIT\_ON\_\* macros](#84-disable-messages-in-esp_return_on_-and-esp_exit_on_-macros)
  - [8.5 Replace ESP-IDF and project paths in binaries](#85-replace-esp-idf-and-project-paths-in-binaries)
  - [8.6 Enable C++ exceptions](#86-enable-c-exceptions)
    - [8.6.1 Emergency Pool Size](#861-emergency-pool-size)
  - [8.7 Enable C++ run-time type info](#87-enable-c-run-time-type-info)
  - [8.7.1 Emergency Pool Size](#871-emergency-pool-size)
  - [8.8 Stack mashing protection mode](#88-stack-mashing-protection-mode)
  - [8.9 Enable -Wwrite-strings warning flag](#89-enable--wwrite-strings-warning-flag)
  - [8.10 Enable -msave-restore flag to reduce code size](#810-enable--msave-restore-flag-to-reduce-code-size)
  - [8.11 Disable new warning introduced in GCC 12](#811-disable-new-warning-introduced-in-gcc-12)
  - [8.12 Disable new warning introduced in GCC 13](#812-disable-new-warning-introduced-in-gcc-13)
  - [8.13 Dump RTL files during compilation](#813-dump-rtl-files-during-compilation)
  - [8.14 Compiler runtime library](#814-compiler-runtime-library)
  - [8.15 Orphan sections handling](#815-orphan-sections-handling)

## 8.1 Optimization Level
- Debug
- Optimize for size
- Optimize for performance
- Debug without optimization
## 8.2 Assertion level
- Enable
- Silent
- Disabled
## 8.3 Compiler float lib source
- libgcc
- librvfp
## 8.4 Disable messages in ESP_RETURN_ON_* and ESP_EXIT_ON_* macros
## 8.5 Replace ESP-IDF and project paths in binaries
## 8.6 Enable C++ exceptions
### 8.6.1 Emergency Pool Size
"[Enable C++ exceptions](#86-enable-c-exceptions)"の有効で設定可能
## 8.7 Enable C++ run-time type info
## 8.7.1 Emergency Pool Size
## 8.8 Stack mashing protection mode
- None
- Normal
- Strong
- Overall
## 8.9 Enable -Wwrite-strings warning flag
## 8.10 Enable -msave-restore flag to reduce code size
## 8.11 Disable new warning introduced in GCC 12
## 8.12 Disable new warning introduced in GCC 13
## 8.13 Dump RTL files during compilation
## 8.14 Compiler runtime library
- libgcc
- libclang_rt
- Host
## 8.15 Orphan sections handling
- Place with warning
- Place silently
