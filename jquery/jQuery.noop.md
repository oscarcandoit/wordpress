---
url: https://api.jquery.com/jQuery.noop/
scraped_at: 2025-10-20T03:15:06.115Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.noop()Returns: [undefined](http://api.jquery.com/Types/\#undefined)

**Description:** An empty function.

- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [jQuery.noop()](https://api.jquery.com/jQuery.noop/\#jQuery-noop)

  - This method does not accept any arguments.

You can use this empty function when you wish to pass around a function that will do nothing.

This is useful for plugin authors who offer optional callbacks; in the case that no callback is given, something like `jQuery.noop` could execute.