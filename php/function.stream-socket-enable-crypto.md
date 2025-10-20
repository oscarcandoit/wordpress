---
url: https://www.php.net/manual/en/function.stream-socket-enable-crypto.php
scraped_at: 2025-10-20T02:39:38.507Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# stream\_socket\_enable\_crypto

(PHP 5 >= 5.1.0, PHP 7, PHP 8)

stream\_socket\_enable\_crypto — Turns encryption on/off on an already connected socket

### Description [¶](https://www.php.net/manual/en/function.stream-socket-enable-crypto.php\#refsect1-function.stream-socket-enable-crypto-description)

**stream\_socket\_enable\_crypto**(

[resource](https://www.php.net/manual/en/language.types.resource.php) `$stream`,

[bool](https://www.php.net/manual/en/language.types.boolean.php) `$enable`,

[?](https://www.php.net/manual/en/language.types.null.php)[int](https://www.php.net/manual/en/language.types.integer.php) `$crypto_method` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**,

[?](https://www.php.net/manual/en/language.types.null.php)[resource](https://www.php.net/manual/en/language.types.resource.php) `$session_stream` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**

): [int](https://www.php.net/manual/en/language.types.integer.php)\|[bool](https://www.php.net/manual/en/language.types.boolean.php)

Enable or disable encryption on the stream.


Once the crypto settings are established, cryptography can be turned
on and off dynamically by passing **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** in the
`enable` parameter.


### Parameters [¶](https://www.php.net/manual/en/function.stream-socket-enable-crypto.php\#refsect1-function.stream-socket-enable-crypto-parameters)

`stream`

The stream resource.


`enable`

Enable/disable cryptography on the stream.


`crypto_method`

Setup encryption on the stream.
Valid methods are


- **`[STREAM\_CRYPTO\_METHOD\_SSLv2\_CLIENT](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-sslv2-client)`**
- **`[STREAM\_CRYPTO\_METHOD\_SSLv3\_CLIENT](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-sslv3-client)`**
- **`[STREAM\_CRYPTO\_METHOD\_SSLv23\_CLIENT](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-sslv23-client)`**
- **`[STREAM\_CRYPTO\_METHOD\_ANY\_CLIENT](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-any-client)`**
- **`[STREAM\_CRYPTO\_METHOD\_TLS\_CLIENT](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-tls-client)`**
- **`[STREAM\_CRYPTO\_METHOD\_TLSv1\_0\_CLIENT](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-tlsv1-0-client)`**
- **`[STREAM\_CRYPTO\_METHOD\_TLSv1\_1\_CLIENT](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-tlsv1-1-client)`**
- **`[STREAM\_CRYPTO\_METHOD\_TLSv1\_2\_CLIENT](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-tlsv1-2-client)`**
- **`[STREAM\_CRYPTO\_METHOD\_TLSv1\_3\_CLIENT](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-tlsv1-3-client)`** (as of PHP 7.4.0)
- **`[STREAM\_CRYPTO\_METHOD\_SSLv2\_SERVER](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-sslv2-server)`**
- **`[STREAM\_CRYPTO\_METHOD\_SSLv3\_SERVER](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-sslv3-server)`**
- **`[STREAM\_CRYPTO\_METHOD\_SSLv23\_SERVER](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-sslv23-server)`**
- **`[STREAM\_CRYPTO\_METHOD\_ANY\_SERVER](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-any-server)`**
- **`[STREAM\_CRYPTO\_METHOD\_TLS\_SERVER](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-tls-server)`**
- **`[STREAM\_CRYPTO\_METHOD\_TLSv1\_0\_SERVER](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-tlsv1-0-server)`**
- **`[STREAM\_CRYPTO\_METHOD\_TLSv1\_1\_SERVER](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-tlsv1-1-server)`**
- **`[STREAM\_CRYPTO\_METHOD\_TLSv1\_2\_SERVER](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-tlsv1-2-server)`**
- **`[STREAM\_CRYPTO\_METHOD\_TLSv1\_3\_SERVER](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-tlsv1-3-server)`** (as of PHP 7.4.0)

If omitted, the `crypto_method` context option on
the stream's SSL context will be used instead.


`session_stream`

Seed the stream with settings from `session_stream`.


### Return Values [¶](https://www.php.net/manual/en/function.stream-socket-enable-crypto.php\#refsect1-function.stream-socket-enable-crypto-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success, **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** if negotiation has failed or
`0` if there isn't enough data and you should try again
(only for non-blocking sockets).


### Changelog [¶](https://www.php.net/manual/en/function.stream-socket-enable-crypto.php\#refsect1-function.stream-socket-enable-crypto-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | `session_stream` is now nullable. |

### Examples [¶](https://www.php.net/manual/en/function.stream-socket-enable-crypto.php\#refsect1-function.stream-socket-enable-crypto-examples)

**Example #1 **stream\_socket\_enable\_crypto()** example**

`<?php
$fp = stream_socket_client("tcp://myproto.example.com:31337", $errno, $errstr, 30);
if (!$fp) {
    die("Unable to connect: $errstr ($errno)");
}
/* Turn on encryption for login phase */
stream_socket_enable_crypto($fp, true, STREAM_CRYPTO_METHOD_SSLv23_CLIENT);
fwrite($fp, "USER god\r\n");
fwrite($fp, "PASS secret\r\n");
/* Turn off encryption for the rest */
stream_socket_enable_crypto($fp, false);
while ($motd = fgets($fp)) {
    echo $motd;
}
fclose($fp);
?>`

The above example will output
something similar to:

```

```

### See Also [¶](https://www.php.net/manual/en/function.stream-socket-enable-crypto.php\#refsect1-function.stream-socket-enable-crypto-seealso)

- [OpenSSL Functions](https://www.php.net/manual/en/ref.openssl.php)
- [List of Supported Socket Transports](https://www.php.net/manual/en/transports.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/stream/functions/stream-socket-enable-crypto.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.stream-socket-enable-crypto%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.stream-socket-enable-crypto&repo=en&redirect=https://www.php.net/manual/en/function.stream-socket-enable-crypto.php)

### User Contributed Notes 4 notes

[up](https://www.php.net/manual/vote-note.php?id=126761&page=function.stream-socket-enable-crypto&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126761&page=function.stream-socket-enable-crypto&vote=down "Vote down!")

2


[**_Anonymous_**](https://www.php.net/manual/en/function.stream-socket-enable-crypto.php#126761) [¶](https://www.php.net/manual/en/function.stream-socket-enable-crypto.php#126761)

**3 years ago**

`If you need to change a stream from unencrypted to crypted after unencrypted traffic has been processed, you use the stream-socket-recvfrom function to read instead of fread when reading the unencrypted traffic. Using fread will cause some of the buffer of the initial CLIENT HELLO message to be read into it's buffers causing the SSL handshake to fail in some situations.`

[up](https://www.php.net/manual/vote-note.php?id=75442&page=function.stream-socket-enable-crypto&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=75442&page=function.stream-socket-enable-crypto&vote=down "Vote down!")

3


[**_tigger (AT) tiggerswelt d0t net_**](https://www.php.net/manual/en/function.stream-socket-enable-crypto.php#75442) [¶](https://www.php.net/manual/en/function.stream-socket-enable-crypto.php#75442)

**18 years ago**

`As already mentioned above:
stream_socket_enable_crypto is likely to fail/return zero if the socket is in non-blocking mode.
You may either wait some seconds until all neccessary data has arrived or switch temporary to blocking mode:
<?PHP
stream_set_blocking ($fd, true);
stream_socket_enable_crypto ($fd, true, STREAM_CRYPTO_METHOD_TLS_CLIENT);
stream_set_blocking ($fd, false);
?>
This works very fine for me ;-)`

[up](https://www.php.net/manual/vote-note.php?id=128999&page=function.stream-socket-enable-crypto&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128999&page=function.stream-socket-enable-crypto&vote=down "Vote down!")

2


[**_play dot it at play-it dot net_**](https://www.php.net/manual/en/function.stream-socket-enable-crypto.php#128999) [¶](https://www.php.net/manual/en/function.stream-socket-enable-crypto.php#128999)

**1 year ago**

````Information to the difference of `crypto_method`
There is `STREAM_CRYPTO_METHOD_*_CLIENT` and `STREAM_CRYPTO_METHOD_*_SERVER`
`STREAM_CRYPTO_METHOD_*_CLIENT` is used for clients, like:
```php
<?php
$client = stream_socket_client("tcp://example.com:443", $errno, $errstr);
stream_socket_enable_crypto($client, true, STREAM_CRYPTO_METHOD_TLS_CLIENT);
//...
?>
```
This code makes a TLS Handshake and the `stream_socket_enable_crypto` sends a `Client HELLO`
`STREAM_CRYPTO_METHOD_*_SERVER` is used for servers, like:
<?php
$server = stream_socket_server("tcp://example.com:443", $errno, $errstr, STREAM_SERVER_BIND | STREAM_SERVER_LISTEN);
stream_context_set_option($server, ["ssl" => [\
    "local_cert" => __DIR__."/https.crt",\
    "local_pk" => __DIR__."/https.key",\
]]);
//...
$client = stream_socket_accept($server);
stream_socket_enable_crypto($client, true, STREAM_CRYPTO_METHOD_TLS_SERVER);
//...
?>
This code makes a TLS Handshake and the `stream_socket_enable_crypto` sends a `Server HELLO` after the client send a `Client HELLO`.
so use `STREAM_CRYPTO_METHOD_*_CLIENT` for requesting data and `STREAM_CRYPTO_METHOD_*_SERVER` for serving data, after accepting a client.````

[up](https://www.php.net/manual/vote-note.php?id=128929&page=function.stream-socket-enable-crypto&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128929&page=function.stream-socket-enable-crypto&vote=down "Vote down!")

 -1


[**_Zero_**](https://www.php.net/manual/en/function.stream-socket-enable-crypto.php#128929) [¶](https://www.php.net/manual/en/function.stream-socket-enable-crypto.php#128929)

**2 years ago**

`Since PHP 7.2, TLS equates to TLS_ANY, so STREAM_CRYPTO_METHOD_TLS_CLIENT means any TLS versions.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.stream-socket-enable-crypto&repo=en&redirect=https://www.php.net/manual/en/function.stream-socket-enable-crypto.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google