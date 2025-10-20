---
url: https://www.php.net/manual/en/ref.swoole-funcs.php
scraped_at: 2025-10-20T02:32:37.449Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Swoole Functions [¶](https://www.php.net/manual/en/ref.swoole-funcs.php\#ref.swoole-funcs)

## Table of Contents [¶](https://www.php.net/manual/en/ref.swoole-funcs.php\#ref.swoole-funcs)

- [swoole\_async\_dns\_lookup](https://www.php.net/manual/en/function.swoole-async-dns-lookup.php) — Async and non-blocking hostname to IP lookup
- [swoole\_async\_read](https://www.php.net/manual/en/function.swoole-async-read.php) — Read file stream asynchronously
- [swoole\_async\_readfile](https://www.php.net/manual/en/function.swoole-async-readfile.php) — Read a file asynchronously
- [swoole\_async\_set](https://www.php.net/manual/en/function.swoole-async-set.php) — Update the async I/O options
- [swoole\_async\_write](https://www.php.net/manual/en/function.swoole-async-write.php) — Write data to a file stream asynchronously
- [swoole\_async\_writefile](https://www.php.net/manual/en/function.swoole-async-writefile.php) — Write data to a file asynchronously
- [swoole\_clear\_error](https://www.php.net/manual/en/function.swoole-clear-error.php) — Clear errors in the socket or on the last error code
- [swoole\_client\_select](https://www.php.net/manual/en/function.swoole-client-select.php) — Get the file description which are ready to read/write or error
- [swoole\_cpu\_num](https://www.php.net/manual/en/function.swoole-cpu-num.php) — Get the number of CPU
- [swoole\_errno](https://www.php.net/manual/en/function.swoole-errno.php) — Get the error code of the latest system call
- [swoole\_error\_log](https://www.php.net/manual/en/function.swoole-error-log.php) — Output error messages to the log
- [swoole\_event\_add](https://www.php.net/manual/en/function.swoole-event-add.php) — Add new callback functions of a socket into the EventLoop
- [swoole\_event\_defer](https://www.php.net/manual/en/function.swoole-event-defer.php) — Add callback function to the next event loop
- [swoole\_event\_del](https://www.php.net/manual/en/function.swoole-event-del.php) — Remove all event callback functions of a socket
- [swoole\_event\_exit](https://www.php.net/manual/en/function.swoole-event-exit.php) — Exit the eventloop, only available at the client side
- [swoole\_event\_set](https://www.php.net/manual/en/function.swoole-event-set.php) — Update the event callback functions of a socket
- [swoole\_event\_wait](https://www.php.net/manual/en/function.swoole-event-wait.php) — Start the event loop
- [swoole\_event\_write](https://www.php.net/manual/en/function.swoole-event-write.php) — Write data to a socket
- [swoole\_get\_local\_ip](https://www.php.net/manual/en/function.swoole-get-local-ip.php) — Get the IPv4 IP addresses of each NIC on the machine
- [swoole\_last\_error](https://www.php.net/manual/en/function.swoole-last-error.php) — Get the lastest error message
- [swoole\_load\_module](https://www.php.net/manual/en/function.swoole-load-module.php) — Load a swoole extension
- [swoole\_select](https://www.php.net/manual/en/function.swoole-select.php) — Select the file descriptions which are ready to read/write or error in the eventloop
- [swoole\_set\_process\_name](https://www.php.net/manual/en/function.swoole-set-process-name.php) — Set the process name
- [swoole\_strerror](https://www.php.net/manual/en/function.swoole-strerror.php) — Convert the Errno into error messages
- [swoole\_timer\_after](https://www.php.net/manual/en/function.swoole-timer-after.php) — Trigger a one time callback function in the future
- [swoole\_timer\_exists](https://www.php.net/manual/en/function.swoole-timer-exists.php) — Check if a timer callback function is existed
- [swoole\_timer\_tick](https://www.php.net/manual/en/function.swoole-timer-tick.php) — Trigger a timer tick callback function by time interval
- [swoole\_version](https://www.php.net/manual/en/function.swoole-version.php) — Get the version of Swoole

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/swoole/reference.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fref.swoole-funcs%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=ref.swoole-funcs&repo=en&redirect=https://www.php.net/manual/en/ref.swoole-funcs.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google