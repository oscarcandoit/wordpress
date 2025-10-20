---
url: https://api.jquery.com/jquery.fx.interval/
scraped_at: 2025-10-20T03:24:40.336Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.fx.intervalReturns: [Number](http://api.jquery.com/Types/\#Number)version deprecated: [3.0](https://api.jquery.com/category/version/3.0/), removed: [4.0](https://api.jquery.com/category/version/4.0/)

**Description:** The rate (in milliseconds) at which animations fire.

- #### version added: [1.4.3](https://api.jquery.com/category/version/1.4.3/)jQuery.fx.interval


This property is deprecated as of version 3.0, and has no effect in browsers that support the [`requestAnimationFrame`](https://caniuse.com/#feat=requestanimationframe) method.

On browsers that do not support `requestAnimationFrame`, this property can be changed to adjust the interval at which animations will run. The default is 13 milliseconds.

Since jQuery uses one global interval, no animation should be running or all animations should stop for the change of this property to take effect.

Cause all animations to run with less frames.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30 | ```<br>``` |

#### Demo: