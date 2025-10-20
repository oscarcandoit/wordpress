---
url: https://api.jquery.com/jQuery.Callbacks/
scraped_at: 2025-10-20T03:04:48.851Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.Callbacks( flags )Returns: [Callbacks](http://api.jquery.com/Types/\#Callbacks)

**Description:** A multi-purpose callbacks list object that provides a powerful way to manage callback lists.

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [jQuery.Callbacks( flags )](https://api.jquery.com/jQuery.Callbacks/\#jQuery-Callbacks-flags)

  - **flags**

    Type: [String](http://api.jquery.com/Types/#String)

    An optional list of space-separated flags that change how the callback list behaves.

The `$.Callbacks()` function is internally used to provide the base functionality behind the jQuery `$.ajax()` and `$.Deferred()` components. It can be used as a similar base to define functionality for new components.

`$.Callbacks()` supports a number of methods including `[callbacks.add()](https://api.jquery.com/callbacks.add/)`, `[callbacks.remove()](https://api.jquery.com/callbacks.remove/)`, `[callbacks.fire()](https://api.jquery.com/callbacks.fire/)` and `[callbacks.disable()](https://api.jquery.com/callbacks.disable/)`.

### Getting started

The following are two sample methods named `fn1` and `fn2`:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8 | ```<br>``` |

These can be added as callbacks to a `$.Callbacks` list and invoked as follows:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10 | ```<br>``` |

The result of this is that it becomes simple to construct complex lists of callbacks where input values can be passed through to as many functions as needed with ease.

Two specific methods were being used above: `.add()` and `.fire()`. The `.add()` method supports adding new callbacks to the callback list, while the `.fire()` method executes the added functions and provides a way to pass arguments to be processed by the callbacks in the same list.

Another method supported by `$.Callbacks` is `.remove()`, which has the ability to remove a particular callback from the callback list. Here's a practical example of `.remove()` being used:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15 | ```<br>``` |

### Supported Flags

The `flags` argument is an optional argument to `$.Callbacks()`, structured as a list of space-separated strings that change how the callback list behaves (eg. `$.Callbacks( "unique stopOnFalse" )`).

## Possible flags:

- `once`: Ensures the callback list can only be fired once (like a Deferred).
- `memory`: Keeps track of previous values and will call any callback added after the list has been fired right away with the latest "memorized" values (like a Deferred).
- `unique`: Ensures a callback can only be added once (so there are no duplicates in the list).
- `stopOnFalse`: Interrupts callings when a callback returns false.

By default a callback list will act like an event callback list and can be "fired" multiple times.

For examples of how `flags` should ideally be used, see below:

## `$.Callbacks( "once" )`:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12 | ```<br>``` |

## `$.Callbacks( "memory" )`:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16 | ```<br>``` |

## `$.Callbacks( "unique" )`:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16 | ```<br>``` |

## `$.Callbacks( "stopOnFalse" )`:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24 | ```<br>``` |

Because `$.Callbacks()` supports a list of flags rather than just one, setting several flags has a cumulative effect similar to "&&". This means it's possible to combine flags to create callback lists that, say, both are _unique_ and _ensure if list was already fired, adding more callbacks will have it called with the latest fired value_ (i.e. `$.Callbacks("unique memory")`).

## `$.Callbacks( 'unique memory' )`:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31 | ```<br>``` |

Flag combinations with `$.Callbacks()` are internally in jQuery for the `.done()` and `.fail()` functions on a Deferred — both of which use `$.Callbacks('memory once')`.

The methods of `$.Callbacks` can also be detached, should there be a need to define short-hand versions for convenience:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8 | ```<br>``` |

### $.Callbacks, $.Deferred and Pub/Sub

The general idea behind pub/sub (Publish/Subscribe, or, the Observer pattern) is the promotion of loose coupling in applications. Rather than single objects calling on the methods of other objects, an object instead subscribes to a specific task or activity of another object and is notified when it occurs. Observers are also called Subscribers, and we refer to the object being observed as the Publisher (or the subject). Publishers notify subscribers when events occur.

To demonstrate the component-creation capabilities of `$.Callbacks()`, it's possible to implement a Pub/Sub system using only callback lists. Using `$.Callbacks` as a topics queue, a system for publishing and subscribing to topics can be implemented as follows:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19 | ```<br>``` |

This can then be used by parts of your application to publish and subscribe to events of interest quite easily:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20 | ```<br>``` |

While this is useful, the implementation can be taken further. Using `$.Deferreds`, it's possible to ensure publishers only publish notifications for subscribers once particular tasks have been completed (resolved). See the below code sample for some further comments on how this could be used in practice:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20 | ```<br>``` |