---
url: https://api.jquery.com/jQuery.holdReady/
scraped_at: 2025-10-20T03:18:41.465Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.holdReady( hold )Returns: [undefined](http://api.jquery.com/Types/\#undefined)version deprecated: [3.2](https://api.jquery.com/category/version/3.2/)

**Description:** Holds or releases the execution of jQuery's ready event.

- #### version added: [1.6](https://api.jquery.com/category/version/1.6/) [jQuery.holdReady( hold )](https://api.jquery.com/jQuery.holdReady/\#jQuery-holdReady-hold)

  - **hold**

    Type: [Boolean](http://api.jquery.com/Types/#Boolean)

    Indicates whether the ready hold is being requested or released

Note: This API has been deprecated in jQuery 3.2. Instead of relying on this global switch, it's better to put explicitly wait for required code. If you need to wait both for the ready state & for a custom promise, use the following pattern:

`$.when( $.ready, customPromise )
.then( function() {
    // main code
} )
.catch( function( error ) {
    // handle errors
} )`

The `$.holdReady()` method allows the caller to delay jQuery's ready event. This _advanced feature_ would typically be used by dynamic script loaders that want to load additional JavaScript such as jQuery plugins before allowing the ready event to occur, even though the DOM may be ready. This method must be called early in the document, such as in the `<head>` immediately after the jQuery script tag. Calling this method after the ready event has already fired will have no effect.

To delay the ready event, first call `$.holdReady( true )`. When the ready event should be released to execute, call `$.holdReady( false )`. Note that multiple holds can be put on the ready event, one for each `$.holdReady( true )` call. The ready event will not actually fire until all holds have been released with a corresponding number of `$.holdReady( false )` calls _and_ the normal document ready conditions are met. (See [`ready`](https://api.jquery.com/ready/) for more information.)

Delay the ready event until a custom plugin has loaded.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |