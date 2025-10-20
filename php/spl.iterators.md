---
url: https://www.php.net/manual/en/spl.iterators.php
scraped_at: 2025-10-20T02:36:42.086Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Iterators [¶](https://www.php.net/manual/en/spl.iterators.php\#spl.iterators)

## Table of Contents [¶](https://www.php.net/manual/en/spl.iterators.php\#spl.iterators)

- [AppendIterator](https://www.php.net/manual/en/class.appenditerator.php)
- [ArrayIterator](https://www.php.net/manual/en/class.arrayiterator.php)
- [CachingIterator](https://www.php.net/manual/en/class.cachingiterator.php)
- [CallbackFilterIterator](https://www.php.net/manual/en/class.callbackfilteriterator.php)
- [DirectoryIterator](https://www.php.net/manual/en/class.directoryiterator.php)
- [EmptyIterator](https://www.php.net/manual/en/class.emptyiterator.php)
- [FilesystemIterator](https://www.php.net/manual/en/class.filesystemiterator.php)
- [FilterIterator](https://www.php.net/manual/en/class.filteriterator.php)
- [GlobIterator](https://www.php.net/manual/en/class.globiterator.php)
- [InfiniteIterator](https://www.php.net/manual/en/class.infiniteiterator.php)
- [IteratorIterator](https://www.php.net/manual/en/class.iteratoriterator.php)
- [LimitIterator](https://www.php.net/manual/en/class.limititerator.php)
- [MultipleIterator](https://www.php.net/manual/en/class.multipleiterator.php)
- [NoRewindIterator](https://www.php.net/manual/en/class.norewinditerator.php)
- [ParentIterator](https://www.php.net/manual/en/class.parentiterator.php)
- [RecursiveArrayIterator](https://www.php.net/manual/en/class.recursivearrayiterator.php)
- [RecursiveCachingIterator](https://www.php.net/manual/en/class.recursivecachingiterator.php)
- [RecursiveCallbackFilterIterator](https://www.php.net/manual/en/class.recursivecallbackfilteriterator.php)
- [RecursiveDirectoryIterator](https://www.php.net/manual/en/class.recursivedirectoryiterator.php)
- [RecursiveFilterIterator](https://www.php.net/manual/en/class.recursivefilteriterator.php)
- [RecursiveIteratorIterator](https://www.php.net/manual/en/class.recursiveiteratoriterator.php)
- [RecursiveRegexIterator](https://www.php.net/manual/en/class.recursiveregexiterator.php)
- [RecursiveTreeIterator](https://www.php.net/manual/en/class.recursivetreeiterator.php)
- [RegexIterator](https://www.php.net/manual/en/class.regexiterator.php)

SPL provides a set of iterators to traverse over objects.


## SPL Iterators Class Tree [¶](https://www.php.net/manual/en/spl.iterators.php\#spl.iterators.tree)

- [ArrayIterator](https://www.php.net/manual/en/class.arrayiterator.php)  - [RecursiveArrayIterator](https://www.php.net/manual/en/class.recursivearrayiterator.php)
- [EmptyIterator](https://www.php.net/manual/en/class.emptyiterator.php)
- [IteratorIterator](https://www.php.net/manual/en/class.iteratoriterator.php)  - [AppendIterator](https://www.php.net/manual/en/class.appenditerator.php)
  - [CachingIterator](https://www.php.net/manual/en/class.cachingiterator.php)    - [RecursiveCachingIterator](https://www.php.net/manual/en/class.recursivecachingiterator.php)
  - [FilterIterator](https://www.php.net/manual/en/class.filteriterator.php)    - [CallbackFilterIterator](https://www.php.net/manual/en/class.callbackfilteriterator.php)      - [RecursiveCallbackFilterIterator](https://www.php.net/manual/en/class.recursivecallbackfilteriterator.php)
    - [RecursiveFilterIterator](https://www.php.net/manual/en/class.recursivefilteriterator.php)      - [ParentIterator](https://www.php.net/manual/en/class.parentiterator.php)
    - [RegexIterator](https://www.php.net/manual/en/class.regexiterator.php)      - [RecursiveRegexIterator](https://www.php.net/manual/en/class.recursiveregexiterator.php)
  - [InfiniteIterator](https://www.php.net/manual/en/class.infiniteiterator.php)
  - [LimitIterator](https://www.php.net/manual/en/class.limititerator.php)
  - [NoRewindIterator](https://www.php.net/manual/en/class.norewinditerator.php)
- [MultipleIterator](https://www.php.net/manual/en/class.multipleiterator.php)
- [RecursiveIteratorIterator](https://www.php.net/manual/en/class.recursiveiteratoriterator.php)  - [RecursiveTreeIterator](https://www.php.net/manual/en/class.recursivetreeiterator.php)
- [DirectoryIterator](https://www.php.net/manual/en/class.directoryiterator.php) (extends [SplFileInfo](https://www.php.net/manual/en/class.splfileinfo.php))  - [FilesystemIterator](https://www.php.net/manual/en/class.filesystemiterator.php)    - [GlobIterator](https://www.php.net/manual/en/class.globiterator.php)
    - [RecursiveDirectoryIterator](https://www.php.net/manual/en/class.recursivedirectoryiterator.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/spl/iterators.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fspl.iterators%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=spl.iterators&repo=en&redirect=https://www.php.net/manual/en/spl.iterators.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google