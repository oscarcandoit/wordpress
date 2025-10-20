---
url: https://api.jquery.com/header-selector/
scraped_at: 2025-10-20T03:28:34.446Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## header selector

**Description:** Selects all elements that are headers, like h1, h2, h3 and so on.

- #### version added: [1.2](https://api.jquery.com/category/version/1.2/)jQuery( ":header" )


### Additional Notes:

- Because `:header` is a jQuery extension and not part of the CSS specification, queries using `:header` cannot take advantage of the performance boost provided by the native DOM `querySelectorAll()` method. To achieve the best performance when using `:header` to select elements, first select the elements using a pure CSS selector, then use [`.filter(":header")`](https://api.jquery.com/filter/).


Adds a background and text color to all the headers on the page.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20 | ```<br>``` |

#### Demo: