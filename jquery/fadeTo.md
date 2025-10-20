---
url: https://api.jquery.com/fadeTo/
scraped_at: 2025-10-20T03:07:55.428Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .fadeTo( duration, opacity \[, complete \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Adjust the opacity of the matched elements.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.fadeTo( duration, opacity \[, complete \] )](https://api.jquery.com/fadeTo/\#fadeTo-duration-opacity-complete)

  - **duration**

    Type: [String](http://api.jquery.com/Types/#String) or [Number](http://api.jquery.com/Types/#Number)

    A string or number determining how long the animation will run.

  - **opacity**

    Type: [Number](http://api.jquery.com/Types/#Number)

    A number between 0 and 1 denoting the target opacity.

  - **complete**

    Type: [Function](http://api.jquery.com/Types/#Function)()

    A function to call once the animation is complete.
- #### version added: [1.4.3](https://api.jquery.com/category/version/1.4.3/) [.fadeTo( duration, opacity \[, easing \] \[, complete \] )](https://api.jquery.com/fadeTo/\#fadeTo-duration-opacity-easing-complete)

  - **duration**

    Type: [String](http://api.jquery.com/Types/#String) or [Number](http://api.jquery.com/Types/#Number)

    A string or number determining how long the animation will run.

  - **opacity**

    Type: [Number](http://api.jquery.com/Types/#Number)

    A number between 0 and 1 denoting the target opacity.

  - **easing**

    Type: [String](http://api.jquery.com/Types/#String)

    A string indicating which easing function to use for the transition.

  - **complete**

    Type: [Function](http://api.jquery.com/Types/#Function)()

    A function to call once the animation is complete.

The `.fadeTo()` method animates the opacity of the matched elements. It is similar to the `[.fadeIn()](https://api.jquery.com/fadeIn/)` method but that method unhides the element and always fades to 100% opacity.

Durations are given in milliseconds; higher values indicate slower animations, not faster ones. The strings `'fast'` and `'slow'` can be supplied to indicate durations of `200` and `600` milliseconds, respectively. If any other string is supplied, the default duration of `400` milliseconds is used. Unlike the other effect methods, `.fadeTo()` requires that `duration` be explicitly specified.

If supplied, the callback is fired once the animation is complete. This can be useful for stringing different animations together in sequence. The callback is not sent any arguments, but `this` is set to the DOM element being animated. If multiple elements are animated, it is important to note that the callback is executed once per matched element, not once for the animation as a whole.

We can animate any element, such as a simple image:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10 | ```<br>``` |

![](https://api.jquery.com/resources/0042_06_41.png)![](https://api.jquery.com/resources/0042_06_42.png)![](https://api.jquery.com/resources/0042_06_43.png)![](https://api.jquery.com/resources/0042_06_44.png)Figure 1 - Illustration of the `fadeTo()` effect

With `duration` set to `0`, this method just changes the `opacity` CSS property, so `.fadeTo( 0, opacity )` is the same as `.css( "opacity", opacity )`.

### Additional Notes:

- All jQuery effects, including `.fadeTo()`, can be turned off globally by setting `jQuery.fx.off = true`, which effectively sets the duration to 0. For more information, see [jQuery.fx.off](https://api.jquery.com/jquery.fx.off/).


### Example 1

Animates first paragraph to fade to an opacity of 0.33 (33%, about one third visible), completing the animation within 600 milliseconds.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25 | ```<br>``` |

#### Demo:

### Example 2

Fade div to a random opacity on each click, completing the animation within 200 milliseconds.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50 | ```<br>``` |

#### Demo:

### Example 3

Find the right answer! The fade will take 250 milliseconds and change various styles when it completes.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55<br>56<br>57<br>58<br>59<br>60<br>61<br>62<br>63<br>64 | ```<br>``` |

#### Demo: