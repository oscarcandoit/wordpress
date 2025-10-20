---
url: https://api.jquery.com/jQuery.cssHooks/
scraped_at: 2025-10-20T03:03:08.714Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.cssHooksReturns: [Object](http://api.jquery.com/Types/\#Object)

**Description:** Hook directly into jQuery to override how particular CSS properties are retrieved or set, normalize CSS property naming, or create custom properties.

- #### version added: [1.4.3](https://api.jquery.com/category/version/1.4.3/)jQuery.cssHooks


The `$.cssHooks` object provides a way to define functions for getting and setting particular CSS values. It can also be used to create new cssHooks for normalizing CSS3 features such as box shadows and gradients.

For example, some versions of Webkit-based browsers require `-webkit-border-radius` to set the `border-radius` on an element, while earlier Firefox versions require `-moz-border-radius`. A css hook can normalize these vendor-prefixed properties to let `.css()` accept a single, standard property name ( `border-radius`, or with DOM property syntax, `borderRadius`).

In addition to providing fine-grained control over how specific style properties are handled, `$.cssHooks` also extends the set of properties available to the `.animate()` method.

Defining a new css hook is straight-forward. The skeleton template below can serve as a guide to creating your own.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23 | ```<br>``` |

#### Feature Testing

Before normalizing a vendor-specific CSS property, first determine whether the browser supports the standard property or a vendor-prefixed variation. For example, to check for support of the `border-radius` property, see if any variation is a member of a temporary element's `style` object.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38 | ```<br>``` |

#### Defining a complete css hook

To define a complete css hook, combine the support test with a filled-out version of the skeleton template provided in the first example:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44 | ```<br>``` |

You can then set the border radius in a supported browser using either the DOM (camelCased) style or the CSS (hyphenated) style:

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

If the browser lacks support for any form of the CSS property, vendor-prefixed or not, the style is not applied to the element. However, if the browser supports a proprietary alternative, it can be applied to the cssHooks instead.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29 | ```<br>``` |

#### Special units

By default, jQuery adds a "px" unit to the values passed to the `.css()` method. This behavior can be prevented by adding the property to the [`jQuery.cssNumber`](https://api.jquery.com/jQuery.cssNumber/) object

|     |     |
| --- | --- |
| 1 | ```<br>``` |

#### Animating with cssHooks

A css hook can also hook into jQuery's animation mechanism by adding a property to the `jQuery.fx.step` object:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

Note that this works best for simple numeric-value animations. More custom code may be required depending on the CSS property, the type of value it returns, and the animation's complexity.