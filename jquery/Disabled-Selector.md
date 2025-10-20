---
url: https://api.jquery.com/disabled-selector/
scraped_at: 2025-10-20T03:27:56.055Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## disabled selector

**Description:** Selects all elements that are disabled.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/)jQuery( ":disabled" )


As with other pseudo-class selectors (those that begin with a ":"), it is recommended to precede it with a tag name or some other selector; otherwise, the universal selector ("\*") is implied. In other words, the bare `$(':disabled')` is equivalent to `$('*:disabled')`, so `$('input:disabled')` or similar should be used instead.

Although their resulting selections are usually the same, the `:disabled` selector is subtly different from the `[disabled]` attribute selector; `:disabled` matches elements that are [actually disabled](https://html.spec.whatwg.org/multipage/scripting.html#disabled-elements) while `[disabled]` only checks for the existence of the disabled attribute.

The `:disabled` selector should only be used for selecting HTML elements that support the `disabled` attribute ( `<button>`, `<input>`, `<optgroup>`, `<option>`, `<select>`, `<textarea>`, `<menuitem>`, and `<fieldset>`).

Finds all input elements that are disabled.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20 | ```<br>``` |

#### Demo: