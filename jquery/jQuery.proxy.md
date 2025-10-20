---
url: https://api.jquery.com/jQuery.proxy/
scraped_at: 2025-10-20T03:12:53.499Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.proxy( function, context )Returns: [Function](http://api.jquery.com/Types/\#Function)version deprecated: [3.3](https://api.jquery.com/category/version/3.3/)

**Description:** Takes a function and returns a new one that will always have a particular context.

- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [jQuery.proxy( function, context )](https://api.jquery.com/jQuery.proxy/\#jQuery-proxy-function-context)

  - **function**

    Type: [Function](http://api.jquery.com/Types/#Function)()

    The function whose context will be changed.

  - **context**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject)

    The object to which the context ( `this`) of the function should be set.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [jQuery.proxy( context, name )](https://api.jquery.com/jQuery.proxy/\#jQuery-proxy-context-name)

  - **context**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject)

    The object to which the context of the function should be set.

  - **name**

    Type: [String](http://api.jquery.com/Types/#String)

    The name of the function whose context will be changed (should be a property of the `context` object).
- #### version added: [1.6](https://api.jquery.com/category/version/1.6/) [jQuery.proxy( function, context \[, additionalArguments \] )](https://api.jquery.com/jQuery.proxy/\#jQuery-proxy-function-context-additionalArguments)

  - **function**

    Type: [Function](http://api.jquery.com/Types/#Function)()

    The function whose context will be changed.

  - **context**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject)

    The object to which the context ( `this`) of the function should be set.

  - **additionalArguments**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    Any number of arguments to be passed to the function referenced in the `function` argument.
- #### version added: [1.6](https://api.jquery.com/category/version/1.6/) [jQuery.proxy( context, name \[, additionalArguments \] )](https://api.jquery.com/jQuery.proxy/\#jQuery-proxy-context-name-additionalArguments)

  - **context**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject)

    The object to which the context of the function should be set.

  - **name**

    Type: [String](http://api.jquery.com/Types/#String)

    The name of the function whose context will be changed (should be a property of the `context` object).

  - **additionalArguments**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    Any number of arguments to be passed to the function named in the `name` argument.

Note: This API has been deprecated in jQuery 3.3; please use the native [`Function.prototype.bind`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_objects/Function/bind) method instead.

This method is most useful for attaching event handlers to an element where the context is pointing back to a different object. Additionally, jQuery makes sure that even if you bind the function returned from `jQuery.proxy()` it will still unbind the correct function if passed the original.

Be aware, however, that jQuery's event binding subsystem assigns a unique id to each event handling function in order to track it when it is used to specify the function to be unbound. The function represented by `jQuery.proxy()` is seen as a single function by the event subsystem, even when it is used to bind different contexts. To avoid unbinding the wrong handler, use a unique event namespace for binding and unbinding (e.g., `"click.myproxy1"`) rather than specifying the proxied function during unbinding.

**As of jQuery 1.6**, any number of additional arguments may be supplied to `$.proxy()`, and they will be passed to the function whose context will be changed.

**As of jQuery 1.9**, when the `context` is `null` or `undefined` the proxied function will be called with the same `this` object as the proxy was called with. This allows `$.proxy()` to be used to partially apply the arguments of a function without changing the context.

### Example 1

Change the context of functions bound to a click handler using the "function, context" signature. Unbind the first handler after first click.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55<br>56<br>57 | ```<br>``` |

#### Demo:

### Example 2

Enforce the context of the function using the "context, function name" signature. Unbind the handler after first click.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25 | ```<br>``` |

#### Demo:

### Example 3

Change the context of a function bound to the click handler,


|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55 | ```<br>``` |

#### Demo: