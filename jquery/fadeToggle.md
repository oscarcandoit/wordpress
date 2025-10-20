---
url: https://api.jquery.com/fadeToggle/
scraped_at: 2025-10-20T03:07:59.841Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .fadeToggle( \[duration \] \[, easing \] \[, complete \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Display or hide the matched elements by animating their opacity.

- #### version added: [1.4.4](https://api.jquery.com/category/version/1.4.4/) [.fadeToggle( \[duration \] \[, easing \] \[, complete \] )](https://api.jquery.com/fadeToggle/\#fadeToggle-duration-easing-complete)

  - **duration** (default: `400`)

    Type: [Number](http://api.jquery.com/Types/#Number) or [String](http://api.jquery.com/Types/#String)

    A string or number determining how long the animation will run.

  - **easing** (default: `swing`)

    Type: [String](http://api.jquery.com/Types/#String)

    A string indicating which easing function to use for the transition.

  - **complete**

    Type: [Function](http://api.jquery.com/Types/#Function)()

    A function to call once the animation is complete, called once per matched element.
- #### version added: [1.4.4](https://api.jquery.com/category/version/1.4.4/) [.fadeToggle( options )](https://api.jquery.com/fadeToggle/\#fadeToggle-options)

  - **options**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject)

    A map of additional options to pass to the method.
    - **duration** (default: `400`)

      Type: [Number](http://api.jquery.com/Types/#Number) or [String](http://api.jquery.com/Types/#String)

      A string or number determining how long the animation will run.

    - **easing** (default: `swing`)

      Type: [String](http://api.jquery.com/Types/#String)

      A string indicating which easing function to use for the transition.

    - **queue** (default: `true`)

      Type: [Boolean](http://api.jquery.com/Types/#Boolean) or [String](http://api.jquery.com/Types/#String)

      A Boolean indicating whether to place the animation in the effects queue. If false, the animation will begin immediately. **As of jQuery 1.7**, the queue option can also accept a string, in which case the animation is added to the queue represented by that string. When a custom queue name is used the animation does not automatically start; you must call `.dequeue("queuename")` to start it.

    - **specialEasing**

      Type: [PlainObject](http://api.jquery.com/Types/#PlainObject)

      An object containing one or more of the CSS properties defined by the properties argument and their corresponding easing functions. (version added: [1.4](https://api.jquery.com/category/version/1.4/))

    - **step**

      Type: [Function](http://api.jquery.com/Types/#Function)( [Number](http://api.jquery.com/Types/#Number) now, [Tween](http://api.jquery.com/Types/#Tween) tween )

      A function to be called for each animated property of each animated element. This function provides an opportunity to modify the Tween object to change the value of the property before it is set.

    - **progress**

      Type: [Function](http://api.jquery.com/Types/#Function)( [Promise](http://api.jquery.com/Types/#Promise) animation, [Number](http://api.jquery.com/Types/#Number) progress, [Number](http://api.jquery.com/Types/#Number) remainingMs )

      A function to be called after each step of the animation, only once per animated element regardless of the number of animated properties. (version added: [1.8](https://api.jquery.com/category/version/1.8/))

    - **complete**

      Type: [Function](http://api.jquery.com/Types/#Function)()

      A function that is called once the animation on an element is complete.

    - **start**

      Type: [Function](http://api.jquery.com/Types/#Function)( [Promise](http://api.jquery.com/Types/#Promise) animation )

      A function to call when the animation on an element begins. (version added: [1.8](https://api.jquery.com/category/version/1.8/))

    - **done**

      Type: [Function](http://api.jquery.com/Types/#Function)( [Promise](http://api.jquery.com/Types/#Promise) animation, [Boolean](http://api.jquery.com/Types/#Boolean) jumpedToEnd )

      A function to be called when the animation on an element completes (its Promise object is resolved). (version added: [1.8](https://api.jquery.com/category/version/1.8/))

    - **fail**

      Type: [Function](http://api.jquery.com/Types/#Function)( [Promise](http://api.jquery.com/Types/#Promise) animation, [Boolean](http://api.jquery.com/Types/#Boolean) jumpedToEnd )

      A function to be called when the animation on an element fails to complete (its Promise object is rejected). (version added: [1.8](https://api.jquery.com/category/version/1.8/))

    - **always**

      Type: [Function](http://api.jquery.com/Types/#Function)( [Promise](http://api.jquery.com/Types/#Promise) animation, [Boolean](http://api.jquery.com/Types/#Boolean) jumpedToEnd )

      A function to be called when the animation on an element completes or stops without completing (its Promise object is either resolved or rejected). (version added: [1.8](https://api.jquery.com/category/version/1.8/))

The `.fadeToggle()` method animates the opacity of the matched elements. When called on a visible element, the element's `display` style property is set to `none` once the opacity reaches 0, so the element no longer affects the layout of the page.

Durations are given in milliseconds; higher values indicate slower animations, not faster ones. The strings `'fast'` and `'slow'` can be supplied to indicate durations of `200` and `600` milliseconds, respectively.

#### Easing

The string representing an easing function specifies the speed at which the animation progresses at different points within the animation. The only easing implementations in the jQuery library are the default, called `swing`, and one that progresses at a constant pace, called `linear`. More easing functions are available with the use of plug-ins, most notably the [jQuery UI suite](https://jqueryui.com/).

#### Callback Function

If supplied, the callback is fired once the animation is complete. This can be useful for stringing different animations together in sequence. The callback is not sent any arguments, but `this` is set to the DOM element being animated. If multiple elements are animated, it is important to note that the callback is executed once per matched element, not once for the animation as a whole.

**As of jQuery 1.6**, the `[.promise()](https://api.jquery.com/promise/)` method can be used in conjunction with the `[deferred.done()](https://api.jquery.com/deferred.done/)` method to execute a single callback for the animation as a whole when _all_ matching elements have completed their animations ( See the [example for .promise()](https://api.jquery.com/promise/#example-1) ).

### Additional Notes:

- All jQuery effects, including `.fadeToggle()`, can be turned off globally by setting `jQuery.fx.off = true`, which effectively sets the duration to 0. For more information, see [jQuery.fx.off](https://api.jquery.com/jquery.fx.off/).


Fades first paragraph in or out, completing the animation within 600 milliseconds and using a linear easing. Fades last paragraph in or out for 200 milliseconds, inserting a "finished" message upon completion.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28 | ```<br>``` |

#### Demo: