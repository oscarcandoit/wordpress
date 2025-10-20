---
url: https://api.jquery.com/enabled-selector/
scraped_at: 2025-10-20T03:28:06.602Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## enabled selector

**Description:** Selects all elements that are enabled.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/)jQuery( ":enabled" )


As with other pseudo-class selectors (those that begin with a ":") it is recommended to precede it with a tag name or some other selector; otherwise, the universal selector ( "\*" ) is implied. In other words, the bare `$( ":enabled" )` is equivalent to `$( "*:enabled" )`, so `$( "input:enabled" )` or similar should be used instead.

Although their resulting selections are usually the same, `:enabled` selector is subtly different from `:not([disabled])`; `:enabled` selects elements that have their boolean disabled property strictly equal to false, while `:not([disabled])` selects elements that do not have a disabled _attribute_ set (regardless of its value).

The `:enabled` selector should only be used for selecting HTML elements that support the `disabled` attribute ( `<button>`, `<input>`, `<optgroup>`, `<option>`, `<select>`, and `<textarea>`).

Find all input elements that are enabled.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20 | ```<br>``` |

#### Demo: