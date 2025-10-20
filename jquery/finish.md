---
url: https://api.jquery.com/finish/
scraped_at: 2025-10-20T03:08:03.525Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .finish( \[queue \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Stop the currently-running animation, remove all queued animations, and complete all animations for the matched elements.

- #### version added: [1.9](https://api.jquery.com/category/version/1.9/) [.finish( \[queue \] )](https://api.jquery.com/finish/\#finish-queue)

  - **queue** (default: `'fx'`)

    Type: [String](http://api.jquery.com/Types/#String)

    The name of the queue in which to stop animations.

When `.finish()` is called on an element, the currently-running animation and all queued animations (if any) immediately stop and their CSS properties set to their target values. All queued animations are removed.

If the first argument is provided, only the animations in the queue represented by that string will be stopped.

The `.finish()` method is similar to `.stop(true, true)` in that it clears the queue and the current animation jumps to its end value. It differs, however, in that `.finish()` also causes the CSS property of all _queued_ animations to jump to their end values, as well.

Animations may be stopped globally by setting the property `$.fx.off` to `true`. When this is done, all animation methods will immediately set elements to their final state when called, rather than displaying an effect.

Click the Go button once to start the animation, and then click the other buttons to see how they affect the current and queued animations.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55<br>56<br>57<br>58<br>59<br>60<br>61<br>62<br>63<br>64<br>65<br>66<br>67<br>68<br>69<br>70<br>71<br>72<br>73<br>74<br>75<br>76<br>77<br>78<br>79<br>80<br>81<br>82<br>83<br>84<br>85<br>86<br>87<br>88<br>89<br>90<br>91<br>92<br>93<br>94<br>95<br>96<br>97<br>98<br>99<br>100<br>101<br>102<br>103<br>104<br>105<br>106<br>107 | ```<br>``` |

#### Demo: