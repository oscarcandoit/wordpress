---
url: https://api.jquery.com/jQuery.sub/
scraped_at: 2025-10-20T03:18:31.631Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.sub()Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)version deprecated: [1.7](https://api.jquery.com/category/version/1.7/), removed: [1.9](https://api.jquery.com/category/version/1.9/)

**Description:** Creates a new copy of jQuery whose properties and methods can be modified without affecting the original jQuery object.

- #### version added: [1.5](https://api.jquery.com/category/version/1.5/) [jQuery.sub()](https://api.jquery.com/jQuery.sub/\#jQuery-sub)

  - This method does not accept any arguments.

Note: This API has been removed in jQuery 1.9.

There are two specific use cases for which jQuery.sub() was created. The first was for providing a painless way of overriding jQuery methods without completely destroying the original methods and another was for helping to do encapsulation and basic namespacing for jQuery plugins.

Note that jQuery.sub() doesn't attempt to do any sort of isolation - that's not its intention. All the methods on the sub'd version of jQuery will still point to the original jQuery (events bound and triggered will still be through the main jQuery, data will be bound to elements through the main jQuery, Ajax queries and events will run through the main jQuery, etc.).

Note that if you're looking to use this for plugin development you should first _strongly_ consider using something like the jQuery UI widget factory which manages both state and plugin sub-methods. [Some examples of using the jQuery UI widget factory](http://blog.nemikor.com/2010/05/15/building-stateful-jquery-plugins/) to build a plugin.

The particular use cases of this method can be best described through some examples.

### Example 1

Adding a method to a jQuery sub so that it isn't exposed externally:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12 | ```<br>``` |

### Example 2

Override some jQuery methods to provide new functionality.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26 | ```<br>``` |

### Example 3

Create a plugin that returns plugin-specific methods.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31 | ```<br>``` |