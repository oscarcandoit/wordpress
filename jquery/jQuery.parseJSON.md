---
url: https://api.jquery.com/jQuery.parseJSON/
scraped_at: 2025-10-20T03:15:16.253Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.parseJSON( json )Returns: [String](http://api.jquery.com/Types/\#String) or [Number](http://api.jquery.com/Types/\#Number) or [Object](http://api.jquery.com/Types/\#Object) or [Array](http://api.jquery.com/Types/\#Array) or [Boolean](http://api.jquery.com/Types/\#Boolean)version deprecated: [3.0](https://api.jquery.com/category/version/3.0/), removed: [4.0](https://api.jquery.com/category/version/4.0/)

**Description:** Takes a well-formed JSON string and returns the resulting JavaScript value.

- #### version added: [1.4.1](https://api.jquery.com/category/version/1.4.1/) [jQuery.parseJSON( json )](https://api.jquery.com/jQuery.parseJSON/\#jQuery-parseJSON-json)

  - **json**

    Type: [String](http://api.jquery.com/Types/#String)

    The JSON string to parse.

As of jQuery 3.0, `$.parseJSON` is deprecated. To parse JSON strings use the native `JSON.parse` method instead.

Passing in a malformed JSON string results in a JavaScript exception being thrown. For example, the following are all invalid JSON strings:

- `"{test: 1}"` (test does not have double quotes around it).
- `"{'test': 1}"` ('test' is using single quotes instead of double quotes).
- `"'test'"` ('test' is using single quotes instead of double quotes).
- `".1"` (a number must start with a digit; `"0.1"` would be valid).
- `"undefined"` ( `undefined` cannot be represented in a JSON string; `null`, however, can be).
- `"NaN"` ( `NaN` cannot be represented in a JSON string; direct representation of `Infinity` is also not permitted).

The JSON standard does not permit "control characters" such as a tab or newline. An example like `$.parseJSON( '{ "testing":"1\t2\n3" }' )` will throw an error in most implementations because the JavaScript parser converts the string's tab and newline escapes into literal tab and newline; doubling the backslashes like `"1\\t2\\n3"` yields expected results. This problem is often seen when injecting JSON into a JavaScript file from a server-side language such as PHP.

Where the browser provides a native implementation of `JSON.parse`, jQuery uses it to parse the string. For details on the JSON format, see [https://json.org/](https://json.org/).

Prior to jQuery 1.9, `$.parseJSON` returned `null` instead of throwing an error if it was passed an empty string, `null`, or `undefined`, even though those are not valid JSON.

Parse a JSON string.

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |