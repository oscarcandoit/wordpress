---
url: https://www.php.net/manual/en/class.swoole-process.php
scraped_at: 2025-10-20T02:34:48.493Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The Swoole\\Process class [¶](https://www.php.net/manual/en/class.swoole-process.php\#class.swoole-process)

(PECL swoole >= 1.9.0)

## Introduction [¶](https://www.php.net/manual/en/class.swoole-process.php\#swoole-process.intro)

## Class synopsis [¶](https://www.php.net/manual/en/class.swoole-process.php\#swoole-process.synopsis)

class **Swoole\\Process**
{

/\\* Constants \*/

const[int](https://www.php.net/manual/en/language.types.integer.php)[IPC\_NOWAIT](https://www.php.net/manual/en/class.swoole-process.php#swoole-process.constants.ipc-nowait) = 256;

/\\* Methods \*/

publicstatic[alarm](https://www.php.net/manual/en/swoole-process.alarm.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$interval_usec`): [void](https://www.php.net/manual/en/language.types.void.php)

public[close](https://www.php.net/manual/en/swoole-process.close.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

publicstatic[daemon](https://www.php.net/manual/en/swoole-process.daemon.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$nochdir` = ?, [bool](https://www.php.net/manual/en/language.types.boolean.php) `$noclose` = ?): [void](https://www.php.net/manual/en/language.types.void.php)

public[\_\_destruct](https://www.php.net/manual/en/swoole-process.destruct.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[exec](https://www.php.net/manual/en/swoole-process.exec.php)([string](https://www.php.net/manual/en/language.types.string.php) `$exec_file`, [string](https://www.php.net/manual/en/language.types.string.php) `$args`): ReturnType

public[exit](https://www.php.net/manual/en/swoole-process.exit.php)([string](https://www.php.net/manual/en/language.types.string.php) `$exit_code` = ?): [void](https://www.php.net/manual/en/language.types.void.php)

public[freeQueue](https://www.php.net/manual/en/swoole-process.freequeue.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

publicstatic[kill](https://www.php.net/manual/en/swoole-process.kill.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$pid`, [int](https://www.php.net/manual/en/language.types.integer.php) `$signal_no` = ?): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[name](https://www.php.net/manual/en/swoole-process.name.php)([string](https://www.php.net/manual/en/language.types.string.php) `$process_name`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[pop](https://www.php.net/manual/en/swoole-process.pop.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$maxsize` = ?): [mixed](https://www.php.net/manual/en/language.types.mixed.php)

public[push](https://www.php.net/manual/en/swoole-process.push.php)([string](https://www.php.net/manual/en/language.types.string.php) `$data`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[read](https://www.php.net/manual/en/swoole-process.read.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$maxsize` = ?): [string](https://www.php.net/manual/en/language.types.string.php)

publicstatic[signal](https://www.php.net/manual/en/swoole-process.signal.php)([string](https://www.php.net/manual/en/language.types.string.php) `$signal_no`, [callable](https://www.php.net/manual/en/language.types.callable.php) `$callback`): [void](https://www.php.net/manual/en/language.types.void.php)

public[start](https://www.php.net/manual/en/swoole-process.start.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[statQueue](https://www.php.net/manual/en/swoole-process.statqueue.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[useQueue](https://www.php.net/manual/en/swoole-process.usequeue.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$key`, [int](https://www.php.net/manual/en/language.types.integer.php) `$mode` = ?): [bool](https://www.php.net/manual/en/language.types.boolean.php)

publicstatic[wait](https://www.php.net/manual/en/swoole-process.wait.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$blocking` = ?): [array](https://www.php.net/manual/en/language.types.array.php)

public[write](https://www.php.net/manual/en/swoole-process.write.php)([string](https://www.php.net/manual/en/language.types.string.php) `$data`): [int](https://www.php.net/manual/en/language.types.integer.php)

}

## Predefined Constants [¶](https://www.php.net/manual/en/class.swoole-process.php\#swoole-process.constants)

**`[Swoole\\Process::IPC\_NOWAIT](https://www.php.net/manual/en/class.swoole-process.php#swoole-process.constants.ipc-nowait)`**

## Table of Contents [¶](https://www.php.net/manual/en/class.swoole-process.php\#class.swoole-process)

- [Swoole\\Process::alarm](https://www.php.net/manual/en/swoole-process.alarm.php) — High precision timer which triggers signal with fixed interval.
- [Swoole\\Process::close](https://www.php.net/manual/en/swoole-process.close.php) — Close the pipe to the child process.
- [Swoole\\Process::\_\_construct](https://www.php.net/manual/en/swoole-process.construct.php) — Construct a process.
- [Swoole\\Process::daemon](https://www.php.net/manual/en/swoole-process.daemon.php) — Change the process to be a daemon process.
- [Swoole\\Process::\_\_destruct](https://www.php.net/manual/en/swoole-process.destruct.php) — Destroy the process.
- [Swoole\\Process::exec](https://www.php.net/manual/en/swoole-process.exec.php) — Execute system commands.
- [Swoole\\Process::exit](https://www.php.net/manual/en/swoole-process.exit.php) — Stop the child processes.
- [Swoole\\Process::freeQueue](https://www.php.net/manual/en/swoole-process.freequeue.php) — Destroy the message queue created by swoole\_process::useQueue.
- [Swoole\\Process::kill](https://www.php.net/manual/en/swoole-process.kill.php) — Send signal to the child process.
- [Swoole\\Process::name](https://www.php.net/manual/en/swoole-process.name.php) — Set name of the process.
- [Swoole\\Process::pop](https://www.php.net/manual/en/swoole-process.pop.php) — Read and pop data from the message queue.
- [Swoole\\Process::push](https://www.php.net/manual/en/swoole-process.push.php) — Write and push data into the message queue.
- [Swoole\\Process::read](https://www.php.net/manual/en/swoole-process.read.php) — Read data sending to the process.
- [Swoole\\Process::signal](https://www.php.net/manual/en/swoole-process.signal.php) — Send signal to the child processes.
- [Swoole\\Process::start](https://www.php.net/manual/en/swoole-process.start.php) — Start the process.
- [Swoole\\Process::statQueue](https://www.php.net/manual/en/swoole-process.statqueue.php) — Get the stats of the message queue used as the communication method between processes.
- [Swoole\\Process::useQueue](https://www.php.net/manual/en/swoole-process.usequeue.php) — Create a message queue as the communication method between the parent process and child processes.
- [Swoole\\Process::wait](https://www.php.net/manual/en/swoole-process.wait.php) — Wait for the events of child processes.
- [Swoole\\Process::write](https://www.php.net/manual/en/swoole-process.write.php) — Write data into the pipe and communicate with the parent process or child processes.

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/swoole/swoole.process.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.swoole-process%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.swoole-process&repo=en&redirect=https://www.php.net/manual/en/class.swoole-process.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google