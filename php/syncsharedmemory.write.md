---
url: https://www.php.net/manual/en/syncsharedmemory.write.php
scraped_at: 2025-10-20T02:43:01.058Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# SyncSharedMemory::write

(PECL sync >= 1.1.0)

SyncSharedMemory::write — Copy data to named shared memory

### Description [¶](https://www.php.net/manual/en/syncsharedmemory.write.php\#refsect1-syncsharedmemory.write-description)

public**SyncSharedMemory::write**([string](https://www.php.net/manual/en/language.types.string.php) `$string` = ?, [int](https://www.php.net/manual/en/language.types.integer.php) `$start` = 0)

Copies data to named shared memory.


### Parameters [¶](https://www.php.net/manual/en/syncsharedmemory.write.php\#refsect1-syncsharedmemory.write-parameters)

`string`

The data to write to shared memory.


> **Note**:
>
>
> If the size of the data exceeds the size of the shared memory, the number of
> bytes written returned will be less than the length of the input.

`start`

The start/offset, in bytes, to begin writing.


> **Note**:
>
>
> If the value is negative, the starting position will begin at the specified
> number of bytes from the end of the shared memory segment.

### Return Values [¶](https://www.php.net/manual/en/syncsharedmemory.write.php\#refsect1-syncsharedmemory.write-returnvalues)

An integer containing the number of bytes written to shared memory.


### Examples [¶](https://www.php.net/manual/en/syncsharedmemory.write.php\#refsect1-syncsharedmemory.write-examples)

**Example #1 **SyncSharedMemory::write()** example**

`<?php
// You will probably need to protect shared memory with other synchronization objects.
// Shared memory goes away when the last reference to it disappears.
$mem = new SyncSharedMemory("AppReportName", 1024);
if ($mem->first())
{
    // Do first time initialization work here.
}
$result = $mem->write("report.txt");
var_dump($result);
$result = $mem->write("report.txt", -3);
var_dump($result);
?>`

The above example will output
something similar to:

```
int(10)
int(3)
```

### See Also [¶](https://www.php.net/manual/en/syncsharedmemory.write.php\#refsect1-syncsharedmemory.write-seealso)

- [SyncSharedMemory::\_\_construct()](https://www.php.net/manual/en/syncsharedmemory.construct.php) \- Constructs a new SyncSharedMemory object
- [SyncSharedMemory::first()](https://www.php.net/manual/en/syncsharedmemory.first.php) \- Check to see if the object is the first instance system-wide of named shared memory
- **SyncSharedMemory::write()**
- [SyncSharedMemory::read()](https://www.php.net/manual/en/syncsharedmemory.read.php) \- Copy data from named shared memory

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/sync/syncsharedmemory/write.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fsyncsharedmemory.write%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=syncsharedmemory.write&repo=en&redirect=https://www.php.net/manual/en/syncsharedmemory.write.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google