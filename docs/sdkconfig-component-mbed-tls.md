# 9.58 mbedTLS
mbedTLSの設定を記載。

- [9.58 mbedTLS](#958-mbedtls)
  - [9.58.1 Memory allocation strategy](#9581-memory-allocation-strategy)
  - [9.58.2 TLS maximum message content length](#9582-tls-maximum-message-content-length)
  - [9.58.3 Asymmetric in/out fragment length](#9583-asymmetric-inout-fragment-length)
  - [9.58.4 TLS maximum incoming fragment length](#9584-tls-maximum-incoming-fragment-length)
  - [9.58.5 TLS maximum outgoing fragment length](#9585-tls-maximum-outgoing-fragment-length)
  - [9.58.6 Using dynamic TX/RX buffer](#9586-using-dynamic-txrx-buffer)
    - [9.58.6.1 Free private key and DHM data after its usage](#95861-free-private-key-and-dhm-data-after-its-usage)
      - [9.58.6.1.1 Free SSL CA certificate after its usage](#958611-free-ssl-ca-certificate-after-its-usage)
  - [9.58.7 Enable mbedTLS debugging](#9587-enable-mbedtls-debugging)
    - [9.58.7.1 Set mbedTLS debugging level](#95871-set-mbedtls-debugging-level)
  - [9.58.8 mbedTLS v3.x related](#9588-mbedtls-v3x-related)
    - [9.58.8.1 Support TLS 1.3 protocol](#95881-support-tls-13-protocol)
      - [9.58.8.1.1 TLS 1.3 related configurations](#958811-tls-13-related-configurations)
        - [9.58.8.1.1.1 TLS 1.3 middlebox compatibility mode](#9588111-tls-13-middlebox-compatibility-mode)
        - [9.58.8.1.1.2 TLS 1.3 PSK key exchange mode](#9588112-tls-13-psk-key-exchange-mode)
        - [9.58.8.1.1.3 TLS 1.3 ephemeral key exchanged mode](#9588113-tls-13-ephemeral-key-exchanged-mode)
        - [9.58.8.1.1.4 TLS 1.3 PSK ephemeral key exchange mode](#9588114-tls-13-psk-ephemeral-key-exchange-mode)
    - [9.58.8.2 Variable SSL buffer length](#95882-variable-ssl-buffer-length)
    - [9.58.8.3 Use a backward compatible ECDH context (Experimental)](#95883-use-a-backward-compatible-ecdh-context-experimental)
    - [9.58.8.4 Enable trusted certificate callbacks](#95884-enable-trusted-certificate-callbacks)
    - [9.58.8.5 Enable serialization of the TLS context structures](#95885-enable-serialization-of-the-tls-context-structures)
    - [9.58.8.6 Keep peer certificate after handshake completion](#95886-keep-peer-certificate-after-handshake-completion)
    - [9.58.8.7 Enable PKCS #7](#95887-enable-pkcs-7)
    - [9.58.8.8 Record plaintext padding](#95888-record-plaintext-padding)
    - [9.58.8.9 DTLS-based configurations](#95889-dtls-based-configurations)
      - [9.58.8.9.1 Support for the DTLS Connection ID extension](#958891-support-for-the-dtls-connection-id-extension)
      - [9.58.8.9.1.1 Maximum length of CIDs used for incoming DTLS messages](#9588911-maximum-length-of-cids-used-for-incoming-dtls-messages)
      - [9.58.8.9.1.2 Maximum length of CIDs used for outgoing DTLS messages](#9588912-maximum-length-of-cids-used-for-outgoing-dtls-messages)
      - [9.58.8.9.2 Enable support for negotiation of DTLS-SRTP (RFC 5764)](#958892-enable-support-for-negotiation-of-dtls-srtp-rfc-5764)
  - [9.58.9 Certificate Bundle](#9589-certificate-bundle)
    - [9.58.9.1 Enable trusted root certificate bundle](#95891-enable-trusted-root-certificate-bundle)
      - [9.58.9.1.1 Default certificate bundle options](#958911-default-certificate-bundle-options)
      - [9.58.9.1.2 Add custom certificates to the default bundle](#958912-add-custom-certificates-to-the-default-bundle)
        - [9.58.9.1.2.1 Custom certificate bundle path](#9589121-custom-certificate-bundle-path)
      - [9.58.9.1.3 Add deprecated root certificate](#958913-add-deprecated-root-certificate)
      - [9.58.9.1.4 Maximum no of certificates allowed in certificate bundle](#958914-maximum-no-of-certificates-allowed-in-certificate-bundle)
  - [9.58.10 Enable mbedTLS ecp restartable](#95810-enable-mbedtls-ecp-restartable)
  - [9.58.11 Enable CMAC mode for block ciphers](#95811-enable-cmac-mode-for-block-ciphers)
  - [9.58.12 Enable hardware AES acceleration](#95812-enable-hardware-aes-acceleration)
    - [9.58.12.1 Use interrupt for long AES operations](#958121-use-interrupt-for-long-aes-operations)
      - [9.58.12.1.1 AES hardware interrupt level](#9581211-aes-hardware-interrupt-level)
    - [9.58.12.2 Enable partially hardware accelerated GCM](#958122-enable-partially-hardware-accelerated-gcm)
    - [9.58.12.3 Enable support for non-AES ciphers in GCM operation](#958123-enable-support-for-non-aes-ciphers-in-gcm-operation)
  - [9.58.13 Enable hardware MPI (bignum) acceleration](#95813-enable-hardware-mpi-bignum-acceleration)
    - [9.58.13.1 Fallback to software implementation for larger MPI values](#958131-fallback-to-software-implementation-for-larger-mpi-values)
    - [9.58.13.2 Use interrupt for MPI exp-mod operations](#958132-use-interrupt-for-mpi-exp-mod-operations)
      - [9.58.13.2.1 MPI hardware interrupt level](#9581321-mpi-hardware-interrupt-level)
  - [9.58.14 Enable hardware SHA acceleration](#95814-enable-hardware-sha-acceleration)
  - [9.58.15 Enable hardware ECC acceleration](#95815-enable-hardware-ecc-acceleration)
    - [9.58.15.1 Fallback to software implementation for curves not supported in hardware](#958151-fallback-to-software-implementation-for-curves-not-supported-in-hardware)
  - [9.58.16 Use MD5 implementation](#95816-use-md5-implementation)
  - [9.58.17 Enable ECDSA signing using on-chip ECDSA peripheral](#95817-enable-ecdsa-signing-using-on-chip-ecdsa-peripheral)
  - [9.58.18 Enable ECDSA signature verification using on-chip ECDSA peripheral](#95818-enable-ecdsa-signature-verification-using-on-chip-ecdsa-peripheral)
  - [9.58.19 Enable hardware ECDSA sign acceleration when using ATECC608A](#95819-enable-hardware-ecdsa-sign-acceleration-when-using-atecc608a)
  - [9.58.20 Enable hardware ECDSA verify acceleration when using ATECC608A](#95820-enable-hardware-ecdsa-verify-acceleration-when-using-atecc608a)
  - [9.58.21 Enable mbedtls time support](#95821-enable-mbedtls-time-support)
    - [9.58.21.1 Enable mbedtls time support: platform-specific](#958211-enable-mbedtls-time-support-platform-specific)
    - [9.58.21.1 Enable mbedtls verify acceleration expiry check](#958211-enable-mbedtls-verify-acceleration-expiry-check)
  - [9.58.22 Enable deterministic ECDSA](#95822-enable-deterministic-ecdsa)
  - [9.58.23 Enable the SHA-384 and SHA-512 cryptographic hash algorithm](#95823-enable-the-sha-384-and-sha-512-cryptographic-hash-algorithm)
  - [9.58.24 TLS Protocol Role](#95824-tls-protocol-role)
  - [9.58.25 TLS Key Exchange Methods](#95825-tls-key-exchange-methods)
    - [9.58.25.1 Enable pre-shared-key ciphersuites](#958251-enable-pre-shared-key-ciphersuites)
      - [9.58.25.1.1 Enable PSK based ciphersuite modes](#9582511-enable-psk-based-ciphersuite-modes)
      - [9.58.25.1.2 Enable DHE-PSK based ciphersuite modes](#9582512-enable-dhe-psk-based-ciphersuite-modes)
      - [9.58.25.1.3 Enable ECDHE-PSK based ciphersuite modes](#9582513-enable-ecdhe-psk-based-ciphersuite-modes)
      - [9.58.25.1.4 Enable RSA-PSK based ciphersuite modes](#9582514-enable-rsa-psk-based-ciphersuite-modes)
    - [9.58.25.2 Enable RSA-only based ciphersuite modes](#958252-enable-rsa-only-based-ciphersuite-modes)
    - [9.58.25.3 Enable DHE-RSA based ciphersuite modes](#958253-enable-dhe-rsa-based-ciphersuite-modes)
    - [9.58.25.4 Support Elliptic Curve based ciphersuites](#958254-support-elliptic-curve-based-ciphersuites)
      - [9.58.25.4.1 Enable ECDHE-RSA based ciphersuite modes](#9582541-enable-ecdhe-rsa-based-ciphersuite-modes)
      - [9.58.25.4.2 Enable ECDHE-ECDSA based ciphersuite modes](#9582542-enable-ecdhe-ecdsa-based-ciphersuite-modes)
      - [9.58.25.4.3 Enable ECDH-ECDSA based ciphersuite modes](#9582543-enable-ecdh-ecdsa-based-ciphersuite-modes)
      - [9.58.25.4.4 Enable ECDH-RSA based ciphersuite modes](#9582544-enable-ecdh-rsa-based-ciphersuite-modes)
    - [9.58.25.5 Enable ECJPAKE based ciphersuite modes](#958255-enable-ecjpake-based-ciphersuite-modes)
  - [9.58.26 Support TLS renegotiation](#95826-support-tls-renegotiation)
  - [9.58.27 Support TLS 1.2 protocol](#95827-support-tls-12-protocol)
  - [9.58.28 Support GM/T SSL 1.1 protocol](#95828-support-gmt-ssl-11-protocol)
  - [9.58.29 Support DTLS protocol  (all versions)](#95829-support-dtls-protocol--all-versions)
  - [9.58.30 Support ALPN (application Layer Protocol Negotiation)](#95830-support-alpn-application-layer-protocol-negotiation)
  - [9.58.31 TLS: Client Support for RFC 5077 SSL session tickets](#95831-tls-client-support-for-rfc-5077-ssl-session-tickets)
  - [9.58.32 TLS: Server Support for RFC 5077 SSL session tickets](#95832-tls-server-support-for-rfc-5077-ssl-session-tickets)
  - [9.58.33 Symmetric Ciphers](#95833-symmetric-ciphers)
    - [9.58.33.1 AES block cipher](#958331-aes-block-cipher)
    - [9.58.33.2 Camellia block cipher](#958332-camellia-block-cipher)
    - [9.58.33.3 DES block cipher (legacy, insecure)](#958333-des-block-cipher-legacy-insecure)
    - [9.58.33.4 Blowfish block cipher](#958334-blowfish-block-cipher)
    - [9.58.33.5 XTEA block cipher](#958335-xtea-block-cipher)
    - [9.58.33.6 CCM (Counter with CBC-MAC) block cipher modes](#958336-ccm-counter-with-cbc-mac-block-cipher-modes)
    - [9.58.33.7 GCM (Galois/Counter) block cipher modes](#958337-gcm-galoiscounter-block-cipher-modes)
    - [9.58.33.8 NIST key wrapping (KW) and KW padding (KWP)](#958338-nist-key-wrapping-kw-and-kw-padding-kwp)
  - [9.58.34 Enable RIPEMD-160 hash algorithm](#95834-enable-ripemd-160-hash-algorithm)
  - [9.58.35 Certificates](#95835-certificates)
    - [9.58.35.1 Read \& Parse PEM formatted certificates](#958351-read--parse-pem-formatted-certificates)
    - [9.58.35.2 Write PEM formatted certificates](#958352-write-pem-formatted-certificates)
    - [9.58.35.3 X.509 CRL parsing](#958353-x509-crl-parsing)
    - [9.58.35.4 X.509 CSR parsing](#958354-x509-csr-parsing)
  - [9.58.36 Elliptic Curve Ciphers](#95836-elliptic-curve-ciphers)
  - [9.58.37 Diffie-Hellman-Merkle key exchange (DHM)](#95837-diffie-hellman-merkle-key-exchange-dhm)
  - [9.58.38 Elliptic Curve Diffie-Hellman (ECDH)](#95838-elliptic-curve-diffie-hellman-ecdh)
    - [9.58.38.1 Elliptic Curve DSA](#958381-elliptic-curve-dsa)
  - [9.58.39 Elliptic curve J-PAKE](#95839-elliptic-curve-j-pake)
  - [9.58.40 Enable SECP192R1 curve](#95840-enable-secp192r1-curve)
  - [9.58.41 Enable SECP224R1 curve](#95841-enable-secp224r1-curve)
  - [9.58.42 Enable SECP256R1 curve](#95842-enable-secp256r1-curve)
  - [9.58.43 Enable SECP384R1 curve](#95843-enable-secp384r1-curve)
  - [9.58.44 Enable SECP521R1 curve](#95844-enable-secp521r1-curve)
  - [9.58.45 Enable SECP192K1 curve](#95845-enable-secp192k1-curve)
  - [9.58.46 Enable SECP224K1 curve](#95846-enable-secp224k1-curve)
  - [9.58.47 Enable SECP256K1 curve](#95847-enable-secp256k1-curve)
  - [9.58.48 Enable BP256R1 curve](#95848-enable-bp256r1-curve)
  - [9.58.49 Enable BP384R1 curve](#95849-enable-bp384r1-curve)
  - [9.58.50 Enable BP512R1 curve](#95850-enable-bp512r1-curve)
  - [9.58.51 CURVE2519 curve](#95851-curve2519-curve)
  - [9.58.52 NIST 'modulo p' optimisations](#95852-nist-modulo-p-optimisations)
  - [9.58.53 Enable fixed-point multiplication optimisations](#95853-enable-fixed-point-multiplication-optimisations)
  - [9.58.54 Poly1305 MAC algorithm](#95854-poly1305-mac-algorithm)
  - [9.58.55 Chacha20 stream cipher](#95855-chacha20-stream-cipher)
    - [9.58.55.1 Chacha20-Poly1305 AEAD algorithm](#958551-chacha20-poly1305-aead-algorithm)
  - [9.58.56 HKDF algorithm (RFC 5869)](#95856-hkdf-algorithm-rfc-5869)
  - [9.58.57 Enable the threading abstraction layer](#95857-enable-the-threading-abstraction-layer)
    - [9.58.57.1 Enable threading alternate implementation](#958571-enable-threading-alternate-implementation)
    - [9.58.57.2 Enable threading pthread implementation](#958572-enable-threading-pthread-implementation)
  - [9.58.58 Enable error code to error string conversion](#95858-enable-error-code-to-error-string-conversion)
  - [9.58.59 Use ROM implementation of the crypto algorithm](#95859-use-rom-implementation-of-the-crypto-algorithm)


## 9.58.1 Memory allocation strategy
- Internal memory
- External SPIRAM
- Default alloc mode
- Custom alloc mode
- Internal IRAM
## 9.58.2 TLS maximum message content length
## 9.58.3 Asymmetric in/out fragment length
## 9.58.4 TLS maximum incoming fragment length
## 9.58.5 TLS maximum outgoing fragment length
## 9.58.6 Using dynamic TX/RX buffer
### 9.58.6.1 Free private key and DHM data after its usage
#### 9.58.6.1.1 Free SSL CA certificate after its usage
## 9.58.7 Enable mbedTLS debugging
### 9.58.7.1 Set mbedTLS debugging level
- Warning
- Info
- Debug
- Verbose
## 9.58.8 mbedTLS v3.x related
### 9.58.8.1 Support TLS 1.3 protocol
#### 9.58.8.1.1 TLS 1.3 related configurations
##### 9.58.8.1.1.1 TLS 1.3 middlebox compatibility mode
##### 9.58.8.1.1.2 TLS 1.3 PSK key exchange mode
##### 9.58.8.1.1.3 TLS 1.3 ephemeral key exchanged mode
##### 9.58.8.1.1.4 TLS 1.3 PSK ephemeral key exchange mode
### 9.58.8.2 Variable SSL buffer length
### 9.58.8.3 Use a backward compatible ECDH context (Experimental)
### 9.58.8.4 Enable trusted certificate callbacks
### 9.58.8.5 Enable serialization of the TLS context structures
### 9.58.8.6 Keep peer certificate after handshake completion
### 9.58.8.7 Enable PKCS #7
### 9.58.8.8 Record plaintext padding
### 9.58.8.9 DTLS-based configurations
#### 9.58.8.9.1 Support for the DTLS Connection ID extension
#### 9.58.8.9.1.1 Maximum length of CIDs used for incoming DTLS messages
#### 9.58.8.9.1.2 Maximum length of CIDs used for outgoing DTLS messages
#### 9.58.8.9.2 Enable support for negotiation of DTLS-SRTP (RFC 5764)
## 9.58.9 Certificate Bundle
### 9.58.9.1 Enable trusted root certificate bundle
#### 9.58.9.1.1 Default certificate bundle options
- Use the full default certificate bundle
- Use only the most common certificates from the default bundles
- Do not use the default certificate bundle
#### 9.58.9.1.2 Add custom certificates to the default bundle
##### 9.58.9.1.2.1 Custom certificate bundle path
#### 9.58.9.1.3 Add deprecated root certificate
#### 9.58.9.1.4 Maximum no of certificates allowed in certificate bundle
## 9.58.10 Enable mbedTLS ecp restartable
## 9.58.11 Enable CMAC mode for block ciphers
## 9.58.12 Enable hardware AES acceleration
### 9.58.12.1 Use interrupt for long AES operations
#### 9.58.12.1.1 AES hardware interrupt level
### 9.58.12.2 Enable partially hardware accelerated GCM
### 9.58.12.3 Enable support for non-AES ciphers in GCM operation
## 9.58.13 Enable hardware MPI (bignum) acceleration
### 9.58.13.1 Fallback to software implementation for larger MPI values
### 9.58.13.2 Use interrupt for MPI exp-mod operations
#### 9.58.13.2.1 MPI hardware interrupt level
## 9.58.14 Enable hardware SHA acceleration
## 9.58.15 Enable hardware ECC acceleration
### 9.58.15.1 Fallback to software implementation for curves not supported in hardware
## 9.58.16 Use MD5 implementation
## 9.58.17 Enable ECDSA signing using on-chip ECDSA peripheral
## 9.58.18 Enable ECDSA signature verification using on-chip ECDSA peripheral
## 9.58.19 Enable hardware ECDSA sign acceleration when using ATECC608A
## 9.58.20 Enable hardware ECDSA verify acceleration when using ATECC608A
## 9.58.21 Enable mbedtls time support
### 9.58.21.1 Enable mbedtls time support: platform-specific
### 9.58.21.1 Enable mbedtls verify acceleration expiry check
## 9.58.22 Enable deterministic ECDSA
## 9.58.23 Enable the SHA-384 and SHA-512 cryptographic hash algorithm
## 9.58.24 TLS Protocol Role
- Server & Client
- Server
- Client
- None
## 9.58.25 TLS Key Exchange Methods
### 9.58.25.1 Enable pre-shared-key ciphersuites
#### 9.58.25.1.1 Enable PSK based ciphersuite modes
#### 9.58.25.1.2 Enable DHE-PSK based ciphersuite modes
#### 9.58.25.1.3 Enable ECDHE-PSK based ciphersuite modes
#### 9.58.25.1.4 Enable RSA-PSK based ciphersuite modes
### 9.58.25.2 Enable RSA-only based ciphersuite modes
### 9.58.25.3 Enable DHE-RSA based ciphersuite modes
### 9.58.25.4 Support Elliptic Curve based ciphersuites
#### 9.58.25.4.1 Enable ECDHE-RSA based ciphersuite modes
#### 9.58.25.4.2 Enable ECDHE-ECDSA based ciphersuite modes
#### 9.58.25.4.3 Enable ECDH-ECDSA based ciphersuite modes
#### 9.58.25.4.4 Enable ECDH-RSA based ciphersuite modes
### 9.58.25.5 Enable ECJPAKE based ciphersuite modes
## 9.58.26 Support TLS renegotiation
## 9.58.27 Support TLS 1.2 protocol
## 9.58.28 Support GM/T SSL 1.1 protocol
## 9.58.29 Support DTLS protocol  (all versions)
## 9.58.30 Support ALPN (application Layer Protocol Negotiation)
## 9.58.31 TLS: Client Support for RFC 5077 SSL session tickets
## 9.58.32 TLS: Server Support for RFC 5077 SSL session tickets
## 9.58.33 Symmetric Ciphers
### 9.58.33.1 AES block cipher
### 9.58.33.2 Camellia block cipher
### 9.58.33.3 DES block cipher (legacy, insecure)
### 9.58.33.4 Blowfish block cipher
### 9.58.33.5 XTEA block cipher
### 9.58.33.6 CCM (Counter with CBC-MAC) block cipher modes
### 9.58.33.7 GCM (Galois/Counter) block cipher modes
### 9.58.33.8 NIST key wrapping (KW) and KW padding (KWP)
## 9.58.34 Enable RIPEMD-160 hash algorithm
## 9.58.35 Certificates
### 9.58.35.1 Read & Parse PEM formatted certificates
### 9.58.35.2 Write PEM formatted certificates
### 9.58.35.3 X.509 CRL parsing
### 9.58.35.4 X.509 CSR parsing
## 9.58.36 Elliptic Curve Ciphers
## 9.58.37 Diffie-Hellman-Merkle key exchange (DHM)
## 9.58.38 Elliptic Curve Diffie-Hellman (ECDH)
### 9.58.38.1 Elliptic Curve DSA
## 9.58.39 Elliptic curve J-PAKE
## 9.58.40 Enable SECP192R1 curve
## 9.58.41 Enable SECP224R1 curve
## 9.58.42 Enable SECP256R1 curve
## 9.58.43 Enable SECP384R1 curve
## 9.58.44 Enable SECP521R1 curve
## 9.58.45 Enable SECP192K1 curve
## 9.58.46 Enable SECP224K1 curve
## 9.58.47 Enable SECP256K1 curve
## 9.58.48 Enable BP256R1 curve
## 9.58.49 Enable BP384R1 curve
## 9.58.50 Enable BP512R1 curve
## 9.58.51 CURVE2519 curve
## 9.58.52 NIST 'modulo p' optimisations
## 9.58.53 Enable fixed-point multiplication optimisations
## 9.58.54 Poly1305 MAC algorithm
## 9.58.55 Chacha20 stream cipher
### 9.58.55.1 Chacha20-Poly1305 AEAD algorithm
## 9.58.56 HKDF algorithm (RFC 5869)
## 9.58.57 Enable the threading abstraction layer
### 9.58.57.1 Enable threading alternate implementation
### 9.58.57.2 Enable threading pthread implementation
## 9.58.58 Enable error code to error string conversion
## 9.58.59 Use ROM implementation of the crypto algorithm
