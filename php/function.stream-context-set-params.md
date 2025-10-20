---
url: https://www.php.net/manual/en/function.stream-context-set-params.php
scraped_at: 2025-10-20T02:40:33.366Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# stream\_context\_set\_params

(PHP 4 >= 4.3.0, PHP 5, PHP 7, PHP 8)

stream\_context\_set\_params — Set parameters for a stream/wrapper/context

### Description [¶](https://www.php.net/manual/en/function.stream-context-set-params.php\#refsect1-function.stream-context-set-params-description)

**stream\_context\_set\_params**([resource](https://www.php.net/manual/en/language.types.resource.php) `$context`, [array](https://www.php.net/manual/en/language.types.array.php) `$params`): [true](https://www.php.net/manual/en/language.types.singleton.php)

Sets parameters on the specified context.


### Parameters [¶](https://www.php.net/manual/en/function.stream-context-set-params.php\#refsect1-function.stream-context-set-params-parameters)

`context`

The stream or context to apply the parameters too.


`params`

An associative array of parameters to be set in the following format:
`$params['paramname'] = "paramvalue";`.


| Parameter | Purpose |
| --- | --- |
| `notification` | Name of user-defined callback function to be called whenever a stream triggers a notification.<br> Only supported for [http://](https://www.php.net/manual/en/wrappers.http.php) and<br> [ftp://](https://www.php.net/manual/en/wrappers.ftp.php) stream wrappers. |
| `options` | Array of options as in [context options and parameters](https://www.php.net/manual/en/context.php). |

**Supported parameters**

### Return Values [¶](https://www.php.net/manual/en/function.stream-context-set-params.php\#refsect1-function.stream-context-set-params-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### See Also [¶](https://www.php.net/manual/en/function.stream-context-set-params.php\#refsect1-function.stream-context-set-params-seealso)

- [stream\_notification\_callback()](https://www.php.net/manual/en/function.stream-notification-callback.php) \- A callback function for the notification context parameter

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/stream/functions/stream-context-set-params.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.stream-context-set-params%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.stream-context-set-params&repo=en&redirect=https://www.php.net/manual/en/function.stream-context-set-params.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google