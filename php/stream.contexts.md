---
url: https://www.php.net/manual/en/stream.contexts.php
scraped_at: 2025-10-20T02:41:24.917Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Stream Contexts [¶](https://www.php.net/manual/en/stream.contexts.php\#stream.contexts)

A `context` is a set of `parameters` and
wrapper specific `options` which modify or enhance the
behavior of a stream. `Contexts` are created using
[stream\_context\_create()](https://www.php.net/manual/en/function.stream-context-create.php) and can be passed to most
filesystem related stream creation functions (i.e. [fopen()](https://www.php.net/manual/en/function.fopen.php),
[file()](https://www.php.net/manual/en/function.file.php), [file\_get\_contents()](https://www.php.net/manual/en/function.file-get-contents.php), etc...).


`Options` can be specified when calling
[stream\_context\_create()](https://www.php.net/manual/en/function.stream-context-create.php), or later using
[stream\_context\_set\_option()](https://www.php.net/manual/en/function.stream-context-set-option.php).
A list of wrapper specific `options` can be found in the
[Context options and parameters](https://www.php.net/manual/en/context.php) chapter.


`Parameters` can be specified for
`contexts` using the
[stream\_context\_set\_params()](https://www.php.net/manual/en/function.stream-context-set-params.php) function.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/stream/contexts.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fstream.contexts%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=stream.contexts&repo=en&redirect=https://www.php.net/manual/en/stream.contexts.php)

### User Contributed Notes 1 note

[up](https://www.php.net/manual/vote-note.php?id=117638&page=stream.contexts&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117638&page=stream.contexts&vote=down "Vote down!")

3


[**_alvaro at demogracia dot com_**](https://www.php.net/manual/en/stream.contexts.php#117638) [¶](https://www.php.net/manual/en/stream.contexts.php#117638)

**10 years ago**

`Two important terms:
- An *option* is a protocol-specific setting, e.g. "method" (get, post, put...) if you are using HTTP or "callback function to be called when inserting a document" in MongoDB.
- A *parameter* is a settings that's common to all protocols. As of 2015 only one parameter got implemented ("notification").
While these words might look vague they are used coherently throughout the stream feature, documentation included.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=stream.contexts&repo=en&redirect=https://www.php.net/manual/en/stream.contexts.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google