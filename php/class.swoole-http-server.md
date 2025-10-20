---
url: https://www.php.net/manual/en/class.swoole-http-server.php
scraped_at: 2025-10-20T02:47:36.707Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The Swoole\\Http\\Server class [¶](https://www.php.net/manual/en/class.swoole-http-server.php\#class.swoole-http-server)

(PECL swoole >= 1.9.0)

## Introduction [¶](https://www.php.net/manual/en/class.swoole-http-server.php\#swoole-http-server.intro)

## Class synopsis [¶](https://www.php.net/manual/en/class.swoole-http-server.php\#swoole-http-server.synopsis)

class **Swoole\\Http\\Server**extends [Swoole\\Server](https://www.php.net/manual/en/class.swoole-server.php)
{

/\\* Methods \*/

public[on](https://www.php.net/manual/en/swoole-http-server.on.php)([string](https://www.php.net/manual/en/language.types.string.php) `$event_name`, [callable](https://www.php.net/manual/en/language.types.callable.php) `$callback`): [void](https://www.php.net/manual/en/language.types.void.php)

public[start](https://www.php.net/manual/en/swoole-http-server.start.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

/\\* Inherited methods \*/

public[Swoole\\Server::addlistener](https://www.php.net/manual/en/swoole-server.addlistener.php)([string](https://www.php.net/manual/en/language.types.string.php) `$host`, [int](https://www.php.net/manual/en/language.types.integer.php) `$port`, [string](https://www.php.net/manual/en/language.types.string.php) `$socket_type`): [void](https://www.php.net/manual/en/language.types.void.php)

public[Swoole\\Server::addProcess](https://www.php.net/manual/en/swoole-server.addprocess.php)([swoole\_process](https://www.php.net/manual/en/class.swoole-process.php) `$process`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[Swoole\\Server::after](https://www.php.net/manual/en/swoole-server.after.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$after_time_ms`, [callable](https://www.php.net/manual/en/language.types.callable.php) `$callback`, [string](https://www.php.net/manual/en/language.types.string.php) `$param` = ?): ReturnType

public[Swoole\\Server::bind](https://www.php.net/manual/en/swoole-server.bind.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$fd`, [int](https://www.php.net/manual/en/language.types.integer.php) `$uid`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[Swoole\\Server::clearTimer](https://www.php.net/manual/en/swoole-server.cleartimer.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$timer_id`): [void](https://www.php.net/manual/en/language.types.void.php)

**swoole\_timer\_clear**([int](https://www.php.net/manual/en/language.types.integer.php) `$timer_id`): [void](https://www.php.net/manual/en/language.types.void.php)

public[Swoole\\Server::close](https://www.php.net/manual/en/swoole-server.close.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$fd`, [bool](https://www.php.net/manual/en/language.types.boolean.php) `$reset` = ?): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[Swoole\\Server::confirm](https://www.php.net/manual/en/swoole-server.confirm.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$fd`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[Swoole\\Server::connection\_info](https://www.php.net/manual/en/swoole-server.connection-info.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$fd`, [int](https://www.php.net/manual/en/language.types.integer.php) `$reactor_id` = ?): [array](https://www.php.net/manual/en/language.types.array.php)

public[Swoole\\Server::connection\_list](https://www.php.net/manual/en/swoole-server.connection-list.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$start_fd`, [int](https://www.php.net/manual/en/language.types.integer.php) `$pagesize` = ?): [array](https://www.php.net/manual/en/language.types.array.php)

public[Swoole\\Server::defer](https://www.php.net/manual/en/swoole-server.defer.php)([callable](https://www.php.net/manual/en/language.types.callable.php) `$callback`): [void](https://www.php.net/manual/en/language.types.void.php)

public[Swoole\\Server::exist](https://www.php.net/manual/en/swoole-server.exist.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$fd`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[Swoole\\Server::finish](https://www.php.net/manual/en/swoole-server.finish.php)([string](https://www.php.net/manual/en/language.types.string.php) `$data`): [void](https://www.php.net/manual/en/language.types.void.php)

public[Swoole\\Server::getClientInfo](https://www.php.net/manual/en/swoole-server.getclientinfo.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$fd`, [int](https://www.php.net/manual/en/language.types.integer.php) `$reactor_id` = ?, [bool](https://www.php.net/manual/en/language.types.boolean.php) `$ignore_error` = ?): [array](https://www.php.net/manual/en/language.types.array.php)

public[Swoole\\Server::getClientList](https://www.php.net/manual/en/swoole-server.getclientlist.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$start_fd`, [int](https://www.php.net/manual/en/language.types.integer.php) `$pagesize` = ?): [array](https://www.php.net/manual/en/language.types.array.php)

public[Swoole\\Server::getLastError](https://www.php.net/manual/en/swoole-server.getlasterror.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[Swoole\\Server::heartbeat](https://www.php.net/manual/en/swoole-server.heartbeat.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$if_close_connection`): [mixed](https://www.php.net/manual/en/language.types.mixed.php)

public[Swoole\\Server::listen](https://www.php.net/manual/en/swoole-server.listen.php)([string](https://www.php.net/manual/en/language.types.string.php) `$host`, [int](https://www.php.net/manual/en/language.types.integer.php) `$port`, [string](https://www.php.net/manual/en/language.types.string.php) `$socket_type`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[Swoole\\Server::on](https://www.php.net/manual/en/swoole-server.on.php)([string](https://www.php.net/manual/en/language.types.string.php) `$event_name`, [callable](https://www.php.net/manual/en/language.types.callable.php) `$callback`): [void](https://www.php.net/manual/en/language.types.void.php)

public[Swoole\\Server::pause](https://www.php.net/manual/en/swoole-server.pause.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$fd`): [void](https://www.php.net/manual/en/language.types.void.php)

public[Swoole\\Server::protect](https://www.php.net/manual/en/swoole-server.protect.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$fd`, [bool](https://www.php.net/manual/en/language.types.boolean.php) `$is_protected` = ?): [void](https://www.php.net/manual/en/language.types.void.php)

public[Swoole\\Server::reload](https://www.php.net/manual/en/swoole-server.reload.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[Swoole\\Server::resume](https://www.php.net/manual/en/swoole-server.resume.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$fd`): [void](https://www.php.net/manual/en/language.types.void.php)

public[Swoole\\Server::send](https://www.php.net/manual/en/swoole-server.send.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$fd`, [string](https://www.php.net/manual/en/language.types.string.php) `$data`, [int](https://www.php.net/manual/en/language.types.integer.php) `$reactor_id` = ?): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[Swoole\\Server::sendfile](https://www.php.net/manual/en/swoole-server.sendfile.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$fd`, [string](https://www.php.net/manual/en/language.types.string.php) `$filename`, [int](https://www.php.net/manual/en/language.types.integer.php) `$offset` = ?): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[Swoole\\Server::sendMessage](https://www.php.net/manual/en/swoole-server.sendmessage.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$worker_id`, [string](https://www.php.net/manual/en/language.types.string.php) `$data`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[Swoole\\Server::sendto](https://www.php.net/manual/en/swoole-server.sendto.php)(

[string](https://www.php.net/manual/en/language.types.string.php) `$ip`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$port`,

[string](https://www.php.net/manual/en/language.types.string.php) `$data`,

[string](https://www.php.net/manual/en/language.types.string.php) `$server_socket` = ?

): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[Swoole\\Server::sendwait](https://www.php.net/manual/en/swoole-server.sendwait.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$fd`, [string](https://www.php.net/manual/en/language.types.string.php) `$data`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[Swoole\\Server::set](https://www.php.net/manual/en/swoole-server.set.php)([array](https://www.php.net/manual/en/language.types.array.php) `$settings`): ReturnType

public[Swoole\\Server::shutdown](https://www.php.net/manual/en/swoole-server.shutdown.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[Swoole\\Server::start](https://www.php.net/manual/en/swoole-server.start.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[Swoole\\Server::stats](https://www.php.net/manual/en/swoole-server.stats.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[Swoole\\Server::stop](https://www.php.net/manual/en/swoole-server.stop.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$worker_id` = ?): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[Swoole\\Server::task](https://www.php.net/manual/en/swoole-server.task.php)([string](https://www.php.net/manual/en/language.types.string.php) `$data`, [int](https://www.php.net/manual/en/language.types.integer.php) `$dst_worker_id` = ?, [callable](https://www.php.net/manual/en/language.types.callable.php) `$callback` = ?): [mixed](https://www.php.net/manual/en/language.types.mixed.php)

public[Swoole\\Server::taskwait](https://www.php.net/manual/en/swoole-server.taskwait.php)([string](https://www.php.net/manual/en/language.types.string.php) `$data`, [float](https://www.php.net/manual/en/language.types.float.php) `$timeout` = ?, [int](https://www.php.net/manual/en/language.types.integer.php) `$worker_id` = ?): [void](https://www.php.net/manual/en/language.types.void.php)

public[Swoole\\Server::taskWaitMulti](https://www.php.net/manual/en/swoole-server.taskwaitmulti.php)([array](https://www.php.net/manual/en/language.types.array.php) `$tasks`, [float](https://www.php.net/manual/en/language.types.float.php) `$timeout_ms` = ?): [void](https://www.php.net/manual/en/language.types.void.php)

public[Swoole\\Server::tick](https://www.php.net/manual/en/swoole-server.tick.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$interval_ms`, [callable](https://www.php.net/manual/en/language.types.callable.php) `$callback`): [void](https://www.php.net/manual/en/language.types.void.php)

}

## Table of Contents [¶](https://www.php.net/manual/en/class.swoole-http-server.php\#class.swoole-http-server)

- [Swoole\\Http\\Server::on](https://www.php.net/manual/en/swoole-http-server.on.php) — Bind callback function to HTTP server by event name.
- [Swoole\\Http\\Server::start](https://www.php.net/manual/en/swoole-http-server.start.php) — Start the swoole http server.

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/swoole/swoole.http.server.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.swoole-http-server%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.swoole-http-server&repo=en&redirect=https://www.php.net/manual/en/class.swoole-http-server.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google