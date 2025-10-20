---
url: https://www.php.net/manual/en/features.persistent-connections.php
scraped_at: 2025-10-20T02:33:23.429Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Persistent Database Connections [¶](https://www.php.net/manual/en/features.persistent-connections.php\#features.persistent-connections)

### What are Persistent Connections?

Persistent connections are links that do not close when the
execution of your script ends. When a persistent connection is
requested, PHP checks if there's already an identical persistent
connection (that remained open from earlier) - and if it exists, it
uses it. If it does not exist, it creates the link. An 'identical'
connection is a connection that was opened to the same host, with
the same username and the same password (where applicable).


There's no method of requesting a specific connection, or guaranteeing
whether you get an existing connection or a brand new one (if all existing
connections are in use, or the request is being served by a different worker,
which has a separate pool of connections).


This means that you cannot use PHP's persistent connections to, for example:


- assign a specific database session to a specific web user
- create a large transaction across multiple requests
- initiate a query on one request and collect the results on another

Persistent connections do not give you _any_
functionality that wasn't possible with non-persistent connections.


### Web Requests [¶](https://www.php.net/manual/en/features.persistent-connections.php\#persistent-connections.web)

There are two ways in which your web server can utilize PHP to generate
web pages:


The first method is to use PHP as a CGI "wrapper". When run this
way, an instance of the PHP interpreter is created and destroyed
for every page request (for a PHP page) to your web server.
Because it is destroyed after every request, any resources that it
acquires (such as a link to an SQL database server) are closed when
it is destroyed. In this case, you do not gain anything from trying
to use persistent connections - they simply don't persist.


The second, and most popular, method is to run PHP-FPM, or PHP as a module
in a multiprocess web server, which currently only includes Apache.
These setups typically have one process (the parent) which
coordinates a set of processes (its children) who actually do the
work of serving up web pages. When a request comes in from a
client, it is handed off to one of the children that is not already
serving another client. This means that when the same client makes
a second request to the server, it may be served by a different
child process than the first time. When opening a persistent connection,
every following page requesting SQL services can reuse the same
established connection to the SQL server.


> **Note**:
>
>
> You can check which method your web requests use by checking the value of
> "Server API" in the output of [phpinfo()](https://www.php.net/manual/en/function.phpinfo.php) or the value of
> **`[PHP\_SAPI](https://www.php.net/manual/en/reserved.constants.php#constant.php-sapi)`**, run from a web request.
>
>
> If the Server API is "Apache 2 Handler" or "FPM/FastCGI", then persistent
> connections will be used across requests served by the same worker. For any
> other value, persistent connections will not persist after each request.

### Command-line Processes [¶](https://www.php.net/manual/en/features.persistent-connections.php\#persistent-connections.cli)

As command-line PHP uses a new process for each script, persistent
connections are not shared between command-line scripts, so there is no
value in using them in transient scripts such as crons or commands.
However, they may be useful if, for example, you're writing a long-running
application server that serves many requests or tasks and each may need
their own database connection.


### Why Use Them? [¶](https://www.php.net/manual/en/features.persistent-connections.php\#persistent-connections.why)

Persistent connections are good if the overhead to create a link to your
SQL server is high. Whether or not this overhead is really high depends
on many factors. Like, what kind of database it is, whether or not
it sits on the same computer on which your web server sits, how
loaded the machine the SQL server sits on is and so forth. The
bottom line is that if that connection overhead is high, persistent
connections help you considerably. They cause the child process to
simply connect only once for its entire lifespan, instead of every
time it processes a page that requires connecting to the SQL
server. This means that for every child that opened a persistent
connection will have its own open persistent connection to the
server. For example, if you had 20 different child processes that
ran a script that made a persistent connection to your SQL server,
you'd have 20 different connections to the SQL server, one from
each child.


### Potential Drawbacks: Connection Limits [¶](https://www.php.net/manual/en/features.persistent-connections.php\#persistent-connections.drawbacks.conn-limits)

Note, however, that this can have some drawbacks if you are using a
database with connection limits that are exceeded by persistent
child connections. If your database has a limit of 16 simultaneous
connections, and in the course of a busy server session, 17 child
threads attempt to connect, one will not be able to. If there are
bugs in your scripts which do not allow the connections to shut
down (such as infinite loops), the database with only 16 connections
may be rapidly swamped.


Persistent connections will usually increase the number of connections open
at any given time because idle workers will still hold the connections for
the previous requests they served. If a large number of workers is spun up to
handle an influx of requests, the connections they opened will remain until
the worker is killed or the database server closes the connection.


Ensure that the maximum number of connections allowed by the database server
is greater than the maximum number of web request workers (plus any other
usage such as crons or administrative connections).


Check your database documentation for information on handling abandoned or
idle connections (timeouts). Long timeouts may significantly increase the
number of persistent connections open at any one time.


### Potential Drawbacks: Maintaining Connection State [¶](https://www.php.net/manual/en/features.persistent-connections.php\#persistent-connections.drawbacks.state)

Some database extensions perform automatic cleanup when the connection is
reused; others leave this task at the discretion of the application developer.
Depending on the chosen database extension and the application design, manual
cleanup may be needed before the script exits. Changes that may leave
connections in an unexpected state include:


- Selected / default database
- Table locks
- Uncommitted transactions
- Temporary tables
- Connection specific settings or features such as profiling

Table locks and transactions that are not cleaned up or closed may cause
other queries to be blocked indefinitely and/or cause subsequent reuse of
the connection to cause unexpected changes.


Having the wrong database selected will cause subsequent reuse of the
connection to be unable to execute queries as expected (or execute them on
the wrong database if schemas are similar enough).


If temporary tables are not cleaned up, subsequent requests will not be able
to recreate the same table.


You can implement cleanup using class destructors or
[register\_shutdown\_function()](https://www.php.net/manual/en/function.register-shutdown-function.php). You may also want to
consider dedicated connection pooling proxies that include this as part of
their functionality.


### Final Words [¶](https://www.php.net/manual/en/features.persistent-connections.php\#persistent-connections.final-words)

Given their behavior and potential drawbacks described above, you should not
use persistent connections without careful consideration. They should not be
used without implementing additional changes to your application and careful
configuration of your database server and web server and/or PHP-FPM.


Consider alternative solutions such as investigating and fixing the causes of
connection creation overheads (for example, disabling reverse DNS lookups on
the database server), or dedicated connection pooling proxies.


For high volume web APIs, consider using alternative runtimes or long-running
application servers.


### See Also [¶](https://www.php.net/manual/en/features.persistent-connections.php\#persistent-connections.seealso)

- [ibase\_pconnect()](https://www.php.net/manual/en/function.ibase-pconnect.php)
- [oci\_pconnect()](https://www.php.net/manual/en/function.oci-pconnect.php)
- [odbc\_pconnect()](https://www.php.net/manual/en/function.odbc-pconnect.php)
- [pfsockopen()](https://www.php.net/manual/en/function.pfsockopen.php)
- [pg\_connect()](https://www.php.net/manual/en/function.pg-connect.php)
- [MySQLi and Persistent Connections](https://www.php.net/manual/en/mysqli.persistconns.php)
- [PDO Connection Management](https://www.php.net/manual/en/pdo.connections.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/features/persistent-connections.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffeatures.persistent-connections%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=features.persistent-connections&repo=en&redirect=https://www.php.net/manual/en/features.persistent-connections.php)

### User Contributed Notes 7 notes

[up](https://www.php.net/manual/vote-note.php?id=95340&page=features.persistent-connections&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=95340&page=features.persistent-connections&vote=down "Vote down!")

22


[**_Tom_**](https://www.php.net/manual/en/features.persistent-connections.php#95340) [¶](https://www.php.net/manual/en/features.persistent-connections.php#95340)

**15 years ago**

`There's a third case for PHP: run on a fastCGI interface. In this case, PHP processes are NOT destroyed after each request, and so persistent connections do persist. Set PHP_FCGI_CHILDREN << mysql's max_connections and you'll be fine.`

[up](https://www.php.net/manual/vote-note.php?id=100009&page=features.persistent-connections&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=100009&page=features.persistent-connections&vote=down "Vote down!")

14


[**_ambrish at php dot net_**](https://www.php.net/manual/en/features.persistent-connections.php#100009) [¶](https://www.php.net/manual/en/features.persistent-connections.php#100009)

**15 years ago**

`In IBM_DB2 extension v1.9.0 or later performs a transaction rollback on persistent connections at the end of a request, thus ending the transaction. This prevents the transaction block from carrying over to the next request which uses that connection if script execution ends before the transaction block does.`

[up](https://www.php.net/manual/vote-note.php?id=114190&page=features.persistent-connections&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114190&page=features.persistent-connections&vote=down "Vote down!")

14


[**_php at alfadog dot net_**](https://www.php.net/manual/en/features.persistent-connections.php#114190) [¶](https://www.php.net/manual/en/features.persistent-connections.php#114190)

**11 years ago**

`One additional not regarding odbc_pconnect  and possibly other variations of pconnect:

If the connection encounters an error (bad SQL, incorrect request, etc), that error will return with  be present in odbc_errormsg for every subsequent action on that connection, even if subsequent actions don't cause another error.
For example:
A script connects with odbc_pconnect.
The connection is created on it's first use.
The script calls a query "Select * FROM Table1".
Table1 doesn't exist and odbc_errormsg contains that error.
Later(days, perhaps), a different script is called using the same parameters to odbc_pconnect.
The connection already exists, to it is reused.
The script calls a query "Select * FROM Table0".
The query runs fine, but odbc_errormsg still returns the error about Table1 not existing.
I'm not seeing a way to clear that error using odbc_ functions, so keep your eyes open for this gotcha or use odbc_connect instead.`

[up](https://www.php.net/manual/vote-note.php?id=76013&page=features.persistent-connections&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=76013&page=features.persistent-connections&vote=down "Vote down!")

14


[**_christopher dot jones at oracle dot com_**](https://www.php.net/manual/en/features.persistent-connections.php#76013) [¶](https://www.php.net/manual/en/features.persistent-connections.php#76013)

**18 years ago**

`For the oci8 extension it is not true that " [...] when using transactions, a transaction block will also carry over to the next script which uses that connection if script execution ends before the transaction block does.".  The oci8 extension does a rollback at the end scripts using persistent connections, thus ending the transaction.  The rollback also releases locks. However any ALTER SESSION command (e.g. changing the date format) on a persistent connection will be retained over to the next script.`

[up](https://www.php.net/manual/vote-note.php?id=89465&page=features.persistent-connections&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=89465&page=features.persistent-connections&vote=down "Vote down!")

11


[**_ynzhang from lakeheadu canada_**](https://www.php.net/manual/en/features.persistent-connections.php#89465) [¶](https://www.php.net/manual/en/features.persistent-connections.php#89465)

**16 years ago**

`It seems that using pg_pconnect() will not persist the temporary views/tables. So if you are trying to create temporary views/tables with the query results and then access them with the next script of the same session, you are out of luck. Those temporary view/tables are gone after each PHP script ended. One way to get around this problem is to create real view/table with session ID as part of the name and record the name&creation time in a common table. Have a garbage collection script to drop the view/table who's session is expired.`

[up](https://www.php.net/manual/vote-note.php?id=24393&page=features.persistent-connections&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=24393&page=features.persistent-connections&vote=down "Vote down!")

10


[**_jean\_christian at myrealbox dot com_**](https://www.php.net/manual/en/features.persistent-connections.php#24393) [¶](https://www.php.net/manual/en/features.persistent-connections.php#24393)

**23 years ago**

`If anyone ever wonders why the number of idle db process (open connections) seems to grow even though you are using persistent connections, here's why:
"You are probably using a multi-process web server such as Apache. Since
database connections cannot be shared among different processes a new
one is created if the request happen to come to a different web server
child process."`

[up](https://www.php.net/manual/vote-note.php?id=73370&page=features.persistent-connections&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=73370&page=features.persistent-connections&vote=down "Vote down!")

8


[**_andy at paradigm-reborn dot com_**](https://www.php.net/manual/en/features.persistent-connections.php#73370) [¶](https://www.php.net/manual/en/features.persistent-connections.php#73370)

**18 years ago**

`To those using MySQL and finding a lot of leftover sleeping processes, take a look at MySQL's wait_timeout directive. By default it is set to 8 hours, but almost any decent production server will have been lowered to the 60 second range. Even on my testing server, I was having problems with too many connections from leftover persistent connections.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=features.persistent-connections&repo=en&redirect=https://www.php.net/manual/en/features.persistent-connections.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google