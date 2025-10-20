---
url: https://api.jquery.com/jquery.fx.off/
scraped_at: 2025-10-20T03:24:44.418Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.fx.offReturns: [Boolean](http://api.jquery.com/Types/\#Boolean)

**Description:** Globally disable all animations.

- #### version added: [1.3](https://api.jquery.com/category/version/1.3/)jQuery.fx.off


When this property is set to `true`, all animation methods will immediately set elements to their final state when called, rather than displaying an effect. This may be desirable for a couple reasons:

- jQuery is being used on a low-resource device.
- Users are encountering accessibility problems with the animations.

Animations can be turned back on by setting the property to `false`.

Toggle animation on and off

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35 | ```<br>``` |

#### Demo: