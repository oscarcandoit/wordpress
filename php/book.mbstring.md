---
url: https://www.php.net/manual/en/book.mbstring.php
scraped_at: 2025-10-20T02:38:30.220Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Multibyte String [¶](https://www.php.net/manual/en/book.mbstring.php\#book.mbstring)

- [Introduction](https://www.php.net/manual/en/intro.mbstring.php)
- [Installing/Configuring](https://www.php.net/manual/en/mbstring.setup.php)
  - [Installation](https://www.php.net/manual/en/mbstring.installation.php)
  - [Runtime Configuration](https://www.php.net/manual/en/mbstring.configuration.php)
- [Predefined Constants](https://www.php.net/manual/en/mbstring.constants.php)
- [Summaries of supported encodings](https://www.php.net/manual/en/mbstring.encodings.php)
- [Basics of Japanese multi-byte encodings](https://www.php.net/manual/en/mbstring.ja-basic.php)
- [HTTP Input and Output](https://www.php.net/manual/en/mbstring.http.php)
- [Supported Character Encodings](https://www.php.net/manual/en/mbstring.supported-encodings.php)
- [Function Overloading Feature](https://www.php.net/manual/en/mbstring.overload.php)
- [PHP Character Encoding Requirements](https://www.php.net/manual/en/mbstring.php4.req.php)
- [Multibyte String Functions](https://www.php.net/manual/en/ref.mbstring.php)
  - [mb\_check\_encoding](https://www.php.net/manual/en/function.mb-check-encoding.php) — Check if strings are valid for the specified encoding
  - [mb\_chr](https://www.php.net/manual/en/function.mb-chr.php) — Return character by Unicode code point value
  - [mb\_convert\_case](https://www.php.net/manual/en/function.mb-convert-case.php) — Perform case folding on a string
  - [mb\_convert\_encoding](https://www.php.net/manual/en/function.mb-convert-encoding.php) — Convert a string from one character encoding to another
  - [mb\_convert\_kana](https://www.php.net/manual/en/function.mb-convert-kana.php) — Convert "kana" one from another ("zen-kaku", "han-kaku" and more)
  - [mb\_convert\_variables](https://www.php.net/manual/en/function.mb-convert-variables.php) — Convert character code in variable(s)
  - [mb\_decode\_mimeheader](https://www.php.net/manual/en/function.mb-decode-mimeheader.php) — Decode string in MIME header field
  - [mb\_decode\_numericentity](https://www.php.net/manual/en/function.mb-decode-numericentity.php) — Decode HTML numeric string reference to character
  - [mb\_detect\_encoding](https://www.php.net/manual/en/function.mb-detect-encoding.php) — Detect character encoding
  - [mb\_detect\_order](https://www.php.net/manual/en/function.mb-detect-order.php) — Set/Get character encoding detection order
  - [mb\_encode\_mimeheader](https://www.php.net/manual/en/function.mb-encode-mimeheader.php) — Encode string for MIME header
  - [mb\_encode\_numericentity](https://www.php.net/manual/en/function.mb-encode-numericentity.php) — Encode character to HTML numeric string reference
  - [mb\_encoding\_aliases](https://www.php.net/manual/en/function.mb-encoding-aliases.php) — Get aliases of a known encoding type
  - [mb\_ereg](https://www.php.net/manual/en/function.mb-ereg.php) — Regular expression match with multibyte support
  - [mb\_ereg\_match](https://www.php.net/manual/en/function.mb-ereg-match.php) — Regular expression match for multibyte string
  - [mb\_ereg\_replace](https://www.php.net/manual/en/function.mb-ereg-replace.php) — Replace regular expression with multibyte support
  - [mb\_ereg\_replace\_callback](https://www.php.net/manual/en/function.mb-ereg-replace-callback.php) — Perform a regular expression search and replace with multibyte support using a callback
  - [mb\_ereg\_search](https://www.php.net/manual/en/function.mb-ereg-search.php) — Multibyte regular expression match for predefined multibyte string
  - [mb\_ereg\_search\_getpos](https://www.php.net/manual/en/function.mb-ereg-search-getpos.php) — Returns start point for next regular expression match
  - [mb\_ereg\_search\_getregs](https://www.php.net/manual/en/function.mb-ereg-search-getregs.php) — Retrieve the result from the last multibyte regular expression match
  - [mb\_ereg\_search\_init](https://www.php.net/manual/en/function.mb-ereg-search-init.php) — Setup string and regular expression for a multibyte regular expression match
  - [mb\_ereg\_search\_pos](https://www.php.net/manual/en/function.mb-ereg-search-pos.php) — Returns position and length of a matched part of the multibyte regular expression for a predefined multibyte string
  - [mb\_ereg\_search\_regs](https://www.php.net/manual/en/function.mb-ereg-search-regs.php) — Returns the matched part of a multibyte regular expression
  - [mb\_ereg\_search\_setpos](https://www.php.net/manual/en/function.mb-ereg-search-setpos.php) — Set start point of next regular expression match
  - [mb\_eregi](https://www.php.net/manual/en/function.mb-eregi.php) — Regular expression match ignoring case with multibyte support
  - [mb\_eregi\_replace](https://www.php.net/manual/en/function.mb-eregi-replace.php) — Replace regular expression with multibyte support ignoring case
  - [mb\_get\_info](https://www.php.net/manual/en/function.mb-get-info.php) — Get internal settings of mbstring
  - [mb\_http\_input](https://www.php.net/manual/en/function.mb-http-input.php) — Detect HTTP input character encoding
  - [mb\_http\_output](https://www.php.net/manual/en/function.mb-http-output.php) — Set/Get HTTP output character encoding
  - [mb\_internal\_encoding](https://www.php.net/manual/en/function.mb-internal-encoding.php) — Set/Get internal character encoding
  - [mb\_language](https://www.php.net/manual/en/function.mb-language.php) — Set/Get current language
  - [mb\_lcfirst](https://www.php.net/manual/en/function.mb-lcfirst.php) — Make a string's first character lowercase
  - [mb\_list\_encodings](https://www.php.net/manual/en/function.mb-list-encodings.php) — Returns an array of all supported encodings
  - [mb\_ltrim](https://www.php.net/manual/en/function.mb-ltrim.php) — Strip whitespace (or other characters) from the beginning of a string
  - [mb\_ord](https://www.php.net/manual/en/function.mb-ord.php) — Get Unicode code point of character
  - [mb\_output\_handler](https://www.php.net/manual/en/function.mb-output-handler.php) — Callback function converts character encoding in output buffer
  - [mb\_parse\_str](https://www.php.net/manual/en/function.mb-parse-str.php) — Parse GET/POST/COOKIE data and set global variable
  - [mb\_preferred\_mime\_name](https://www.php.net/manual/en/function.mb-preferred-mime-name.php) — Get MIME charset string
  - [mb\_regex\_encoding](https://www.php.net/manual/en/function.mb-regex-encoding.php) — Set/Get character encoding for multibyte regex
  - [mb\_regex\_set\_options](https://www.php.net/manual/en/function.mb-regex-set-options.php) — Set/Get the default options for mbregex functions
  - [mb\_rtrim](https://www.php.net/manual/en/function.mb-rtrim.php) — Strip whitespace (or other characters) from the end of a string
  - [mb\_scrub](https://www.php.net/manual/en/function.mb-scrub.php) — Replace ill-formed byte sequences with the substitute character
  - [mb\_send\_mail](https://www.php.net/manual/en/function.mb-send-mail.php) — Send encoded mail
  - [mb\_split](https://www.php.net/manual/en/function.mb-split.php) — Split multibyte string using regular expression
  - [mb\_str\_pad](https://www.php.net/manual/en/function.mb-str-pad.php) — Pad a multibyte string to a certain length with another multibyte string
  - [mb\_str\_split](https://www.php.net/manual/en/function.mb-str-split.php) — Given a multibyte string, return an array of its characters
  - [mb\_strcut](https://www.php.net/manual/en/function.mb-strcut.php) — Get part of string
  - [mb\_strimwidth](https://www.php.net/manual/en/function.mb-strimwidth.php) — Get truncated string with specified width
  - [mb\_stripos](https://www.php.net/manual/en/function.mb-stripos.php) — Finds position of first occurrence of a string within another, case insensitive
  - [mb\_stristr](https://www.php.net/manual/en/function.mb-stristr.php) — Finds first occurrence of a string within another, case insensitive
  - [mb\_strlen](https://www.php.net/manual/en/function.mb-strlen.php) — Get string length
  - [mb\_strpos](https://www.php.net/manual/en/function.mb-strpos.php) — Find position of first occurrence of string in a string
  - [mb\_strrchr](https://www.php.net/manual/en/function.mb-strrchr.php) — Finds the last occurrence of a character in a string within another
  - [mb\_strrichr](https://www.php.net/manual/en/function.mb-strrichr.php) — Finds the last occurrence of a character in a string within another, case insensitive
  - [mb\_strripos](https://www.php.net/manual/en/function.mb-strripos.php) — Finds position of last occurrence of a string within another, case insensitive
  - [mb\_strrpos](https://www.php.net/manual/en/function.mb-strrpos.php) — Find position of last occurrence of a string in a string
  - [mb\_strstr](https://www.php.net/manual/en/function.mb-strstr.php) — Finds first occurrence of a string within another
  - [mb\_strtolower](https://www.php.net/manual/en/function.mb-strtolower.php) — Make a string lowercase
  - [mb\_strtoupper](https://www.php.net/manual/en/function.mb-strtoupper.php) — Make a string uppercase
  - [mb\_strwidth](https://www.php.net/manual/en/function.mb-strwidth.php) — Return width of string
  - [mb\_substitute\_character](https://www.php.net/manual/en/function.mb-substitute-character.php) — Set/Get substitution character
  - [mb\_substr](https://www.php.net/manual/en/function.mb-substr.php) — Get part of string
  - [mb\_substr\_count](https://www.php.net/manual/en/function.mb-substr-count.php) — Count the number of substring occurrences
  - [mb\_trim](https://www.php.net/manual/en/function.mb-trim.php) — Strip whitespace (or other characters) from the beginning and end of a string
  - [mb\_ucfirst](https://www.php.net/manual/en/function.mb-ucfirst.php) — Make a string's first character uppercase

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/mbstring/book.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fbook.mbstring%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=book.mbstring&repo=en&redirect=https://www.php.net/manual/en/book.mbstring.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google