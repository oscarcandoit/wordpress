---
url: https://api.jquery.com/deferred.catch/
scraped_at: 2025-10-20T03:06:08.360Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## deferred.catch( failFilter )Returns: [Promise](http://api.jquery.com/Types/\#Promise)

**Description:** Add handlers to be called when the Deferred object is rejected.

- #### version added: [3.0](https://api.jquery.com/category/version/3.0/) [deferred.catch( failFilter )](https://api.jquery.com/deferred.catch/\#deferred-catch-failFilter)

  - **failFilter**

    Type: [Function](http://api.jquery.com/Types/#Function)()


     A function that is called when the Deferred is rejected.

`deferred.catch( fn )` is an alias to [`deferred.then( null, fn )`](https://api.jquery.com/deferred.then/). Read its page for more information.

Since the [`jQuery.get`](https://api.jquery.com/jQuery.get/) method returns a jqXHR object, which is derived from a Deferred object, we can add rejection handlers using the `.catch` method.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |