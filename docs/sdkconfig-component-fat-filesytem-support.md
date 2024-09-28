# 9.51 FAT Filesystem support
FAT Filesystem supportの設定を記載。

- [9.51 FAT Filesystem support](#951-fat-filesystem-support)
  - [9.51.1 Number of volumes](#9511-number-of-volumes)
  - [9.51.2 Long filename support](#9512-long-filename-support)
    - [9.51.2.1 No long filenames](#95121-no-long-filenames)
    - [9.51.2.2 Long filename buffer in heap](#95122-long-filename-buffer-in-heap)
    - [9.51.2.3 Long filename buffer on stack](#95123-long-filename-buffer-on-stack)
  - [9.51.3 Sector size](#9513-sector-size)
  - [9.51.4 OEM Code Page](#9514-oem-code-page)
  - [9.51.5 Max long filename length](#9515-max-long-filename-length)
  - [9.51.6 API character encoding](#9516-api-character-encoding)
  - [9.51.7 Number of simultaneously open files protected by lock function](#9517-number-of-simultaneously-open-files-protected-by-lock-function)
  - [9.51.8 Timeout for acquiring a file lock, ms](#9518-timeout-for-acquiring-a-file-lock-ms)
  - [9.51.9 Use separate cache for each file](#9519-use-separate-cache-for-each-file)
  - [9.51.10 Prefer external RAM when allocating FATFS buffer](#95110-prefer-external-ram-when-allocating-fatfs-buffer)
  - [9.51.11 Enable fast seek algorithm when suing lseek function through VFS FAT](#95111-enable-fast-seek-algorithm-when-suing-lseek-function-through-vfs-fat)
    - [9.51.11.1 Fast seek CLMT buffer size](#951111-fast-seek-clmt-buffer-size)
  - [9.51.12 Default block size](#95112-default-block-size)
  - [9.51.13 Enable automatic f\_sync](#95113-enable-automatic-f_sync)
  - [9.51.14 Use FATFS volume label](#95114-use-fatfs-volume-label)
  - [9.51.15 Perform the whole link operation under lock](#95115-perform-the-whole-link-operation-under-lock)
  - [9.51.16 Use dynamic buffers](#95116-use-dynamic-buffers)

## 9.51.1 Number of volumes
## 9.51.2 Long filename support
### 9.51.2.1 No long filenames
### 9.51.2.2 Long filename buffer in heap
### 9.51.2.3 Long filename buffer on stack
## 9.51.3 Sector size
- 512
- 4096
## 9.51.4 OEM Code Page
- Dynamic (all code pages supported)
- US (CP437)
- Arabic (CP720)
- Greek (CP737)
- KBL (CP771)
- Baltic (CP775)
- Latin 1 (CP850)
- Latin 2 (CP852)
- Cyrillic (CP855)
- Turkish (CP857)
- Portuguese (CP860)
- Icelandic (CP861)
- Hebrew (CP862)
- Canadian French (CP863)
- Arabic (CP864)
- Nordic (CP865)
- Russian (CP866)
- Greek 2 (CP869)
- Japanese (DBCS) (CP932)
- Simplified Chinese (DBCS) (CP936)
- Korean (DBCS) (CP949)
- Traditional Chinese (DBCS) (CP950)
## 9.51.5 Max long filename length
## 9.51.6 API character encoding
- API uses ANSI/OEM encoding
- API uses UTF-8 encoding
## 9.51.7 Number of simultaneously open files protected by lock function
## 9.51.8 Timeout for acquiring a file lock, ms
## 9.51.9 Use separate cache for each file
## 9.51.10 Prefer external RAM when allocating FATFS buffer
## 9.51.11 Enable fast seek algorithm when suing lseek function through VFS FAT
### 9.51.11.1 Fast seek CLMT buffer size
## 9.51.12 Default block size
## 9.51.13 Enable automatic f_sync
## 9.51.14 Use FATFS volume label
## 9.51.15 Perform the whole link operation under lock
## 9.51.16 Use dynamic buffers
