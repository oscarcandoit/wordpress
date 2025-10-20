---
url: https://www.php.net/manual/en/class.seaslog.php
scraped_at: 2025-10-20T02:42:42.229Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The SeasLog class [¶](https://www.php.net/manual/en/class.seaslog.php\#class.seaslog)

(PECL seaslog >=1.0.0)

## Introduction [¶](https://www.php.net/manual/en/class.seaslog.php\#seaslog.intro)

## Class synopsis [¶](https://www.php.net/manual/en/class.seaslog.php\#seaslog.synopsis)

class **SeasLog**
{

/\\* Methods \*/

publicstatic[alert](https://www.php.net/manual/en/seaslog.alert.php)([string](https://www.php.net/manual/en/language.types.string.php) `$message`, [array](https://www.php.net/manual/en/language.types.array.php) `$content` = ?, [string](https://www.php.net/manual/en/language.types.string.php) `$logger` = ?): [bool](https://www.php.net/manual/en/language.types.boolean.php)

publicstatic[analyzerCount](https://www.php.net/manual/en/seaslog.analyzercount.php)([string](https://www.php.net/manual/en/language.types.string.php) `$level`, [string](https://www.php.net/manual/en/language.types.string.php) `$log_path` = ?, [string](https://www.php.net/manual/en/language.types.string.php) `$key_word` = ?): [mixed](https://www.php.net/manual/en/language.types.mixed.php)

publicstatic[analyzerDetail](https://www.php.net/manual/en/seaslog.analyzerdetail.php)(

[string](https://www.php.net/manual/en/language.types.string.php) `$level`,

[string](https://www.php.net/manual/en/language.types.string.php) `$log_path` = ?,

[string](https://www.php.net/manual/en/language.types.string.php) `$key_word` = ?,

[int](https://www.php.net/manual/en/language.types.integer.php) `$start` = ?,

[int](https://www.php.net/manual/en/language.types.integer.php) `$limit` = ?,

[int](https://www.php.net/manual/en/language.types.integer.php) `$order` = ?

): [mixed](https://www.php.net/manual/en/language.types.mixed.php)

publicstatic[closeLoggerStream](https://www.php.net/manual/en/seaslog.closeloggerstream.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$model`, [string](https://www.php.net/manual/en/language.types.string.php) `$logger`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

publicstatic[critical](https://www.php.net/manual/en/seaslog.critical.php)([string](https://www.php.net/manual/en/language.types.string.php) `$message`, [array](https://www.php.net/manual/en/language.types.array.php) `$content` = ?, [string](https://www.php.net/manual/en/language.types.string.php) `$logger` = ?): [bool](https://www.php.net/manual/en/language.types.boolean.php)

publicstatic[debug](https://www.php.net/manual/en/seaslog.debug.php)([string](https://www.php.net/manual/en/language.types.string.php) `$message`, [array](https://www.php.net/manual/en/language.types.array.php) `$content` = ?, [string](https://www.php.net/manual/en/language.types.string.php) `$logger` = ?): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[\_\_destruct](https://www.php.net/manual/en/seaslog.destruct.php)()

publicstatic[emergency](https://www.php.net/manual/en/seaslog.emergency.php)([string](https://www.php.net/manual/en/language.types.string.php) `$message`, [array](https://www.php.net/manual/en/language.types.array.php) `$content` = ?, [string](https://www.php.net/manual/en/language.types.string.php) `$logger` = ?): [bool](https://www.php.net/manual/en/language.types.boolean.php)

publicstatic[error](https://www.php.net/manual/en/seaslog.error.php)([string](https://www.php.net/manual/en/language.types.string.php) `$message`, [array](https://www.php.net/manual/en/language.types.array.php) `$content` = ?, [string](https://www.php.net/manual/en/language.types.string.php) `$logger` = ?): [bool](https://www.php.net/manual/en/language.types.boolean.php)

publicstatic[flushBuffer](https://www.php.net/manual/en/seaslog.flushbuffer.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

publicstatic[Seaslog::getBasePath](https://www.php.net/manual/en/seaslog.getbasepath.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

publicstatic[getBuffer](https://www.php.net/manual/en/seaslog.getbuffer.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

publicstatic[getBufferEnabled](https://www.php.net/manual/en/seaslog.getbufferenabled.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

publicstatic[getDatetimeFormat](https://www.php.net/manual/en/seaslog.getdatetimeformat.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

publicstatic[getLastLogger](https://www.php.net/manual/en/seaslog.getlastlogger.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

publicstatic[getRequestID](https://www.php.net/manual/en/seaslog.getrequestid.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

publicstatic[getRequestVariable](https://www.php.net/manual/en/seaslog.getrequestvariable.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$key`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

publicstatic[info](https://www.php.net/manual/en/seaslog.info.php)([string](https://www.php.net/manual/en/language.types.string.php) `$message`, [array](https://www.php.net/manual/en/language.types.array.php) `$content` = ?, [string](https://www.php.net/manual/en/language.types.string.php) `$logger` = ?): [bool](https://www.php.net/manual/en/language.types.boolean.php)

publicstatic[log](https://www.php.net/manual/en/seaslog.log.php)(

[string](https://www.php.net/manual/en/language.types.string.php) `$level`,

[string](https://www.php.net/manual/en/language.types.string.php) `$message` = ?,

[array](https://www.php.net/manual/en/language.types.array.php) `$content` = ?,

[string](https://www.php.net/manual/en/language.types.string.php) `$logger` = ?

): [bool](https://www.php.net/manual/en/language.types.boolean.php)

publicstatic[notice](https://www.php.net/manual/en/seaslog.notice.php)([string](https://www.php.net/manual/en/language.types.string.php) `$message`, [array](https://www.php.net/manual/en/language.types.array.php) `$content` = ?, [string](https://www.php.net/manual/en/language.types.string.php) `$logger` = ?): [bool](https://www.php.net/manual/en/language.types.boolean.php)

publicstatic[setBasePath](https://www.php.net/manual/en/seaslog.setbasepath.php)([string](https://www.php.net/manual/en/language.types.string.php) `$base_path`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

publicstatic[setDatetimeFormat](https://www.php.net/manual/en/seaslog.setdatetimeformat.php)([string](https://www.php.net/manual/en/language.types.string.php) `$format`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

publicstatic[setLogger](https://www.php.net/manual/en/seaslog.setlogger.php)([string](https://www.php.net/manual/en/language.types.string.php) `$logger`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

publicstatic[setRequestID](https://www.php.net/manual/en/seaslog.setrequestid.php)([string](https://www.php.net/manual/en/language.types.string.php) `$request_id`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

publicstatic[setRequestVariable](https://www.php.net/manual/en/seaslog.setrequestvariable.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$key`, [string](https://www.php.net/manual/en/language.types.string.php) `$value`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

publicstatic[warning](https://www.php.net/manual/en/seaslog.warning.php)([string](https://www.php.net/manual/en/language.types.string.php) `$message`, [array](https://www.php.net/manual/en/language.types.array.php) `$content` = ?, [string](https://www.php.net/manual/en/language.types.string.php) `$logger` = ?): [bool](https://www.php.net/manual/en/language.types.boolean.php)

}

## Table of Contents [¶](https://www.php.net/manual/en/class.seaslog.php\#class.seaslog)

- [SeasLog::alert](https://www.php.net/manual/en/seaslog.alert.php) — Record alert log information
- [SeasLog::analyzerCount](https://www.php.net/manual/en/seaslog.analyzercount.php) — Get log count by level, log\_path and key\_word
- [SeasLog::analyzerDetail](https://www.php.net/manual/en/seaslog.analyzerdetail.php) — Get log detail by level, log\_path, key\_word, start, limit, order
- [SeasLog::closeLoggerStream](https://www.php.net/manual/en/seaslog.closeloggerstream.php) — Manually release stream flow from logger
- [SeasLog::\_\_construct](https://www.php.net/manual/en/seaslog.construct.php) — Description
- [SeasLog::critical](https://www.php.net/manual/en/seaslog.critical.php) — Record critical log information
- [SeasLog::debug](https://www.php.net/manual/en/seaslog.debug.php) — Record debug log information
- [SeasLog::\_\_destruct](https://www.php.net/manual/en/seaslog.destruct.php) — Description
- [SeasLog::emergency](https://www.php.net/manual/en/seaslog.emergency.php) — Record emergency log information
- [SeasLog::error](https://www.php.net/manual/en/seaslog.error.php) — Record error log information
- [SeasLog::flushBuffer](https://www.php.net/manual/en/seaslog.flushbuffer.php) — Flush logs buffer, dump to appender file, or send to remote api with tcp/udp
- [SeasLog::getBasePath](https://www.php.net/manual/en/seaslog.getbasepath.php) — Get SeasLog base path.
- [SeasLog::getBuffer](https://www.php.net/manual/en/seaslog.getbuffer.php) — Get the logs buffer in memory as array
- [SeasLog::getBufferEnabled](https://www.php.net/manual/en/seaslog.getbufferenabled.php) — Determin if buffer enabled
- [SeasLog::getDatetimeFormat](https://www.php.net/manual/en/seaslog.getdatetimeformat.php) — Get SeasLog datetime format style
- [SeasLog::getLastLogger](https://www.php.net/manual/en/seaslog.getlastlogger.php) — Get SeasLog last logger path
- [SeasLog::getRequestID](https://www.php.net/manual/en/seaslog.getrequestid.php) — Get SeasLog request\_id differentiated requests
- [SeasLog::getRequestVariable](https://www.php.net/manual/en/seaslog.getrequestvariable.php) — Get SeasLog request variable
- [SeasLog::info](https://www.php.net/manual/en/seaslog.info.php) — Record info log information
- [SeasLog::log](https://www.php.net/manual/en/seaslog.log.php) — The Common Record Log Function
- [SeasLog::notice](https://www.php.net/manual/en/seaslog.notice.php) — Record notice log information
- [SeasLog::setBasePath](https://www.php.net/manual/en/seaslog.setbasepath.php) — Set SeasLog base path
- [SeasLog::setDatetimeFormat](https://www.php.net/manual/en/seaslog.setdatetimeformat.php) — Set SeasLog datetime format style
- [SeasLog::setLogger](https://www.php.net/manual/en/seaslog.setlogger.php) — Set SeasLog logger name
- [SeasLog::setRequestID](https://www.php.net/manual/en/seaslog.setrequestid.php) — Set SeasLog request\_id differentiated requests
- [SeasLog::setRequestVariable](https://www.php.net/manual/en/seaslog.setrequestvariable.php) — Manually set SeasLog request variable
- [SeasLog::warning](https://www.php.net/manual/en/seaslog.warning.php) — Record warning log information

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/seaslog/seaslog.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.seaslog%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.seaslog&repo=en&redirect=https://www.php.net/manual/en/class.seaslog.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google