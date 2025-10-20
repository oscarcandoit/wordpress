---
url: https://www.php.net/manual/en/ref.sodium.php
scraped_at: 2025-10-20T02:47:20.128Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Sodium Functions [¶](https://www.php.net/manual/en/ref.sodium.php\#ref.sodium)

## Table of Contents [¶](https://www.php.net/manual/en/ref.sodium.php\#ref.sodium)

- [sodium\_add](https://www.php.net/manual/en/function.sodium-add.php) — Add large numbers
- [sodium\_base642bin](https://www.php.net/manual/en/function.sodium-base642bin.php) — Decodes a base64-encoded string into raw binary.
- [sodium\_bin2base64](https://www.php.net/manual/en/function.sodium-bin2base64.php) — Encodes a raw binary string with base64.
- [sodium\_bin2hex](https://www.php.net/manual/en/function.sodium-bin2hex.php) — Encode to hexadecimal
- [sodium\_compare](https://www.php.net/manual/en/function.sodium-compare.php) — Compare large numbers
- [sodium\_crypto\_aead\_aegis128l\_decrypt](https://www.php.net/manual/en/function.sodium-crypto-aead-aegis128l-decrypt.php) — Verify then decrypt a message with AEGIS-128L
- [sodium\_crypto\_aead\_aegis128l\_encrypt](https://www.php.net/manual/en/function.sodium-crypto-aead-aegis128l-encrypt.php) — Encrypt then authenticate a message with AEGIS-128L
- [sodium\_crypto\_aead\_aegis128l\_keygen](https://www.php.net/manual/en/function.sodium-crypto-aead-aegis128l-keygen.php) — Generate a random AEGIS-128L key
- [sodium\_crypto\_aead\_aegis256\_decrypt](https://www.php.net/manual/en/function.sodium-crypto-aead-aegis256-decrypt.php) — Verify then decrypt a message with AEGIS-256
- [sodium\_crypto\_aead\_aegis256\_encrypt](https://www.php.net/manual/en/function.sodium-crypto-aead-aegis256-encrypt.php) — Encrypt then authenticate a message with AEGIS-256
- [sodium\_crypto\_aead\_aegis256\_keygen](https://www.php.net/manual/en/function.sodium-crypto-aead-aegis256-keygen.php) — Generate a random AEGIS-256 key
- [sodium\_crypto\_aead\_aes256gcm\_decrypt](https://www.php.net/manual/en/function.sodium-crypto-aead-aes256gcm-decrypt.php) — Verify then decrypt a message with AES-256-GCM
- [sodium\_crypto\_aead\_aes256gcm\_encrypt](https://www.php.net/manual/en/function.sodium-crypto-aead-aes256gcm-encrypt.php) — Encrypt then authenticate with AES-256-GCM
- [sodium\_crypto\_aead\_aes256gcm\_is\_available](https://www.php.net/manual/en/function.sodium-crypto-aead-aes256gcm-is-available.php) — Check if hardware supports AES256-GCM
- [sodium\_crypto\_aead\_aes256gcm\_keygen](https://www.php.net/manual/en/function.sodium-crypto-aead-aes256gcm-keygen.php) — Generate a random AES-256-GCM key
- [sodium\_crypto\_aead\_chacha20poly1305\_decrypt](https://www.php.net/manual/en/function.sodium-crypto-aead-chacha20poly1305-decrypt.php) — Verify then decrypt with ChaCha20-Poly1305
- [sodium\_crypto\_aead\_chacha20poly1305\_encrypt](https://www.php.net/manual/en/function.sodium-crypto-aead-chacha20poly1305-encrypt.php) — Encrypt then authenticate with ChaCha20-Poly1305
- [sodium\_crypto\_aead\_chacha20poly1305\_ietf\_decrypt](https://www.php.net/manual/en/function.sodium-crypto-aead-chacha20poly1305-ietf-decrypt.php) — Verify that the ciphertext includes a valid tag
- [sodium\_crypto\_aead\_chacha20poly1305\_ietf\_encrypt](https://www.php.net/manual/en/function.sodium-crypto-aead-chacha20poly1305-ietf-encrypt.php) — Encrypt a message
- [sodium\_crypto\_aead\_chacha20poly1305\_ietf\_keygen](https://www.php.net/manual/en/function.sodium-crypto-aead-chacha20poly1305-ietf-keygen.php) — Generate a random ChaCha20-Poly1305 (IETF) key.
- [sodium\_crypto\_aead\_chacha20poly1305\_keygen](https://www.php.net/manual/en/function.sodium-crypto-aead-chacha20poly1305-keygen.php) — Generate a random ChaCha20-Poly1305 key.
- [sodium\_crypto\_aead\_xchacha20poly1305\_ietf\_decrypt](https://www.php.net/manual/en/function.sodium-crypto-aead-xchacha20poly1305-ietf-decrypt.php) — (Preferred) Verify then decrypt with XChaCha20-Poly1305
- [sodium\_crypto\_aead\_xchacha20poly1305\_ietf\_encrypt](https://www.php.net/manual/en/function.sodium-crypto-aead-xchacha20poly1305-ietf-encrypt.php) — (Preferred) Encrypt then authenticate with XChaCha20-Poly1305
- [sodium\_crypto\_aead\_xchacha20poly1305\_ietf\_keygen](https://www.php.net/manual/en/function.sodium-crypto-aead-xchacha20poly1305-ietf-keygen.php) — Generate a random XChaCha20-Poly1305 key.
- [sodium\_crypto\_auth](https://www.php.net/manual/en/function.sodium-crypto-auth.php) — Compute a tag for the message
- [sodium\_crypto\_auth\_keygen](https://www.php.net/manual/en/function.sodium-crypto-auth-keygen.php) — Generate a random key for sodium\_crypto\_auth
- [sodium\_crypto\_auth\_verify](https://www.php.net/manual/en/function.sodium-crypto-auth-verify.php) — Verifies that the tag is valid for the message
- [sodium\_crypto\_box](https://www.php.net/manual/en/function.sodium-crypto-box.php) — Authenticated public-key encryption
- [sodium\_crypto\_box\_keypair](https://www.php.net/manual/en/function.sodium-crypto-box-keypair.php) — Randomly generate a secret key and a corresponding public key
- [sodium\_crypto\_box\_keypair\_from\_secretkey\_and\_publickey](https://www.php.net/manual/en/function.sodium-crypto-box-keypair-from-secretkey-and-publickey.php) — Create a unified keypair string from a secret key and public key
- [sodium\_crypto\_box\_open](https://www.php.net/manual/en/function.sodium-crypto-box-open.php) — Authenticated public-key decryption
- [sodium\_crypto\_box\_publickey](https://www.php.net/manual/en/function.sodium-crypto-box-publickey.php) — Extract the public key from a crypto\_box keypair
- [sodium\_crypto\_box\_publickey\_from\_secretkey](https://www.php.net/manual/en/function.sodium-crypto-box-publickey-from-secretkey.php) — Calculate the public key from a secret key
- [sodium\_crypto\_box\_seal](https://www.php.net/manual/en/function.sodium-crypto-box-seal.php) — Anonymous public-key encryption
- [sodium\_crypto\_box\_seal\_open](https://www.php.net/manual/en/function.sodium-crypto-box-seal-open.php) — Anonymous public-key decryption
- [sodium\_crypto\_box\_secretkey](https://www.php.net/manual/en/function.sodium-crypto-box-secretkey.php) — Extracts the secret key from a crypto\_box keypair
- [sodium\_crypto\_box\_seed\_keypair](https://www.php.net/manual/en/function.sodium-crypto-box-seed-keypair.php) — Deterministically derive the key pair from a single key
- [sodium\_crypto\_core\_ristretto255\_add](https://www.php.net/manual/en/function.sodium-crypto-core-ristretto255-add.php) — Adds an element
- [sodium\_crypto\_core\_ristretto255\_from\_hash](https://www.php.net/manual/en/function.sodium-crypto-core-ristretto255-from-hash.php) — Maps a vector
- [sodium\_crypto\_core\_ristretto255\_is\_valid\_point](https://www.php.net/manual/en/function.sodium-crypto-core-ristretto255-is-valid-point.php) — Determines if a point on the ristretto255 curve
- [sodium\_crypto\_core\_ristretto255\_random](https://www.php.net/manual/en/function.sodium-crypto-core-ristretto255-random.php) — Generates a random key
- [sodium\_crypto\_core\_ristretto255\_scalar\_add](https://www.php.net/manual/en/function.sodium-crypto-core-ristretto255-scalar-add.php) — Adds a scalar value
- [sodium\_crypto\_core\_ristretto255\_scalar\_complement](https://www.php.net/manual/en/function.sodium-crypto-core-ristretto255-scalar-complement.php) — The sodium\_crypto\_core\_ristretto255\_scalar\_complement purpose
- [sodium\_crypto\_core\_ristretto255\_scalar\_invert](https://www.php.net/manual/en/function.sodium-crypto-core-ristretto255-scalar-invert.php) — Inverts a scalar value
- [sodium\_crypto\_core\_ristretto255\_scalar\_mul](https://www.php.net/manual/en/function.sodium-crypto-core-ristretto255-scalar-mul.php) — Multiplies a scalar value
- [sodium\_crypto\_core\_ristretto255\_scalar\_negate](https://www.php.net/manual/en/function.sodium-crypto-core-ristretto255-scalar-negate.php) — Negates a scalar value
- [sodium\_crypto\_core\_ristretto255\_scalar\_random](https://www.php.net/manual/en/function.sodium-crypto-core-ristretto255-scalar-random.php) — Generates a random key
- [sodium\_crypto\_core\_ristretto255\_scalar\_reduce](https://www.php.net/manual/en/function.sodium-crypto-core-ristretto255-scalar-reduce.php) — Reduces a scalar value
- [sodium\_crypto\_core\_ristretto255\_scalar\_sub](https://www.php.net/manual/en/function.sodium-crypto-core-ristretto255-scalar-sub.php) — Subtracts a scalar value
- [sodium\_crypto\_core\_ristretto255\_sub](https://www.php.net/manual/en/function.sodium-crypto-core-ristretto255-sub.php) — Subtracts an element
- [sodium\_crypto\_generichash](https://www.php.net/manual/en/function.sodium-crypto-generichash.php) — Get a hash of the message
- [sodium\_crypto\_generichash\_final](https://www.php.net/manual/en/function.sodium-crypto-generichash-final.php) — Complete the hash
- [sodium\_crypto\_generichash\_init](https://www.php.net/manual/en/function.sodium-crypto-generichash-init.php) — Initialize a hash for streaming
- [sodium\_crypto\_generichash\_keygen](https://www.php.net/manual/en/function.sodium-crypto-generichash-keygen.php) — Generate a random generichash key
- [sodium\_crypto\_generichash\_update](https://www.php.net/manual/en/function.sodium-crypto-generichash-update.php) — Add message to a hash
- [sodium\_crypto\_kdf\_derive\_from\_key](https://www.php.net/manual/en/function.sodium-crypto-kdf-derive-from-key.php) — Derive a subkey
- [sodium\_crypto\_kdf\_keygen](https://www.php.net/manual/en/function.sodium-crypto-kdf-keygen.php) — Generate a random root key for the KDF interface
- [sodium\_crypto\_kx\_client\_session\_keys](https://www.php.net/manual/en/function.sodium-crypto-kx-client-session-keys.php) — Calculate the client-side session keys.
- [sodium\_crypto\_kx\_keypair](https://www.php.net/manual/en/function.sodium-crypto-kx-keypair.php) — Creates a new sodium keypair
- [sodium\_crypto\_kx\_publickey](https://www.php.net/manual/en/function.sodium-crypto-kx-publickey.php) — Extract the public key from a crypto\_kx keypair
- [sodium\_crypto\_kx\_secretkey](https://www.php.net/manual/en/function.sodium-crypto-kx-secretkey.php) — Extract the secret key from a crypto\_kx keypair.
- [sodium\_crypto\_kx\_seed\_keypair](https://www.php.net/manual/en/function.sodium-crypto-kx-seed-keypair.php) — Description
- [sodium\_crypto\_kx\_server\_session\_keys](https://www.php.net/manual/en/function.sodium-crypto-kx-server-session-keys.php) — Calculate the server-side session keys.
- [sodium\_crypto\_pwhash](https://www.php.net/manual/en/function.sodium-crypto-pwhash.php) — Derive a key from a password, using Argon2
- [sodium\_crypto\_pwhash\_scryptsalsa208sha256](https://www.php.net/manual/en/function.sodium-crypto-pwhash-scryptsalsa208sha256.php) — Derives a key from a password, using scrypt
- [sodium\_crypto\_pwhash\_scryptsalsa208sha256\_str](https://www.php.net/manual/en/function.sodium-crypto-pwhash-scryptsalsa208sha256-str.php) — Get an ASCII encoded hash
- [sodium\_crypto\_pwhash\_scryptsalsa208sha256\_str\_verify](https://www.php.net/manual/en/function.sodium-crypto-pwhash-scryptsalsa208sha256-str-verify.php) — Verify that the password is a valid password verification string
- [sodium\_crypto\_pwhash\_str](https://www.php.net/manual/en/function.sodium-crypto-pwhash-str.php) — Get an ASCII-encoded hash
- [sodium\_crypto\_pwhash\_str\_needs\_rehash](https://www.php.net/manual/en/function.sodium-crypto-pwhash-str-needs-rehash.php) — Determine whether or not to rehash a password
- [sodium\_crypto\_pwhash\_str\_verify](https://www.php.net/manual/en/function.sodium-crypto-pwhash-str-verify.php) — Verifies that a password matches a hash
- [sodium\_crypto\_scalarmult](https://www.php.net/manual/en/function.sodium-crypto-scalarmult.php) — Compute a shared secret given a user's secret key and another user's public key
- [sodium\_crypto\_scalarmult\_base](https://www.php.net/manual/en/function.sodium-crypto-scalarmult-base.php) — Alias of sodium\_crypto\_box\_publickey\_from\_secretkey
- [sodium\_crypto\_scalarmult\_ristretto255](https://www.php.net/manual/en/function.sodium-crypto-scalarmult-ristretto255.php) — Computes a shared secret
- [sodium\_crypto\_scalarmult\_ristretto255\_base](https://www.php.net/manual/en/function.sodium-crypto-scalarmult-ristretto255-base.php) — Calculates the public key from a secret key
- [sodium\_crypto\_secretbox](https://www.php.net/manual/en/function.sodium-crypto-secretbox.php) — Authenticated shared-key encryption
- [sodium\_crypto\_secretbox\_keygen](https://www.php.net/manual/en/function.sodium-crypto-secretbox-keygen.php) — Generate random key for sodium\_crypto\_secretbox
- [sodium\_crypto\_secretbox\_open](https://www.php.net/manual/en/function.sodium-crypto-secretbox-open.php) — Authenticated shared-key decryption
- [sodium\_crypto\_secretstream\_xchacha20poly1305\_init\_pull](https://www.php.net/manual/en/function.sodium-crypto-secretstream-xchacha20poly1305-init-pull.php) — Initialize a secretstream context for decryption
- [sodium\_crypto\_secretstream\_xchacha20poly1305\_init\_push](https://www.php.net/manual/en/function.sodium-crypto-secretstream-xchacha20poly1305-init-push.php) — Initialize a secretstream context for encryption
- [sodium\_crypto\_secretstream\_xchacha20poly1305\_keygen](https://www.php.net/manual/en/function.sodium-crypto-secretstream-xchacha20poly1305-keygen.php) — Generate a random secretstream key.
- [sodium\_crypto\_secretstream\_xchacha20poly1305\_pull](https://www.php.net/manual/en/function.sodium-crypto-secretstream-xchacha20poly1305-pull.php) — Decrypt a chunk of data from an encrypted stream
- [sodium\_crypto\_secretstream\_xchacha20poly1305\_push](https://www.php.net/manual/en/function.sodium-crypto-secretstream-xchacha20poly1305-push.php) — Encrypt a chunk of data so that it can safely be decrypted in a streaming API
- [sodium\_crypto\_secretstream\_xchacha20poly1305\_rekey](https://www.php.net/manual/en/function.sodium-crypto-secretstream-xchacha20poly1305-rekey.php) — Explicitly rotate the key in the secretstream state
- [sodium\_crypto\_shorthash](https://www.php.net/manual/en/function.sodium-crypto-shorthash.php) — Compute a short hash of a message and key
- [sodium\_crypto\_shorthash\_keygen](https://www.php.net/manual/en/function.sodium-crypto-shorthash-keygen.php) — Get random bytes for key
- [sodium\_crypto\_sign](https://www.php.net/manual/en/function.sodium-crypto-sign.php) — Sign a message
- [sodium\_crypto\_sign\_detached](https://www.php.net/manual/en/function.sodium-crypto-sign-detached.php) — Sign the message
- [sodium\_crypto\_sign\_ed25519\_pk\_to\_curve25519](https://www.php.net/manual/en/function.sodium-crypto-sign-ed25519-pk-to-curve25519.php) — Convert an Ed25519 public key to a Curve25519 public key
- [sodium\_crypto\_sign\_ed25519\_sk\_to\_curve25519](https://www.php.net/manual/en/function.sodium-crypto-sign-ed25519-sk-to-curve25519.php) — Convert an Ed25519 secret key to a Curve25519 secret key
- [sodium\_crypto\_sign\_keypair](https://www.php.net/manual/en/function.sodium-crypto-sign-keypair.php) — Randomly generate a secret key and a corresponding public key
- [sodium\_crypto\_sign\_keypair\_from\_secretkey\_and\_publickey](https://www.php.net/manual/en/function.sodium-crypto-sign-keypair-from-secretkey-and-publickey.php) — Join a secret key and public key together
- [sodium\_crypto\_sign\_open](https://www.php.net/manual/en/function.sodium-crypto-sign-open.php) — Check that the signed message has a valid signature
- [sodium\_crypto\_sign\_publickey](https://www.php.net/manual/en/function.sodium-crypto-sign-publickey.php) — Extract the Ed25519 public key from a keypair
- [sodium\_crypto\_sign\_publickey\_from\_secretkey](https://www.php.net/manual/en/function.sodium-crypto-sign-publickey-from-secretkey.php) — Extract the Ed25519 public key from the secret key
- [sodium\_crypto\_sign\_secretkey](https://www.php.net/manual/en/function.sodium-crypto-sign-secretkey.php) — Extract the Ed25519 secret key from a keypair
- [sodium\_crypto\_sign\_seed\_keypair](https://www.php.net/manual/en/function.sodium-crypto-sign-seed-keypair.php) — Deterministically derive the key pair from a single key
- [sodium\_crypto\_sign\_verify\_detached](https://www.php.net/manual/en/function.sodium-crypto-sign-verify-detached.php) — Verify signature for the message
- [sodium\_crypto\_stream](https://www.php.net/manual/en/function.sodium-crypto-stream.php) — Generate a deterministic sequence of bytes from a seed
- [sodium\_crypto\_stream\_keygen](https://www.php.net/manual/en/function.sodium-crypto-stream-keygen.php) — Generate a random sodium\_crypto\_stream key.
- [sodium\_crypto\_stream\_xchacha20](https://www.php.net/manual/en/function.sodium-crypto-stream-xchacha20.php) — Expands the key and nonce into a keystream of pseudorandom bytes
- [sodium\_crypto\_stream\_xchacha20\_keygen](https://www.php.net/manual/en/function.sodium-crypto-stream-xchacha20-keygen.php) — Returns a secure random key
- [sodium\_crypto\_stream\_xchacha20\_xor](https://www.php.net/manual/en/function.sodium-crypto-stream-xchacha20-xor.php) — Encrypts a message using a nonce and a secret key (no authentication)
- [sodium\_crypto\_stream\_xchacha20\_xor\_ic](https://www.php.net/manual/en/function.sodium-crypto-stream-xchacha20-xor-ic.php) — Encrypts a message using a nonce and a secret key (no authentication)
- [sodium\_crypto\_stream\_xor](https://www.php.net/manual/en/function.sodium-crypto-stream-xor.php) — Encrypt a message without authentication
- [sodium\_hex2bin](https://www.php.net/manual/en/function.sodium-hex2bin.php) — Decodes a hexadecimally encoded binary string
- [sodium\_increment](https://www.php.net/manual/en/function.sodium-increment.php) — Increment large number
- [sodium\_memcmp](https://www.php.net/manual/en/function.sodium-memcmp.php) — Test for equality in constant-time
- [sodium\_memzero](https://www.php.net/manual/en/function.sodium-memzero.php) — Overwrite a string with NUL characters
- [sodium\_pad](https://www.php.net/manual/en/function.sodium-pad.php) — Add padding data
- [sodium\_unpad](https://www.php.net/manual/en/function.sodium-unpad.php) — Remove padding data

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/sodium/reference.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fref.sodium%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=ref.sodium&repo=en&redirect=https://www.php.net/manual/en/ref.sodium.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google