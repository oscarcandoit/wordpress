---
url: https://www.php.net/manual/en/stream.constants.php
scraped_at: 2025-10-20T02:39:02.566Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Predefined Constants [¶](https://www.php.net/manual/en/stream.constants.php\#stream.constants)

The constants below are defined by this extension, and
will only be available when the extension has either
been compiled into PHP or dynamically loaded at runtime.

**Available `flags` for**
**[stream\_socket\_client()](https://www.php.net/manual/en/function.stream-socket-client.php)****`[STREAM\_CLIENT\_ASYNC\_CONNECT](https://www.php.net/manual/en/stream.constants.php#constant.stream-client-async-connect)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Open client socket asynchronously.
This option must be used together with the
**`[STREAM\_CLIENT\_CONNECT](https://www.php.net/manual/en/stream.constants.php#constant.stream-client-connect)`** flag.
**`[STREAM\_CLIENT\_CONNECT](https://www.php.net/manual/en/stream.constants.php#constant.stream-client-connect)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Open client socket connection.
Client sockets should always include this flag.
**`[STREAM\_CLIENT\_PERSISTENT](https://www.php.net/manual/en/stream.constants.php#constant.stream-client-persistent)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Client socket should remain persistent between page loads.
**Available `flags` for**
**[stream\_socket\_server()](https://www.php.net/manual/en/function.stream-socket-server.php)****`[STREAM\_SERVER\_BIND](https://www.php.net/manual/en/stream.constants.php#constant.stream-server-bind)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Indicates that a stream should bind to the specified target.
Server sockets should always include this flag.
**`[STREAM\_SERVER\_LISTEN](https://www.php.net/manual/en/stream.constants.php#constant.stream-server-listen)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Indicates that a stream bound using
**`[STREAM\_SERVER\_BIND](https://www.php.net/manual/en/stream.constants.php#constant.stream-server-bind)`**
flag to start listening to the socket.
Connection-orientated transports (such as TCP) must use this flag,
otherwise the server socket will not be enabled.
Using this flag for connect-less transports (such as UDP) is an error.
**Values for the `mode` parameter of**
**[stream\_socket\_shutdown()](https://www.php.net/manual/en/function.stream-socket-shutdown.php)****`[STREAM\_SHUT\_RD](https://www.php.net/manual/en/stream.constants.php#constant.stream-shut-rd)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Disable further receptions.
**`[STREAM\_SHUT\_WR](https://www.php.net/manual/en/stream.constants.php#constant.stream-shut-wr)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Disable further transmissions.
**`[STREAM\_SHUT\_RDWR](https://www.php.net/manual/en/stream.constants.php#constant.stream-shut-rdwr)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Disable further receptions and transmissions.
**Stream Socket Transfer flags**

Those constants are used for the `flags`
parameter of the
[stream\_socket\_recvfrom()](https://www.php.net/manual/en/function.stream-socket-recvfrom.php) and
[stream\_socket\_sendto()](https://www.php.net/manual/en/function.stream-socket-sendto.php) functions.


**`[STREAM\_OOB](https://www.php.net/manual/en/stream.constants.php#constant.stream-oob)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Process OOB ( `out-of-band`) data.
**`[STREAM\_PEEK](https://www.php.net/manual/en/stream.constants.php#constant.stream-peek)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Retrieve data from the socket, but do not consume the buffer.

Subsequent calls to [fread()](https://www.php.net/manual/en/function.fread.php) or
[stream\_socket\_recvfrom()](https://www.php.net/manual/en/function.stream-socket-recvfrom.php) will see the same data.


> **Note**:
>
> Is not a valid flag for [stream\_socket\_sendto()](https://www.php.net/manual/en/function.stream-socket-sendto.php).

**Stream Filter constants**

Those constants are used for the
[stream\_filter\_append()](https://www.php.net/manual/en/function.stream-filter-append.php) and
[stream\_filter\_prepend()](https://www.php.net/manual/en/function.stream-filter-prepend.php) functions.


**`[STREAM\_FILTER\_READ](https://www.php.net/manual/en/stream.constants.php#constant.stream-filter-read)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Indicate that the specified filter should only be applied when
_reading_.
**`[STREAM\_FILTER\_WRITE](https://www.php.net/manual/en/stream.constants.php#constant.stream-filter-write)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Indicate that the specified filter should only be applied when
_writing_.
**`[STREAM\_FILTER\_ALL](https://www.php.net/manual/en/stream.constants.php#constant.stream-filter-all)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Equivalent to `STREAM_FILTER_READ | STREAM_FILTER_WRITE`.
**Stream Crypto Methods****`[STREAM\_CRYPTO\_METHOD\_ANY\_CLIENT](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-any-client)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Any TLS or SSL version on a client stream.
**`[STREAM\_CRYPTO\_METHOD\_SSLv2\_CLIENT](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-sslv2-client)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

SSL 2 on a client stream.
**`[STREAM\_CRYPTO\_METHOD\_SSLv3\_CLIENT](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-sslv3-client)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

SSL 3 on a client stream.
**`[STREAM\_CRYPTO\_METHOD\_SSLv23\_CLIENT](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-sslv23-client)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TLS 1.0, 1.1 or 1.2 on a client stream.
**`[STREAM\_CRYPTO\_METHOD\_TLS\_CLIENT](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-tls-client)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Any TLS version on a client stream.
**`[STREAM\_CRYPTO\_METHOD\_TLSv1\_0\_CLIENT](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-tlsv1-0-client)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TLS 1.0 on a client stream.
**`[STREAM\_CRYPTO\_METHOD\_TLSv1\_1\_CLIENT](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-tlsv1-1-client)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TLS 1.1 on a client stream.
**`[STREAM\_CRYPTO\_METHOD\_TLSv1\_2\_CLIENT](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-tlsv1-2-client)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TLS 1.2 on a client stream.
**`[STREAM\_CRYPTO\_METHOD\_TLSv1\_3\_CLIENT](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-tlsv1-3-client)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TLS 1.3 on a client stream.
**`[STREAM\_CRYPTO\_METHOD\_ANY\_SERVER](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-any-server)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Any TLS or SSL version on a server stream.
**`[STREAM\_CRYPTO\_METHOD\_SSLv2\_SERVER](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-sslv2-server)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

SSL 2 on a server stream.
**`[STREAM\_CRYPTO\_METHOD\_SSLv3\_SERVER](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-sslv3-server)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

SSL 3 on a server stream.
**`[STREAM\_CRYPTO\_METHOD\_SSLv23\_SERVER](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-sslv23-server)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TLS 1.0, 1.1 or 1.2 on a server stream.
**`[STREAM\_CRYPTO\_METHOD\_TLS\_SERVER](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-tls-server)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Any TLS version on a server stream.
**`[STREAM\_CRYPTO\_METHOD\_TLSv1\_0\_SERVER](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-tlsv1-0-server)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TLS 1.0 on a server stream.
**`[STREAM\_CRYPTO\_METHOD\_TLSv1\_1\_SERVER](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-tlsv1-1-server)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TLS 1.1 on a server stream.
**`[STREAM\_CRYPTO\_METHOD\_TLSv1\_2\_SERVER](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-tlsv1-2-server)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TLS 1.2 on a server stream.
**`[STREAM\_CRYPTO\_METHOD\_TLSv1\_3\_SERVER](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-tlsv1-3-server)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TLS 1.3 on a server stream.
**`[STREAM\_CRYPTO\_PROTO\_SSLv3](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-proto-sslv3)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Alias of **`[STREAM\_CRYPTO\_METHOD\_SSLv3\_SERVER](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-sslv3-server)`**.
**`[STREAM\_CRYPTO\_PROTO\_TLSv1\_0](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-proto-tlsv1-0)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Alias of **`[STREAM\_CRYPTO\_METHOD\_TLSv1\_0\_SERVER](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-tlsv1-0-server)`**.
**`[STREAM\_CRYPTO\_PROTO\_TLSv1\_1](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-proto-tlsv1-1)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Alias of **`[STREAM\_CRYPTO\_METHOD\_TLSv1\_1\_SERVER](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-tlsv1-1-server)`**.
**`[STREAM\_CRYPTO\_PROTO\_TLSv1\_2](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-proto-tlsv1-2)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Alias of **`[STREAM\_CRYPTO\_METHOD\_TLSv1\_2\_SERVER](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-tlsv1-2-server)`**.
**`[STREAM\_CRYPTO\_PROTO\_TLSv1\_3](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-proto-tlsv1-3)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Alias of **`[STREAM\_CRYPTO\_METHOD\_TLSv1\_3\_SERVER](https://www.php.net/manual/en/stream.constants.php#constant.stream-crypto-method-tlsv1-3-server)`**.
**Unused internal constants****`[STREAM\_MUST\_SEEK](https://www.php.net/manual/en/stream.constants.php#constant.stream-must-seek)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Ensure stream is seekable.
This may result in a copy of the stream being created.
**`[STREAM\_IGNORE\_URL](https://www.php.net/manual/en/stream.constants.php#constant.stream-ignore-url)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Do not use plugin wrappers.


### Constants used with [stream\_socket\_pair()](https://www.php.net/manual/en/function.stream-socket-pair.php)

> **Note**:
>
> Not all constants might be available on a given system.

**Constants for the `domain` parameter****`[STREAM\_PF\_INET](https://www.php.net/manual/en/stream.constants.php#constant.stream-pf-inet)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Internet Protocol Version 4 (IPv4).
**`[STREAM\_PF\_INET6](https://www.php.net/manual/en/stream.constants.php#constant.stream-pf-inet6)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Internet Protocol Version 6 (IPv6).
**`[STREAM\_PF\_UNIX](https://www.php.net/manual/en/stream.constants.php#constant.stream-pf-unix)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Unix system internal protocols.
**Constants for the `type` parameter****`[STREAM\_SOCK\_DGRAM](https://www.php.net/manual/en/stream.constants.php#constant.stream-sock-dgram)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Provides datagrams, which are connectionless messages.
For example: UDP.
**`[STREAM\_SOCK\_RAW](https://www.php.net/manual/en/stream.constants.php#constant.stream-sock-raw)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Provides a raw socket, which provides access to internal network
protocols and interfaces.
Usually this type of socket is just available to the root user.
**`[STREAM\_SOCK\_RDM](https://www.php.net/manual/en/stream.constants.php#constant.stream-sock-rdm)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Provides a RDM (Reliably-delivered messages) socket.
**`[STREAM\_SOCK\_SEQPACKET](https://www.php.net/manual/en/stream.constants.php#constant.stream-sock-seqpacket)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Provides a sequenced packet stream socket.
**`[STREAM\_SOCK\_STREAM](https://www.php.net/manual/en/stream.constants.php#constant.stream-sock-stream)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Provides sequenced, two-way byte streams with a transmission mechanism
for out-of-band data.
For example: TCP.
**Constants for the `protocol` parameter****`[STREAM\_IPPROTO\_ICMP](https://www.php.net/manual/en/stream.constants.php#constant.stream-ipproto-icmp)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Provides a ICMP socket.
**`[STREAM\_IPPROTO\_IP](https://www.php.net/manual/en/stream.constants.php#constant.stream-ipproto-ip)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Provides a IP socket.
**`[STREAM\_IPPROTO\_RAW](https://www.php.net/manual/en/stream.constants.php#constant.stream-ipproto-raw)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Provides a RAW socket.
**`[STREAM\_IPPROTO\_TCP](https://www.php.net/manual/en/stream.constants.php#constant.stream-ipproto-tcp)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Provides a TCP socket.
**`[STREAM\_IPPROTO\_UDP](https://www.php.net/manual/en/stream.constants.php#constant.stream-ipproto-udp)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Provides a UDP socket.


### Constants used with [stream\_notification\_callback()](https://www.php.net/manual/en/function.stream-notification-callback.php)

**Values for the `notification_code` parameter****`[STREAM\_NOTIFY\_RESOLVE](https://www.php.net/manual/en/stream.constants.php#constant.stream-notify-resolve)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

A remote address required for this stream has been resolved,
or the resolution failed.

See `severity` for an indication of which happened.


**Warning**

Support for this notification code is not yet implemented.


**`[STREAM\_NOTIFY\_CONNECT](https://www.php.net/manual/en/stream.constants.php#constant.stream-notify-connect)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

A connection with an external resource has been established.
**`[STREAM\_NOTIFY\_AUTH\_REQUIRED](https://www.php.net/manual/en/stream.constants.php#constant.stream-notify-auth-required)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Additional authorization is required to access the specified resource.

Typical issued with `severity` level of
**`[STREAM\_NOTIFY\_SEVERITY\_ERR](https://www.php.net/manual/en/stream.constants.php#constant.stream-notify-severity-err)`**.
**`[STREAM\_NOTIFY\_MIME\_TYPE\_IS](https://www.php.net/manual/en/stream.constants.php#constant.stream-notify-mime-type-is)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

The `mime-type` of resource has been identified.

Refer to `message` for a description of the
discovered type.
**`[STREAM\_NOTIFY\_FILE\_SIZE\_IS](https://www.php.net/manual/en/stream.constants.php#constant.stream-notify-file-size-is)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

The `size` of the resource has been discovered.
**`[STREAM\_NOTIFY\_REDIRECTED](https://www.php.net/manual/en/stream.constants.php#constant.stream-notify-redirected)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

The external resource has redirected the stream to an alternate location.

Refer to `message`.
**`[STREAM\_NOTIFY\_PROGRESS](https://www.php.net/manual/en/stream.constants.php#constant.stream-notify-progress)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Indicates current progress of the stream transfer in
`bytes_transferred` and possibly
`bytes_max` as well.
**`[STREAM\_NOTIFY\_COMPLETED](https://www.php.net/manual/en/stream.constants.php#constant.stream-notify-completed)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

There is no more data available on the stream.
(First implemented as of PHP 8.3.0.)
**`[STREAM\_NOTIFY\_FAILURE](https://www.php.net/manual/en/stream.constants.php#constant.stream-notify-failure)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

A generic error occurred on the stream.

Refer to `message` and
`message_code` for details.
**`[STREAM\_NOTIFY\_AUTH\_RESULT](https://www.php.net/manual/en/stream.constants.php#constant.stream-notify-auth-result)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Authorization has been completed (with or without success).
**Values for the `severity` parameter****`[STREAM\_NOTIFY\_SEVERITY\_INFO](https://www.php.net/manual/en/stream.constants.php#constant.stream-notify-severity-info)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Normal, non-error related, notification.
**`[STREAM\_NOTIFY\_SEVERITY\_WARN](https://www.php.net/manual/en/stream.constants.php#constant.stream-notify-severity-warn)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Non critical error condition.
Processing may continue.
**`[STREAM\_NOTIFY\_SEVERITY\_ERR](https://www.php.net/manual/en/stream.constants.php#constant.stream-notify-severity-err)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

A critical error occurred.
Processing cannot continue.


### [streamWrapper](https://www.php.net/manual/en/class.streamwrapper.php) related constants

**Valid flags for [stream\_wrapper\_register()](https://www.php.net/manual/en/function.stream-wrapper-register.php)****`[STREAM\_IS\_URL](https://www.php.net/manual/en/stream.constants.php#constant.stream-is-url)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Indicates that the stream wrapper protocol is a
URL protocol.
**Values for the `cast_as` parameter of**
**[streamWrapper::stream\_cast()](https://www.php.net/manual/en/streamwrapper.stream-cast.php)****`[STREAM\_CAST\_FOR\_SELECT](https://www.php.net/manual/en/stream.constants.php#constant.stream-cast-for-select)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Indicates that [streamWrapper::stream\_cast()](https://www.php.net/manual/en/streamwrapper.stream-cast.php)
was called by **streamWrapper::stream\_select()**.
**`[STREAM\_CAST\_AS\_STREAM](https://www.php.net/manual/en/stream.constants.php#constant.stream-cast-as-stream)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Indicates that [streamWrapper::stream\_cast()](https://www.php.net/manual/en/streamwrapper.stream-cast.php)
was called by any method other than
**streamWrapper::stream\_select()**.
**Values for the `option` parameter of**
**[streamWrapper::stream\_metadata()](https://www.php.net/manual/en/streamwrapper.stream-metadata.php)****`[STREAM\_META\_TOUCH](https://www.php.net/manual/en/stream.constants.php#constant.stream-meta-touch)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Indicates a call to [touch()](https://www.php.net/manual/en/function.touch.php).
**`[STREAM\_META\_OWNER](https://www.php.net/manual/en/stream.constants.php#constant.stream-meta-owner)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Indicates a call to [chown()](https://www.php.net/manual/en/function.chown.php).
**`[STREAM\_META\_OWNER\_NAME](https://www.php.net/manual/en/stream.constants.php#constant.stream-meta-owner-name)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Indicates a call to [chown()](https://www.php.net/manual/en/function.chown.php).
**`[STREAM\_META\_GROUP](https://www.php.net/manual/en/stream.constants.php#constant.stream-meta-group)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Indicates a call to [chgrp()](https://www.php.net/manual/en/function.chgrp.php).
**`[STREAM\_META\_GROUP\_NAME](https://www.php.net/manual/en/stream.constants.php#constant.stream-meta-group-name)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Indicates a call to [chgrp()](https://www.php.net/manual/en/function.chgrp.php).
**`[STREAM\_META\_ACCESS](https://www.php.net/manual/en/stream.constants.php#constant.stream-meta-access)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Indicates a call to [chmod()](https://www.php.net/manual/en/function.chmod.php).
**Valid flags for**
**[streamWrapper::mkdir()](https://www.php.net/manual/en/streamwrapper.mkdir.php)**

**and**
**[streamWrapper::rmdir()](https://www.php.net/manual/en/streamwrapper.rmdir.php)****`[STREAM\_MKDIR\_RECURSIVE](https://www.php.net/manual/en/stream.constants.php#constant.stream-mkdir-recursive)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Recursive flag for the options parameters of
[mkdir()](https://www.php.net/manual/en/function.mkdir.php) and [rmdir()](https://www.php.net/manual/en/function.rmdir.php).
**Values for the `options` parameter of**
**[streamWrapper::stream\_open()](https://www.php.net/manual/en/streamwrapper.stream-open.php)****`[STREAM\_USE\_PATH](https://www.php.net/manual/en/stream.constants.php#constant.stream-use-path)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Flag indicating that relative paths should use the include path to
locate the resource.
**`[STREAM\_REPORT\_ERRORS](https://www.php.net/manual/en/stream.constants.php#constant.stream-report-errors)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Flag indicating that the stream wrapper should report errors.
If the flag is not set, no errors should be reported.

Errors are usually reported by the use of the
[trigger\_error()](https://www.php.net/manual/en/function.trigger-error.php) function.
**Values for the `option` parameter of**
**[streamWrapper::stream\_set\_option()](https://www.php.net/manual/en/streamwrapper.stream-set-option.php)****`[STREAM\_OPTION\_BLOCKING](https://www.php.net/manual/en/stream.constants.php#constant.stream-option-blocking)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Set blocking/non-blocking mode on a stream.
**`[STREAM\_OPTION\_READ\_BUFFER](https://www.php.net/manual/en/stream.constants.php#constant.stream-option-read-buffer)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Set read file buffering on a stream.
**Valid option values****`[STREAM\_BUFFER\_NONE](https://www.php.net/manual/en/stream.constants.php#constant.stream-buffer-none)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

No buffering.
**`[STREAM\_BUFFER\_LINE](https://www.php.net/manual/en/stream.constants.php#constant.stream-buffer-line)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Line buffering.
**`[STREAM\_BUFFER\_FULL](https://www.php.net/manual/en/stream.constants.php#constant.stream-buffer-full)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Full buffering.
**`[STREAM\_OPTION\_READ\_TIMEOUT](https://www.php.net/manual/en/stream.constants.php#constant.stream-option-read-timeout)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Set read file buffering on a stream.

**`[STREAM\_OPTION\_WRITE\_BUFFER](https://www.php.net/manual/en/stream.constants.php#constant.stream-option-write-buffer)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Set write file buffering on a stream.

See **`[STREAM\_OPTION\_READ\_BUFFER](https://www.php.net/manual/en/stream.constants.php#constant.stream-option-read-buffer)`**
for valid buffer options.
**Values for the `flags` parameter of**
**[streamWrapper::url\_stat()](https://www.php.net/manual/en/streamwrapper.url-stat.php)****`[STREAM\_URL\_STAT\_LINK](https://www.php.net/manual/en/stream.constants.php#constant.stream-url-stat-link)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Only information about the link itself should be returned,
not the resource pointed to by the link.
**`[STREAM\_URL\_STAT\_QUIET](https://www.php.net/manual/en/stream.constants.php#constant.stream-url-stat-quiet)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

The wrapper should not raise any errors.


### [php\_user\_filter](https://www.php.net/manual/en/class.php-user-filter.php) related constants

**Valid return values for**
**[php\_user\_filter::filter()](https://www.php.net/manual/en/php-user-filter.filter.php)****`[PSFS\_PASS\_ON](https://www.php.net/manual/en/stream.constants.php#constant.psfs-pass-on)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Return value indicating that the userspace filter
returned buckets in `$out`.
**`[PSFS\_FEED\_ME](https://www.php.net/manual/en/stream.constants.php#constant.psfs-feed-me)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Return value indicating that the userspace filter
did not return buckets in `$out`.
(i.e. No data available.)
**`[PSFS\_ERR\_FATAL](https://www.php.net/manual/en/stream.constants.php#constant.psfs-err-fatal)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Return value indicating that the userspace filter
encountered an unrecoverable error.
(i.e. Invalid data received.)
**Unused internal constants****`[PSFS\_FLAG\_NORMAL](https://www.php.net/manual/en/stream.constants.php#constant.psfs-flag-normal)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Regular read/write.
**`[PSFS\_FLAG\_FLUSH\_INC](https://www.php.net/manual/en/stream.constants.php#constant.psfs-flag-flush-inc)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

An incremental flush.
**`[PSFS\_FLAG\_FLUSH\_CLOSE](https://www.php.net/manual/en/stream.constants.php#constant.psfs-flag-flush-close)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Final flush prior to closing.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/stream/constants.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fstream.constants%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=stream.constants&repo=en&redirect=https://www.php.net/manual/en/stream.constants.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google