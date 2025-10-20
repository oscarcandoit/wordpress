---
url: https://api.jquery.com/jQuery.parseHTML/
scraped_at: 2025-10-20T03:15:13.284Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.parseHTML( data \[, context \] \[, keepScripts \] )Returns: [Array](http://api.jquery.com/Types/\#Array)

**Description:** Parses a string into an array of DOM nodes.

- #### version added: [1.8](https://api.jquery.com/category/version/1.8/) [jQuery.parseHTML( data \[, context \] \[, keepScripts \] )](https://api.jquery.com/jQuery.parseHTML/\#jQuery-parseHTML-data-context-keepScripts)

  - **data**

    Type: [String](http://api.jquery.com/Types/#String)

    HTML string to be parsed

  - **context** (default: `document`)

    Type: [Element](http://api.jquery.com/Types/#Element)

    Document element to serve as the context in which the HTML fragment will be created

  - **keepScripts** (default: `false`)

    Type: [Boolean](http://api.jquery.com/Types/#Boolean)

    A Boolean indicating whether to include scripts passed in the HTML string

`jQuery.parseHTML` uses native methods to convert the string to a set of DOM nodes, which can then be inserted into the document. These methods do render all trailing or leading text (even if that's just whitespace). To prevent trailing/leading whitespace from being converted to text nodes you can pass the HTML string through [`jQuery.trim`](https://api.jquery.com/jQuery.trim/).

By default, the `context` is the current `document` if not specified or given as `null` or `undefined`. If the HTML was to be used in another document such as an iframe, that frame's document could be used.

As of 3.0 the default behavior is changed. If the `context` is not specified or given as `null` or `undefined`, a new `document` is used. This can potentially improve security because inline events will not execute when the HTML is parsed. Once the parsed HTML is injected into a document it does execute, but this gives tools a chance to traverse the created DOM and remove anything deemed unsafe. This improvement does not apply to internal uses of `jQuery.parseHTML` as they usually pass in the current `document`. Therefore, a statement like `$( "#log" ).append( $( htmlString ) )` is still subject to the injection of malicious code.

## Security Considerations

Most jQuery APIs that accept HTML strings will run scripts that are included in the HTML. `jQuery.parseHTML` does not run scripts in the parsed HTML unless `keepScripts` is explicitly `true`. However, it is still possible in most environments to execute scripts indirectly, for example via the `<img onerror>` attribute. The caller should be aware of this and guard against it by cleaning or escaping any untrusted inputs from sources such as the URL or cookies. For future compatibility, callers should not depend on the ability to run _any_ script content when `keepScripts` is unspecified or `false`.

Create an array of DOM nodes using an HTML string and insert it into a div.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36 | ```<br>``` |

#### Demo: