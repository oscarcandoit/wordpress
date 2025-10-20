---
url: https://api.jquery.com/hide/
scraped_at: 2025-10-20T03:08:07.263Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .hide()Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Hide the matched elements.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.hide()](https://api.jquery.com/hide/\#hide)

  - This signature does not accept any arguments.
- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.hide( \[duration \] \[, complete \] )](https://api.jquery.com/hide/\#hide-duration-complete)

  - **duration** (default: `400`)

    Type: [Number](http://api.jquery.com/Types/#Number) or [String](http://api.jquery.com/Types/#String)

    A string or number determining how long the animation will run.

  - **complete**

    Type: [Function](http://api.jquery.com/Types/#Function)()

    A function to call once the animation is complete, called once per matched element.
- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.hide( options )](https://api.jquery.com/hide/\#hide-options)

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
- #### version added: [1.4.3](https://api.jquery.com/category/version/1.4.3/) [.hide( duration \[, easing \] \[, complete \] )](https://api.jquery.com/hide/\#hide-duration-easing-complete)

  - **duration** (default: `400`)

    Type: [Number](http://api.jquery.com/Types/#Number) or [String](http://api.jquery.com/Types/#String)

    A string or number determining how long the animation will run.

  - **easing** (default: `swing`)

    Type: [String](http://api.jquery.com/Types/#String)

    A string indicating which easing function to use for the transition.

  - **complete**

    Type: [Function](http://api.jquery.com/Types/#Function)()

    A function to call once the animation is complete, called once per matched element.

With no parameters, the `.hide()` method is the simplest way to hide an element:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

The matched elements will be hidden immediately, with no animation. This is roughly equivalent to calling `.css( "display", "none" )`, except that the value of the `display` property is saved in jQuery's data cache so that `display` can later be restored to its initial value. If an element has a `display` value of `inline` and is hidden then shown, it will once again be displayed `inline`.

When a duration, a plain object, or a "complete" function is provided, `.hide()` becomes an animation method. The `.hide()` method animates the width, height, and opacity of the matched elements simultaneously. When these properties reach 0, the `display` style property is set to `none` to ensure that the element no longer affects the layout of the page.

Durations are given in milliseconds; higher values indicate slower animations, not faster ones. The strings `'fast'` and `'slow'` can be supplied to indicate durations of `200` and `600` milliseconds, respectively.

Note that `.hide()` is fired immediately and will override the animation queue if no duration or a duration of 0 is specified.

As of jQuery **1.4.3**, an optional string naming an easing function may be used. Easing functions specify the speed at which the animation progresses at different points within the animation. The only easing implementations in the jQuery library are the default, called `swing`, and one that progresses at a constant pace, called `linear`. More easing functions are available with the use of plug-ins, most notably the [jQuery UI suite](https://jqueryui.com/).

If supplied, the callback is fired once the animation is complete. This can be useful for stringing different animations together in sequence. The callback is not sent any arguments, but `this` is set to the DOM element being animated. If multiple elements are animated, it is important to note that the callback is executed once per matched element, not once for the animation as a whole.

**Note:** This method may cause performance issues, especially when used on many elements. If you're encountering such issues, use performance testing tools to determine whether this method is causing them. Moreover, this method can cause problems with responsive layouts if the display value differs at different viewport sizes.

We can animate any element, such as a simple image:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |

![](https://api.jquery.com/resources/0042_06_05.png)![](https://api.jquery.com/resources/0042_06_06.png)![](https://api.jquery.com/resources/0042_06_07.png)![](https://api.jquery.com/resources/0042_06_08.png)Figure 1 - Illustration of the `hide()` effect

### Additional Notes:

- All jQuery effects, including `.hide()`, can be turned off globally by setting `jQuery.fx.off = true`, which effectively sets the duration to 0. For more information, see [jQuery.fx.off](https://api.jquery.com/jquery.fx.off/).


### Example 1

Hides all paragraphs then the link on click.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23 | ```<br>``` |

#### Demo:

### Example 2

Animates all shown paragraphs to hide slowly, completing the animation within 600 milliseconds.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27 | ```<br>``` |

#### Demo:

### Example 3

Animates all spans (words in this case) to hide fastly, completing each animation within 200 milliseconds. Once each animation is done, it starts the next one.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38 | ```<br>``` |

#### Demo:

### Example 4

Hides the divs when clicked over 2 seconds, then removes the div element when its hidden. Try clicking on more than one box at a time.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33 | ```<br>``` |

#### Demo: