---
url: https://api.jquery.com/lang-selector/
scraped_at: 2025-10-20T03:28:57.263Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## lang selector

**Description:** Selects all elements of the specified language.

- #### version added: [1.9](https://api.jquery.com/category/version/1.9/)jQuery( ":lang(language)" )


**language:** A language code.


The `:lang()` selector matches elements that have a language value equal to the supplied language code or that start with the supplied language code immediately followed by "-". For example, the selector `$("div:lang(en)")` will match `<div lang="en">` and `<div lang="en-us">` (and any of their descendant `<div>` s), but not `<div lang="fr">`

For HTML elements, the language value is determined by the `lang` attribute and possibly information from `meta` elements or HTTP headers.

Further discussion of this usage can be found in the [W3C CSS specification](https://www.w3.org/TR/css3-selectors/#lang-pseudo).

Color div elements according to their language.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55<br>56<br>57<br>58<br>59<br>60<br>61<br>62<br>63<br>64<br>65<br>66 | ```<br>``` |

#### Demo: