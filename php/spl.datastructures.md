---
url: https://www.php.net/manual/en/spl.datastructures.php
scraped_at: 2025-10-20T02:39:20.396Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Datastructures [¶](https://www.php.net/manual/en/spl.datastructures.php\#spl.datastructures)

## Table of Contents [¶](https://www.php.net/manual/en/spl.datastructures.php\#spl.datastructures)

- [SplDoublyLinkedList](https://www.php.net/manual/en/class.spldoublylinkedlist.php)
- [SplStack](https://www.php.net/manual/en/class.splstack.php)
- [SplQueue](https://www.php.net/manual/en/class.splqueue.php)
- [SplHeap](https://www.php.net/manual/en/class.splheap.php)
- [SplMaxHeap](https://www.php.net/manual/en/class.splmaxheap.php)
- [SplMinHeap](https://www.php.net/manual/en/class.splminheap.php)
- [SplPriorityQueue](https://www.php.net/manual/en/class.splpriorityqueue.php)
- [SplFixedArray](https://www.php.net/manual/en/class.splfixedarray.php)
- [ArrayObject](https://www.php.net/manual/en/class.arrayobject.php)
- [SplObjectStorage](https://www.php.net/manual/en/class.splobjectstorage.php)

SPL provides a set of standard datastructures. They are grouped here by their
underlying implementation which usually defines their general field of
application.


## Doubly Linked Lists

A Doubly Linked List (DLL) is a list of nodes linked in both directions to
each other. Iterator's operations, access to both ends, addition or
removal of nodes have a cost of O(1) when the underlying structure is a DLL.
It hence provides a decent implementation for stacks and queues.


- [SplDoublyLinkedList](https://www.php.net/manual/en/class.spldoublylinkedlist.php)  - [SplStack](https://www.php.net/manual/en/class.splstack.php)
  - [SplQueue](https://www.php.net/manual/en/class.splqueue.php)

## Heaps

Heaps are tree-like structures that follow the heap-property: each node
is greater than or equal to its children, when compared using the
implemented compare method which is global to the heap.


- [SplHeap](https://www.php.net/manual/en/class.splheap.php)  - [SplMaxHeap](https://www.php.net/manual/en/class.splmaxheap.php)
  - [SplMinHeap](https://www.php.net/manual/en/class.splminheap.php)
- [SplPriorityQueue](https://www.php.net/manual/en/class.splpriorityqueue.php)

## Arrays

Arrays are structures that store the data in a contiguous way,
accessible via indexes.


> **Note**:
>
> Do not confuse this with PHP's native [array](https://www.php.net/manual/en/language.types.array.php) type.
> PHP arrays are in reality ordered hashtables.
> However, SPL provides the [ArrayObject](https://www.php.net/manual/en/class.arrayobject.php) class
> to wrap PHP arrays into an object.

- [SplFixedArray](https://www.php.net/manual/en/class.splfixedarray.php)

## Map

A map is a datastructure holding key-value pairs. PHP arrays can be seen as maps from integers/strings to values. SPL provides a map from objects to data. This map can also be used as an object set.


- [SplObjectStorage](https://www.php.net/manual/en/class.splobjectstorage.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/spl/datastructures.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fspl.datastructures%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=spl.datastructures&repo=en&redirect=https://www.php.net/manual/en/spl.datastructures.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google