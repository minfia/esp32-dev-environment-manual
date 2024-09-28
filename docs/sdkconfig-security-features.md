# 3 Security features
Security featuresの設定を記載。

- [3 Security features](#3-security-features)
  - [3.1 Requires signed app images](#31-requires-signed-app-images)
  - [3.2 App Singing Scheme](#32-app-singing-scheme)
  - [3.3 ECDSA key size](#33-ecdsa-key-size)
    - [3.3.1 Using ECC curve NISTP192](#331-using-ecc-curve-nistp192)
    - [3.3.2 Using ECC curve NISTP256 (Recommended)](#332-using-ecc-curve-nistp256-recommended)
  - [3.4 Bootloader verifies app signatures](#34-bootloader-verifies-app-signatures)
  - [3.5 Verify app signature on update](#35-verify-app-signature-on-update)
  - [3.6 Enable hardware Secure Boot in bootloader](#36-enable-hardware-secure-boot-in-bootloader)
    - [3.6.1 Select secure boot version](#361-select-secure-boot-version)
      - [3.6.1.1 Enable Secure Boot version 1](#3611-enable-secure-boot-version-1)
      - [3.6.1.2 Enable Secure Boot version 2](#3612-enable-secure-boot-version-2)
  - [3.7 Secure bootloader mode](#37-secure-bootloader-mode)
  - [3.8 Sign binaries during build](#38-sign-binaries-during-build)
  - [3.9 Secure boot private signing key](#39-secure-boot-private-signing-key)
  - [3.10 Secure boot public signature verification key](#310-secure-boot-public-signature-verification-key)
  - [3.11 Enable Aggressive key revoke strategy](#311-enable-aggressive-key-revoke-strategy)
  - [3.12 Flash bootloader along with other artifacts when using the default flash command](#312-flash-bootloader-along-with-other-artifacts-when-using-the-default-flash-command)
  - [3.13 Hardware Key Encoding](#313-hardware-key-encoding)
    - [3.13.1 No encoding (256 bit key)](#3131-no-encoding-256-bit-key)
    - [3.13.2 3/4 encoding (192 bit key)](#3132-34-encoding-192-bit-key)
  - [3.13 Allow potentially insecure options](#313-allow-potentially-insecure-options)
  - [3.14 Enable flash encryption on boot](#314-enable-flash-encryption-on-boot)
    - [3.14.1 Size of generated XTS-AES key](#3141-size-of-generated-xts-aes-key)
      - [3.14.1.1 AES-128 key derived from 28 bites (SHA256(128 bits))](#31411-aes-128-key-derived-from-28-bites-sha256128-bits)
      - [3.14.1.2 AES-128 (256-bit key)](#31412-aes-128-256-bit-key)
      - [3.14.1.3 AES-256 (512-bit key)](#31413-aes-256-512-bit-key)
    - [3.14.2 Enable usage mode](#3142-enable-usage-mode)
  - [3.15 Potentially insecure options](#315-potentially-insecure-options)
    - [3.15.1 Leave ROM BASIC Interpreter available on reset](#3151-leave-rom-basic-interpreter-available-on-reset)
    - [3.15.2 Allow JTAG Debugging](#3152-allow-jtag-debugging)
    - [3.15.3 Allow app partition length not 64KB aligned](#3153-allow-app-partition-length-not-64kb-aligned)
    - [3.15.4 additional read protecting of efuses](#3154-additional-read-protecting-of-efuses)
    - [3.15.5 Leave unused digest slots available (not revoke)](#3155-leave-unused-digest-slots-available-not-revoke)
    - [3.15.6 Leave UART bootloader encryption enable](#3156-leave-uart-bootloader-encryption-enable)
    - [3.15.7 Leave UART bootloader decryption enable](#3157-leave-uart-bootloader-decryption-enable)
    - [3.15.8 Leave UART bootloader flash cache enable](#3158-leave-uart-bootloader-flash-cache-enable)
    - [3.15.9 Require flash encryption to be already enable](#3159-require-flash-encryption-to-be-already-enable)
    - [3.15.10 Skip write-protection of DIS\_CACHE](#31510-skip-write-protection-of-dis_cache)
  - [3.16 Encrypt only the app image that is present in the partition of type app](#316-encrypt-only-the-app-image-that-is-present-in-the-partition-of-type-app)
  - [3.17 Check Flash Encryption enabled on app startup](#317-check-flash-encryption-enabled-on-app-startup)
  - [3.18 UART ROM download mode](#318-uart-rom-download-mode)
    - [3.18.1 UART ROM download mode (Permanently disabled (recommended))](#3181-uart-rom-download-mode-permanently-disabled-recommended)
    - [3.18.2 UART ROM download mode (Permanently switch to Secure mode(recommended))](#3182-uart-rom-download-mode-permanently-switch-to-secure-moderecommended)
    - [3.18.3 UART ROM download mode (Enable (not recommended))](#3183-uart-rom-download-mode-enable-not-recommended)

## 3.1 Requires signed app images
"[Enable hardware Secure Boot in bootloader](#36-enable-hardware-secure-boot-in-bootloader)"の有効で非表示
## 3.2 App Singing Scheme
以下の有効で表示される。\
- [Requires signed app images](#31-requires-signed-app-images)
- [Enable hardware Secure Boot in bootloader](#36-enable-hardware-secure-boot-in-bootloader)
- ECDSA
- RSA
- ECDSA (V2)
## 3.3 ECDSA key size
### 3.3.1 Using ECC curve NISTP192
### 3.3.2 Using ECC curve NISTP256 (Recommended)
## 3.4 Bootloader verifies app signatures
"[Requires signed app images](#31-requires-signed-app-images)"の有効で表示
## 3.5 Verify app signature on update
"[Requires signed app images](#31-requires-signed-app-images)"の有効で表示
## 3.6 Enable hardware Secure Boot in bootloader
### 3.6.1 Select secure boot version
"[Enable hardware Secure Boot in bootloader](#36-enable-hardware-secure-boot-in-bootloader)"の有効で表示
#### 3.6.1.1 Enable Secure Boot version 1
#### 3.6.1.2 Enable Secure Boot version 2
## 3.7 Secure bootloader mode
"[Enable hardware Secure Boot in bootloader](#36-enable-hardware-secure-boot-in-bootloader)"の有効で表示
- One-time flash
- Reflashable
## 3.8 Sign binaries during build
以下の有効で表示する。\
- [Bootloader verifies app signatures](#34-bootloader-verifies-app-signatures)
- [Verify app signature on update](#35-verify-app-signature-on-update)
- [Enable hardware Secure Boot in bootloader](#36-enable-hardware-secure-boot-in-bootloader)
## 3.9 Secure boot private signing key
"[Sign binaries during build](#38-sign-binaries-during-build)"の有効で表示
## 3.10 Secure boot public signature verification key
"[Sign binaries during build](#38-sign-binaries-during-build)"の無効で表示
## 3.11 Enable Aggressive key revoke strategy
## 3.12 Flash bootloader along with other artifacts when using the default flash command
## 3.13 Hardware Key Encoding
### 3.13.1 No encoding (256 bit key)
### 3.13.2 3/4 encoding (192 bit key)
## 3.13 Allow potentially insecure options
"[Enable hardware Secure Boot in bootloader](#36-enable-hardware-secure-boot-in-bootloader)"の有効で表示
## 3.14 Enable flash encryption on boot
### 3.14.1 Size of generated XTS-AES key
#### 3.14.1.1 AES-128 key derived from 28 bites (SHA256(128 bits))
#### 3.14.1.2 AES-128 (256-bit key)
#### 3.14.1.3 AES-256 (512-bit key)
### 3.14.2 Enable usage mode
"[Enable flash encryption on boot](#314-enable-flash-encryption-on-boot)"の有効で表示
- Development
- Release
## 3.15 Potentially insecure options
以下の有効で表示される。\
- [Verify app signature on update](#35-verify-app-signature-on-update)
- [Allow potentially insecure options](#313-allow-potentially-insecure-options)
- [Enable flash encryption on boot](#314-enable-flash-encryption-on-boot)
- [Enable usage mode](#3142-enable-usage-mode)のDevelopment
### 3.15.1 Leave ROM BASIC Interpreter available on reset
以下の有効で表示される。\
- [Enable hardware Secure Boot in bootloader](#36-enable-hardware-secure-boot-in-bootloader)
- [Enable flash encryption on boot](#314-enable-flash-encryption-on-boot)
### 3.15.2 Allow JTAG Debugging
"[Enable hardware Secure Boot in bootloader](#36-enable-hardware-secure-boot-in-bootloader)"の有効で表示
"[Enable flash encryption on boot](#314-enable-flash-encryption-on-boot)"の有効で表示
### 3.15.3 Allow app partition length not 64KB aligned
以下の有効で表示する。\
- [Requires signed app images](#31-requires-signed-app-images)
- [Enable hardware Secure Boot in bootloader](#36-enable-hardware-secure-boot-in-bootloader)
### 3.15.4 additional read protecting of efuses
### 3.15.5 Leave unused digest slots available (not revoke)
### 3.15.6 Leave UART bootloader encryption enable
"[Enable flash encryption on boot](#314-enable-flash-encryption-on-boot)"の有効で表示
### 3.15.7 Leave UART bootloader decryption enable
"[Enable flash encryption on boot](#314-enable-flash-encryption-on-boot)"の有効で表示
### 3.15.8 Leave UART bootloader flash cache enable
"[Enable flash encryption on boot](#314-enable-flash-encryption-on-boot)"の有効で表示
### 3.15.9 Require flash encryption to be already enable
"[Enable flash encryption on boot](#314-enable-flash-encryption-on-boot)"の有効で表示
### 3.15.10 Skip write-protection of DIS_CACHE
"[Enable flash encryption on boot](#314-enable-flash-encryption-on-boot)"の有効で表示
## 3.16 Encrypt only the app image that is present in the partition of type app
"[Enable flash encryption on boot](#314-enable-flash-encryption-on-boot)"の有効で表示
## 3.17 Check Flash Encryption enabled on app startup
"[Enable flash encryption on boot](#314-enable-flash-encryption-on-boot)"の有効で表示
## 3.18 UART ROM download mode
### 3.18.1 UART ROM download mode (Permanently disabled (recommended))
### 3.18.2 UART ROM download mode (Permanently switch to Secure mode(recommended))
### 3.18.3 UART ROM download mode (Enable (not recommended))
