---
url: https://api.jquery.com/jQuery.parseXML/
scraped_at: 2025-10-20T03:15:36.600Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.parseXML( data )Returns: [XMLDocument](http://api.jquery.com/Types/\#XMLDocument)

**Description:** Parses a string into an XML document.

- #### version added: [1.5](https://api.jquery.com/category/version/1.5/) [jQuery.parseXML( data )](https://api.jquery.com/jQuery.parseXML/\#jQuery-parseXML-data)

  - **data**

    Type: [String](http://api.jquery.com/Types/#String)

    a well-formed XML string to be parsed

`jQuery.parseXML` uses the native parsing function of the browser to create a valid XML Document. This document can then be passed to `jQuery` to create a typical jQuery object that can be traversed and manipulated.

Create a jQuery object using an XML string and obtain the value of the title node.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30 | ```<br>``` |

#### Demo: