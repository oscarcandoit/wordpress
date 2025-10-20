---
url: https://www.php.net/manual/en/swoole.constants.php
scraped_at: 2025-10-20T02:47:24.663Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Predefined Constants [¶](https://www.php.net/manual/en/swoole.constants.php\#swoole.constants)

The constants below are defined by this extension, and
will only be available when the extension has either
been compiled into PHP or dynamically loaded at runtime.

**`[SWOOLE\_VERSION](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-version)`**
([string](https://www.php.net/manual/en/language.types.string.php))

Swoole version.
**`[SWOOLE\_VERSION\_ID](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-version-id)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Swoole version.
**`[SWOOLE\_MAJOR\_VERSION](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-major-version)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Swoole major version.
**`[SWOOLE\_MINOR\_VERSION](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-minor-version)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Swoole minor version.
**`[SWOOLE\_RELEASE\_VERSION](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-release-version)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Swoole release version.
**`[SWOOLE\_EXTRA\_VERSION](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-extra-version)`**
([string](https://www.php.net/manual/en/language.types.string.php))

Swoole extra version.
**`[SWOOLE\_DEBUG](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-debug)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Debug mode.
**`[SWOOLE\_HAVE\_COMPRESSION](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-have-compression)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Enable HTTP response compression mode.
**`[SWOOLE\_HAVE\_ZLIB](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-have-zlib)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Have zlib compression tool.
**`[SWOOLE\_HAVE\_BROTLI](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-have-brotli)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Have brotli compression tool.
**`[SWOOLE\_USE\_HTTP2](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-use-http2)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Support http2 server.
**`[SWOOLE\_USE\_SHORTNAME](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-use-shortname)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Enable/disable short aliases.
**`[SWOOLE\_SOCK\_TCP](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-sock-tcp)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TCP ipv4 socket.
**`[SWOOLE\_SOCK\_TCP6](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-sock-tcp6)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TCP ipv6 socket.
**`[SWOOLE\_SOCK\_UDP](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-sock-udp)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

UDP ipv4 socket.
**`[SWOOLE\_SOCK\_UDP6](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-sock-udp6)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

UDP ipv6 socket.
**`[SWOOLE\_SOCK\_UNIX\_DGRAM](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-sock-unix-dgram)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

UNIX socket dgram.
**`[SWOOLE\_SOCK\_UNIX\_STREAM](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-sock-unix-stream)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

UNIX socket stream.
**`[SWOOLE\_SOCK\_SYNC](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-sock-sync)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Synchronous client mode.
**`[SWOOLE\_SOCK\_ASYNC](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-sock-async)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Asynchronous client mode.
**`[SWOOLE\_KEEP](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-keep)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Swoole\\Client supports creating a TCP long connection to the server in PHP-FPM/Apache.
**`[SWOOLE\_SSL](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-ssl)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Enable SSL tunnel encryption.
**`[SWOOLE\_SSLv3\_METHOD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-sslv3-method)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

SSLv3 method.
**`[SWOOLE\_SSLv3\_SERVER\_METHOD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-sslv3-server-method)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

SSLv3 server method.
**`[SWOOLE\_SSLv3\_CLIENT\_METHOD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-sslv3-client-method)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

SSLv3 client method.
**`[SWOOLE\_TLSv1\_METHOD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-tlsv1-method)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TLSv1 method.
**`[SWOOLE\_TLSv1\_SERVER\_METHOD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-tlsv1-server-method)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TLSv1 server method.
**`[SWOOLE\_TLSv1\_CLIENT\_METHOD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-tlsv1-client-method)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TLSv1 client method.
**`[SWOOLE\_TLSv1\_1\_METHOD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-tlsv1-1-method)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TLSv1\_1 method.
**`[SWOOLE\_TLSv1\_1\_SERVER\_METHOD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-tlsv1-1-server-method)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TLSv1\_1 server method.
**`[SWOOLE\_TLSv1\_1\_CLIENT\_METHOD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-tlsv1-1-client-method)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TLSv1\_1 client method.
**`[SWOOLE\_TLSv1\_2\_METHOD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-tlsv1-2-method)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TLSv1\_2 method.
**`[SWOOLE\_TLSv1\_2\_SERVER\_METHOD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-tlsv1-2-server-method)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TLSv1\_2 server method.
**`[SWOOLE\_TLSv1\_2\_CLIENT\_METHOD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-tlsv1-2-client-method)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TLSv1\_2 client method.
**`[SWOOLE\_DTLS\_SERVER\_METHOD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-dtls-server-method)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

DTLS server method.
**`[SWOOLE\_DTLS\_CLIENT\_METHOD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-dtls-client-method)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

DTLS client method.
**`[SWOOLE\_SSLv23\_METHOD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-sslv23-method)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

SSLv23 method.
**`[SWOOLE\_SSLv23\_SERVER\_METHOD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-sslv23-server-method)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

SSLv23 server method.
**`[SWOOLE\_SSLv23\_CLIENT\_METHOD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-sslv23-client-method)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

SSLv23 client method.
**`[SWOOLE\_TLS\_METHOD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-tls-method)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TLS method.
**`[SWOOLE\_TLS\_SERVER\_METHOD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-tls-server-method)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TLS server method.
**`[SWOOLE\_TLS\_CLIENT\_METHOD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-tls-client-method)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TLS client method.
**`[SWOOLE\_SSL\_SSLv3](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-ssl-sslv3)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

SSLv3 protocol.
**`[SWOOLE\_SSL\_TLSv1](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-ssl-tlsv1)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TLSv1 protocol.
**`[SWOOLE\_SSL\_TLSv1\_1](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-ssl-tlsv1-1)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TLSv1\_1 protocol.
**`[SWOOLE\_SSL\_TLSv1\_2](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-ssl-tlsv1-2)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TLSv1\_2 protocol.
**`[SWOOLE\_SSL\_TLSv1\_3](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-ssl-tlsv1-3)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TLSv1\_3 protocol.
**`[SWOOLE\_SSL\_DTLS](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-ssl-dtls)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

DTLS protocol.
**`[SWOOLE\_SSL\_SSLv2](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-ssl-sslv2)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

SSLv2 protocol.
**`[SWOOLE\_EVENT\_READ](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-event-read)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Whether to listen for readable events.
**`[SWOOLE\_EVENT\_WRITE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-event-write)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Whether to listen for writable events.
**`[SWOOLE\_STRERROR\_SYSTEM](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-strerror-system)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Convert the system errno no into error messages.
**`[SWOOLE\_STRERROR\_GAI](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-strerror-gai)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Convert the addr info errno no into error messages.
**`[SWOOLE\_STRERROR\_DNS](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-strerror-dns)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Convert the DNS errno no into error messages.
**`[SWOOLE\_STRERROR\_SWOOLE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-strerror-swoole)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Convert the swoole errno no into error messages.
**`[SWOOLE\_ERROR\_MALLOC\_FAIL](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-malloc-fail)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Malloc memory fail.
**`[SWOOLE\_ERROR\_SYSTEM\_CALL\_FAIL](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-system-call-fail)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

System call fail.
**`[SWOOLE\_ERROR\_PHP\_FATAL\_ERROR](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-php-fatal-error)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

PHP fatal error.
**`[SWOOLE\_ERROR\_NAME\_TOO\_LONG](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-name-too-long)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Name too long.
**`[SWOOLE\_ERROR\_INVALID\_PARAMS](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-invalid-params)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Invalid params.
**`[SWOOLE\_ERROR\_QUEUE\_FULL](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-queue-full)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Queue full.
**`[SWOOLE\_ERROR\_OPERATION\_NOT\_SUPPORT](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-operation-not-support)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Operation not support.
**`[SWOOLE\_ERROR\_PROTOCOL\_ERROR](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-protocol-error)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Protocol error.
**`[SWOOLE\_ERROR\_WRONG\_OPERATION](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-wrong-operation)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Wrong operation.
**`[SWOOLE\_ERROR\_PHP\_RUNTIME\_NOTICE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-php-runtime-notice)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

PHP runtime notice.
**`[SWOOLE\_ERROR\_FOR\_TEST](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-for-test)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

For test.
**`[SWOOLE\_ERROR\_NO\_PAYLOAD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-no-payload)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

No payload.
**`[SWOOLE\_ERROR\_UNDEFINED\_BEHAVIOR](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-undefined-behavior)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Undefined behavior.
**`[SWOOLE\_ERROR\_NOT\_THREAD\_SAFETY](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-not-thread-safety)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Not thread safety.
**`[SWOOLE\_ERROR\_FILE\_NOT\_EXIST](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-file-not-exist)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

File not exist.
**`[SWOOLE\_ERROR\_FILE\_TOO\_LARGE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-file-too-large)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

File too large.
**`[SWOOLE\_ERROR\_FILE\_EMPTY](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-file-empty)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

File empty.
**`[SWOOLE\_ERROR\_DNSLOOKUP\_DUPLICATE\_REQUEST](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-dnslookup-duplicate-request)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

DNS Lookup duplicate request.
**`[SWOOLE\_ERROR\_DNSLOOKUP\_RESOLVE\_FAILED](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-dnslookup-resolve-failed)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

DNS Lookup resolve failed.
**`[SWOOLE\_ERROR\_DNSLOOKUP\_RESOLVE\_TIMEOUT](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-dnslookup-resolve-timeout)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

DNS Lookup resolve timeout.
**`[SWOOLE\_ERROR\_DNSLOOKUP\_UNSUPPORTED](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-dnslookup-unsupported)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

DNS Lookup unsupported.
**`[SWOOLE\_ERROR\_DNSLOOKUP\_NO\_SERVER](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-dnslookup-no-server)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

DNS Lookup no server.
**`[SWOOLE\_ERROR\_BAD\_IPV6\_ADDRESS](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-bad-ipv6-address)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Bad ipv6 address.
**`[SWOOLE\_ERROR\_UNREGISTERED\_SIGNAL](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-unregistered-signal)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Unregistered signal.
**`[SWOOLE\_ERROR\_BAD\_HOST\_ADDR](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-bad-host-addr)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Bad host addr.
**`[SWOOLE\_ERROR\_EVENT\_SOCKET\_REMOVED](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-event-socket-removed)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Event socket removed.
**`[SWOOLE\_ERROR\_SESSION\_CLOSED\_BY\_SERVER](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-session-closed-by-server)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Session closed by server.
**`[SWOOLE\_ERROR\_SESSION\_CLOSED\_BY\_CLIENT](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-session-closed-by-client)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Session closed by client.
**`[SWOOLE\_ERROR\_SESSION\_CLOSING](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-session-closing)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Session closing.
**`[SWOOLE\_ERROR\_SESSION\_CLOSED](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-session-closed)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Session closed.
**`[SWOOLE\_ERROR\_SESSION\_NOT\_EXIST](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-session-not-exist)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Session not exist.
**`[SWOOLE\_ERROR\_SESSION\_INVALID\_ID](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-session-invalid-id)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Session invalid id.
**`[SWOOLE\_ERROR\_SESSION\_DISCARD\_TIMEOUT\_DATA](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-session-discard-timeout-data)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Session discard timeout data.
**`[SWOOLE\_ERROR\_SESSION\_DISCARD\_DATA](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-session-discard-data)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Session discard data.
**`[SWOOLE\_ERROR\_OUTPUT\_BUFFER\_OVERFLOW](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-output-buffer-overflow)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Output buffer overflow.
**`[SWOOLE\_ERROR\_OUTPUT\_SEND\_YIELD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-output-send-yield)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Output send yield
**`[SWOOLE\_ERROR\_SSL\_NOT\_READY](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-ssl-not-ready)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

SSL not ready
**`[SWOOLE\_ERROR\_SSL\_CANNOT\_USE\_SENFILE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-ssl-cannot-use-senfile)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

SSL cannot use senfile
**`[SWOOLE\_ERROR\_SSL\_EMPTY\_PEER\_CERTIFICATE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-ssl-empty-peer-certificate)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

SSL empty peer certificate.
**`[SWOOLE\_ERROR\_SSL\_VERIFY\_FAILED](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-ssl-verify-failed)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

SSL verify failed.
**`[SWOOLE\_ERROR\_SSL\_BAD\_CLIENT](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-ssl-bad-client)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

SSL bad client.
**`[SWOOLE\_ERROR\_SSL\_BAD\_PROTOCOL](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-ssl-bad-protocol)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

SSL bad protocol.
**`[SWOOLE\_ERROR\_SSL\_RESET](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-ssl-reset)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

SSL reset.
**`[SWOOLE\_ERROR\_SSL\_HANDSHAKE\_FAILED](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-ssl-handshake-failed)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

SSL handshake failed.
**`[SWOOLE\_ERROR\_PACKAGE\_LENGTH\_TOO\_LARGE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-package-length-too-large)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Package length too large.
**`[SWOOLE\_ERROR\_PACKAGE\_LENGTH\_NOT\_FOUND](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-package-length-not-found)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Package length not found.
**`[SWOOLE\_ERROR\_DATA\_LENGTH\_TOO\_LARGE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-data-length-too-large)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Data length too large.
**`[SWOOLE\_ERROR\_PACKAGE\_MALFORMED\_DATA](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-package-malformed-data)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Package malformed error data.
**`[SWOOLE\_ERROR\_TASK\_PACKAGE\_TOO\_BIG](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-task-package-too-big)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Task package too big.
**`[SWOOLE\_ERROR\_TASK\_DISPATCH\_FAIL](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-task-dispatch-fail)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Task dispatch fail.
**`[SWOOLE\_ERROR\_TASK\_TIMEOUT](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-task-timeout)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Task timeout.
**`[SWOOLE\_ERROR\_HTTP2\_STREAM\_ID\_TOO\_BIG](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-http2-stream-id-too-big)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Http2 stream id too big.
**`[SWOOLE\_ERROR\_HTTP2\_STREAM\_NO\_HEADER](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-http2-stream-no-header)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Http2 stream no header.
**`[SWOOLE\_ERROR\_HTTP2\_STREAM\_NOT\_FOUND](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-http2-stream-not-found)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Http2 stream not found.
**`[SWOOLE\_ERROR\_HTTP2\_STREAM\_IGNORE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-http2-stream-ignore)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Http2 stream ignore.
**`[SWOOLE\_ERROR\_HTTP2\_SEND\_CONTROL\_FRAME\_FAILED](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-http2-send-control-frame-failed)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Http2 send control frame failed.
**`[SWOOLE\_ERROR\_AIO\_BAD\_REQUEST](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-aio-bad-request)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Aio bad request.
**`[SWOOLE\_ERROR\_AIO\_CANCELED](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-aio-canceled)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Aio canceled.
**`[SWOOLE\_ERROR\_AIO\_TIMEOUT](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-aio-timeout)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Aio timeout.
**`[SWOOLE\_ERROR\_CLIENT\_NO\_CONNECTION](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-client-no-connection)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Client no connection.
**`[SWOOLE\_ERROR\_SOCKET\_CLOSED](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-socket-closed)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Socket closed.
**`[SWOOLE\_ERROR\_SOCKET\_POLL\_TIMEOUT](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-socket-poll-timeout)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Socket poll timeout.
**`[SWOOLE\_ERROR\_SOCKS5\_UNSUPPORT\_VERSION](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-socks5-unsupport-version)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Socks5 unsupport version.
**`[SWOOLE\_ERROR\_SOCKS5\_UNSUPPORT\_METHOD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-socks5-unsupport-method)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Socks5 unsupport method.
**`[SWOOLE\_ERROR\_SOCKS5\_AUTH\_FAILED](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-socks5-auth-failed)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Socks5 auth failed.
**`[SWOOLE\_ERROR\_SOCKS5\_SERVER\_ERROR](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-socks5-server-error)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Socks5 server error.
**`SWOOLE_ERROR_SOCKS5_HANDSHAKE_FAILED`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Socks5 handshake failed.
**`[SWOOLE\_ERROR\_HTTP\_PROXY\_HANDSHAKE\_ERROR](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-http-proxy-handshake-error)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Http proxy handshake error.
**`[SWOOLE\_ERROR\_HTTP\_INVALID\_PROTOCOL](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-http-invalid-protocol)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Http invalid protocol.
**`[SWOOLE\_ERROR\_HTTP\_PROXY\_HANDSHAKE\_FAILED](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-http-proxy-handshake-failed)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Http proxy handshake failed.
**`[SWOOLE\_ERROR\_HTTP\_PROXY\_BAD\_RESPONSE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-http-proxy-bad-response)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Http proxy bad response.
**`[SWOOLE\_ERROR\_HTTP\_CONFLICT\_HEADER](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-http-conflict-header)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Http conflict header.
**`[SWOOLE\_ERROR\_HTTP\_CONTEXT\_UNAVAILABLE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-http-context-unavailable)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Http context unavailable.
**`[SWOOLE\_ERROR\_HTTP\_COOKIE\_UNAVAILABLE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-http-cookie-unavailable)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Http cookie unavailable.
**`[SWOOLE\_ERROR\_WEBSOCKET\_BAD\_CLIENT](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-websocket-bad-client)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Websocket bad client.
**`[SWOOLE\_ERROR\_WEBSOCKET\_BAD\_OPCODE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-websocket-bad-opcode)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Websocket bad opcode.
**`[SWOOLE\_ERROR\_WEBSOCKET\_UNCONNECTED](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-websocket-unconnected)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Websocket unconnected.
**`[SWOOLE\_ERROR\_WEBSOCKET\_HANDSHAKE\_FAILED](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-websocket-handshake-failed)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Websocket handshake failed.
**`[SWOOLE\_ERROR\_WEBSOCKET\_PACK\_FAILED](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-websocket-pack-failed)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Websocket pack failed.
**`[SWOOLE\_ERROR\_WEBSOCKET\_UNPACK\_FAILED](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-websocket-unpack-failed)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Websocket unpack failed.
**`[SWOOLE\_ERROR\_WEBSOCKET\_INCOMPLETE\_PACKET](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-websocket-incomplete-packet)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Websocket incomplete packet.
**`[SWOOLE\_ERROR\_SERVER\_MUST\_CREATED\_BEFORE\_CLIENT](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-server-must-created-before-client)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Server must be created before client.
**`[SWOOLE\_ERROR\_SERVER\_TOO\_MANY\_SOCKET](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-server-too-many-socket)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Server too many socket.
**`[SWOOLE\_ERROR\_SERVER\_WORKER\_TERMINATED](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-server-worker-terminated)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Server worker terminated.
**`[SWOOLE\_ERROR\_SERVER\_INVALID\_LISTEN\_PORT](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-server-invalid-listen-port)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Server invalid listen port.
**`[SWOOLE\_ERROR\_SERVER\_TOO\_MANY\_LISTEN\_PORT](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-server-too-many-listen-port)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Server too many listen port.
**`[SWOOLE\_ERROR\_SERVER\_PIPE\_BUFFER\_FULL](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-server-pipe-buffer-full)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Server pipe buffer full.
**`[SWOOLE\_ERROR\_SERVER\_NO\_IDLE\_WORKER](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-server-no-idle-worker)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Server no idle worker.
**`[SWOOLE\_ERROR\_SERVER\_ONLY\_START\_ONE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-server-only-start-one)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Server only start one.
**`[SWOOLE\_ERROR\_SERVER\_SEND\_IN\_MASTER](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-server-send-in-master)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Server send in master.
**`[SWOOLE\_ERROR\_SERVER\_INVALID\_REQUEST](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-server-invalid-request)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Server invalid request.
**`[SWOOLE\_ERROR\_SERVER\_CONNECT\_FAIL](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-server-connect-fail)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Server connect failed.
**`[SWOOLE\_ERROR\_SERVER\_INVALID\_COMMAND](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-server-invalid-command)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Server invalid command.
**`[SWOOLE\_ERROR\_SERVER\_IS\_NOT\_REGULAR\_FILE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-server-is-not-regular-file)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Server is not regular file.
**`[SWOOLE\_ERROR\_SERVER\_SEND\_TO\_WOKER\_TIMEOUT](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-server-send-to-woker-timeout)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Server send to woker timeout.
**`[SWOOLE\_ERROR\_SERVER\_INVALID\_CALLBACK](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-server-invalid-callback)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Server invalid callback.
**`[SWOOLE\_ERROR\_SERVER\_UNRELATED\_THREAD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-server-unrelated-thread)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Server unrelated thread.
**`[SWOOLE\_ERROR\_SERVER\_WORKER\_EXIT\_TIMEOUT](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-server-worker-exit-timeout)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Server worker exit timeout.
**`[SWOOLE\_ERROR\_SERVER\_WORKER\_ABNORMAL\_PIPE\_DATA](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-server-worker-abnormal-pipe-data)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Server worker abnormal pipe data.
**`[SWOOLE\_ERROR\_SERVER\_WORKER\_UNPROCESSED\_DATA](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-server-worker-unprocessed-data)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Server worker unprocessed data.
**`[SWOOLE\_ERROR\_CO\_OUT\_OF\_COROUTINE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-co-out-of-coroutine)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine out of coroutine.
**`[SWOOLE\_ERROR\_CO\_HAS\_BEEN\_BOUND](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-co-has-been-bound)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine has been bound.
**`[SWOOLE\_ERROR\_CO\_HAS\_BEEN\_DISCARDED](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-co-has-been-discarded)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine has been discarded.
**`[SWOOLE\_ERROR\_CO\_MUTEX\_DOUBLE\_UNLOCK](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-co-mutex-double-unlock)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine mutex double unlock.
**`[SWOOLE\_ERROR\_CO\_BLOCK\_OBJECT\_LOCKED](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-co-block-object-locked)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine block object locked.
**`[SWOOLE\_ERROR\_CO\_BLOCK\_OBJECT\_WAITING](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-co-block-object-waiting)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine block object waiting.
**`[SWOOLE\_ERROR\_CO\_YIELD\_FAILED](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-co-yield-failed)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine yield failed.
**`[SWOOLE\_ERROR\_CO\_GETCONTEXT\_FAILED](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-co-getcontext-failed)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine getcontext failed.
**`[SWOOLE\_ERROR\_CO\_SWAPCONTEXT\_FAILED](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-co-swapcontext-failed)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine swapcontext failed.
**`[SWOOLE\_ERROR\_CO\_MAKECONTEXT\_FAILED](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-co-makecontext-failed)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine makecontext failed.
**`[SWOOLE\_ERROR\_CO\_IOCPINIT\_FAILED](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-co-iocpinit-failed)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine iocpinit failed.
**`[SWOOLE\_ERROR\_CO\_PROTECT\_STACK\_FAILED](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-co-protect-stack-failed)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine protect stack failed.
**`[SWOOLE\_ERROR\_CO\_STD\_THREAD\_LINK\_ERROR](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-co-std-thread-link-error)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine std thread link error.
**`[SWOOLE\_ERROR\_CO\_DISABLED\_MULTI\_THREAD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-co-disabled-multi-thread)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine disabled multi thread.
**`[SWOOLE\_ERROR\_CO\_CANNOT\_CANCEL](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-co-cannot-cancel)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine cannot cancel.
**`[SWOOLE\_ERROR\_CO\_NOT\_EXISTS](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-co-not-exists)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine not exists.
**`[SWOOLE\_ERROR\_CO\_CANCELED](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-co-canceled)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine canceled.
**`[SWOOLE\_ERROR\_CO\_TIMEDOUT](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-co-timedout)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine timedout.
**`[SWOOLE\_ERROR\_CO\_SOCKET\_CLOSE\_WAIT](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-error-co-socket-close-wait)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine socket close wait.
**`[SWOOLE\_TRACE\_SERVER](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-server)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record server log flag.
**`[SWOOLE\_TRACE\_CLIENT](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-client)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record client log flag.
**`[SWOOLE\_TRACE\_BUFFER](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-buffer)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record buffer log flag.
**`[SWOOLE\_TRACE\_CONN](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-conn)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record connect log flag.
**`[SWOOLE\_TRACE\_EVENT](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-event)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record event log flag.
**`[SWOOLE\_TRACE\_WORKER](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-worker)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record worker log flag.
**`[SWOOLE\_TRACE\_MEMORY](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-memory)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record memory log flag.
**`[SWOOLE\_TRACE\_REACTOR](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-reactor)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record reactor log flag.
**`[SWOOLE\_TRACE\_PHP](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-php)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record php log flag.
**`[SWOOLE\_TRACE\_HTTP](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-http)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record http log flag.
**`[SWOOLE\_TRACE\_HTTP2](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-http2)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record http2 log flag.
**`[SWOOLE\_TRACE\_EOF\_PROTOCOL](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-eof-protocol)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record eof protocol log flag.
**`[SWOOLE\_TRACE\_LENGTH\_PROTOCOL](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-length-protocol)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record length protocol log flag.
**`[SWOOLE\_TRACE\_CLOSE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-close)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record close event log flag.
**`[SWOOLE\_TRACE\_WEBSOCKET](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-websocket)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record websocket log flag.
**`[SWOOLE\_TRACE\_REDIS\_CLIENT](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-redis-client)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record redis client log flag.
**`[SWOOLE\_TRACE\_MYSQL\_CLIENT](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-mysql-client)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record mysql client log flag.
**`[SWOOLE\_TRACE\_HTTP\_CLIENT](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-http-client)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record http client log flag.
**`[SWOOLE\_TRACE\_AIO](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-aio)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record AIO log flag.
**`[SWOOLE\_TRACE\_SSL](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-ssl)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record SSL log flag.
**`[SWOOLE\_TRACE\_NORMAL](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-normal)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record normal log flag.
**`[SWOOLE\_TRACE\_CHANNEL](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-channel)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record channel log flag.
**`[SWOOLE\_TRACE\_TIMER](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-timer)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record timer log flag.
**`[SWOOLE\_TRACE\_SOCKET](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-socket)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record socket log flag.
**`[SWOOLE\_TRACE\_COROUTINE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-coroutine)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record coroutine log flag.
**`[SWOOLE\_TRACE\_CONTEXT](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-context)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record context log flag.
**`[SWOOLE\_TRACE\_CO\_HTTP\_SERVER](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-co-http-server)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record coroutine http server log flag.
**`[SWOOLE\_TRACE\_TABLE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-table)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record table log flag.
**`[SWOOLE\_TRACE\_CO\_CURL](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-co-curl)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record coroutine curl log flag.
**`[SWOOLE\_TRACE\_CARES](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-cares)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record cares log flag.
**`[SWOOLE\_TRACE\_ZLIB](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-zlib)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record zlib log flag.
**`[SWOOLE\_TRACE\_CO\_PGSQL](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-co-pgsql)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record pgsql coroutine log flag.
**`[SWOOLE\_TRACE\_CO\_ODBC](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-co-odbc)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record odbc coroutine log flag.
**`[SWOOLE\_TRACE\_CO\_ORACLE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-co-oracle)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record oracle coroutine log flag.
**`[SWOOLE\_TRACE\_CO\_SQLITE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-co-sqlite)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record sqlite coroutine log flag.
**`[SWOOLE\_TRACE\_ALL](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-trace-all)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record all level log flag.
**`[SWOOLE\_LOG\_DEBUG](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-log-debug)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record debug level log flag.
**`[SWOOLE\_LOG\_TRACE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-log-trace)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record trace level log flag.
**`[SWOOLE\_LOG\_INFO](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-log-info)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record info level log flag.
**`[SWOOLE\_LOG\_NOTICE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-log-notice)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record notice level log flag.
**`[SWOOLE\_LOG\_WARNING](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-log-warning)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record warning level log flag.
**`[SWOOLE\_LOG\_ERROR](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-log-error)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Record error level log flag.
**`[SWOOLE\_LOG\_NONE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-log-none)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Equivalent to turning off log information, log information will not be thrown.
**`[SWOOLE\_LOG\_ROTATION\_SINGLE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-log-rotation-single)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

disable log rotation.
**`[SWOOLE\_LOG\_ROTATION\_MONTHLY](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-log-rotation-monthly)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Rotate logs monthly.
**`[SWOOLE\_LOG\_ROTATION\_DAILY](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-log-rotation-daily)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Rotate logs daily.
**`[SWOOLE\_LOG\_ROTATION\_HOURLY](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-log-rotation-hourly)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Rotate logs hourly.
**`[SWOOLE\_LOG\_ROTATION\_EVERY\_MINUTE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-log-rotation-every-minute)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Rotate logs every minute.
**`[SWOOLE\_IPC\_NONE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-ipc-none)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Do not use any inter-process communication (IPC) features.
**`[SWOOLE\_IPC\_UNIXSOCK](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-ipc-unixsock)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

For inter-process communication (IPC), using Unix domain sockets (UnixSocket) in coroutine mode
is highly recommended.
**`[SWOOLE\_IPC\_SOCKET](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-ipc-socket)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

To use sockets for inter-process communication (IPC),
the listen method must be called to specify the address and port to monitor.
**`[SWOOLE\_IOV\_MAX](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-iov-max)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

MAX iov limit.
**`[SWOOLE\_IOURING\_DEFAULT](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-iouring-default)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

In interrupt-driven mode, I/O requests can be submitted via the io\_uring\_enter syscall,
and completion is determined by directly checking the completion queue status.
**`[SWOOLE\_IOURING\_SQPOLL](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-iouring-sqpoll)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

In kernel polling mode, the kernel creates dedicated threads to submit and reap I/O requests,
nearly eliminating user-kernel context switches.
**`[SWOOLE\_BASE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-base)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Basic mode.
**`[SWOOLE\_PROCESS](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-process)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Multi-process mode.
**`[SWOOLE\_THREAD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-thread)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Multi-thread mode.
**`[SWOOLE\_IPC\_UNSOCK](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-ipc-unsock)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

The task process communicates with the worker process using a Unix Socket.
**`[SWOOLE\_IPC\_MSGQUEUE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-ipc-msgqueue)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

The task process communicates with the worker process using a sysvmsg queue.
**`[SWOOLE\_IPC\_PREEMPTIVE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-ipc-preemptive)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

The task process communicates with the worker process using a preemptive mode over a sysvmsg queue.
**`[SWOOLE\_SERVER\_COMMAND\_MASTER](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-server-command-master)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Master process accept requests.
**`[SWOOLE\_SERVER\_COMMAND\_MANAGER](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-server-command-manager)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Manager process accept requests.
**`[SWOOLE\_SERVER\_COMMAND\_REACTOR\_THREAD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-server-command-reactor-thread)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Reactor thread accept requests.
**`[SWOOLE\_SERVER\_COMMAND\_EVENT\_WORKER](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-server-command-event-worker)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Event worker thread process accept requests.
**`[SWOOLE\_SERVER\_COMMAND\_TASK\_WORKER](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-server-command-task-worker)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Task worker thread process accept requests.
**`[SWOOLE\_DISPATCH\_ROUND](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-dispatch-round)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Round robin mode, each Worker process will be allocated sequentially for every received connection.
**`[SWOOLE\_DISPATCH\_FDMOD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-dispatch-fdmod)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Allocate Worker based on the connection's file descriptor. This ensures that data from the same connection
will be processed by the same Worker only.
**`[SWOOLE\_DISPATCH\_IDLE\_WORKER](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-dispatch-idle-worker)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

The main process will choose delivery based on the workload status of the Worker, delivering only to idle Workers.
**`[SWOOLE\_DISPATCH\_IPMOD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-dispatch-ipmod)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Allocate based on client IP using modulo hash, assigning to a specific Worker process.
This ensures that data from the same source IP connection will always be assigned to
the same Worker process. Algorithm: inet\_addr\_mod(ClientIP, worker\_num).
**`[SWOOLE\_DISPATCH\_UIDMOD](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-dispatch-uidmod)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Requires binding a connection to a unique uid by calling Server->bind() in the user code.
Then, the underlying system allocates to different Worker processes based on the value of UID.
Algorithm: UID % worker\_num. To use strings as UID, you can use crc32(UID\_STRING).
**`[SWOOLE\_DISPATCH\_USERFUNC](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-dispatch-userfunc)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Set a dispatch\_func callback function, where its return value determines
which process handles the request.
**`[SWOOLE\_DISPATCH\_CO\_CONN\_LB](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-dispatch-co-conn-lb)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Determine which process handles the request based on the number of connections.
**`[SWOOLE\_DISPATCH\_CO\_REQ\_LB](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-dispatch-co-req-lb)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Determine which process handles the request based on the number of requests.
**`[SWOOLE\_DISPATCH\_CONCURRENT\_LB](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-dispatch-concurrent-lb)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Determine which process handles the request based on concurrency count.
**`[SWOOLE\_WORKER\_BUSY](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-worker-busy)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Process is busy.
**`[SWOOLE\_WORKER\_IDLE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-worker-idle)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Process is idle.
**`[SWOOLE\_WORKER\_EXIT](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-worker-exit)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Process exited.
**`[SWOOLE\_MUTEX](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-mutex)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Mutex lock.
**`[SWOOLE\_RWLOCK](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-rwlock)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

RW lock.
**`[SWOOLE\_SPINLOCK](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-spinlock)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Spin lock.
**`[SWOOLE\_CORO\_MAX\_NUM\_LIMIT](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-coro-max-num-limit)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Maximum number of coroutines created(PHP\_INT\_MAX).
**`[SWOOLE\_CORO\_INIT](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-coro-init)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine initializing.
**`[SWOOLE\_CORO\_WAITING](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-coro-waiting)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine yield.
**`[SWOOLE\_CORO\_RUNNING](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-coro-running)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine completed
**`[SWOOLE\_CORO\_END](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-coro-end)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine completed.
**`[SWOOLE\_EXIT\_IN\_COROUTINE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-exit-in-coroutine)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Executing exit() function in coroutine.
**`[SWOOLE\_EXIT\_IN\_SERVER](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-exit-in-server)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Executing exit() function in server.
**`[SWOOLE\_HTTP2\_TYPE\_DATA](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-http2-type-data)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

HTTP2 data frame.
**`[SWOOLE\_HTTP2\_TYPE\_HEADERS](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-http2-type-headers)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

HTTP2 headers frame.
**`[SWOOLE\_HTTP2\_TYPE\_PRIORITY](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-http2-type-priority)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

HTTP2 priority frame.
**`[SWOOLE\_HTTP2\_TYPE\_RST\_STREAM](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-http2-type-rst-stream)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

HTTP2 rst stream frame.
**`[SWOOLE\_HTTP2\_TYPE\_SETTINGS](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-http2-type-settings)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

HTTP2 settings frame.
**`[SWOOLE\_HTTP2\_TYPE\_PUSH\_PROMISE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-http2-type-push-promise)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

HTTP2 push promise frame.
**`[SWOOLE\_HTTP2\_TYPE\_PING](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-http2-type-ping)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

HTTP2 ping frame.
**`[SWOOLE\_HTTP2\_TYPE\_GOAWAY](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-http2-type-goaway)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

HTTP2 goaway frame.
**`[SWOOLE\_HTTP2\_TYPE\_WINDOW\_UPDATE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-http2-type-window-update)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

HTTP2 window update frame.
**`[SWOOLE\_HTTP2\_TYPE\_CONTINUATION](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-http2-type-continuation)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

HTTP2 continuation frame.
**`[SWOOLE\_HTTP2\_ERROR\_NO\_ERROR](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-http2-error-no-error)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

HTTP2 no error.
**`[SWOOLE\_HTTP2\_ERROR\_PROTOCOL\_ERROR](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-http2-error-protocol-error)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

HTTP2 protocol error.
**`[SWOOLE\_HTTP2\_ERROR\_INTERNAL\_ERROR](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-http2-error-internal-error)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

HTTP2 internal error.
**`[SWOOLE\_HTTP2\_ERROR\_FLOW\_CONTROL\_ERROR](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-http2-error-flow-control-error)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

HTTP2 flow control error.
**`[SWOOLE\_HTTP2\_ERROR\_SETTINGS\_TIMEOUT](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-http2-error-settings-timeout)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

HTTP2 setting timeout error.
**`[SWOOLE\_HTTP2\_ERROR\_STREAM\_CLOSED](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-http2-error-stream-closed)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

HTTP2 stream closed error.
**`[SWOOLE\_HTTP2\_ERROR\_FRAME\_SIZE\_ERROR](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-http2-error-frame-size-error)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

HTTP2 frame size error error.
**`[SWOOLE\_HTTP2\_ERROR\_REFUSED\_STREAM](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-http2-error-refused-stream)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

HTTP2 refused stream error.
**`[SWOOLE\_HTTP2\_ERROR\_CANCEL](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-http2-error-cancel)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

HTTP2 cancel error.
**`[SWOOLE\_HTTP2\_ERROR\_COMPRESSION\_ERROR](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-http2-error-compression-error)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

HTTP2 compression error.
**`[SWOOLE\_HTTP2\_ERROR\_CONNECT\_ERROR](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-http2-error-connect-error)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

HTTP2 connect error.
**`[SWOOLE\_HTTP2\_ERROR\_ENHANCE\_YOUR\_CALM](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-http2-error-enhance-your-calm)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

HTTP2 enhance your calm error.
**`[SWOOLE\_HTTP2\_ERROR\_INADEQUATE\_SECURITY](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-http2-error-inadequate-security)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

HTTP2 inadequate security error.
**`[SWOOLE\_HTTP2\_ERROR\_HTTP\_1\_1\_REQUIRED](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-http2-error-http-1-1-required)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

HTTP2 require http1.1 error.
**`[SWOOLE\_HTTP\_CLIENT\_ESTATUS\_CONNECT\_FAILED](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-http-client-estatus-connect-failed)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Connection timeout, the server is not listening on the port or there is a network failure,
you can read $errCode to get the specific network error code.
**`[SWOOLE\_HTTP\_CLIENT\_ESTATUS\_REQUEST\_TIMEOUT](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-http-client-estatus-request-timeout)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Request timeout, the server did not return a response within the specified timeout time.
**`[SWOOLE\_HTTP\_CLIENT\_ESTATUS\_SERVER\_RESET](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-http-client-estatus-server-reset)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

After the client's request is sent, the server forcefully disconnects the connection.
**`[SWOOLE\_HTTP\_CLIENT\_ESTATUS\_SEND\_FAILED](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-http-client-estatus-send-failed)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Client send failed (this constant is available in Swoole version >= v4.5.9,
for versions less than this, please use the status code).
**`[SWOOLE\_MSGQUEUE\_ORIENT](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-msgqueue-orient)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Swoole\\Process::pop() will return specific data in the queue with the message type as process id + 1,
Swoole\\Process::push() will add the type process id + 1 to the message.
**`[SWOOLE\_MSGQUEUE\_BALANCE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-msgqueue-balance)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Swoole\\Process::pop() will return the first message in the queue,
Swoole\\Process::push() will not add a specific type to the message.
**`[SWOOLE\_HOOK\_TCP](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-hook-tcp)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine-based stream of TCP Socket type, including the most common ones like Redis, PDO, Mysqli.
**`[SWOOLE\_HOOK\_UDP](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-hook-udp)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine-based stream of UDP Socket type.
**`[SWOOLE\_HOOK\_UNIX](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-hook-unix)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine-based stream for Unix Stream Socket type.
**`[SWOOLE\_HOOK\_UDG](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-hook-udg)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine-based stream for UDG Stream Socket type.
**`[SWOOLE\_HOOK\_SSL](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-hook-ssl)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine-based stream for SSL Stream Socket type.
**`[SWOOLE\_HOOK\_TLS](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-hook-tls)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine-based stream for TLS Stream Socket type.
**`[SWOOLE\_HOOK\_STREAM\_FUNCTION](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-hook-stream-function)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine-based stream\_\*() function.
**`[SWOOLE\_HOOK\_FILE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-hook-file)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine-based file operations.
**`[SWOOLE\_HOOK\_STDIO](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-hook-stdio)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine-based STDIO operations.
**`[SWOOLE\_HOOK\_SLEEP](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-hook-sleep)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine-based sleep operations, including sleep, usleep, time\_nanosleep, time\_sleep\_until.
**`[SWOOLE\_HOOK\_PROC](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-hook-proc)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine-based proc\* functions, including: proc\_open, proc\_close, proc\_get\_status, proc\_terminate.
**`[SWOOLE\_HOOK\_CURL](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-hook-curl)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine-based for curl extension.
**`[SWOOLE\_HOOK\_NATIVE\_CURL](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-hook-native-curl)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine-based for native curl extension.
**`[SWOOLE\_HOOK\_BLOCKING\_FUNCTION](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-hook-blocking-function)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine-based for blocking function, include gethostbyname, exec, shell\_exec.
**`[SWOOLE\_HOOK\_SOCKETS](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-hook-sockets)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine-based for the sockets extension
**`[SWOOLE\_HOOK\_PDO\_PGSQL](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-hook-pdo-pgsql)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine-based for pdo\_pgsql extension.
**`[SWOOLE\_HOOK\_PDO\_ODBC](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-hook-pdo-odbc)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine-based for pdo\_odbc extension.
**`[SWOOLE\_HOOK\_PDO\_ORACLE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-hook-pdo-oracle)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine-based for pdo\_oci extension.
**`[SWOOLE\_HOOK\_PDO\_SQLITE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-hook-pdo-sqlite)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine-based for pdo\_sqlite extension.
**`[SWOOLE\_HOOK\_ALL](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-hook-all)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Coroutine-based for all block functions and extensions.
**`[SOCKET\_ECANCELED](https://www.php.net/manual/en/swoole.constants.php#constant.socket-ecanceled)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Socket ecanceled error.
**`[TCP\_INFO](https://www.php.net/manual/en/swoole.constants.php#constant.tcp-info)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TCP\_INFO.
**`[SWOOLE\_TIMER\_MIN\_MS](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-timer-min-ms)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Minimum supported timer interval (in milliseconds).
**`[SWOOLE\_TIMER\_MIN\_SEC](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-timer-min-sec)`**
([double](https://www.php.net/manual/en/language.types.float.php))

Minimum supported timer interval (in seconds).
**`[SWOOLE\_TIMER\_MAX\_MS](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-timer-max-ms)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Maximum supported timer interval (in milliseconds).
**`[SWOOLE\_TIMER\_MAX\_SEC](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-timer-max-sec)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Maximum supported timer interval (in seconds).
**`[SWOOLE\_WEBSOCKET\_STATUS\_CONNECTION](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-status-connection)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

WebSocket is establishing a connection.
**`[SWOOLE\_WEBSOCKET\_STATUS\_HANDSHAKE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-status-handshake)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

The WebSocket is in the handshake phase.
**`[SWOOLE\_WEBSOCKET\_STATUS\_ACTIVE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-status-active)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Active WebSocket connection.
**`[SWOOLE\_WEBSOCKET\_STATUS\_CLOSING](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-status-closing)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

WebSocket connection is closed.
**`[SWOOLE\_WEBSOCKET\_OPCODE\_CONTINUATION](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-opcode-continuation)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Websocket continuation frame.
**`[SWOOLE\_WEBSOCKET\_OPCODE\_TEXT](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-opcode-text)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Websocket text frame.
**`[SWOOLE\_WEBSOCKET\_OPCODE\_BINARY](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-opcode-binary)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Websocket binary frame.
**`[SWOOLE\_WEBSOCKET\_OPCODE\_CLOSE](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-opcode-close)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Websocket close frame.
**`[SWOOLE\_WEBSOCKET\_OPCODE\_PING](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-opcode-ping)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Websocket ping frame.
**`[SWOOLE\_WEBSOCKET\_OPCODE\_PONG](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-opcode-pong)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Websocket pong frame.
**`[SWOOLE\_WEBSOCKET\_FLAG\_FIN](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-flag-fin)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Websocket FIN flag.
**`[SWOOLE\_WEBSOCKET\_FLAG\_RSV1](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-flag-rsv1)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Websocket RSV1 flag.
**`[SWOOLE\_WEBSOCKET\_FLAG\_RSV2](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-flag-rsv2)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Websocket RSV2 flag.
**`[SWOOLE\_WEBSOCKET\_FLAG\_RSV3](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-flag-rsv3)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Websocket RSV3 flag.
**`[SWOOLE\_WEBSOCKET\_FLAG\_MASK](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-flag-mask)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Websocket MASK flag.
**`[SWOOLE\_WEBSOCKET\_FLAG\_COMPRESS](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-flag-compress)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Websocket COMPRESS flag.
**`[SWOOLE\_WEBSOCKET\_CLOSE\_NORMAL](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-close-normal)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Normal closure (connection completed successfully).
**`[SWOOLE\_WEBSOCKET\_CLOSE\_GOING\_AWAY](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-close-going-away)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Endpoint is going away (e.g., browser tab closed).
**`[SWOOLE\_WEBSOCKET\_CLOSE\_PROTOCOL\_ERROR](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-close-protocol-error)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Protocol error (malformed data frame).
**`[SWOOLE\_WEBSOCKET\_CLOSE\_DATA\_ERROR](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-close-data-error)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Received unsupported data (e.g., binary when expecting text).
**`[SWOOLE\_WEBSOCKET\_CLOSE\_STATUS\_ERROR](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-close-status-error)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

No status code provided (sent as a placeholder).
**`[SWOOLE\_WEBSOCKET\_CLOSE\_ABNORMAL](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-close-abnormal)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Abnormal closure (no close frame received, e.g., TCP reset).
**`[SWOOLE\_WEBSOCKET\_CLOSE\_MESSAGE\_ERROR](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-close-message-error)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Invalid data (e.g., non-UTF-8 text in a text frame).
**`[SWOOLE\_WEBSOCKET\_CLOSE\_POLICY\_ERROR](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-close-policy-error)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Policy violation (e.g., unauthorized action).
**`[SWOOLE\_WEBSOCKET\_CLOSE\_MESSAGE\_TOO\_BIG](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-close-message-too-big)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Message too large (exceeds server’s max size).
**`[SWOOLE\_WEBSOCKET\_CLOSE\_EXTENSION\_MISSING](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-close-extension-missing)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Client didn’t negotiate required extensions.
**`[SWOOLE\_WEBSOCKET\_CLOSE\_SERVER\_ERROR](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-close-server-error)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Server encountered an error.
**`[SWOOLE\_WEBSOCKET\_CLOSE\_CLOSE\_SERVICE\_RESTART](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-close-close-service-restart)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Server is restarting (temporary condition).
**`[SWOOLE\_WEBSOCKET\_CLOSE\_TRY\_AGAIN\_LATER](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-close-try-again-later)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Temporary server overload (client should retry).
**`[SWOOLE\_WEBSOCKET\_CLOSE\_BAD\_GATEWAY](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-close-bad-gateway)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Invalid response from upstream server.
**`[SWOOLE\_WEBSOCKET\_CLOSE\_TLS](https://www.php.net/manual/en/swoole.constants.php#constant.swoole-websocket-close-tls)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

TLS handshake failed (used when HTTPS fails).


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/swoole/constants.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fswoole.constants%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=swoole.constants&repo=en&redirect=https://www.php.net/manual/en/swoole.constants.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google