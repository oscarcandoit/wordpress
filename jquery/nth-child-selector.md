---
url: https://api.jquery.com/nth-child-selector/
scraped_at: 2025-10-20T03:29:21.372Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## nth-child selector

**Description:** Selects all elements that are the nth-child of their parent.

- #### version added: [1.1.4](https://api.jquery.com/category/version/1.1.4/)jQuery( ":nth-child(index/even/odd/equation)" )


**index:** The index of each child to match, starting with `1`, the string `even` or `odd`, or an equation ( eg. `:nth-child(even)`, `:nth-child(4n)` )


Because jQuery's implementation of `:nth-` selectors is strictly derived from the CSS specification, the value of `n` is "1-indexed", meaning that the counting starts at 1. jQuery methods like [`.first()`](https://api.jquery.com/first/) or [`.eq()`](https://api.jquery.com/eq/) jQuery follows JavaScript's "0-indexed" counting. Given a single `<ul>` containing two `<li>` s, `$( "li:nth-child(1)" )` selects the first `<li>` while `$( "li" ).eq( 1 )` selects the second.

The `:nth-child(n)` pseudo-class is easily confused with the `.eq( n )` call, even though the two can result in dramatically different matched elements. With `:nth-child(n)`, all children are counted, regardless of what they are, and the specified element is selected only if it matches the selector attached to the pseudo-class. With the `.eq( n )` call only the selector attached to the pseudo-class is counted, not limited to children of any other element, and the (n+1)th one (n is 0-based) is selected.

Further discussion of this unusual usage can be found in the [W3C CSS specification](https://www.w3.org/TR/css3-selectors/#nth-child-pseudo).

### Example 1

Find the second li in each matched ul and note it.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44 | ```<br>``` |

#### Demo:

### Example 2

This is a playground to see how the selector works with different strings. Notice that this is different from the [`even`](https://api.jquery.com/even/) and [`odd`](https://api.jquery.com/odd/) which have no regard for parent and just filter the list of elements to every other one. The :nth-child, however, counts the index of the child to its particular parent. In any case, it's easier to see than explain so...

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55<br>56<br>57<br>58<br>59<br>60<br>61<br>62<br>63<br>64<br>65<br>66<br>67<br>68<br>69<br>70<br>71<br>72<br>73<br>74<br>75<br>76<br>77<br>78<br>79<br>80<br>81<br>82<br>83<br>84<br>85<br>86<br>87<br>88 | ```<br>``` |

#### Demo: