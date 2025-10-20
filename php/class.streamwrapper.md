---
url: https://www.php.net/manual/en/class.streamwrapper.php
scraped_at: 2025-10-20T02:47:42.996Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The streamWrapper class [¶](https://www.php.net/manual/en/class.streamwrapper.php\#class.streamwrapper)

(PHP 4 >= 4.3.2, PHP 5, PHP 7, PHP 8)

## Introduction [¶](https://www.php.net/manual/en/class.streamwrapper.php\#streamwrapper.intro)

Allows you to implement your own protocol handlers and streams for use
with all the other filesystem functions (such as [fopen()](https://www.php.net/manual/en/function.fopen.php),
[fread()](https://www.php.net/manual/en/function.fread.php) etc.).


> **Note**:
>
>
> This is _NOT_ a real class, only a prototype of how
> a class defining its own protocol should be.

> **Note**:
>
>
> Implementing the methods in other ways than described here can lead to
> undefined behaviour.

An instance of this class is initialized as soon as a stream function
tries to access the protocol it is associated with.


## Class synopsis [¶](https://www.php.net/manual/en/class.streamwrapper.php\#streamwrapper.synopsis)

classstreamWrapper
{

/\\* Properties \*/

public[resource](https://www.php.net/manual/en/language.types.resource.php)[$context](https://www.php.net/manual/en/class.streamwrapper.php#streamwrapper.props.context);

/\\* Methods \*/

public[\_\_construct](https://www.php.net/manual/en/streamwrapper.construct.php)()

public[dir\_closedir](https://www.php.net/manual/en/streamwrapper.dir-closedir.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[dir\_opendir](https://www.php.net/manual/en/streamwrapper.dir-opendir.php)([string](https://www.php.net/manual/en/language.types.string.php) `$path`, [int](https://www.php.net/manual/en/language.types.integer.php) `$options`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[dir\_readdir](https://www.php.net/manual/en/streamwrapper.dir-readdir.php)(): [string](https://www.php.net/manual/en/language.types.string.php)\|[bool](https://www.php.net/manual/en/language.types.boolean.php)

public[dir\_rewinddir](https://www.php.net/manual/en/streamwrapper.dir-rewinddir.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[mkdir](https://www.php.net/manual/en/streamwrapper.mkdir.php)([string](https://www.php.net/manual/en/language.types.string.php) `$path`, [int](https://www.php.net/manual/en/language.types.integer.php) `$mode`, [int](https://www.php.net/manual/en/language.types.integer.php) `$options`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[rename](https://www.php.net/manual/en/streamwrapper.rename.php)([string](https://www.php.net/manual/en/language.types.string.php) `$path_from`, [string](https://www.php.net/manual/en/language.types.string.php) `$path_to`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[rmdir](https://www.php.net/manual/en/streamwrapper.rmdir.php)([string](https://www.php.net/manual/en/language.types.string.php) `$path`, [int](https://www.php.net/manual/en/language.types.integer.php) `$options`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[stream\_cast](https://www.php.net/manual/en/streamwrapper.stream-cast.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$cast_as`): [resource](https://www.php.net/manual/en/language.types.resource.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

public[stream\_close](https://www.php.net/manual/en/streamwrapper.stream-close.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[stream\_eof](https://www.php.net/manual/en/streamwrapper.stream-eof.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[stream\_flush](https://www.php.net/manual/en/streamwrapper.stream-flush.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[stream\_lock](https://www.php.net/manual/en/streamwrapper.stream-lock.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$operation`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[stream\_metadata](https://www.php.net/manual/en/streamwrapper.stream-metadata.php)([string](https://www.php.net/manual/en/language.types.string.php) `$path`, [int](https://www.php.net/manual/en/language.types.integer.php) `$option`, [mixed](https://www.php.net/manual/en/language.types.mixed.php) `$value`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[stream\_open](https://www.php.net/manual/en/streamwrapper.stream-open.php)(

[string](https://www.php.net/manual/en/language.types.string.php) `$path`,

[string](https://www.php.net/manual/en/language.types.string.php) `$mode`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$options`,

[?](https://www.php.net/manual/en/language.types.null.php)[string](https://www.php.net/manual/en/language.types.string.php) `&$opened_path`

): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[stream\_read](https://www.php.net/manual/en/streamwrapper.stream-read.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$count`): [string](https://www.php.net/manual/en/language.types.string.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

public[stream\_seek](https://www.php.net/manual/en/streamwrapper.stream-seek.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$offset`, [int](https://www.php.net/manual/en/language.types.integer.php) `$whence`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[stream\_set\_option](https://www.php.net/manual/en/streamwrapper.stream-set-option.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$option`, [int](https://www.php.net/manual/en/language.types.integer.php) `$arg1`, [int](https://www.php.net/manual/en/language.types.integer.php) `$arg2`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[stream\_stat](https://www.php.net/manual/en/streamwrapper.stream-stat.php)(): [array](https://www.php.net/manual/en/language.types.array.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

public[stream\_tell](https://www.php.net/manual/en/streamwrapper.stream-tell.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[stream\_truncate](https://www.php.net/manual/en/streamwrapper.stream-truncate.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$new_size`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[stream\_write](https://www.php.net/manual/en/streamwrapper.stream-write.php)([string](https://www.php.net/manual/en/language.types.string.php) `$data`): [int](https://www.php.net/manual/en/language.types.integer.php)

public[unlink](https://www.php.net/manual/en/streamwrapper.unlink.php)([string](https://www.php.net/manual/en/language.types.string.php) `$path`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[url\_stat](https://www.php.net/manual/en/streamwrapper.url-stat.php)([string](https://www.php.net/manual/en/language.types.string.php) `$path`, [int](https://www.php.net/manual/en/language.types.integer.php) `$flags`): [array](https://www.php.net/manual/en/language.types.array.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

public[\_\_destruct](https://www.php.net/manual/en/streamwrapper.destruct.php)()

}

## Properties [¶](https://www.php.net/manual/en/class.streamwrapper.php\#streamwrapper.props)

resource context

The current [context](https://www.php.net/manual/en/context.php), or **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** if no
context was passed to the caller function.


Use the [stream\_context\_get\_options()](https://www.php.net/manual/en/function.stream-context-get-options.php) to parse the
context.


> **Note**:
>
>
> This property _must_ be public so PHP can populate
> it with the actual context resource.

## See Also

- [Example class registered as stream wrapper](https://www.php.net/manual/en/stream.streamwrapper.example-1.php)
- [stream\_wrapper\_register()](https://www.php.net/manual/en/function.stream-wrapper-register.php)
- [stream\_wrapper\_unregister()](https://www.php.net/manual/en/function.stream-wrapper-unregister.php)
- [stream\_wrapper\_restore()](https://www.php.net/manual/en/function.stream-wrapper-restore.php)

## Table of Contents [¶](https://www.php.net/manual/en/class.streamwrapper.php\#class.streamwrapper)

- [streamWrapper::\_\_construct](https://www.php.net/manual/en/streamwrapper.construct.php) — Constructs a new stream wrapper
- [streamWrapper::\_\_destruct](https://www.php.net/manual/en/streamwrapper.destruct.php) — Destructs an existing stream wrapper
- [streamWrapper::dir\_closedir](https://www.php.net/manual/en/streamwrapper.dir-closedir.php) — Close directory handle
- [streamWrapper::dir\_opendir](https://www.php.net/manual/en/streamwrapper.dir-opendir.php) — Open directory handle
- [streamWrapper::dir\_readdir](https://www.php.net/manual/en/streamwrapper.dir-readdir.php) — Read entry from directory handle
- [streamWrapper::dir\_rewinddir](https://www.php.net/manual/en/streamwrapper.dir-rewinddir.php) — Rewind directory handle
- [streamWrapper::mkdir](https://www.php.net/manual/en/streamwrapper.mkdir.php) — Create a directory
- [streamWrapper::rename](https://www.php.net/manual/en/streamwrapper.rename.php) — Renames a file or directory
- [streamWrapper::rmdir](https://www.php.net/manual/en/streamwrapper.rmdir.php) — Removes a directory
- [streamWrapper::stream\_cast](https://www.php.net/manual/en/streamwrapper.stream-cast.php) — Retrieve the underlaying resource
- [streamWrapper::stream\_close](https://www.php.net/manual/en/streamwrapper.stream-close.php) — Close a resource
- [streamWrapper::stream\_eof](https://www.php.net/manual/en/streamwrapper.stream-eof.php) — Tests for end-of-file on a file pointer
- [streamWrapper::stream\_flush](https://www.php.net/manual/en/streamwrapper.stream-flush.php) — Flushes the output
- [streamWrapper::stream\_lock](https://www.php.net/manual/en/streamwrapper.stream-lock.php) — Advisory file locking
- [streamWrapper::stream\_metadata](https://www.php.net/manual/en/streamwrapper.stream-metadata.php) — Change stream metadata
- [streamWrapper::stream\_open](https://www.php.net/manual/en/streamwrapper.stream-open.php) — Opens file or URL
- [streamWrapper::stream\_read](https://www.php.net/manual/en/streamwrapper.stream-read.php) — Read from stream
- [streamWrapper::stream\_seek](https://www.php.net/manual/en/streamwrapper.stream-seek.php) — Seeks to specific location in a stream
- [streamWrapper::stream\_set\_option](https://www.php.net/manual/en/streamwrapper.stream-set-option.php) — Change stream options
- [streamWrapper::stream\_stat](https://www.php.net/manual/en/streamwrapper.stream-stat.php) — Retrieve information about a file resource
- [streamWrapper::stream\_tell](https://www.php.net/manual/en/streamwrapper.stream-tell.php) — Retrieve the current position of a stream
- [streamWrapper::stream\_truncate](https://www.php.net/manual/en/streamwrapper.stream-truncate.php) — Truncate stream
- [streamWrapper::stream\_write](https://www.php.net/manual/en/streamwrapper.stream-write.php) — Write to stream
- [streamWrapper::unlink](https://www.php.net/manual/en/streamwrapper.unlink.php) — Delete a file
- [streamWrapper::url\_stat](https://www.php.net/manual/en/streamwrapper.url-stat.php) — Retrieve information about a file

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/stream/streamwrapper.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.streamwrapper%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.streamwrapper&repo=en&redirect=https://www.php.net/manual/en/class.streamwrapper.php)

### User Contributed Notes 4 notes

[up](https://www.php.net/manual/vote-note.php?id=100549&page=class.streamwrapper&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=100549&page=class.streamwrapper&vote=down "Vote down!")

14


[**_isaac dot z dot no dot foster at spam dot gmail dot please dot com_**](https://www.php.net/manual/en/class.streamwrapper.php#100549) [¶](https://www.php.net/manual/en/class.streamwrapper.php#100549)

**14 years ago**

`It's worth noting that the interface defined by yannick at gmail should not always be implemented by a stream wrapper class, as several of the methods should not be implemented if the class has no use for them (as per the manual).
Specifically, mkdir, rename, rmdir, and unlink are methods that "should not be defined" if the wrapper has no use for them. The consequence is that the appropriate error message will not be returned.
If the interface is implemented, you won't have the flexibility to not implement those methods.
Not trying to be academic, but it was useful for me.`

[up](https://www.php.net/manual/vote-note.php?id=125226&page=class.streamwrapper&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125226&page=class.streamwrapper&vote=down "Vote down!")

1


[**_info at ensostudio dot ru_**](https://www.php.net/manual/en/class.streamwrapper.php#125226) [¶](https://www.php.net/manual/en/class.streamwrapper.php#125226)

**5 years ago**

`THIS METHODS NOT REQUIRED, you can implement only part of their: directories, files, etc.
For example, "glob://" support minimal syntax, glob() more powerful, you can replace/extend native wrapper: check options in table [https://www.php.net/manual/ru/wrappers.glob](https://www.php.net/manual/ru/wrappers.glob) , you need create wrapper only with 'dir_...dir' methods. For more info, see [https://www.php.net/manual/en/class.globiterator.php#125220](https://www.php.net/manual/en/class.globiterator.php#125220)`

[up](https://www.php.net/manual/vote-note.php?id=105872&page=class.streamwrapper&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=105872&page=class.streamwrapper&vote=down "Vote down!")

2


[**_Anonymous_**](https://www.php.net/manual/en/class.streamwrapper.php#105872) [¶](https://www.php.net/manual/en/class.streamwrapper.php#105872)

**14 years ago**

`Here is a very simple stream wrapper which calls your callback function for reads:
<?php
class CallbackUrl
{
    const WRAPPER_NAME = 'callback';
    public $context;
    private $_cb;
    private $_eof = false;
    private static $_isRegistered = false;
    public static function getContext($cb)
    {
        if (!self::$_isRegistered) {
            stream_wrapper_register(self::WRAPPER_NAME, get_class());
            self::$_isRegistered = true;
        }
        if (!is_callable($cb)) return false;
        return stream_context_create(array(self::WRAPPER_NAME => array('cb' => $cb)));
    }
    public function stream_open($path, $mode, $options, &$opened_path)
    {
        if (!preg_match('/^r[bt]?$/', $mode) || !$this->context) return false;
        $opt = stream_context_get_options($this->context);
        if (!is_array($opt[self::WRAPPER_NAME]) ||
            !isset($opt[self::WRAPPER_NAME]['cb']) ||
            !is_callable($opt[self::WRAPPER_NAME]['cb'])) return false;
        $this->_cb = $opt[self::WRAPPER_NAME]['cb'];
        return true;
    }
    public function stream_read($count)
    {
        if ($this->_eof || !$count) return '';
        if (($s = call_user_func($this->_cb, $count)) == '') $this->_eof = true;
        return $s;
    }
    public function stream_eof()
    {
        return $this->_eof;
    }
}
class Test {
    private $_s;
    public function __construct($s)
    {
        $this->_s = $s;
    }
    public function read($count) {
        return fread($this->_s, $count);
    }
}
$t = new Test(fopen('/etc/services', 'r'));
$fd = fopen('callback://', 'r', false, CallbackUrl::getContext(array($t, 'read')));
while(($buf = fread($fd, 128)) != '') {
    print $buf;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=92277&page=class.streamwrapper&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=92277&page=class.streamwrapper&vote=down "Vote down!")

2


[**_yannick dot battail at gmail dot com_**](https://www.php.net/manual/en/class.streamwrapper.php#92277) [¶](https://www.php.net/manual/en/class.streamwrapper.php#92277)

**16 years ago**

`a php interface for wrapper
<?php
interface WrapperInterface
{
    /**
     * resource context
     *
     * @var resource
     */
    //public $context;
    /**
     * constructor
     *
     */
    public function __construct();
    /**
     *
     *
     * @return bool
     */
    public function dir_closedir();
    /**
     * Enter description here...
     *
     * @param string $path
     * @param int $options
     * @return bool
     */
    public function dir_opendir($path , $options);
    /**
     * Enter description here...
     *
     * @return string
     */
    public function dir_readdir();
    /**
     * Enter description here...
     *
     * @return bool
     */
    public function dir_rewinddir();
    /**
     * Enter description here...
     *
     * @param string $path
     * @param int $mode
     * @param int $options
     * @return bool
     */
    public function mkdir($path , $mode , $options);
    /**
     * Enter description here...
     *
     * @param string $path_from
     * @param string $path_to
     * @return bool
     */
    public function rename($path_from , $path_to);
    /**
     * Enter description here...
     *
     * @param string $path
     * @param int $options
     * @return bool
     */
    public function rmdir($path , $options);
    /**
     * Enter description here...
     *
     * @param int $cast_as
     * @return resource
     */
    public function stream_cast($cast_as);
    /**
     * Enter description here...
     *
     */
    public function stream_close();
    /**
     * Enter description here...
     *
     * @return bool
     */
    public function stream_eof();
    /**
     * Enter description here...
     *
     * @return bool
     */
    public function stream_flush();
    /**
     * Enter description here...
     *
     * @param mode $operation
     * @return bool
     */
    public function stream_lock($operation);
    /**
     * Enter description here...
     *
     * @param string $path
     * @param string $mode
     * @param int $options
     * @param string &$opened_path
     * @return bool
     */
    public function stream_open($path , $mode , $options , &$opened_path);
    /**
     * Enter description here...
     *
     * @param int $count
     * @return string
     */
    public function stream_read($count);
    /**
     * Enter description here...
     *
     * @param int $offset
     * @param int $whence = SEEK_SET
     * @return bool
     */
    public function stream_seek($offset , $whence = SEEK_SET);
    /**
     * Enter description here...
     *
     * @param int $option
     * @param int $arg1
     * @param int $arg2
     * @return bool
     */
    public function stream_set_option($option , $arg1 , $arg2);
    /**
     * Enter description here...
     *
     * @return array
     */
    public function stream_stat();
    /**
     * Enter description here...
     *
     * @return int
     */
    public function stream_tell();
    /**
     * Enter description here...
     *
     * @param string $data
     * @return int
     */
    public function stream_write($data);
    /**
     * Enter description here...
     *
     * @param string $path
     * @return bool
     */
    public function unlink($path);
    /**
     * Enter description here...
     *
     * @param string $path
     * @param int $flags
     * @return array
     */
    public function url_stat($path , $flags);
}
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.streamwrapper&repo=en&redirect=https://www.php.net/manual/en/class.streamwrapper.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google