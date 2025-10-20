---
url: https://www.php.net/manual/en/class.jsonserializable.php
scraped_at: 2025-10-20T02:40:53.581Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The JsonSerializable interface [¶](https://www.php.net/manual/en/class.jsonserializable.php\#class.jsonserializable)

(PHP 5 >= 5.4.0, PHP 7, PHP 8)

## Introduction [¶](https://www.php.net/manual/en/class.jsonserializable.php\#jsonserializable.intro)

Objects implementing **JsonSerializable**
can customize their JSON representation when encoded with
[json\_encode()](https://www.php.net/manual/en/function.json-encode.php).


## Interface synopsis [¶](https://www.php.net/manual/en/class.jsonserializable.php\#jsonserializable.synopsis)

interface **JsonSerializable** {

/\\* Methods \*/

public[jsonSerialize](https://www.php.net/manual/en/jsonserializable.jsonserialize.php)(): [mixed](https://www.php.net/manual/en/language.types.mixed.php)

}

## Table of Contents [¶](https://www.php.net/manual/en/class.jsonserializable.php\#class.jsonserializable)

- [JsonSerializable::jsonSerialize](https://www.php.net/manual/en/jsonserializable.jsonserialize.php) — Specify data which should be serialized to JSON

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/json/jsonserializable.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.jsonserializable%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.jsonserializable&repo=en&redirect=https://www.php.net/manual/en/class.jsonserializable.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google