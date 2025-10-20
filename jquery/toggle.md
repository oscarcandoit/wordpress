---
url: https://api.jquery.com/toggle/
scraped_at: 2025-10-20T03:08:49.342Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .toggle( \[duration \] \[, complete \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Display or hide the matched elements.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.toggle( \[duration \] \[, complete \] )](https://api.jquery.com/toggle/\#toggle-duration-complete)

  - **duration** (default: `400`)

    Type: [Number](http://api.jquery.com/Types/#Number) or [String](http://api.jquery.com/Types/#String)

    A string or number determining how long the animation will run.

  - **complete**

    Type: [Function](http://api.jquery.com/Types/#Function)()

    A function to call once the animation is complete, called once per matched element.
- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.toggle( options )](https://api.jquery.com/toggle/\#toggle-options)

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
- #### version added: [1.4.3](https://api.jquery.com/category/version/1.4.3/) [.toggle( duration \[, easing \] \[, complete \] )](https://api.jquery.com/toggle/\#toggle-duration-easing-complete)

  - **duration** (default: `400`)

    Type: [Number](http://api.jquery.com/Types/#Number) or [String](http://api.jquery.com/Types/#String)

    A string or number determining how long the animation will run.

  - **easing** (default: `swing`)

    Type: [String](http://api.jquery.com/Types/#String)

    A string indicating which easing function to use for the transition.

  - **complete**

    Type: [Function](http://api.jquery.com/Types/#Function)()

    A function to call once the animation is complete, called once per matched element.
- #### version added: [1.3](https://api.jquery.com/category/version/1.3/) [.toggle( display )](https://api.jquery.com/toggle/\#toggle-display)

  - **display**

    Type: [Boolean](http://api.jquery.com/Types/#Boolean)

    Use `true` to show the element or `false` to hide it.

Note: The event handling suite also has a method named [.toggle()](https://api.jquery.com/toggle-event/). Which one is fired depends on the set of arguments passed.

With no parameters, the `.toggle()` method simply toggles the visibility of elements:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

The matched elements will be revealed or hidden immediately, with no animation, by changing the CSS `display` property. If the element is initially displayed, it will be hidden; if hidden, it will be shown. The `display` property is saved and restored as needed. If an element has a `display` value of `inline`, then is hidden and shown, it will once again be displayed `inline`.

When a duration, a plain object, or a _single_ "complete" function is provided, `.toggle()` becomes an animation method. The `.toggle()` method animates the width, height, and opacity of the matched elements simultaneously. When these properties reach 0 after a hiding animation, the `display` style property is set to `none` to ensure that the element no longer affects the layout of the page.

Durations are given in milliseconds; higher values indicate slower animations, not faster ones. The strings `'fast'` and `'slow'` can be supplied to indicate durations of `200` and `600` milliseconds, respectively.

As of jQuery 1.4.3, an optional string naming an easing function may be used. Easing functions specify the speed at which the animation progresses at different points within the animation. The only easing implementations in the jQuery library are the default, called `swing`, and one that progresses at a constant pace, called `linear`. More easing functions are available with the use of plug-ins, most notably the [jQuery UI suite](https://jqueryui.com/).

If supplied, the callback is fired once the animation is complete. This can be useful for stringing different animations together in sequence. The callback is not sent any arguments, but `this` is set to the DOM element being animated. If multiple elements are animated, it is important to note that the callback is executed once per matched element, not once for the animation as a whole.

We can animate any element, such as a simple image:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

We will cause `.toggle()` to be called when another element is clicked:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

With the element initially shown, we can hide it slowly with the first click:


![](https://api.jquery.com/resources/0042_06_09.png)![](https://api.jquery.com/resources/0042_06_10.png)![](https://api.jquery.com/resources/0042_06_11.png)![](https://api.jquery.com/resources/0042_06_12.png)Figure 1 - Illustration of the `toggle()` effect when hiding the image

A second click will show the element once again:

![](https://api.jquery.com/resources/0042_06_13.png)![](https://api.jquery.com/resources/0042_06_14.png)![](https://api.jquery.com/resources/0042_06_15.png)![](https://api.jquery.com/resources/0042_06_16.png)Figure 2 - Illustration of the `toggle()` effect when showing the image

The second version of the method accepts a Boolean parameter. If this parameter is `true`, then the matched elements are shown; if `false`, the elements are hidden. In essence, the statement:


|     |     |
| --- | --- |
| 1 | ```<br>``` |

is equivalent to:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

### Additional Notes:

- All jQuery effects, including `.toggle()`, can be turned off globally by setting `jQuery.fx.off = true`, which effectively sets the duration to 0. For more information, see [jQuery.fx.off](https://api.jquery.com/jquery.fx.off/).


### Example 1

Toggles all paragraphs.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21 | ```<br>``` |

#### Demo:

### Example 2

Animates all paragraphs to be shown if they are hidden and hidden if they are visible, completing the animation within 600 milliseconds.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28 | ```<br>``` |

#### Demo:

### Example 3

Shows all paragraphs, then hides them all, back and forth.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22 | ```<br>``` |

#### Demo: