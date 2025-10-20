---
url: https://www.php.net/manual/en/function.stream-context-set-option.php
scraped_at: 2025-10-20T02:40:00.360Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# stream\_context\_set\_option

(PHP 4 >= 4.3.0, PHP 5, PHP 7, PHP 8)

stream\_context\_set\_option — Sets an option for a stream/wrapper/context

### Description [¶](https://www.php.net/manual/en/function.stream-context-set-option.php\#refsect1-function.stream-context-set-option-description)

**stream\_context\_set\_option**(

[resource](https://www.php.net/manual/en/language.types.resource.php) `$stream_or_context`,

[string](https://www.php.net/manual/en/language.types.string.php) `$wrapper`,

[string](https://www.php.net/manual/en/language.types.string.php) `$option`,

[mixed](https://www.php.net/manual/en/language.types.mixed.php) `$value`

): [bool](https://www.php.net/manual/en/language.types.boolean.php)

The following alternative signature is deprecated as of PHP 8.4.0,
use [stream\_context\_set\_options()](https://www.php.net/manual/en/function.stream-context-set-options.php) instead.


**stream\_context\_set\_option**([resource](https://www.php.net/manual/en/language.types.resource.php) `$stream_or_context`, [array](https://www.php.net/manual/en/language.types.array.php) `$options`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Sets an option on the specified context. `value`
is set to `option` for `wrapper`

### Parameters [¶](https://www.php.net/manual/en/function.stream-context-set-option.php\#refsect1-function.stream-context-set-option-parameters)

`stream_or_context`

The stream or context resource to apply the options to.


`wrapper`

The name of the wrapper (which may be different than the protocol).
Refer to [context options and parameters](https://www.php.net/manual/en/context.php)
for a listing of stream options.


`option`

The name of the option.


`value`

The value of the option.


`options`

The options to set for `stream_or_context`.


> **Note**:
>
>
> `options` must be an associative
> array of associative arrays in the format
> `$arr['wrapper']['option'] = $value`.
>
>
> Refer to [context options and parameters](https://www.php.net/manual/en/context.php)
> for a listing of stream options.

### Return Values [¶](https://www.php.net/manual/en/function.stream-context-set-option.php\#refsect1-function.stream-context-set-option-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Changelog [¶](https://www.php.net/manual/en/function.stream-context-set-option.php\#refsect1-function.stream-context-set-option-changelog)

| Version | Description |
| --- | --- |
| 8.4.0 | The alternative 2-parameter signature is now deprecated.<br> Use [stream\_context\_set\_options()](https://www.php.net/manual/en/function.stream-context-set-options.php) instead. |

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/stream/functions/stream-context-set-option.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.stream-context-set-option%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.stream-context-set-option&repo=en&redirect=https://www.php.net/manual/en/function.stream-context-set-option.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google