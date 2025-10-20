---
url: https://api.jquery.com/children/
scraped_at: 2025-10-20T03:00:43.240Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .children( \[selector \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Get the children of each element in the set of matched elements, optionally filtered by a selector.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.children( \[selector \] )](https://api.jquery.com/children/\#children-selector)

  - **selector**

    Type: [Selector](http://api.jquery.com/Types/#Selector)

    A string containing a selector expression to match elements against.

Given a jQuery object that represents a set of DOM elements, the `.children()` method allows us to search through the children of these elements in the DOM tree and construct a new jQuery object from the matching elements. The `.children()` method differs from `[.find()](https://api.jquery.com/find/)` in that `.children()` only travels a single level down the DOM tree while `.find()` can traverse down multiple levels to select descendant elements (grandchildren, etc.) as well. Note also that like most jQuery methods, `.children()` does not return text nodes; to get _all_ children including text and comment nodes, use `[.contents()](https://api.jquery.com/contents/)`.

The `.children()` method optionally accepts a selector expression of the same type that we can pass to the `$()` function. If the selector is supplied, the elements will be filtered by testing whether they match it.

Consider a page with a basic nested list on it:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17 | ```<br>``` |

If we begin at the level-2 list, we can find its children:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

The result of this call is a red background behind items A, B, and C. Since we do not supply a selector expression, all of the children are part of the returned jQuery object. If we had supplied one, only the matching items among these three would be included.

### Example 1

Find all children of the clicked element.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55<br>56<br>57<br>58<br>59<br>60<br>61<br>62<br>63<br>64<br>65<br>66<br>67<br>68<br>69<br>70<br>71<br>72<br>73<br>74<br>75<br>76<br>77<br>78<br>79<br>80<br>81<br>82<br>83<br>84<br>85<br>86 | ```<br>``` |

#### Demo:

### Example 2

Find all children of each div.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34 | ```<br>``` |

#### Demo:

### Example 3

Find all children with a class "selected" of each div.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31 | ```<br>``` |

#### Demo: