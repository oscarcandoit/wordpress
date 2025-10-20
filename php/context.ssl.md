---
url: https://www.php.net/manual/en/context.ssl.php
scraped_at: 2025-10-20T02:35:25.986Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# SSL context options

SSL context options — SSL context option listing

### Description [¶](https://www.php.net/manual/en/context.ssl.php\#refsect1-context.ssl-description)

Context options for `ssl://` and `tls://`
transports.


### Options [¶](https://www.php.net/manual/en/context.ssl.php\#refsect1-context.ssl-options)

`peer_name` [string](https://www.php.net/manual/en/language.types.string.php)

Peer name to be used. If this value is not set, then the name is guessed
based on the hostname used when opening the stream.


`verify_peer` [bool](https://www.php.net/manual/en/language.types.boolean.php)

Require verification of SSL certificate used.


Defaults to **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**.


`verify_peer_name` [bool](https://www.php.net/manual/en/language.types.boolean.php)

Require verification of peer name.


Defaults to **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**.


`allow_self_signed` [bool](https://www.php.net/manual/en/language.types.boolean.php)

Allow self-signed certificates. Requires
[`verify_peer`](https://www.php.net/manual/en/context.ssl.php#context.ssl.verify-peer).


Defaults to **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**

`cafile` [string](https://www.php.net/manual/en/language.types.string.php)

Location of Certificate Authority file on local filesystem
which should be used with the `verify_peer`
context option to authenticate the identity of the remote peer.


`capath` [string](https://www.php.net/manual/en/language.types.string.php)

If `cafile` is not specified or if the certificate
is not found there, the directory pointed to by `capath`
is searched for a suitable certificate. `capath`
must be a correctly hashed certificate directory.


`local_cert` [string](https://www.php.net/manual/en/language.types.string.php)

Path to local certificate file on filesystem. It must be a
PEM encoded file which contains your certificate and
private key. It can optionally contain the certificate chain of issuers.
The private key also may be contained in a separate file specified
by `local_pk`.


`local_pk` [string](https://www.php.net/manual/en/language.types.string.php)

Path to local private key file on filesystem in case of separate
files for certificate ( `local_cert`) and private key.


`passphrase` [string](https://www.php.net/manual/en/language.types.string.php)

Passphrase with which your `local_cert` file
was encoded.


`verify_depth` [int](https://www.php.net/manual/en/language.types.integer.php)

Abort if the certificate chain is too deep.


Defaults to no verification.


`ciphers` [string](https://www.php.net/manual/en/language.types.string.php)

Sets the list of available ciphers. The format of the string is described
in [» ciphers(1)](https://www.openssl.org/docs/manmaster/man1/ciphers.html#CIPHER-LIST-FORMAT).


Defaults to `DEFAULT`.


`capture_peer_cert` [bool](https://www.php.net/manual/en/language.types.boolean.php)

If set to **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** a `peer_certificate` context option
will be created containing the peer certificate.


`capture_peer_cert_chain` [bool](https://www.php.net/manual/en/language.types.boolean.php)

If set to **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** a `peer_certificate_chain` context
option will be created containing the certificate chain.


`SNI_enabled` [bool](https://www.php.net/manual/en/language.types.boolean.php)

If set to **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** server name indication will be enabled. Enabling SNI
allows multiple certificates on the same IP address.


`disable_compression` [bool](https://www.php.net/manual/en/language.types.boolean.php)

If set, disable TLS compression. This can help mitigate the CRIME attack
vector.


`peer_fingerprint` [string](https://www.php.net/manual/en/language.types.string.php) \| [array](https://www.php.net/manual/en/language.types.array.php)

Aborts when the remote certificate digest doesn't match the specified
hash.


When a [string](https://www.php.net/manual/en/language.types.string.php) is used, the length will determine which hashing algorithm
is applied, either "md5" (32) or "sha1" (40).


When an [array](https://www.php.net/manual/en/language.types.array.php) is used, the keys indicate the hashing algorithm name
and each corresponding value is the expected digest.


`security_level` [int](https://www.php.net/manual/en/language.types.integer.php)

Sets the security level. If not specified the library default security level is used.
The security levels are described in
[» SSL\_CTX\_get\_security\_level(3)](https://www.openssl.org/docs/man1.1.1/man3/SSL_CTX_get_security_level.html).


Available as of PHP 7.2.0 and OpenSSL 1.1.0.


### Changelog [¶](https://www.php.net/manual/en/context.ssl.php\#refsect1-context.ssl-changelog)

| Version | Description |
| --- | --- |
| 7.2.0 | Added `security_level`. Requires OpenSSL >= 1.1.0. |

### Notes [¶](https://www.php.net/manual/en/context.ssl.php\#refsect1-context.ssl-notes)

> **Note**:
>
> Because `ssl://` is the underlying transport for the
> [`https://`](https://www.php.net/manual/en/wrappers.http.php) and
> [`ftps://`](https://www.php.net/manual/en/wrappers.ftp.php) wrappers,
> any context options which apply to `ssl://` also apply to
> `https://` and `ftps://`.

> **Note**:
>
> For SNI (Server Name Indication) to be available, then PHP must be compiled
> with OpenSSL 0.9.8j or greater. Use the
> **`[OPENSSL\_TLSEXT\_SERVER\_NAME](https://www.php.net/manual/en/openssl.constsni.php#constant.openssl-tlsext-server-name)`** to determine whether SNI is
> supported.

### See Also [¶](https://www.php.net/manual/en/context.ssl.php\#refsect1-context.ssl-seealso)

- [Socket context options](https://www.php.net/manual/en/context.socket.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/context/ssl.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fcontext.ssl%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=context.ssl&repo=en&redirect=https://www.php.net/manual/en/context.ssl.php)

### User Contributed Notes 9 notes

[up](https://www.php.net/manual/vote-note.php?id=119844&page=context.ssl&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119844&page=context.ssl&vote=down "Vote down!")

9


[**_website at meezaan dot net_**](https://www.php.net/manual/en/context.ssl.php#119844) [¶](https://www.php.net/manual/en/context.ssl.php#119844)

**9 years ago**

`There is also a crypto_type context. In older versions this was crypto_method. This is referenced on [http://php.net/manual/en/function.stream-socket-enable-crypto.php](http://php.net/manual/en/function.stream-socket-enable-crypto.php)`

[up](https://www.php.net/manual/vote-note.php?id=128002&page=context.ssl&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128002&page=context.ssl&vote=down "Vote down!")

6


[**_tianyiw at vip dot qq dot com_**](https://www.php.net/manual/en/context.ssl.php#128002) [¶](https://www.php.net/manual/en/context.ssl.php#128002)

**2 years ago**

`Enable SNI (Server Name Indication):
PEM must be contains certificate and private key.
<?php
$context = stream_context_create([\
    'ssl' => [\
        'SNI_enabled' => true,\
        'SNI_server_certs' => [\
            'host1.com' => '/path/host1.com.pem',\
            'host2.com' => '/path/host2.com.pem',\
        ],\
    ]\
]);
?>`

[up](https://www.php.net/manual/vote-note.php?id=124605&page=context.ssl&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124605&page=context.ssl&vote=down "Vote down!")

4


[**_gabri dot ns at gmail dot com_**](https://www.php.net/manual/en/context.ssl.php#124605) [¶](https://www.php.net/manual/en/context.ssl.php#124605)

**5 years ago**

`i usually download root CA certificate from [https://curl.haxx.se/docs/caextract.html](https://curl.haxx.se/docs/caextract.html) then put it as 'cafile' and it work almost all of the time.
the only problem i'v ever found is when the server does not properly sending intermediete CA certificate, then, you must add it manually to the file.`

[up](https://www.php.net/manual/vote-note.php?id=120278&page=context.ssl&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120278&page=context.ssl&vote=down "Vote down!")

4


[**_Charlie_**](https://www.php.net/manual/en/context.ssl.php#120278) [¶](https://www.php.net/manual/en/context.ssl.php#120278)

**8 years ago**

`I am unable to load a PEM that was generated with the stunnel tools. However, I am able to use PHP calls to generate a working PEM that is recognized both by stunnel and php, as outlined here:
[http://www.devdungeon.com/content/how-use-ssl-sockets-php](http://www.devdungeon.com/content/how-use-ssl-sockets-php)
This code fragment is now working for me, and with stunnel verify=4, both sides confirm the fingerprint. Oddly, if "tls://" is set below, then TLSv1 is forced, but using "ssl://" allows TLSv1.2:
$stream_context = stream_context_create([ 'ssl' => [\
'local_cert'        => '/path/to/key.pem',\
'peer_fingerprint'  => openssl_x509_fingerprint(file_get_contents('/path/to/key.crt')),\
'verify_peer'       => false,\
'verify_peer_name'  => false,\
'allow_self_signed' => true,\
'verify_depth'      => 0 ]]);
$fp = stream_socket_client('ssl://ssl.server.com:12345',
$errno, $errstr, 30, STREAM_CLIENT_CONNECT, $stream_context);
fwrite($fp, "foo bar\n");
while($line = fgets($fp, 8192)) echo $line;`

[up](https://www.php.net/manual/vote-note.php?id=96328&page=context.ssl&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=96328&page=context.ssl&vote=down "Vote down!")

3


[**_Botjan kufca_**](https://www.php.net/manual/en/context.ssl.php#96328) [¶](https://www.php.net/manual/en/context.ssl.php#96328)

**15 years ago**

`CN_match works contrary to intuitive thinking. I came across this when I was developing SSL server implemented in PHP. I stated (in code):
- do not allow self signed certs (works)
- verify peer certs against CA cert (works)
- verify the client's CN against CN_match (does not work), like this:
stream_context_set_option($context, 'ssl', 'CN_match', '*.example.org');
I presumed this would match any client with CN below .example.org domain.
Unfortunately this is NOT the case. The option above does not do that.
What it really does is this:
- it takes client's CN and compares it to CN_match
- IF CLIENT's CN CONTAINS AN ASTERISK like *.example.org, then it is matched against CN_match in wildcard matching fashion
Examples to illustrate behaviour:
(CNM = server's CN_match)
(CCN = client's CN)
- CNM=host.example.org, CCN=host.example.org ---> OK
- CNM=host.example.org, CCN=*.example.org ---> OK
- CNM=.example.org, CCN=*.example.org ---> OK
- CNM=example.org, CCN=*.example.org ---> ERROR
- CNM=*.example.org, CCN=host.example.org ---> ERROR
- CNM=*.example.org, CCN=*.example.org ---> OK
According to PHP sources I believe that the same applies if you are trying to act as Client and the server contains a wildcard certificate. If you set CN_match to myserver.example.org and server presents itself with *.example.org, the connection is allowed.
Everything above applies to PHP version 5.2.12.
I will supply a patch to support CN_match starting with asterisk.`

[up](https://www.php.net/manual/vote-note.php?id=114269&page=context.ssl&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114269&page=context.ssl&vote=down "Vote down!")

1


[**_borbas dot geri at gmail dot com_**](https://www.php.net/manual/en/context.ssl.php#114269) [¶](https://www.php.net/manual/en/context.ssl.php#114269)

**11 years ago**

``I used this for Apple Push Notification Service.
Passed in a local certificate filename `cert.pem` trough local_cert option.
Worked fine, when invoked the script directly.
But when I included/required the script from a different location, it stopped working, without any explicit error message.
Resolved by passed in the full path for the file `<FullPathTo>cert.pem`.``

[up](https://www.php.net/manual/vote-note.php?id=126992&page=context.ssl&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126992&page=context.ssl&vote=down "Vote down!")

0


[**_consatangmail dot com_**](https://www.php.net/manual/en/context.ssl.php#126992) [¶](https://www.php.net/manual/en/context.ssl.php#126992)

**3 years ago**

`recommended use "ssl://" transport.
in php 5.5 ~ 7.1
ssl:// transport = ssl_v2|ssl_v3|tls_v1.0|tls_v1.1|tls_v1.2
tls:// transport = tls_v1.0
after 7.2 ssl:// and tls:// transports is same
php 7.2 ~ 7.3 = tls_v1.0|tls_v1.1|tls_v1.2
php 7.4 ~ 8.1 = tls_v1.0|tls_v1.1|tls_v1.2|tls_v1.3`

[up](https://www.php.net/manual/vote-note.php?id=120265&page=context.ssl&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120265&page=context.ssl&vote=down "Vote down!")

 -1


[**_Charlie_**](https://www.php.net/manual/en/context.ssl.php#120265) [¶](https://www.php.net/manual/en/context.ssl.php#120265)

**8 years ago**

`It appears that "allow_self_signed" does not and cannot apply to the local_cert option.
The stunnel verify=4 option, which verifies but ignores a CA, has no analog in these settings, which is unfortunate.
Even more perplexingly, while the "openssl verify -CAfile" is successful, PHP appears unable to use the new ca/crt pair in any configuration.
I did actually link my PHP against a copy of LibreSSL 2.3.8, but PHP oddly is unable to use TLS1.1 or 1.2. It does, however, enable EC secp521r1 (of which my native OpenSSL 0.9.8e is incapable).`

[up](https://www.php.net/manual/vote-note.php?id=123325&page=context.ssl&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123325&page=context.ssl&vote=down "Vote down!")

 -1


[**_mechtecs at gmail dot com_**](https://www.php.net/manual/en/context.ssl.php#123325) [¶](https://www.php.net/manual/en/context.ssl.php#123325)

**6 years ago**

`If you want to validate the server against a local certificate, which you already saved, to further validate the target server, you have to use a fullchain.pem. Then the verify_peer option will work. So just get the server certificate, and search the root CA's pem's and copy everything into a single file. For example:
My certificate has the "GeoTrust TLS RSA CA G1" certificate in the chain, so you google that string. Go to the official digicert Geotrust page and download the "GeoTrustTLSRSACAG1.crt" certificate. Then you can use the following command to convert it into the pem format:
openssl x509 -inform DER -in GeoTrustTLSRSACAG1.crt -out GeoTrustTLSRSACAG1.crt.pem -outform PEM`

[＋add a note](https://www.php.net/manual/add-note.php?sect=context.ssl&repo=en&redirect=https://www.php.net/manual/en/context.ssl.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google