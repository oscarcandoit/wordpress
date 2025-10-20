---
url: https://api.jquery.com/serialize/
scraped_at: 2025-10-20T02:59:48.916Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .serialize()Returns: [String](http://api.jquery.com/Types/\#String)

**Description:** Encode a set of form elements as a string for submission.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.serialize()](https://api.jquery.com/serialize/\#serialize)

  - This method does not accept any arguments.

The `.serialize()` method creates a text string in standard URL-encoded notation. It can act on a jQuery object that has selected individual form controls, such as `<input>`, `<textarea>`, and `<select>`: `$( "input, textarea, select" ).serialize();`

It is typically easier, however, to select the `<form>` itself for serialization:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

In this case, jQuery serializes the successful controls within the form. Only `form` elements are examined for inputs they contain, in all other cases the input elements to be serialized should be part of the set passed to the `.serialize()` method. Selecting both the form and its children in a set will cause duplicates in the serialized string.

Note: Only ["successful controls"](https://www.w3.org/TR/html401/interact/forms.html#h-17.13.2) are serialized to the string. No submit button value is serialized since the form was not submitted using a button. For a form element's value to be included in the serialized string, the element must have a `name` attribute. Values from checkboxes and radio buttons ( `input` s of type "radio" or "checkbox") are included only if they are checked. Data from file select elements is not serialized.

Serialize a form to a query string that could be sent to a server in an Ajax request.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55<br>56<br>57<br>58<br>59<br>60<br>61<br>62<br>63<br>64<br>65 | ```<br>``` |

#### Demo: