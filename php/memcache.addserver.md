---
url: https://www.php.net/manual/en/memcache.addserver.php
scraped_at: 2025-10-20T02:34:29.477Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Memcache::addServer

# memcache\_add\_server

(PECL memcache >= 2.0.0)

Memcache::addServer \-\- memcache\_add\_server — Add a memcached server to connection pool

### Description [¶](https://www.php.net/manual/en/memcache.addserver.php\#refsect1-memcache.addserver-description)

**Memcache::addServer**(

[string](https://www.php.net/manual/en/language.types.string.php) `$host`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$port` = 11211,

[bool](https://www.php.net/manual/en/language.types.boolean.php) `$persistent` = ?,

[int](https://www.php.net/manual/en/language.types.integer.php) `$weight` = ?,

[int](https://www.php.net/manual/en/language.types.integer.php) `$timeout` = ?,

[int](https://www.php.net/manual/en/language.types.integer.php) `$retry_interval` = ?,

[bool](https://www.php.net/manual/en/language.types.boolean.php) `$status` = ?,

[callable](https://www.php.net/manual/en/language.types.callable.php) `$failure_callback` = ?,

[int](https://www.php.net/manual/en/language.types.integer.php) `$timeoutms` = ?

): [bool](https://www.php.net/manual/en/language.types.boolean.php)

**memcache\_add\_server**(

[Memcache](https://www.php.net/manual/en/class.memcache.php) `$memcache`,

[string](https://www.php.net/manual/en/language.types.string.php) `$host`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$port` = 11211,

[bool](https://www.php.net/manual/en/language.types.boolean.php) `$persistent` = ?,

[int](https://www.php.net/manual/en/language.types.integer.php) `$weight` = ?,

[int](https://www.php.net/manual/en/language.types.integer.php) `$timeout` = ?,

[int](https://www.php.net/manual/en/language.types.integer.php) `$retry_interval` = ?,

[bool](https://www.php.net/manual/en/language.types.boolean.php) `$status` = ?,

[callable](https://www.php.net/manual/en/language.types.callable.php) `$failure_callback` = ?,

[int](https://www.php.net/manual/en/language.types.integer.php) `$timeoutms` = ?

): [bool](https://www.php.net/manual/en/language.types.boolean.php)

**Memcache::addServer()** adds a server to the connection pool.


When using this method (as opposed to [Memcache::connect()](https://www.php.net/manual/en/memcache.connect.php) and
[Memcache::pconnect()](https://www.php.net/manual/en/memcache.pconnect.php)) the network connection is not established
until actually needed. Thus there is no overhead in adding a large number of servers
to the pool, even though they might not all be used.


Failover may occur at any stage in any of the methods, as long as other
servers are available the request the user won't notice. Any kind of
socket or Memcached server level errors (except out-of-memory) may trigger
the failover. Normal client errors such as adding an existing key will not
trigger a failover.


> **Note**:
>
>
> This function has been added to Memcache version 2.0.0.

### Parameters [¶](https://www.php.net/manual/en/memcache.addserver.php\#refsect1-memcache.addserver-parameters)

`host`

Point to the host where memcached is listening for connections. This parameter
may also specify other transports like `unix:///path/to/memcached.sock`
to use UNIX domain sockets, in this case `port` must also
be set to `0`.


`port`

Point to the port where memcached is listening for connections.
Set this
parameter to `0` when using UNIX domain sockets.


Please note: `port` defaults to
[memcache.default\_port](https://www.php.net/manual/en/memcache.ini.php#ini.memcache.default-port)
if not specified. For this reason it is wise to specify the port
explicitly in this method call.


`persistent`

Controls the use of a persistent connection. Default to **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**.


`weight`

Number of buckets to create for this server which in turn control its
probability of it being selected. The probability is relative to the
total weight of all servers.


`timeout`

Value in seconds which will be used for connecting to the daemon. Think
twice before changing the default value of 1 second - you can lose all
the advantages of caching if your connection is too slow.


`retry_interval`

Controls how often a failed server will be retried, the default value
is 15 seconds. Setting this parameter to -1 disables automatic retry.
Neither this nor the `persistent` parameter has any
effect when the extension is loaded dynamically via [dl()](https://www.php.net/manual/en/function.dl.php).


Each failed connection struct has its own timeout and before it has expired
the struct will be skipped when selecting backends to serve a request. Once
expired the connection will be successfully reconnected or marked as failed
for another `retry_interval` seconds. The typical
effect is that each web server child will retry the connection about every
`retry_interval` seconds when serving a page.


`status`

Controls if the server should be flagged as online. Setting this parameter
to **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** and `retry_interval` to -1 allows a failed
server to be kept in the pool so as not to affect the key distribution
algorithm. Requests for this server will then failover or fail immediately
depending on the `memcache.allow_failover` setting.
Default to **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**, meaning the server should be considered online.


`failure_callback`

Allows the user to specify a callback function to run upon encountering an
error. The callback is run before failover is attempted. The function takes
two parameters, the hostname and port of the failed server.


`timeoutms`

### Return Values [¶](https://www.php.net/manual/en/memcache.addserver.php\#refsect1-memcache.addserver-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Examples [¶](https://www.php.net/manual/en/memcache.addserver.php\#refsect1-memcache.addserver-examples)

**Example #1 **Memcache::addServer()** example**

`<?php
/* OO API */
$memcache = new Memcache;
$memcache->addServer('memcache_host', 11211);
$memcache->addServer('memcache_host2', 11211);
/* procedural API */
$memcache_obj = memcache_connect('memcache_host', 11211);
memcache_add_server($memcache_obj, 'memcache_host2', 11211);
?>`

### Notes [¶](https://www.php.net/manual/en/memcache.addserver.php\#refsect1-memcache.addserver-notes)

**Warning**

When the `port` is unspecified, this method defaults to the
value set of the PHP ini directive
[memcache.default\_port](https://www.php.net/manual/en/memcache.ini.php#ini.memcache.default-port)
If this value was changed elsewhere in your application it might lead to
unexpected results: for this reason it is wise to always specify the port
explicitly in this method call.


### See Also [¶](https://www.php.net/manual/en/memcache.addserver.php\#refsect1-memcache.addserver-seealso)

- [Memcache::connect()](https://www.php.net/manual/en/memcache.connect.php) \- Open memcached server connection
- [Memcache::pconnect()](https://www.php.net/manual/en/memcache.pconnect.php) \- Open memcached server persistent connection
- [Memcache::close()](https://www.php.net/manual/en/memcache.close.php) \- Close memcached server connection
- [Memcache::setServerParams()](https://www.php.net/manual/en/memcache.setserverparams.php) \- Changes server parameters and status at runtime
- [Memcache::getServerStatus()](https://www.php.net/manual/en/memcache.getserverstatus.php) \- Returns server status

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/memcache/memcache/addserver.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmemcache.addserver%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=memcache.addserver&repo=en&redirect=https://www.php.net/manual/en/memcache.addserver.php)

### User Contributed Notes 6 notes

[up](https://www.php.net/manual/vote-note.php?id=104484&page=memcache.addserver&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=104484&page=memcache.addserver&vote=down "Vote down!")

6


[**_rstaveley at seseit dot com_**](https://www.php.net/manual/en/memcache.addserver.php#104484) [¶](https://www.php.net/manual/en/memcache.addserver.php#104484)

**14 years ago**

`The Memcache client library is responsible for picking the right server to set/get data. That's why addServer is what you want to use rather than connect, when you have more than one Memcache server. A subsequent set/get will then connect on demand to the appropriate instance as needs be. Disconnection to whatever servers were connected to happening when you close or your script terminates.
Memcache instances added to your Memcache object via addServer should be added in the same order in your application to ensure that the same server is picked for use with the same key.
A client library may be implemented to run a CRC on the key and do a modulus over the number of instances in the list to select an instance from the list for the set/get. This ensures that data is spread nicely across the nodes.
That all works nicely behind the scenes for you in your PHP code, as long as you add your list of Memcache instances in a consistent manner with addServer.`

[up](https://www.php.net/manual/vote-note.php?id=105728&page=memcache.addserver&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=105728&page=memcache.addserver&vote=down "Vote down!")

3


[**_enno dot rehling at gmail dot com_**](https://www.php.net/manual/en/memcache.addserver.php#105728) [¶](https://www.php.net/manual/en/memcache.addserver.php#105728)

**14 years ago**

`The $timeoutms argument can be used to specify the timeout in milliseconds, but isn't available in all versions. For example, it exists in php_memcache 2.2.6, but not in 3.0.4. In 2.2.6, if you specify it, then it overrides $timeout.
Caveat emptor: If $timeoutms is not specified, it defaults to the value of memcache.default_timeout_ms in php.ini, which defaults to 1000 if not set. This also overrides $timeout, which has the curious effect that $timeout is always ignored in php_memcache 2.2.6 (either in favor of $timeoutms, memcache.default_timeout_ms or the value 1000, in that order of priority).`

[up](https://www.php.net/manual/vote-note.php?id=113527&page=memcache.addserver&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113527&page=memcache.addserver&vote=down "Vote down!")

2


[**_joewynn dot nz+phpnet at gmail dot com_**](https://www.php.net/manual/en/memcache.addserver.php#113527) [¶](https://www.php.net/manual/en/memcache.addserver.php#113527)

**11 years ago**

`Note that this method will always return TRUE because a connection is not actually made at call time. See this bug report for more information: [https://bugs.php.net/bug.php?id=58193](https://bugs.php.net/bug.php?id=58193)`

[up](https://www.php.net/manual/vote-note.php?id=103801&page=memcache.addserver&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=103801&page=memcache.addserver&vote=down "Vote down!")

1


[**_eu at serbannistor dot ro_**](https://www.php.net/manual/en/memcache.addserver.php#103801) [¶](https://www.php.net/manual/en/memcache.addserver.php#103801)

**14 years ago**

`Actually if you have two memcached servers from which one of them is on localhost, and the other is on a remote machine you can communicate with both even if you specify the loopback address for the local one.
<?php
$memcache_obj = memcache_connect("127.0.0.1", 11211);
memcache_add_server($memcache_obj, "memcache_remote_host");
$memcache_obj->set('var_key', time());
?>
This WILL communicate with both hosts but however there are two aspects that must be taken into account:
1. the communication will be done through different network interfaces with the two hosts. It will use the loopback interface for the "127.0.0.1" host (lo in my case on Linux) and the external interface for the "memcache_remote_host" (eth0 in my case). Only if you want to use the same network interface to communicate with both hosts you must use the external IPs of both machines (and all communication will go out through the eth0 interface).
2. the connection with the two hosts will be established differently because of how memcache_connect() and memcache_add_server() work. Therefore the memcache_connect() will initiate the connection to localhost through the loopback interface when it is called, while memcache_add_server() will just add the second server to the pool, but it will not send any package through the network until it's absolutely needed (for example when a memcache_set() command is issued).`

[up](https://www.php.net/manual/vote-note.php?id=96084&page=memcache.addserver&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=96084&page=memcache.addserver&vote=down "Vote down!")

0


[**_iwind dot liu at gmail dot com_**](https://www.php.net/manual/en/memcache.addserver.php#96084) [¶](https://www.php.net/manual/en/memcache.addserver.php#96084)

**15 years ago**

`The weight of the server must be greater than 0.
If there is no memcached server to use, and you try to set/add variables, the apache will be crashed, with the error message "[notice] child pid 18725 exit signal Segmentation fault (11)" in error_log file.`

[up](https://www.php.net/manual/vote-note.php?id=82984&page=memcache.addserver&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=82984&page=memcache.addserver&vote=down "Vote down!")

 -5


[**_Jean-Baptiste Quenot_**](https://www.php.net/manual/en/memcache.addserver.php#82984) [¶](https://www.php.net/manual/en/memcache.addserver.php#82984)

**17 years ago**

`The default value for the "weight" argument is 1`

[＋add a note](https://www.php.net/manual/add-note.php?sect=memcache.addserver&repo=en&redirect=https://www.php.net/manual/en/memcache.addserver.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google