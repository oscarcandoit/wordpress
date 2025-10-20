---
url: https://www.php.net/manual/en/memcached.construct.php
scraped_at: 2025-10-20T02:41:12.525Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Memcached::\_\_construct

(PECL memcached >= 0.1.0)

Memcached::\_\_construct — Create a Memcached instance

### Description [¶](https://www.php.net/manual/en/memcached.construct.php\#refsect1-memcached.construct-description)

public**Memcached::\_\_construct**([?](https://www.php.net/manual/en/language.types.null.php)[string](https://www.php.net/manual/en/language.types.string.php) `$persistent_id` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**, [?](https://www.php.net/manual/en/language.types.null.php)[callable](https://www.php.net/manual/en/language.types.callable.php) `$callback` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**, [?](https://www.php.net/manual/en/language.types.null.php)[string](https://www.php.net/manual/en/language.types.string.php) `$connection_str` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**)

Creates a Memcached instance representing the connection to the memcache
servers.


**Warning**

This function is
currently not documented; only its argument list is available.

### Parameters [¶](https://www.php.net/manual/en/memcached.construct.php\#refsect1-memcached.construct-parameters)

`persistent_id`

By default the Memcached instances are destroyed at the end of the
request. To create an instance that persists between requests, use
`persistent_id` to specify a unique ID for the
instance. All instances created with the same
`persistent_id` will share the same connection.


`callback``connection_str`

### Examples [¶](https://www.php.net/manual/en/memcached.construct.php\#refsect1-memcached.construct-examples)

**Example #1 Creating a Memcached object**

`<?php
/* Create a regular instance */
$m = new Memcached();
echo get_class($m);
/* Create a persistent instance */
$m2 = new Memcached('story_pool');
$m3 = new Memcached('story_pool');
/* now $m2 and $m3 share the same connection */
?>`

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/memcached/memcached/construct.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmemcached.construct%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=memcached.construct&repo=en&redirect=https://www.php.net/manual/en/memcached.construct.php)

### User Contributed Notes 7 notes

[up](https://www.php.net/manual/vote-note.php?id=93536&page=memcached.construct&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=93536&page=memcached.construct&vote=down "Vote down!")

22


[**_tschundler at gmail dot com_**](https://www.php.net/manual/en/memcached.construct.php#93536) [¶](https://www.php.net/manual/en/memcached.construct.php#93536)

**16 years ago**

`When using persistent connections, it is important to not re-add servers.
This is what you do not want to do:
<?php
$mc = new Memcached('mc');
$mc->setOption(Memcached::OPT_LIBKETAMA_COMPATIBLE, true);
$mc->addServers(array(
    array('mc1.example.com',11211),
    array('mc2.example.com',11211),
));
?>
Every time the page is loaded those servers will be appended to the list resulting in many simultaneous open connections to the same server. The addServer/addServers functions to not check for existing references to the specified servers.
A better approach is something like:
<?php
$mc = new Memcached('mc');
$mc->setOption(Memcached::OPT_LIBKETAMA_COMPATIBLE, true);
if (!count($mc->getServerList())) {
    $mc->addServers(array(
        array('mc1.example.com',11211),
        array('mc2.example.com',11211),
    ));
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=104269&page=memcached.construct&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=104269&page=memcached.construct&vote=down "Vote down!")

5


[**_clancy hood at gmail dot com_**](https://www.php.net/manual/en/memcached.construct.php#104269) [¶](https://www.php.net/manual/en/memcached.construct.php#104269)

**14 years ago**

`If you're wanting to get started with Memcached on a relatively small project but need some scalability then it can make sense to allow $persistent_id to also denote both a key prefix and a server set which you define yourself.  This keeps both key separation and allocation of data sets to certain server(s) incredibly simple throughout the project's life, without hampering any of your options.
<?php
    // Here is the array which we will add to in the future
    $GLOBALS['memcached-sets'] = array (
        '_' => array (
            array('localhost', 11211)
        )
    );
    define('DEFAULT_MEMCACHED_SET', '_');
    function mcache( $persistent_id=DEFAULT_MEMCACHED_SET ) {
        // one instantiation per-connection per-request
        static $memcached_instances = array();

        if( array_key_exists($persistent_id, $memcached_instances)) {
            $instance = $memcached_instances[$persistent_id];
        }else{
            $instance = new Memcached($persistent_id);
            $instance->setOption(Memcached::OPT_PREFIX_KEY, $persistent_id);
            $instance->setOption(Memcached::OPT_LIBKETAMA_COMPATIBLE, true); // advisable option

            // Add servers if no connections listed. Get server set by $persistent_id or use default set.
            // In a production environment with multiple server sets you may wish to prevent typos from silently adding data
            // to the default pool, in which case return an error on no match instead of defaulting
            if( !count($instance->getServerList()) ) {
                $servers = array_key_exists($persistent_id, $GLOBALS['memcached-sets'])
                    ? $GLOBALS['memcached-sets'][$persistent_id]
                    : $GLOBALS['memcached-sets'][DEFAULT_MEMCACHED_SET];
                $instance->addServers($servers);
            }
            $memcached_instances[$persistent_id] = $instance;
        }
        return $instance;
    }
    // simple example
    mcache()->set('foo', 'bar');
    mcache('myset')->set('foo', 'baz');
    var_dump(mcache()->get('foo'), mcache('myset')->get('foo'));
?>
string(3) "bar"
string(3) "baz"
Just remember to keep your $persistent_ids short as they infringe upon your maximum key length.  Happy coding! :)`

[up](https://www.php.net/manual/vote-note.php?id=106865&page=memcached.construct&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=106865&page=memcached.construct&vote=down "Vote down!")

2


[**_enknamel AT gmail DOT com_**](https://www.php.net/manual/en/memcached.construct.php#106865) [¶](https://www.php.net/manual/en/memcached.construct.php#106865)

**13 years ago**

`This was causing me to tear my hair out since I listened to the comments posted here.
If you enable persistence, the options you set will persist as well AND certain options if you set them with persistence enabled WILL CLOSE ALL YOUR PERSISTED CONNECTIONS. This is a part of libmemcached that the memcached extensions is built against. You can verify this by running strace.
So this is what you should do:
<?php
$mem = new Memcached($myPoolId);
if(empty($mem->getServerList())) {
    //This code block will only execute if we are setting up a new EG(persistent_list) entry
    $mem->setOption(Memcached::OPT_RECV_TIMEOUT, 1000);
    $mem->setOption(Memcached::OPT_SEND_TIMEOUT, 3000);
    $mem->setOption(Memcached::OPT_TCP_NODELAY, true);
    $mem->setOption(Memcached::OPT_PREFIX_KEY, "md_");
    $mem->addServer($myMemcahceIp, $myMemcachePort);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=102493&page=memcached.construct&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=102493&page=memcached.construct&vote=down "Vote down!")

2


[**_Tobias_**](https://www.php.net/manual/en/memcached.construct.php#102493) [¶](https://www.php.net/manual/en/memcached.construct.php#102493)

**14 years ago**

`Note that with this Memcached interface, if one or more underlying memcached daemons are down, suffering high network latency (over 1 second by default), or have crashed, then there still will be no warning, no error, no notice.  Everything will appear to work correctly, you just won't get proper results back.`

[up](https://www.php.net/manual/vote-note.php?id=102487&page=memcached.construct&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=102487&page=memcached.construct&vote=down "Vote down!")

3


[**_Tobias_**](https://www.php.net/manual/en/memcached.construct.php#102487) [¶](https://www.php.net/manual/en/memcached.construct.php#102487)

**14 years ago**

`Not positive, but it seems like the __construct() creates an instance of Memcache() class that lives (and stays alive) in at least the child Apache procs, if not the main Apache proc.
This (seems to) mean that Memcache daemons added to the server "pool" (via ->addServers() ) stay remembered.
This is why you do not want to call ->addServers() every time your script runs, because ->addServers() does not check for dups and will add hundreds or thousands of connections to the memcached daemon proc from the Apache proc(s).
One side effect is that any other scripts (even across different website domains) can also add to your server "pool" (if they know the server pool name, or if they can get it from the memcached daemon itself (not sure if/how this is possible), or if you or your team has coded several sites using the same server pool (i.e., new Memcached( 'same-server-pool-name' ) ).  This may present a security hole.`

[up](https://www.php.net/manual/vote-note.php?id=94636&page=memcached.construct&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=94636&page=memcached.construct&vote=down "Vote down!")

 -1


[**_jeroen at 4worx dot com_**](https://www.php.net/manual/en/memcached.construct.php#94636) [¶](https://www.php.net/manual/en/memcached.construct.php#94636)

**15 years ago**

`Using multiple memcached instances with options in combination with persistent connections might be confusing:
<?php
$a = new Memcached('memcached_pool');
$a->setOption(Memcached::OPT_COMPRESSION, false);
$b = new Memcached('memcached_pool');
$b->setOption(Memcached::OPT_COMPRESSION, true);
$a->add('key', 'some data');
?>
You might think that connection $a will store everything uncompressed, but this is not the case.
The persistent connection options are changed by the second object creation.`

[up](https://www.php.net/manual/vote-note.php?id=111154&page=memcached.construct&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=111154&page=memcached.construct&vote=down "Vote down!")

 -2


[**_kangzjnet at gmail dot com_**](https://www.php.net/manual/en/memcached.construct.php#111154) [¶](https://www.php.net/manual/en/memcached.construct.php#111154)

**12 years ago**

`To enable automatic failover, you have to set OPT_REMOVE_FAILED_SERVERS option, which is supported by php-memcached 2.0.0b2 or above.
Here is the example,
<?php
$memcache = new Memcached ( 'a_mem_pool' );
$ss = $memcache->getServerList ();
if (empty ( $ss )) {
$memcache->setOption(Memcached::OPT_RECV_TIMEOUT, 1000);
$memcache->setOption(Memcached::OPT_SEND_TIMEOUT, 1000);
$memcache->setOption(Memcached::OPT_TCP_NODELAY, true);
$memcache->setOption(Memcached::OPT_SERVER_FAILURE_LIMIT, 50);
$memcache->setOption(Memcached::OPT_CONNECT_TIMEOUT, 500);
$memcache->setOption(Memcached::OPT_RETRY_TIMEOUT, 300);
$memcache->setOption(Memcached::OPT_DISTRIBUTION, Memcached::DISTRIBUTION_CONSISTENT);
$memcache->setOption(Memcached::OPT_REMOVE_FAILED_SERVERS, true);
$memcache->setOption(Memcached::OPT_LIBKETAMA_COMPATIBLE, true);
$memcache->addServer ( '10.10.1.75', 11211, 1 );
$memcache->addServer ( '10.10.1.76', 11211, 1 );
$memcache->addServer ( '10.10.1.77', 11211, 1 );
}
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=memcached.construct&repo=en&redirect=https://www.php.net/manual/en/memcached.construct.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google