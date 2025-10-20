---
url: https://api.jquery.com/jQuery.type/
scraped_at: 2025-10-20T03:15:47.753Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.type( obj )Returns: [String](http://api.jquery.com/Types/\#String)version deprecated: [3.3](https://api.jquery.com/category/version/3.3/), removed: [4.0](https://api.jquery.com/category/version/4.0/)

**Description:** Determine the internal JavaScript \[\[Class\]\] of an object.

- #### version added: [1.4.3](https://api.jquery.com/category/version/1.4.3/) [jQuery.type( obj )](https://api.jquery.com/jQuery.type/\#jQuery-type-obj)

  - **obj**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    Object to get the internal JavaScript \[\[Class\]\] of.

Note: This API has been deprecated in jQuery 3.3.

A number of techniques are used to determine the exact return value for an object. The \[\[Class\]\] is determined as follows:

- If the object is undefined or null, then "undefined" or "null" is returned accordingly.
  - jQuery.type( undefined ) === "undefined"
  - jQuery.type() === "undefined"
  - jQuery.type( window.notDefined ) === "undefined"
  - jQuery.type( null ) === "null"
- If the argument is either a primitive value or an instance of a standard built-in ECMAScript object, the \[\[Class\]\] internal property is used to determine the type. ( [More details about this technique.](http://perfectionkills.com/instanceof-considered-harmful-or-how-to-write-a-robust-isarray/))

  - jQuery.type( true ) === "boolean"
  - jQuery.type( new Boolean() ) === "boolean"
  - jQuery.type( 3 ) === "number"
  - jQuery.type( new Number( 3 ) ) === "number"
  - jQuery.type( "test" ) === "string"
  - jQuery.type( new String( "test" ) ) === "string"
  - jQuery.type( function() {} ) === "function"
  - jQuery.type( \[\] ) === "array"
  - jQuery.type( new Array() ) === "array"
  - jQuery.type( new Date() ) === "date"
  - jQuery.type( new Error() ) === "error" // **as of jQuery 1.9**
  - jQuery.type( Symbol() ) === "symbol" // **as of jQuery 1.9**
  - jQuery.type( Object( Symbol() ) ) === "symbol" // **as of jQuery 1.12**
  - jQuery.type( /test/ ) === "regexp"
- Everything else returns "object" as its type.

Find out if the parameter is a RegExp.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17 | ```<br>``` |

#### Demo: