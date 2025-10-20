---
url: https://www.php.net/manual/en/language.generators.comparison.php
scraped_at: 2025-10-20T02:36:21.218Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Comparing generators with [Iterator](https://www.php.net/manual/en/class.iterator.php) objects [¶](https://www.php.net/manual/en/language.generators.comparison.php\#language.generators.comparison)

The primary advantage of generators is their simplicity. Much less
boilerplate code has to be written compared to implementing an
[Iterator](https://www.php.net/manual/en/class.iterator.php) class, and the code is generally much more
readable. For example, the following function and class are equivalent:


`<?php
function getLinesFromFile($fileName) {
    if (!$fileHandle = fopen($fileName, 'r')) {
        return;
    }
    while (false !== $line = fgets($fileHandle)) {
        yield $line;
    }
    fclose($fileHandle);
}
// versus...
class LineIterator implements Iterator {
    protected $fileHandle;
    protected $line;
    protected $i;
    public function __construct($fileName) {
        if (!$this->fileHandle = fopen($fileName, 'r')) {
            throw new RuntimeException('Couldn\'t open file "' . $fileName . '"');
        }
    }
    public function rewind() {
        fseek($this->fileHandle, 0);
        $this->line = fgets($this->fileHandle);
        $this->i = 0;
    }
    public function valid() {
        return false !== $this->line;
    }
    public function current() {
        return $this->line;
    }
    public function key() {
        return $this->i;
    }
    public function next() {
        if (false !== $this->line) {
            $this->line = fgets($this->fileHandle);
            $this->i++;
        }
    }
    public function __destruct() {
        fclose($this->fileHandle);
    }
}
?>`

This flexibility does come at a cost, however: generators are forward-only
iterators, and cannot be rewound once iteration has started. This also
means that the same generator can't be iterated over multiple times: the
generator will need to be rebuilt by calling the generator function again.


### See Also

- [Object Iteration](https://www.php.net/manual/en/language.oop5.iterations.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/generators.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.generators.comparison%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.generators.comparison&repo=en&redirect=https://www.php.net/manual/en/language.generators.comparison.php)

### User Contributed Notes 2 notes

[up](https://www.php.net/manual/vote-note.php?id=112482&page=language.generators.comparison&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=112482&page=language.generators.comparison&vote=down "Vote down!")

106


[**_mNOSPAMsenghaa at nospam dot gmail dot com_**](https://www.php.net/manual/en/language.generators.comparison.php#112482) [¶](https://www.php.net/manual/en/language.generators.comparison.php#112482)

**12 years ago**

`This hardly seems a fair comparison between the two examples, size-for-size. As noted, generators are forward-only, meaning that it should be compared to an iterator with a dummy rewind function defined. Also, to be fair, since the iterator throws an exception, shouldn't the generator example also throw the same exception? The code comparison would become more like this:
<?php
function getLinesFromFile($fileName) {
    if (!$fileHandle = fopen($fileName, 'r')) {
        throw new RuntimeException('Couldn\'t open file "' . $fileName . '"');
    }

    while (false !== $line = fgets($fileHandle)) {
        yield $line;
    }

    fclose($fileHandle);
}
// versus...
class LineIterator implements Iterator {
    protected $fileHandle;

    protected $line;
    protected $i;

    public function __construct($fileName) {
        if (!$this->fileHandle = fopen($fileName, 'r')) {
            throw new RuntimeException('Couldn\'t open file "' . $fileName . '"');
        }
    }

    public function rewind() { }

    public function valid() {
        return false !== $this->line;
    }

    public function current() {
        return $this->line;
    }

    public function key() {
        return $this->i;
    }

    public function next() {
        if (false !== $this->line) {
            $this->line = fgets($this->fileHandle);
            $this->i++;
        }
    }

    public function __destruct() {
        fclose($this->fileHandle);
    }
}
?>
The generator is still obviously much shorter, but this seems a more reasonable comparison.`

[up](https://www.php.net/manual/vote-note.php?id=115173&page=language.generators.comparison&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=115173&page=language.generators.comparison&vote=down "Vote down!")

22


[**_sergeyzsg at yandex dot ru_**](https://www.php.net/manual/en/language.generators.comparison.php#115173) [¶](https://www.php.net/manual/en/language.generators.comparison.php#115173)

**11 years ago**

`I think that this is bad generator example.
If user will not consume all lines then file will not be closed.
<?php
function getLinesFromFile($fileHandle) {
    while (false !== $line = fgets($fileHandle)) {
        yield $line;
    }
}
if ($fileHandle = fopen($fileName, 'r')) {
    /*
    something with getLinesFromFile
    */
    fclose($fileHandle);
}
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.generators.comparison&repo=en&redirect=https://www.php.net/manual/en/language.generators.comparison.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google