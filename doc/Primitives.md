# Cryptography Primitives used in Halite

* Symmetric-key encryption: [**Xsalsa20**](https://paragonie.com/book/pecl-libsodium/read/08-advanced.md#crypto-stream)
* Symmetric-key authentication: **[HMAC-SHA512/256](https://paragonie.com/book/pecl-libsodium/read/04-secretkey-crypto.md#crypto-auth)**
* Asymmetric-key encryption: [**X25519**](https://paragonie.com/book/pecl-libsodium/read/08-advanced.md#crypto-scalarmult) followed by [symmetric-key authenticated encryption](https://paragonie.com/book/pecl-libsodium/read/04-secretkey-crypto.md#crypto-secretbox)
* Asymmetric-key digital signatures: [**Ed25519**](https://paragonie.com/book/pecl-libsodium/read/05-publickey-crypto.md#crypto-sign)
* Checksums ([File](Classes/File.md) only): [**BLAKE2b**](https://paragonie.com/book/pecl-libsodium/read/06-hashing.md#crypto-generichash)
* Key splitting: [**HKDF-BLAKE2b**](Classes/Util.md)
* Password-Based Key Derivation:
    * Version 2: [**Argon2**](https://paragonie.com/book/pecl-libsodium/read/07-password-hashing.md#crypto-pwhash-str)
    * Version 1: [**Scrypt**](https://paragonie.com/book/pecl-libsodium/read/07-password-hashing.md#crypto-pwhash-scryptsalsa208sha256-str)

In all cases, we follow an Encrypt then MAC construction, thus avoiding the [cryptographic doom principle](http://www.thoughtcrime.org/blog/the-cryptographic-doom-principle).