---
url: https://www.php.net/manual/en/wrappers.ftp.php
scraped_at: 2025-10-20T02:34:55.761Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# ftp://

# ftps://

ftp:// \-\- ftps:// — Accessing FTP(s) URLs

### Description [¶](https://www.php.net/manual/en/wrappers.ftp.php\#refsect1-wrappers.ftp-description)

Allows read access to existing files and creation of new files
via FTP. If the server does not support passive mode ftp, the
connection will fail.


You can open files for either reading or writing, but not both
simultaneously. If the remote file already exists on the ftp
server and you attempt to open it for writing but have not specified
the context option `overwrite`, the connection
will fail. If you need to overwrite existing files over ftp,
specify the `overwrite` option in the context
and open the file for writing. Alternatively, you can
use the [FTP extension](https://www.php.net/manual/en/ref.ftp.php).


If you have set the [from](https://www.php.net/manual/en/filesystem.configuration.php#ini.from) directive
in php.ini, then this value will be sent as the anonymous FTP
password.


### Usage [¶](https://www.php.net/manual/en/wrappers.ftp.php\#refsect1-wrappers.ftp-usage)

- ftp://example.com/pub/file.txt
- ftp://user:password@example.com/pub/file.txt
- ftps://example.com/pub/file.txt
- ftps://user:password@example.com/pub/file.txt

### Options [¶](https://www.php.net/manual/en/wrappers.ftp.php\#refsect1-wrappers.ftp-options)

| Attribute | Supported |
| --- | --- |
| Restricted by [allow\_url\_fopen](https://www.php.net/manual/en/filesystem.configuration.php#ini.allow-url-fopen) | Yes |
| Allows Reading | Yes |
| Allows Writing | Yes (new files/existing files with `overwrite`) |
| Allows Appending | Yes |
| Allows Simultaneous Reading and Writing | No |
| Supports [stat()](https://www.php.net/manual/en/function.stat.php) | [filesize()](https://www.php.net/manual/en/function.filesize.php), [filemtime()](https://www.php.net/manual/en/function.filemtime.php),<br> [filetype()](https://www.php.net/manual/en/function.filetype.php), [file\_exists()](https://www.php.net/manual/en/function.file-exists.php),<br> [is\_file()](https://www.php.net/manual/en/function.is-file.php), and [is\_dir()](https://www.php.net/manual/en/function.is-dir.php)<br> elements only. |
| Supports [unlink()](https://www.php.net/manual/en/function.unlink.php) | Yes |
| Supports [rename()](https://www.php.net/manual/en/function.rename.php) | Yes |
| Supports [mkdir()](https://www.php.net/manual/en/function.mkdir.php) | Yes |
| Supports [rmdir()](https://www.php.net/manual/en/function.rmdir.php) | Yes |

**Wrapper Summary**

### Notes [¶](https://www.php.net/manual/en/wrappers.ftp.php\#refsect1-wrappers.ftp-notes)

> **Note**:
>
>
> FTPS is only supported when the [openssl](https://www.php.net/manual/en/book.openssl.php)
> extension is enabled.
>
>
>  If the server does not support SSL, then the connection falls back
>  to regular unencrypted ftp.

> **Note**:
> **Appending**
>
> Files may be appended via the `ftp://` URL wrapper.

### See Also [¶](https://www.php.net/manual/en/wrappers.ftp.php\#refsect1-wrappers.ftp-seealso)

- [FTP context options](https://www.php.net/manual/en/context.ftp.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/wrappers/ftp.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fwrappers.ftp%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=wrappers.ftp&repo=en&redirect=https://www.php.net/manual/en/wrappers.ftp.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google