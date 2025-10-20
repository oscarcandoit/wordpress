---
url: https://www.php.net/manual/en/migration81.constants.php
scraped_at: 2025-10-20T02:35:19.848Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## New Global Constants [¶](https://www.php.net/manual/en/migration81.constants.php\#migration81.constants)

### cURL [¶](https://www.php.net/manual/en/migration81.constants.php\#migration81.constants.curl)

- **`[CURLOPT\_DOH\_URL](https://www.php.net/manual/en/curl.constants.php#constant.curlopt-doh-url)`**
- **`[CURLOPT\_ISSUERCERT\_BLOB](https://www.php.net/manual/en/curl.constants.php#constant.curlopt-issuercert-blob)`**
- **`[CURLOPT\_PROXY\_ISSUERCERT](https://www.php.net/manual/en/curl.constants.php#constant.curlopt-proxy-issuercert)`**
- **`[CURLOPT\_PROXY\_ISSUERCERT\_BLOB](https://www.php.net/manual/en/curl.constants.php#constant.curlopt-proxy-issuercert-blob)`**
- **`[CURLOPT\_PROXY\_SSLCERT\_BLOB](https://www.php.net/manual/en/curl.constants.php#constant.curlopt-proxy-sslcert-blob)`**
- **`[CURLOPT\_PROXY\_SSLKEY\_BLOB](https://www.php.net/manual/en/curl.constants.php#constant.curlopt-proxy-sslkey-blob)`**
- **`[CURLOPT\_SSLCERT\_BLOB](https://www.php.net/manual/en/curl.constants.php#constant.curlopt-sslcert-blob)`**
- **`[CURLOPT\_SSLKEY\_BLOB](https://www.php.net/manual/en/curl.constants.php#constant.curlopt-sslkey-blob)`**

### GD [¶](https://www.php.net/manual/en/migration81.constants.php\#migration81.constants.gd)

- **`[IMG\_AVIF](https://www.php.net/manual/en/image.constants.php#constant.img-avif)`**
- **`[IMG\_WEBP\_LOSSLESS](https://www.php.net/manual/en/image.constants.php#constant.img-webp-lossless)`**

### MySQLi [¶](https://www.php.net/manual/en/migration81.constants.php\#migration81.constants.mysqli)

- **`[MYSQLI\_REFRESH\_REPLICA](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-refresh-replica)`**

This constant has been added as a replacement for
**`[MYSQLI\_REFRESH\_SLAVE](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-refresh-slave)`**,
in line with an upstream change in MySQL.
The old constant is still available for backwards-compatibility reasons,
but may be deprecated/removed in the future.



### PCNTL [¶](https://www.php.net/manual/en/migration81.constants.php\#migration81.constants.pcntl)

- **`[PRIO\_DARWIN\_BG](https://www.php.net/manual/en/pcntl.constants.php#constant.prio-darwin-bg)`**
- **`[PRIO\_DARWIN\_THREAD](https://www.php.net/manual/en/pcntl.constants.php#constant.prio-darwin-thread)`**

### POSIX [¶](https://www.php.net/manual/en/migration81.constants.php\#migration81.constants.posix)

- **`[POSIX\_RLIMIT\_KQUEUES](https://www.php.net/manual/en/posix.constants.setrlimit.php#constant.posix-rlimit-kqueues)`**
- **`[POSIX\_RLIMIT\_NPTS](https://www.php.net/manual/en/posix.constants.setrlimit.php#constant.posix-rlimit-npts)`**

### Sockets [¶](https://www.php.net/manual/en/migration81.constants.php\#migration81.constants.sockets)

The following socket options are now defined if they are supported:


- **`[SO\_ACCEPTFILTER](https://www.php.net/manual/en/sockets.constants.php#constant.so-acceptfilter)`**
- **`[SO\_DONTTRUNC](https://www.php.net/manual/en/sockets.constants.php#constant.so-donttrunc)`**
- **`[SO\_WANTMORE](https://www.php.net/manual/en/sockets.constants.php#constant.so-wantmore)`**
- **`[SO\_MARK](https://www.php.net/manual/en/sockets.constants.php#constant.so-mark)`**
- **`[TCP\_DEFER\_ACCEPT](https://www.php.net/manual/en/sockets.constants.php#constant.tcp-defer-accept)`**

### Sodium [¶](https://www.php.net/manual/en/migration81.constants.php\#migration81.constants.sodium)

- **`[SODIUM\_CRYPTO\_STREAM\_XCHACHA20\_NONCEBYTES](https://www.php.net/manual/en/sodium.constants.php#constant.sodium-crypto-stream-xchacha20-noncebytes)`**
- **`[SODIUM\_CRYPTO\_STREAM\_XCHACHA20\_KEYBYTES](https://www.php.net/manual/en/sodium.constants.php#constant.sodium-crypto-stream-xchacha20-keybytes)`**
- **`[SODIUM\_CRYPTO\_SCALARMULT\_RISTRETTO255\_BYTES](https://www.php.net/manual/en/sodium.constants.php#constant.sodium-crypto-scalarmult-ristretto255-bytes)`**
- **`[SODIUM\_CRYPTO\_SCALARMULT\_RISTRETTO255\_SCALARBYTES](https://www.php.net/manual/en/sodium.constants.php#constant.sodium-crypto-scalarmult-ristretto255-scalarbytes)`**
- **`[SODIUM\_CRYPTO\_CORE\_RISTRETTO255\_BYTES](https://www.php.net/manual/en/sodium.constants.php#constant.sodium-crypto-core-ristretto255-bytes)`**
- **`[SODIUM\_CRYPTO\_CORE\_RISTRETTO255\_HASHBYTES](https://www.php.net/manual/en/sodium.constants.php#constant.sodium-crypto-core-ristretto255-hashbytes)`**
- **`[SODIUM\_CRYPTO\_CORE\_RISTRETTO255\_SCALARBYTES](https://www.php.net/manual/en/sodium.constants.php#constant.sodium-crypto-core-ristretto255-scalarbytes)`**
- **`[SODIUM\_CRYPTO\_CORE\_RISTRETTO255\_NONREDUCEDSCALARBYTES](https://www.php.net/manual/en/sodium.constants.php#constant.sodium-crypto-core-ristretto255-nonreducedscalarbytes)`**

### Tokenizer [¶](https://www.php.net/manual/en/migration81.constants.php\#migration81.constants.tokenizer)

- **`[T\_READONLY](https://www.php.net/manual/en/tokens.php#constant.t-readonly)`**

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/appendices/migration81/constants.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmigration81.constants%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=migration81.constants&repo=en&redirect=https://www.php.net/manual/en/migration81.constants.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google