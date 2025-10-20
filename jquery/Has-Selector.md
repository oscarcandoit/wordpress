---
url: https://api.jquery.com/has-selector/
scraped_at: 2025-10-20T03:26:56.469Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## has selector

**Description:** Selects elements which contain at least one element that matches the specified selector.

- #### version added: [1.1.4](https://api.jquery.com/category/version/1.1.4/)jQuery( ":has(selector)" )


**selector:** Any selector.


The expression `$( "div:has(p)" )` matches a `<div>` if a `<p>` exists anywhere among its descendants, not just as a direct child.

### Additional Notes:

- Because `:has()` is a jQuery extension and not part of the CSS specification, queries using `:has()` cannot take advantage of the performance boost provided by the native DOM `querySelectorAll()` method. For better performance in modern browsers, use `$( "your-pure-css-selector" ).has( selector/DOMElement )` instead.


Adds the class "test" to all divs that have a paragraph inside of them.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23 | ```<br>``` |

#### Demo: