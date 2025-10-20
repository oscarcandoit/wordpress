---
url: https://www.php.net/manual/en/class.swoole-server.php
scraped_at: 2025-10-20T02:32:35.185Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The Swoole\\Server class [¶](https://www.php.net/manual/en/class.swoole-server.php\#class.swoole-server)

(PECL swoole >= 1.9.0)

## Introduction [¶](https://www.php.net/manual/en/class.swoole-server.php\#swoole-server.intro)

## Class synopsis [¶](https://www.php.net/manual/en/class.swoole-server.php\#swoole-server.synopsis)

class **Swoole\\Server**
{

/\\* Methods \*/

public[addlistener](https://www.php.net/manual/en/swoole-server.addlistener.php)([string](https://www.php.net/manual/en/language.types.string.php) `$host`, [int](https://www.php.net/manual/en/language.types.integer.php) `$port`, [string](https://www.php.net/manual/en/language.types.string.php) `$socket_type`): [void](https://www.php.net/manual/en/language.types.void.php)

public[addProcess](https://www.php.net/manual/en/swoole-server.addprocess.php)([swoole\_process](https://www.php.net/manual/en/class.swoole-process.php) `$process`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[after](https://www.php.net/manual/en/swoole-server.after.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$after_time_ms`, [callable](https://www.php.net/manual/en/language.types.callable.php) `$callback`, [string](https://www.php.net/manual/en/language.types.string.php) `$param` = ?): ReturnType

public[bind](https://www.php.net/manual/en/swoole-server.bind.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$fd`, [int](https://www.php.net/manual/en/language.types.integer.php) `$uid`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[clearTimer](https://www.php.net/manual/en/swoole-server.cleartimer.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$timer_id`): [void](https://www.php.net/manual/en/language.types.void.php)

**swoole\_timer\_clear**([int](https://www.php.net/manual/en/language.types.integer.php) `$timer_id`): [void](https://www.php.net/manual/en/language.types.void.php)

public[close](https://www.php.net/manual/en/swoole-server.close.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$fd`, [bool](https://www.php.net/manual/en/language.types.boolean.php) `$reset` = ?): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[confirm](https://www.php.net/manual/en/swoole-server.confirm.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$fd`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[connection\_info](https://www.php.net/manual/en/swoole-server.connection-info.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$fd`, [int](https://www.php.net/manual/en/language.types.integer.php) `$reactor_id` = ?): [array](https://www.php.net/manual/en/language.types.array.php)

public[connection\_list](https://www.php.net/manual/en/swoole-server.connection-list.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$start_fd`, [int](https://www.php.net/manual/en/language.types.integer.php) `$pagesize` = ?): [array](https://www.php.net/manual/en/language.types.array.php)

public[defer](https://www.php.net/manual/en/swoole-server.defer.php)([callable](https://www.php.net/manual/en/language.types.callable.php) `$callback`): [void](https://www.php.net/manual/en/language.types.void.php)

public[exist](https://www.php.net/manual/en/swoole-server.exist.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$fd`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[finish](https://www.php.net/manual/en/swoole-server.finish.php)([string](https://www.php.net/manual/en/language.types.string.php) `$data`): [void](https://www.php.net/manual/en/language.types.void.php)

public[getClientInfo](https://www.php.net/manual/en/swoole-server.getclientinfo.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$fd`, [int](https://www.php.net/manual/en/language.types.integer.php) `$reactor_id` = ?, [bool](https://www.php.net/manual/en/language.types.boolean.php) `$ignore_error` = ?): [array](https://www.php.net/manual/en/language.types.array.php)

public[getClientList](https://www.php.net/manual/en/swoole-server.getclientlist.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$start_fd`, [int](https://www.php.net/manual/en/language.types.integer.php) `$pagesize` = ?): [array](https://www.php.net/manual/en/language.types.array.php)

public[getLastError](https://www.php.net/manual/en/swoole-server.getlasterror.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[heartbeat](https://www.php.net/manual/en/swoole-server.heartbeat.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$if_close_connection`): [mixed](https://www.php.net/manual/en/language.types.mixed.php)

public[listen](https://www.php.net/manual/en/swoole-server.listen.php)([string](https://www.php.net/manual/en/language.types.string.php) `$host`, [int](https://www.php.net/manual/en/language.types.integer.php) `$port`, [string](https://www.php.net/manual/en/language.types.string.php) `$socket_type`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[on](https://www.php.net/manual/en/swoole-server.on.php)([string](https://www.php.net/manual/en/language.types.string.php) `$event_name`, [callable](https://www.php.net/manual/en/language.types.callable.php) `$callback`): [void](https://www.php.net/manual/en/language.types.void.php)

public[pause](https://www.php.net/manual/en/swoole-server.pause.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$fd`): [void](https://www.php.net/manual/en/language.types.void.php)

public[protect](https://www.php.net/manual/en/swoole-server.protect.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$fd`, [bool](https://www.php.net/manual/en/language.types.boolean.php) `$is_protected` = ?): [void](https://www.php.net/manual/en/language.types.void.php)

public[reload](https://www.php.net/manual/en/swoole-server.reload.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[resume](https://www.php.net/manual/en/swoole-server.resume.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$fd`): [void](https://www.php.net/manual/en/language.types.void.php)

public[send](https://www.php.net/manual/en/swoole-server.send.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$fd`, [string](https://www.php.net/manual/en/language.types.string.php) `$data`, [int](https://www.php.net/manual/en/language.types.integer.php) `$reactor_id` = ?): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[sendfile](https://www.php.net/manual/en/swoole-server.sendfile.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$fd`, [string](https://www.php.net/manual/en/language.types.string.php) `$filename`, [int](https://www.php.net/manual/en/language.types.integer.php) `$offset` = ?): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[sendMessage](https://www.php.net/manual/en/swoole-server.sendmessage.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$worker_id`, [string](https://www.php.net/manual/en/language.types.string.php) `$data`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[sendto](https://www.php.net/manual/en/swoole-server.sendto.php)(

[string](https://www.php.net/manual/en/language.types.string.php) `$ip`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$port`,

[string](https://www.php.net/manual/en/language.types.string.php) `$data`,

[string](https://www.php.net/manual/en/language.types.string.php) `$server_socket` = ?

): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[sendwait](https://www.php.net/manual/en/swoole-server.sendwait.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$fd`, [string](https://www.php.net/manual/en/language.types.string.php) `$data`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[set](https://www.php.net/manual/en/swoole-server.set.php)([array](https://www.php.net/manual/en/language.types.array.php) `$settings`): ReturnType

public[shutdown](https://www.php.net/manual/en/swoole-server.shutdown.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[start](https://www.php.net/manual/en/swoole-server.start.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[stats](https://www.php.net/manual/en/swoole-server.stats.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[stop](https://www.php.net/manual/en/swoole-server.stop.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$worker_id` = ?): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[task](https://www.php.net/manual/en/swoole-server.task.php)([string](https://www.php.net/manual/en/language.types.string.php) `$data`, [int](https://www.php.net/manual/en/language.types.integer.php) `$dst_worker_id` = ?, [callable](https://www.php.net/manual/en/language.types.callable.php) `$callback` = ?): [mixed](https://www.php.net/manual/en/language.types.mixed.php)

public[taskwait](https://www.php.net/manual/en/swoole-server.taskwait.php)([string](https://www.php.net/manual/en/language.types.string.php) `$data`, [float](https://www.php.net/manual/en/language.types.float.php) `$timeout` = ?, [int](https://www.php.net/manual/en/language.types.integer.php) `$worker_id` = ?): [void](https://www.php.net/manual/en/language.types.void.php)

public[taskWaitMulti](https://www.php.net/manual/en/swoole-server.taskwaitmulti.php)([array](https://www.php.net/manual/en/language.types.array.php) `$tasks`, [float](https://www.php.net/manual/en/language.types.float.php) `$timeout_ms` = ?): [void](https://www.php.net/manual/en/language.types.void.php)

public[tick](https://www.php.net/manual/en/swoole-server.tick.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$interval_ms`, [callable](https://www.php.net/manual/en/language.types.callable.php) `$callback`): [void](https://www.php.net/manual/en/language.types.void.php)

}

## Table of Contents [¶](https://www.php.net/manual/en/class.swoole-server.php\#class.swoole-server)

- [Swoole\\Server::addlistener](https://www.php.net/manual/en/swoole-server.addlistener.php) — Add a new listener to the server.
- [Swoole\\Server::addProcess](https://www.php.net/manual/en/swoole-server.addprocess.php) — Add a user defined swoole\_process to the server.
- [Swoole\\Server::after](https://www.php.net/manual/en/swoole-server.after.php) — Trigger a callback function after a period of time.
- [Swoole\\Server::bind](https://www.php.net/manual/en/swoole-server.bind.php) — Bind the connection to a user defined user ID.
- [Swoole\\Server::clearTimer](https://www.php.net/manual/en/swoole-server.cleartimer.php) — Stop and destroy a timer.
- [Swoole\\Server::close](https://www.php.net/manual/en/swoole-server.close.php) — Close a connection to the client.
- [Swoole\\Server::confirm](https://www.php.net/manual/en/swoole-server.confirm.php) — Check status of the connection.
- [Swoole\\Server::connection\_info](https://www.php.net/manual/en/swoole-server.connection-info.php) — Get the connection info by file description.
- [Swoole\\Server::connection\_list](https://www.php.net/manual/en/swoole-server.connection-list.php) — Get all of the established connections.
- [Swoole\\Server::\_\_construct](https://www.php.net/manual/en/swoole-server.construct.php) — Construct a Swoole server.
- [Swoole\\Server::defer](https://www.php.net/manual/en/swoole-server.defer.php) — Delay execution of the callback function at the end of current EventLoop.
- [Swoole\\Server::exist](https://www.php.net/manual/en/swoole-server.exist.php) — Check if the connection is existed.
- [Swoole\\Server::finish](https://www.php.net/manual/en/swoole-server.finish.php) — Used in task process for sending result to the worker process when the task is finished.
- [Swoole\\Server::getClientInfo](https://www.php.net/manual/en/swoole-server.getclientinfo.php) — Get the connection info by file description.
- [Swoole\\Server::getClientList](https://www.php.net/manual/en/swoole-server.getclientlist.php) — Get all of the established connections.
- [Swoole\\Server::getLastError](https://www.php.net/manual/en/swoole-server.getlasterror.php) — Get the error code of the most recent error.
- [Swoole\\Server::heartbeat](https://www.php.net/manual/en/swoole-server.heartbeat.php) — Check all the connections on the server.
- [Swoole\\Server::listen](https://www.php.net/manual/en/swoole-server.listen.php) — Listen on the given IP and port, socket type.
- [Swoole\\Server::on](https://www.php.net/manual/en/swoole-server.on.php) — Register a callback function by event name.
- [Swoole\\Server::pause](https://www.php.net/manual/en/swoole-server.pause.php) — Stop receiving data from the connection.
- [Swoole\\Server::protect](https://www.php.net/manual/en/swoole-server.protect.php) — Set the connection to be protected mode.
- [Swoole\\Server::reload](https://www.php.net/manual/en/swoole-server.reload.php) — Restart all the worker process.
- [Swoole\\Server::resume](https://www.php.net/manual/en/swoole-server.resume.php) — Start receiving data from the connection.
- [Swoole\\Server::send](https://www.php.net/manual/en/swoole-server.send.php) — Send data to the client.
- [Swoole\\Server::sendfile](https://www.php.net/manual/en/swoole-server.sendfile.php) — Send file to the connection.
- [Swoole\\Server::sendMessage](https://www.php.net/manual/en/swoole-server.sendmessage.php) — Send message to worker processes by ID.
- [Swoole\\Server::sendto](https://www.php.net/manual/en/swoole-server.sendto.php) — Send data to the remote UDP address.
- [Swoole\\Server::sendwait](https://www.php.net/manual/en/swoole-server.sendwait.php) — Send data to the remote socket in the blocking way.
- [Swoole\\Server::set](https://www.php.net/manual/en/swoole-server.set.php) — Set the runtime settings of the swoole server.
- [Swoole\\Server::shutdown](https://www.php.net/manual/en/swoole-server.shutdown.php) — Shutdown the master server process, this function can be called in worker processes.
- [Swoole\\Server::start](https://www.php.net/manual/en/swoole-server.start.php) — Start the Swoole server.
- [Swoole\\Server::stats](https://www.php.net/manual/en/swoole-server.stats.php) — Get the stats of the Swoole server.
- [Swoole\\Server::stop](https://www.php.net/manual/en/swoole-server.stop.php) — Stop the Swoole server.
- [Swoole\\Server::task](https://www.php.net/manual/en/swoole-server.task.php) — Send data to the task worker processes.
- [Swoole\\Server::taskwait](https://www.php.net/manual/en/swoole-server.taskwait.php) — Send data to the task worker processes in blocking way.
- [Swoole\\Server::taskWaitMulti](https://www.php.net/manual/en/swoole-server.taskwaitmulti.php) — Execute multiple tasks concurrently.
- [Swoole\\Server::tick](https://www.php.net/manual/en/swoole-server.tick.php) — Repeats a given function at every given time-interval.

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/swoole/swoole.server.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.swoole-server%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.swoole-server&repo=en&redirect=https://www.php.net/manual/en/class.swoole-server.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google