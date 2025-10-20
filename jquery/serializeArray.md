---
url: https://api.jquery.com/serializeArray/
scraped_at: 2025-10-20T02:59:52.259Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .serializeArray()Returns: [Array](http://api.jquery.com/Types/\#Array)

**Description:** Encode a set of form elements as an array of names and values.

- #### version added: [1.2](https://api.jquery.com/category/version/1.2/) [.serializeArray()](https://api.jquery.com/serializeArray/\#serializeArray)

  - This method does not accept any arguments.

The `.serializeArray()` method creates a JavaScript array of objects, ready to be encoded as a JSON string. It operates on a jQuery collection of `form` s and/or form controls. The controls can be of several types:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19 | ```<br>``` |

The `.serializeArray()` method uses the standard W3C rules for [successful controls](https://www.w3.org/TR/html401/interact/forms.html#h-17.13.2) to determine which elements it should include; in particular the element cannot be disabled and must contain a `name` attribute. No submit button value is serialized since the form was not submitted using a button. Data from file select elements is not serialized. Elements that do not contain a `value` attribute are represented with the empty string value.

This method can act on a jQuery object that has selected individual form controls, such as `<input>`, `<textarea>`, and `<select>`. However, it is typically easier to select the `<form>` element itself for serialization:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

This produces the following data structure (provided that the browser supports `console.log`):

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22 | ```<br>``` |

Get the values from a form, iterate through them, and append them to a results display.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55<br>56<br>57<br>58<br>59<br>60<br>61<br>62 | ```<br>``` |

#### Demo: