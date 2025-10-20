---
url: https://www.php.net/manual/en/memcached.addserver.php
scraped_at: 2025-10-20T02:50:37.721Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Memcached::addServer

(PECL memcached >= 0.1.0)

Memcached::addServer — Add a server to the server pool

### Description [¶](https://www.php.net/manual/en/memcached.addserver.php\#refsect1-memcached.addserver-description)

public**Memcached::addServer**([string](https://www.php.net/manual/en/language.types.string.php) `$host`, [int](https://www.php.net/manual/en/language.types.integer.php) `$port`, [int](https://www.php.net/manual/en/language.types.integer.php) `$weight` = 0): [bool](https://www.php.net/manual/en/language.types.boolean.php)

**Memcached::addServer()** adds the specified server to the
server pool. No connection is established to the server at this time, but
if you are using consistent key distribution option (via
**`[Memcached::DISTRIBUTION\_CONSISTENT](https://www.php.net/manual/en/memcached.constants.php#memcached.constants.distribution-consistent)`** or
**`[Memcached::OPT\_LIBKETAMA\_COMPATIBLE](https://www.php.net/manual/en/memcached.constants.php#memcached.constants.opt-libketama-compatible)`**), some of the
internal data structures will have to be updated. Thus, if you need to add
multiple servers, it is better to use
[Memcached::addServers()](https://www.php.net/manual/en/memcached.addservers.php) as the update then happens
only once.


The same server may appear multiple times in the server pool, because no
duplication checks are made. This is not advisable; instead, use the
`weight` option to increase the selection weighting of
this server.


### Parameters [¶](https://www.php.net/manual/en/memcached.addserver.php\#refsect1-memcached.addserver-parameters)

`host`

The hostname of the memcache server. If the hostname is invalid,
data-related operations will set
**`[Memcached::RES\_HOST\_LOOKUP\_FAILURE](https://www.php.net/manual/en/memcached.constants.php#memcached.constants.res-host-lookup-failure)`** result code. As
of version 2.0.0b1, this parameter may also specify the path of a unix
socket filepath ex. `/path/to/memcached.sock`
to use UNIX domain sockets, in this case `port`
must also be set to `0`.


`port`

The port on which memcache is running. Usually, this is
`11211`. As of version 2.0.0b1, set this parameter to `0` when
using UNIX domain sockets.


`weight`

The weight of the server relative to the total weight of all the
servers in the pool. This controls the probability of the server being
selected for operations. This is used only with consistent distribution
option and usually corresponds to the amount of memory available to
memcache on that server.


### Return Values [¶](https://www.php.net/manual/en/memcached.addserver.php\#refsect1-memcached.addserver-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Examples [¶](https://www.php.net/manual/en/memcached.addserver.php\#refsect1-memcached.addserver-examples)

**Example #1 **Memcached::addServer()** example**

`<?php
$m = new Memcached();
/* Add 2 servers, so that the second one
is twice as likely to be selected. */
$m->addServer('mem1.domain.com', 11211, 33);
$m->addServer('mem2.domain.com', 11211, 67);
?>`

### See Also [¶](https://www.php.net/manual/en/memcached.addserver.php\#refsect1-memcached.addserver-seealso)

- [Memcached::addServers()](https://www.php.net/manual/en/memcached.addservers.php) \- Add multiple servers to the server pool
- [Memcached::resetServerList()](https://www.php.net/manual/en/memcached.resetserverlist.php) \- Clears all servers from the server list

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/memcached/memcached/addserver.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmemcached.addserver%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=memcached.addserver&repo=en&redirect=https://www.php.net/manual/en/memcached.addserver.php)

### User Contributed Notes 3 notes

[up](https://www.php.net/manual/vote-note.php?id=110003&page=memcached.addserver&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=110003&page=memcached.addserver&vote=down "Vote down!")

19


[**_mbarriolinares at gmail dot com_**](https://www.php.net/manual/en/memcached.addserver.php#110003) [¶](https://www.php.net/manual/en/memcached.addserver.php#110003)

**13 years ago**

`Important to not call ->addServers() every run -- only call it if no servers exist (check getServerList() ); otherwise, since addServers() does not check for dups, it will let you add the same server again and again and again, resultings in hundreds if not thousands of connections to the MC daemon. Specially when using FastCGI.
Example:
<?php
class Cache {
        private $id;
        private $obj;
        function __construct($id){
                $this->id = $id;
                $this->obj = new Memcached($id);
        }
        public function connect($host , $port){
                $servers = $this->obj->getServerList();
                if(is_array($servers)) {
                        foreach ($servers as $server)
                                if($server['host'] == $host and $server['port'] == $port)
                                        return true;
                }
                return $this->obj->addServer($host , $port);
        }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=110661&page=memcached.addserver&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=110661&page=memcached.addserver&vote=down "Vote down!")

16


[**_Dave_**](https://www.php.net/manual/en/memcached.addserver.php#110661) [¶](https://www.php.net/manual/en/memcached.addserver.php#110661)

**12 years ago**

`As of version 2.0.0b1 you can use Unix socket.
<?php
$m = new Memcached();
$m->addServer('/path/to/socket',0);
?>
Not to be confused with Memcache that use 'unix:///path/to/socket'`

[up](https://www.php.net/manual/vote-note.php?id=105501&page=memcached.addserver&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=105501&page=memcached.addserver&vote=down "Vote down!")

2


[**_Robbie De Lise_**](https://www.php.net/manual/en/memcached.addserver.php#105501) [¶](https://www.php.net/manual/en/memcached.addserver.php#105501)

**14 years ago**

`On my Debian Squeeze system I was getting WRITE FAILURE errors. After debugging and finally tcpdump it seems that the problem was me adding the server 'localhost', which resolved to '::1' (ipv6) while the default memcached server on debian only listens to '127.0.0.1' (ipv4). DNS automatically prefers ipv6 over ipv4.
I added the server '127.0.0.1' instead and everything worked. You could also disable ipv6 or have memcached listen on ::1`

[＋add a note](https://www.php.net/manual/add-note.php?sect=memcached.addserver&repo=en&redirect=https://www.php.net/manual/en/memcached.addserver.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google