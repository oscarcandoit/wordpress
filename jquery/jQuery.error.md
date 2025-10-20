---
url: https://api.jquery.com/jQuery.error/
scraped_at: 2025-10-20T03:24:31.075Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.error( message )Returns:

**Description:** Takes a string and throws an exception containing it.

- #### version added: [1.4.1](https://api.jquery.com/category/version/1.4.1/) [jQuery.error( message )](https://api.jquery.com/jQuery.error/\#jQuery-error-message)

  - **message**

    Type: [String](http://api.jquery.com/Types/#String)

    The message to send out.

This method exists primarily for plugin developers who wish to override it and provide a better display (or more information) for the error messages.

If you do override the method, remember to still throw an error at the end to preserve semantics.

Override `jQuery.error` to send it to a logging service, assuming the `sendErrorLog` method is provided by this service.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |