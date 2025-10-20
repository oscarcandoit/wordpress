---
url: https://api.jquery.com/jQuery.Deferred/
scraped_at: 2025-10-20T03:05:42.626Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.Deferred( \[beforeStart \] )Returns: [Deferred](http://api.jquery.com/Types/\#Deferred)

**Description:** A factory function that returns a chainable utility object with methods to register multiple callbacks into callback queues, invoke callback queues, and relay the success or failure state of any synchronous or asynchronous function.

- #### version added: [1.5](https://api.jquery.com/category/version/1.5/) [jQuery.Deferred( \[beforeStart \] )](https://api.jquery.com/jQuery.Deferred/\#jQuery-Deferred-beforeStart)

  - **beforeStart**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Deferred](http://api.jquery.com/Types/#Deferred) deferred )


     A function that is called just before the constructor returns.

The `jQuery.Deferred()` factory creates a new `deferred` object.

The `jQuery.Deferred` method can be passed an optional function, which is called just before the method returns and is passed the new `deferred` object as both the `this` object and as the first argument to the function. The called function can attach callbacks using [`deferred.then()`](https://api.jquery.com/deferred.then/), for example.

A Deferred object starts in the _pending_ state. Any callbacks added to the object with [`deferred.then()`](https://api.jquery.com/deferred.then/), [`deferred.always()`](https://api.jquery.com/deferred.always/), [`deferred.done()`](https://api.jquery.com/deferred.done/), or [`deferred.fail()`](https://api.jquery.com/deferred.fail/) are queued to be executed later. Calling [`deferred.resolve()`](https://api.jquery.com/deferred.resolve/) or [`deferred.resolveWith()`](https://api.jquery.com/deferred.resolveWith/) transitions the Deferred into the _resolved_ state and immediately executes any `doneCallbacks` that are set. Calling [`deferred.reject()`](https://api.jquery.com/deferred.reject/) or [`deferred.rejectWith()`](https://api.jquery.com/deferred.rejectWith/) transitions the Deferred into the _rejected_ state and immediately executes any `failCallbacks` that are set. Once the object has entered the resolved or rejected state, it stays in that state. Callbacks can still be added to the resolved or rejected Deferred — they will execute immediately.

#### Enhanced Callbacks with jQuery Deferred

In JavaScript it is common to invoke functions that optionally accept callbacks that are called within that function. For example, in versions prior to jQuery 1.5, asynchronous processes such as `jQuery.ajax()` accept callbacks to be invoked some time in the near-future upon success, error, and completion of the ajax request.

`jQuery.Deferred()` introduces several enhancements to the way callbacks are managed and invoked. In particular, `jQuery.Deferred()` provides flexible ways to provide multiple callbacks, and these callbacks can be invoked regardless of whether the original callback dispatch has already occurred. jQuery Deferred is based on the [CommonJS Promises/A](http://wiki.commonjs.org/wiki/Promises/A) design.

One model for understanding Deferred is to think of it as a chain-aware function wrapper. The [`deferred.then()`](https://api.jquery.com/deferred.then/), [`deferred.always()`](https://api.jquery.com/deferred.always/), [`deferred.done()`](https://api.jquery.com/deferred.done/), and [`deferred.fail()`](https://api.jquery.com/deferred.fail/) methods specify the functions to be called and the [`deferred.resolve(args)`](https://api.jquery.com/deferred.resolve/) or [`deferred.reject(args)`](https://api.jquery.com/deferred.reject/) methods "call" the functions with the arguments you supply. Once the Deferred has been resolved or rejected it stays in that state; a second call to `deferred.resolve()`, for example, is ignored. If more functions are added by `deferred.then()`, for example, after the Deferred is resolved, they are called immediately with the arguments previously provided.

In most cases where a jQuery API call returns a Deferred or Promise-compatible object, such as [`jQuery.ajax()`](https://api.jquery.com/jQuery.ajax/) or [`jQuery.when()`](https://api.jquery.com/jQuery.when/), you will only want to use the [`deferred.then()`](https://api.jquery.com/deferred.then/), [`deferred.done()`](https://api.jquery.com/deferred.done/), and [`deferred.fail()`](https://api.jquery.com/deferred.fail/) methods to add callbacks to the Deferred's queues. The internals of the API call or code that created the Deferred will invoke [`deferred.resolve()`](https://api.jquery.com/deferred.resolve/) or [`deferred.reject()`](https://api.jquery.com/deferred.reject/) on the deferred at some point, causing the appropriate callbacks to run.