---
url: https://www.php.net/manual/en/ref.spl.php
scraped_at: 2025-10-20T02:34:41.460Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# SPL Functions [¶](https://www.php.net/manual/en/ref.spl.php\#ref.spl)

## Table of Contents [¶](https://www.php.net/manual/en/ref.spl.php\#ref.spl)

- [class\_implements](https://www.php.net/manual/en/function.class-implements.php) — Return the interfaces which are implemented by the given class or interface
- [class\_parents](https://www.php.net/manual/en/function.class-parents.php) — Return the parent classes of the given class
- [class\_uses](https://www.php.net/manual/en/function.class-uses.php) — Return the traits used by the given class
- [iterator\_apply](https://www.php.net/manual/en/function.iterator-apply.php) — Call a function for every element in an iterator
- [iterator\_count](https://www.php.net/manual/en/function.iterator-count.php) — Count the elements in an iterator
- [iterator\_to\_array](https://www.php.net/manual/en/function.iterator-to-array.php) — Copy the iterator into an array
- [spl\_autoload](https://www.php.net/manual/en/function.spl-autoload.php) — Default implementation for \_\_autoload()
- [spl\_autoload\_call](https://www.php.net/manual/en/function.spl-autoload-call.php) — Try all registered \_\_autoload() functions to load the requested class
- [spl\_autoload\_extensions](https://www.php.net/manual/en/function.spl-autoload-extensions.php) — Register and return default file extensions for spl\_autoload
- [spl\_autoload\_functions](https://www.php.net/manual/en/function.spl-autoload-functions.php) — Return all registered \_\_autoload() functions
- [spl\_autoload\_register](https://www.php.net/manual/en/function.spl-autoload-register.php) — Register given function as \_\_autoload() implementation
- [spl\_autoload\_unregister](https://www.php.net/manual/en/function.spl-autoload-unregister.php) — Unregister given function as \_\_autoload() implementation
- [spl\_classes](https://www.php.net/manual/en/function.spl-classes.php) — Return available SPL classes
- [spl\_object\_hash](https://www.php.net/manual/en/function.spl-object-hash.php) — Return hash id for given object
- [spl\_object\_id](https://www.php.net/manual/en/function.spl-object-id.php) — Return the integer object handle for given object

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/spl/reference.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fref.spl%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=ref.spl&repo=en&redirect=https://www.php.net/manual/en/ref.spl.php)

### User Contributed Notes 8 notes

[up](https://www.php.net/manual/vote-note.php?id=60636&page=ref.spl&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=60636&page=ref.spl&vote=down "Vote down!")

7


[**_ville</.>witt</a>gmail</.>com_**](https://www.php.net/manual/en/ref.spl.php#60636) [¶](https://www.php.net/manual/en/ref.spl.php#60636)

**19 years ago**

`These to funtions has excatly the same output, the only diff. is in which directory iterator they use. I hope someone out there can use it:
<?php
function listfilesin1 ($dir = ".", $depth=0) {
    echo "Dir: ".$dir."<br/>";
    foreach(new DirectoryIterator($dir) as $file) {
        if (!$file->isDot()) {
            if ($file->isDir()) {
                $newdir = $file->getPathname();
                listfilesin1($newdir, $depth+1);
            } else {
                echo "($depth)".$file->getPathname() . "<br/>";
            }
        }
    }
}
function listfilesin2 ($dir = ".", $depth=0) {
    echo "Dir: ".$dir."<br/>";
    foreach(new RecursiveDirectoryIterator($dir) as $file) {
        if ($file->hasChildren(false)) {
            $newdir = $file->key();
            listfilesin2($newdir, $depth+1);
        } else {
            echo "($depth)".$file->key() . "<br/>";
        }
    }
}
listfilesin();
?>`

[up](https://www.php.net/manual/vote-note.php?id=83295&page=ref.spl&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=83295&page=ref.spl&vote=down "Vote down!")

5


[**_loaded67 at hotmail dot com_**](https://www.php.net/manual/en/ref.spl.php#83295) [¶](https://www.php.net/manual/en/ref.spl.php#83295)

**17 years ago**

`For some application I needed to reverse some standard iterators.
So I mocked up this flexible function.
Enjoy
<?php
function reverse_iterator(Iterator $iterator){
    $type     = get_class($iterator);
    $array     = array_reverse(iterator_to_array($iterator), true);
    return new $type($array);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=72790&page=ref.spl&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=72790&page=ref.spl&vote=down "Vote down!")

3


[**_semperluc (at) yahoo.\_forgot\_the\_rest_**](https://www.php.net/manual/en/ref.spl.php#72790) [¶](https://www.php.net/manual/en/ref.spl.php#72790)

**18 years ago**

`<?php
/*
How to store SPL Iterator results (rather than just echo-and-forget):
The library of Iterators  are object based, so you need to trick the little rascals into an array.
Here's how (two ways) ...
1. Explicit typecasts: $a[] = (array)$Obj->objMethod();
2. Array definition: $a[] = array( key => $Obj->objMethod() );
Examples: DirectoryIterator()
*/
// 1. explicity typecast object as array
foreach ( new DirectoryIterator('./') as $Item )
{
$fname = (array)$Item->getFilename();
$dir_listing[] = $fname[0];
}
//
echo "<pre>";
print_r($dir_listing); unset($dir_listing);
echo"</pre><hr />";
//
// or
// 2. define array as key => object->method
foreach ( new DirectoryIterator('./') as $Item )
{
$dir_listing[] = array (
    "fname" => $Item->getFilename(),
    "path" => $Item->getPathname(),
    "size" => $Item->getSize(),
    "mtime" => $Item->getMTime()
);
}
//
echo "<pre>";
print_r($dir_listing); unset($dir_listing);
echo"</pre>";
//
?>`

[up](https://www.php.net/manual/vote-note.php?id=84627&page=ref.spl&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=84627&page=ref.spl&vote=down "Vote down!")

2


[**_benny at whitewashing dot de_**](https://www.php.net/manual/en/ref.spl.php#84627) [¶](https://www.php.net/manual/en/ref.spl.php#84627)

**17 years ago**

`I have to correct my implementation from before. The example before only supported correct read-access but failed on setting new values after creation of the ArrayMultiObject. Also i had to correct a bug that occured from my CopyPasteChange into the comment textarea.
This snippet now hopefully implements a fully functional multidimensional array, represented by an ArrayObject:
<?php
class ArrayMultiObject extends ArrayObject
{
    function __construct($array, $flags = 0, $iterator_class = "ArrayIterator")
    {
        $objects = array();
        foreach($array AS $key => $value) {
            if(is_array($value)) {
                $objects[$key] = new ArrayMultiObject($value, $flags, $iterator_class);
            } else {
                $objects[$key] = $value;
            }
        }
        parent::__construct($objects, $flags, $iterator_class);
    }
    public function offsetSet($name, $value)
    {
        if(is_array($value)) {
            $value = new ArrayMultiObject($value);
        }
        return parent::offsetSet($name, $value);
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=57147&page=ref.spl&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=57147&page=ref.spl&vote=down "Vote down!")

2


[**_helly at php dot net_**](https://www.php.net/manual/en/ref.spl.php#57147) [¶](https://www.php.net/manual/en/ref.spl.php#57147)

**20 years ago**

`There is a RecursiveFilterIterator that makes the above code much easier. And then ther is ParentIterator thta is already a filtering recursive iterator that only accepts elements that have children, with a RecursiveDirectoryIterator as inner iterator you would obviously get only the directories. Further more it ensures that it creates the correct children. All in all you simply need to do this:
$it = new RecursiveDirectoryIterator($path);
$it = new ParentIterator($it);
$it = new RecursiveIteratorIteator($it);
foreach($it as $dir  => $o) { ... }`

[up](https://www.php.net/manual/vote-note.php?id=41636&page=ref.spl&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=41636&page=ref.spl&vote=down "Vote down!")

2


[**_phil &ampersat; flatnet.net_**](https://www.php.net/manual/en/ref.spl.php#41636) [¶](https://www.php.net/manual/en/ref.spl.php#41636)

**21 years ago**

`Here's a sample implementation of the RecursiveDirectoryIterator class. It prints a simple treeview of a given directory:
<?php
function recurse($it) {
echo '<ul>';
for( ; $it->valid(); $it->next()) {
       if($it->isDir() && !$it->isDot()) {
           printf('<li class="dir">%s</li>', $it->current());
           if($it->hasChildren()) {
               $bleh = $it->getChildren();
               echo '<ul>' . recurse($bleh) . '</ul>';
           }
       } elseif($it->isFile()) {
           echo '<li class="file">'. $it->current() . ' (' . $it->getSize(). ' Bytes)</li>';
       }
}
echo '</ul>';
}
recurse(new RecursiveDirectoryIterator('D:/'));
?>`

[up](https://www.php.net/manual/vote-note.php?id=57663&page=ref.spl&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=57663&page=ref.spl&vote=down "Vote down!")

2


[**_adove at booyahnetworks dot com_**](https://www.php.net/manual/en/ref.spl.php#57663) [¶](https://www.php.net/manual/en/ref.spl.php#57663)

**20 years ago**

`Something to note that, at least to me, seems pretty important and is not entirely clear in the documentation is the fact that the ArrayObject class supports get/set on uni-dimensional keys and get ONLY on *passed* multi-dimensional keys/paths (see source below). If you, like me, need to support array accesss overloading for multi-dimensional data, you will need to derive from ArrayObject and overide the ArrayAccess interface methods to "walk" passed data and convert embedded arrays to objects of some kind...
Reference Bug 34816 @ [http://bugs.php.net/bug.php?id=34816.](http://bugs.php.net/bug.php?id=34816.)
Illustration of the issue:
$a = array(
    "test" => array(
        "one" => "dunno",
        "two" => array(
            "peekabo" => "do you see me?",
            "anyone" => array("there")
            )
        )
    );
$oArray = new ArrayObject($a);
var_dump($oArray);
$oArray["three"] = "No problems here.";
echo "\n\\test\\one == " . $oArray["test"]["one"] . "\n\n";
// NEITHER of the two below will work!
$oArray["test"]["one"] = "Yes I do!";
$oArray["test"]["yes"] = array(
    "hello" => "Goodbye!"
    );
var_dump($oArray);
---
Note from the extension author:
Actually there is RecursiveArrayObject and RecursiveArrayIterator to deal with recursive structures. However this does not always solve all multidimensional issues as expected.`

[up](https://www.php.net/manual/vote-note.php?id=77794&page=ref.spl&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=77794&page=ref.spl&vote=down "Vote down!")

1


[**_prometheus - csaba dot dobai at php-sparcle dot hu_**](https://www.php.net/manual/en/ref.spl.php#77794) [¶](https://www.php.net/manual/en/ref.spl.php#77794)

**18 years ago**

`This code is an example. By using classes like this, you gives a chance to create classes which extends another class but have most of the ability what a class extends ArrayObject (like multiple inheritance):
<?php
class foo
{
    public $foo = 'foo';
} // class
class foobar extends foo implements ArrayAccess,IteratorAggregate,Countable
{
    public function offsetExists($offset)
    {
        $array = array(1, 2, 3, 4);
        return array_key_exists($offset, $array);
    }

    public function offsetGet($offset)
    {
        $array = array(1, 2, 3, 4);
        return $array[$offset];
    }

    public function offsetSet($offset, $value)
    {
        // Makes "array" to readonly
    }

    public function offsetUnset($offset)
    {
        // Makes "array" to readonly
    }

    function count()
    {
        $array = array(1, 2, 3, 4);
        return count($array);
    } // function

    function getArray()
    {
        return array(1, 2, 3, 4);
    } // function

    function getIterator()
    {
        return new ArrayIterator(array(1, 2, 3, 4));
    } // function

    function __toString()
    {
        return 'String test';
    } // function
} // class
$foobar = new foobar();
print $foobar[0].'<br/>';
print $foobar->foo.'<br/>';
print count($foobar).'<br/>';
foreach ($foobar as $k=>$v)
{
    print $k.'=>'.$v.'<br/>';
} // foreach
var_dump($foobar->getArray());
print $foobar;
/* Generated output:
1
foo
4
0=>1
1=>2
2=>3
3=>4
array
0 => int 1
1 => int 2
2 => int 3
3 => int 4
String test
*/
?>
For proper use you must be define all these methods except getArray()
Browse SPL's sources to be a very helpful think.
ps.: sry for my english`

[＋add a note](https://www.php.net/manual/add-note.php?sect=ref.spl&repo=en&redirect=https://www.php.net/manual/en/ref.spl.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google