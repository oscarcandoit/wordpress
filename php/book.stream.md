---
url: https://www.php.net/manual/en/book.stream.php
scraped_at: 2025-10-20T02:36:35.849Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Streams [¶](https://www.php.net/manual/en/book.stream.php\#book.stream)

- [Introduction](https://www.php.net/manual/en/intro.stream.php)
- [Installing/Configuring](https://www.php.net/manual/en/stream.setup.php)
  - [Stream Classes](https://www.php.net/manual/en/stream.resources.php)
- [Predefined Constants](https://www.php.net/manual/en/stream.constants.php)
- [Stream Filters](https://www.php.net/manual/en/stream.filters.php)
- [Stream Contexts](https://www.php.net/manual/en/stream.contexts.php)
- [Stream Errors](https://www.php.net/manual/en/stream.errors.php)
- [Examples](https://www.php.net/manual/en/stream.examples.php)
  - [Example class registered as stream wrapper](https://www.php.net/manual/en/stream.streamwrapper.example-1.php)
- [php\_user\_filter](https://www.php.net/manual/en/class.php-user-filter.php) — The php\_user\_filter class
  - [php\_user\_filter::filter](https://www.php.net/manual/en/php-user-filter.filter.php) — Called when applying the filter
  - [php\_user\_filter::onClose](https://www.php.net/manual/en/php-user-filter.onclose.php) — Called when closing the filter
  - [php\_user\_filter::onCreate](https://www.php.net/manual/en/php-user-filter.oncreate.php) — Called when creating the filter
- [streamWrapper](https://www.php.net/manual/en/class.streamwrapper.php) — The streamWrapper class
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
- [Stream Functions](https://www.php.net/manual/en/ref.stream.php)
  - [stream\_bucket\_append](https://www.php.net/manual/en/function.stream-bucket-append.php) — Append bucket to brigade
  - [stream\_bucket\_make\_writeable](https://www.php.net/manual/en/function.stream-bucket-make-writeable.php) — Returns a bucket object from the brigade to operate on
  - [stream\_bucket\_new](https://www.php.net/manual/en/function.stream-bucket-new.php) — Create a new bucket for use on the current stream
  - [stream\_bucket\_prepend](https://www.php.net/manual/en/function.stream-bucket-prepend.php) — Prepend bucket to brigade
  - [stream\_context\_create](https://www.php.net/manual/en/function.stream-context-create.php) — Creates a stream context
  - [stream\_context\_get\_default](https://www.php.net/manual/en/function.stream-context-get-default.php) — Retrieve the default stream context
  - [stream\_context\_get\_options](https://www.php.net/manual/en/function.stream-context-get-options.php) — Retrieve options for a stream/wrapper/context
  - [stream\_context\_get\_params](https://www.php.net/manual/en/function.stream-context-get-params.php) — Retrieves parameters from a context
  - [stream\_context\_set\_default](https://www.php.net/manual/en/function.stream-context-set-default.php) — Set the default stream context
  - [stream\_context\_set\_option](https://www.php.net/manual/en/function.stream-context-set-option.php) — Sets an option for a stream/wrapper/context
  - [stream\_context\_set\_options](https://www.php.net/manual/en/function.stream-context-set-options.php) — Sets options on the specified context
  - [stream\_context\_set\_params](https://www.php.net/manual/en/function.stream-context-set-params.php) — Set parameters for a stream/wrapper/context
  - [stream\_copy\_to\_stream](https://www.php.net/manual/en/function.stream-copy-to-stream.php) — Copies data from one stream to another
  - [stream\_filter\_append](https://www.php.net/manual/en/function.stream-filter-append.php) — Attach a filter to a stream
  - [stream\_filter\_prepend](https://www.php.net/manual/en/function.stream-filter-prepend.php) — Attach a filter to a stream
  - [stream\_filter\_register](https://www.php.net/manual/en/function.stream-filter-register.php) — Register a user defined stream filter
  - [stream\_filter\_remove](https://www.php.net/manual/en/function.stream-filter-remove.php) — Remove a filter from a stream
  - [stream\_get\_contents](https://www.php.net/manual/en/function.stream-get-contents.php) — Reads remainder of a stream into a string
  - [stream\_get\_filters](https://www.php.net/manual/en/function.stream-get-filters.php) — Retrieve list of registered filters
  - [stream\_get\_line](https://www.php.net/manual/en/function.stream-get-line.php) — Gets line from stream resource up to a given delimiter
  - [stream\_get\_meta\_data](https://www.php.net/manual/en/function.stream-get-meta-data.php) — Retrieves header/meta data from streams/file pointers
  - [stream\_get\_transports](https://www.php.net/manual/en/function.stream-get-transports.php) — Retrieve list of registered socket transports
  - [stream\_get\_wrappers](https://www.php.net/manual/en/function.stream-get-wrappers.php) — Retrieve list of registered streams
  - [stream\_is\_local](https://www.php.net/manual/en/function.stream-is-local.php) — Checks if a stream is a local stream
  - [stream\_isatty](https://www.php.net/manual/en/function.stream-isatty.php) — Check if a stream is a TTY
  - [stream\_notification\_callback](https://www.php.net/manual/en/function.stream-notification-callback.php) — A callback function for the notification context parameter
  - [stream\_register\_wrapper](https://www.php.net/manual/en/function.stream-register-wrapper.php) — Alias of stream\_wrapper\_register
  - [stream\_resolve\_include\_path](https://www.php.net/manual/en/function.stream-resolve-include-path.php) — Resolve filename against the include path
  - [stream\_select](https://www.php.net/manual/en/function.stream-select.php) — Runs the equivalent of the select() system call on the given
     arrays of streams with a timeout specified by seconds and microseconds
  - [stream\_set\_blocking](https://www.php.net/manual/en/function.stream-set-blocking.php) — Set blocking/non-blocking mode on a stream
  - [stream\_set\_chunk\_size](https://www.php.net/manual/en/function.stream-set-chunk-size.php) — Set the stream chunk size
  - [stream\_set\_read\_buffer](https://www.php.net/manual/en/function.stream-set-read-buffer.php) — Set read file buffering on the given stream
  - [stream\_set\_timeout](https://www.php.net/manual/en/function.stream-set-timeout.php) — Set timeout period on a stream
  - [stream\_set\_write\_buffer](https://www.php.net/manual/en/function.stream-set-write-buffer.php) — Sets write file buffering on the given stream
  - [stream\_socket\_accept](https://www.php.net/manual/en/function.stream-socket-accept.php) — Accept a connection on a socket created by stream\_socket\_server
  - [stream\_socket\_client](https://www.php.net/manual/en/function.stream-socket-client.php) — Open Internet or Unix domain socket connection
  - [stream\_socket\_enable\_crypto](https://www.php.net/manual/en/function.stream-socket-enable-crypto.php) — Turns encryption on/off on an already connected socket
  - [stream\_socket\_get\_name](https://www.php.net/manual/en/function.stream-socket-get-name.php) — Retrieve the name of the local or remote sockets
  - [stream\_socket\_pair](https://www.php.net/manual/en/function.stream-socket-pair.php) — Creates a pair of connected, indistinguishable socket streams
  - [stream\_socket\_recvfrom](https://www.php.net/manual/en/function.stream-socket-recvfrom.php) — Receives data from a socket, connected or not
  - [stream\_socket\_sendto](https://www.php.net/manual/en/function.stream-socket-sendto.php) — Sends a message to a socket, whether it is connected or not
  - [stream\_socket\_server](https://www.php.net/manual/en/function.stream-socket-server.php) — Create an Internet or Unix domain server socket
  - [stream\_socket\_shutdown](https://www.php.net/manual/en/function.stream-socket-shutdown.php) — Shutdown a full-duplex connection
  - [stream\_supports\_lock](https://www.php.net/manual/en/function.stream-supports-lock.php) — Tells whether the stream supports locking
  - [stream\_wrapper\_register](https://www.php.net/manual/en/function.stream-wrapper-register.php) — Register a URL wrapper implemented as a PHP class
  - [stream\_wrapper\_restore](https://www.php.net/manual/en/function.stream-wrapper-restore.php) — Restores a previously unregistered built-in wrapper
  - [stream\_wrapper\_unregister](https://www.php.net/manual/en/function.stream-wrapper-unregister.php) — Unregister a URL wrapper

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/stream/book.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fbook.stream%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=book.stream&repo=en&redirect=https://www.php.net/manual/en/book.stream.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google