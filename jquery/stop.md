---
url: https://api.jquery.com/stop/
scraped_at: 2025-10-20T03:08:35.836Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .stop( \[clearQueue \] \[, jumpToEnd \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Stop the currently-running animation on the matched elements.

- #### version added: [1.2](https://api.jquery.com/category/version/1.2/) [.stop( \[clearQueue \] \[, jumpToEnd \] )](https://api.jquery.com/stop/\#stop-clearQueue-jumpToEnd)

  - **clearQueue** (default: `false`)

    Type: [Boolean](http://api.jquery.com/Types/#Boolean)

    A Boolean indicating whether to remove queued animation as well. Defaults to `false`.

  - **jumpToEnd** (default: `false`)

    Type: [Boolean](http://api.jquery.com/Types/#Boolean)

    A Boolean indicating whether to complete the current animation immediately. Defaults to `false`.
- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.stop( \[queue \] \[, clearQueue \] \[, jumpToEnd \] )](https://api.jquery.com/stop/\#stop-queue-clearQueue-jumpToEnd)

  - **queue**

    Type: [String](http://api.jquery.com/Types/#String)

    The name of the queue in which to stop animations.

  - **clearQueue** (default: `false`)

    Type: [Boolean](http://api.jquery.com/Types/#Boolean)

    A Boolean indicating whether to remove queued animation as well. Defaults to `false`.

  - **jumpToEnd** (default: `false`)

    Type: [Boolean](http://api.jquery.com/Types/#Boolean)

    A Boolean indicating whether to complete the current animation immediately. Defaults to `false`.

When `.stop()` is called on an element, the currently-running animation (if any) is immediately stopped. If, for instance, an element is being hidden with `.slideUp()` when `.stop()` is called, the element will now still be displayed, but will be a fraction of its previous height. Callback functions are not called.

If more than one animation method is called on the same element, the later animations are placed in the effects queue for the element. These animations will not begin until the first one completes. When `.stop()` is called, the next animation in the queue begins immediately. If the `clearQueue` parameter is provided with a value of `true`, then the rest of the animations in the queue are removed and never run.

If the `jumpToEnd` argument is provided with a value of `true`, the current animation stops, but the element is immediately given its target values for each CSS property. In our above `.slideUp()` example, the element would be immediately hidden. The callback function is then immediately called, if provided.

**As of jQuery 1.7**, if the first argument is provided as a string, only the animations in the queue represented by that string will be stopped.

The usefulness of the `.stop()` method is evident when we need to animate an element on `mouseenter` and `mouseleave`:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

We can create a nice fade effect without the common problem of multiple queued animations by adding `.stop(true, true)` to the chain:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

## Toggling Animations

**As of jQuery 1.7,** stopping a toggled animation prematurely with `.stop()` will trigger jQuery's internal effects tracking. In previous versions, calling the `.stop()` method before a toggled animation was completed would cause the animation to lose track of its state (if jumpToEnd was false). Any subsequent animations would start at a new "half-way" state, sometimes resulting in the element disappearing. To observe the new behavior, see the final example below.

Animations may be stopped globally by setting the property `$.fx.off` to `true`. When this is done, all animation methods will immediately set elements to their final state when called, rather than displaying an effect.

### Example 1

Click the Go button once to start the animation, then click the STOP button to stop it where it's currently positioned. Another option is to click several buttons to queue them up and see that stop just kills the currently playing one.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44 | ```<br>``` |

#### Demo:

### Example 2

Click the slideToggle button to start the animation, then click again before the animation is completed. The animation will toggle the other direction from the saved starting point.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32 | ```<br>``` |

#### Demo: