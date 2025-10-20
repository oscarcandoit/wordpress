---
url: https://api.jquery.com/Types/
scraped_at: 2025-10-20T02:58:58.265Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

# Types

* * *

This page documents data types appearing in jQuery function signatures, whether defined by JavaScript itself or further restricted by jQuery. Unless explicitly stated otherwise, jQuery functions require primitive values where applicable, and do not accept their Object-wrapped forms. If you want to study these concepts in depth, take a look at [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript).

You should be able to try out most of the examples below by just copying them to your browser's JavaScript Console.

Whenever an example mentions that a type defaults to a boolean value, the result is good to know when using that type in a boolean context:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |

In this case, `"x defaulted to false"` is printed.

To keep the examples short, the invert ("not") operator and double-negation are used to show a boolean context:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

On to the actual types.

## Contents

01. [Anything](https://api.jquery.com/Types/#Anything)
02. [String](https://api.jquery.com/Types/#String)
    - [Quoting](https://api.jquery.com/Types/#Quoting)
    - [Built-in Methods](https://api.jquery.com/Types/#Built-in_Methods)
    - [Length Property](https://api.jquery.com/Types/#Length_Property)
    - [Boolean Default](https://api.jquery.com/Types/#Boolean_Default)
03. [htmlString](https://api.jquery.com/Types/#htmlString)
04. [Number](https://api.jquery.com/Types/#Number)
    - [Boolean Default](https://api.jquery.com/Types/#Boolean_Default_2)
    - [Math](https://api.jquery.com/Types/#Math)
    - [Parsing Numbers](https://api.jquery.com/Types/#Parsing_Numbers)
    - [Numbers to Strings](https://api.jquery.com/Types/#Numbers_to_Strings)
    - [NaN and Infinity](https://api.jquery.com/Types/#NaN_and_Infinity)
    - [Integer](https://api.jquery.com/Types/#Integer)
    - [Float](https://api.jquery.com/Types/#Float)
05. [Boolean](https://api.jquery.com/Types/#Boolean)
06. [Object](https://api.jquery.com/Types/#Object)
    - [Dot Notation](https://api.jquery.com/Types/#Dot_Notation)
    - [Array Notation](https://api.jquery.com/Types/#Array_Notation)
    - [Iteration](https://api.jquery.com/Types/#Iteration)
    - [Boolean default](https://api.jquery.com/Types/#Boolean_default_3)
    - [Prototype](https://api.jquery.com/Types/#Prototype)
07. [Array](https://api.jquery.com/Types/#Array)
    - [Iteration](https://api.jquery.com/Types/#Iteration_2)
    - [Boolean Default](https://api.jquery.com/Types/#Boolean_Default_4)
    - [Array<Type> Notation](https://api.jquery.com/Types/#Array.3CType.3E_Notation)
08. [Array-Like Object](https://api.jquery.com/Types/#ArrayLikeObject)
09. [PlainObject](https://api.jquery.com/Types/#PlainObject)
10. [Date](https://api.jquery.com/Types/#Date)
11. [Function](https://api.jquery.com/Types/#Function)
    - [Arguments](https://api.jquery.com/Types/#Arguments)
    - [Context, Call and Apply](https://api.jquery.com/Types/#Context.2C_Call_and_Apply)
    - [Scope](https://api.jquery.com/Types/#Scope)
    - [Closures](https://api.jquery.com/Types/#Closures)
    - [Proxy Pattern](https://api.jquery.com/Types/#Proxy_Pattern)
12. [Error](https://api.jquery.com/Types/#Error)
13. [Selector](https://api.jquery.com/Types/#Selector)
14. [Event](https://api.jquery.com/Types/#Event)
15. [Element](https://api.jquery.com/Types/#Element)
16. [Text](https://api.jquery.com/Types/#Text)
17. [jQuery](https://api.jquery.com/Types/#jQuery)
18. [XMLHttpRequest](https://api.jquery.com/Types/#XMLHttpRequest)
19. [jqXHR](https://api.jquery.com/Types/#jqXHR)
20. [Thenable](https://api.jquery.com/Types/#Thenable)
21. [Deferred Object](https://api.jquery.com/Types/#Deferred)
22. [Promise Object](https://api.jquery.com/Types/#Promise)
23. [Callbacks Object](https://api.jquery.com/Types/#Callbacks)
24. [XML Document](https://api.jquery.com/Types/#XMLDocument)
25. [Qunit's Assert Object](https://api.jquery.com/Types/#Assert)

## Anything

The **Anything** virtual type is used in jQuery documentation to indicate that any type can be used or should be expected.

## String

A string in JavaScript is an immutable primitive value that contains none, one or many characters.

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

The type of a string is "string".

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Quoting

A string can be defined using single or double quotes. You can nest single quotes inside of double quotes, and the other way around. To mix double quotes with double quotes (or single with single), the nested ones have to be escaped with a backslash.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

### Built-in Methods

A string in JavaScript has some built-in methods to manipulate the string, though the result is always a new string - or something else, eg. split returns an [array](https://api.jquery.com/Types/#Array "Types").

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

### Length Property

All strings have a length property.

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

### Boolean Default

An empty string defaults to false:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

## htmlString

A string is designated **htmlString** in jQuery documentation when it is used to represent one or more DOM elements, typically to be created and inserted in the document. When passed as an argument of the `jQuery()` function, the string is identified as HTML if it starts with `<tag ... >`) and is parsed as such until the final `>` character. Prior to jQuery 1.9, a string was considered to be HTML if it contained `<tag ... >` _anywhere within the string_.

When a string is passed as an argument to a manipulation method such as `.append()`, it is always considered to be HTML since jQuery's other common interpretation of a string (CSS selectors) does not apply in those contexts.

For explicit parsing of a string to HTML, the `[$.parseHTML()](https://api.jquery.com/jQuery.parseHTML/)` method is available as of jQuery 1.8.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14 | ```<br>``` |

## Number

Numbers in JavaScript are double-precision 64-bit format IEEE 754 values. They are immutable primitive values, just like [strings](https://api.jquery.com/Types/#String ""). All operators common in c-based languages are available to work with numbers (+, -, \*, /, %, =, +=, -=, \*=, /=, ++, --).

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

The type of a number is "number".

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

### Boolean Default

If a number is zero, it defaults to false:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

Due to the implementation of numbers as double-precision values, the following result is not an error:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Math

JavaScript provides utilities to work with numbers in the Math object:

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

### Parsing Numbers

parseInt and parseFloat help parsing strings into numbers. Both do some implicit conversion if the base isn't specified:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |

### Numbers to Strings

When appending numbers to string, the result is always a string. The operator is the same, so be careful: If you want to add numbers and then append them to a string, put parentheses around the numbers:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

Or you use the String class provided by javascript, which try to parse a value as string:

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

### NaN and Infinity

Parsing something that isn't a number results in NaN. isNaN helps to detect those cases:

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

Division by zero results in Infinity:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

Both NaN and Infinity are of type "number":

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

Note that NaN compares in a strange way:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

But:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Integer

An integer is a plain Number type, but whenever explicitly mentioned, indicates that a non-floating-point number is expected.

### Float

A float is a plain Number type, just as Integer, but whenever explicitly mentioned, indicates that a floating-point number is expected.

## Boolean

A boolean in JavaScript can be either true or false:

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

## Object

Everything in JavaScript is an object, though some are more objective (haha). The easiest way to create an object is the object literal:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

The type of an object is "object":

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Dot Notation

You can write and read properties of an object using the dot notation:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

### Array Notation

Or you write and read properties using the array notation, which allows you to dynamically choose the property:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

### Iteration

Iterating over objects is easy with the for-in-loop:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

Note that for-in-loop can be spoiled by extending `Object.prototype` (see [Object.prototype is verboten](https://web.archive.org/web/20200416084623/https://erik.eae.net/archives/2005/06/06/22.13.54/ "https://web.archive.org/web/20200416084623/https://erik.eae.net/archives/2005/06/06/22.13.54/")) so take care when using other libraries.

jQuery provides a generic [_each_ function](https://api.jquery.com/jQuery.each/) to iterate over properties of objects, as well as elements of arrays:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

The drawback is that the callback is called in the context of each value and you therefore lose the context of your own object if applicable. More on this below at Functions.

### Boolean default

An object, no matter if it has properties or not, never defaults to false:

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

### Prototype

All objects have a prototype property. Whenever the interpreter looks for a property, it also checks in the object's prototype if the property is not found on the object itself. jQuery uses the prototype extensively to add methods to jQuery instances. Internally, jQuery makes `jQuery.fn` an alias of `jQuery.prototype` so you can use either one (though plugin developers have standardized on `fn`).

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14 | ```<br>``` |

## Array

Arrays in JavaScript are mutable lists with a few built-in methods. You can define arrays using the array literal:

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

The type of an array is "object":

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

Reading and writing elements to an array uses the array-notation:

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

### Iteration

An array has a length property that is useful for iteration:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

When performance is critical, reading the length property only once can help to speed things up. This should be used only when a performance bottleneck was discovered:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

Another variation defines a variable that is filled for each iteration, removing the array-notation from the loop-body. It does not work when the array contains 0 or empty strings!

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

jQuery provides a generic [_each_ function](https://api.jquery.com/jQuery.each/) to iterate over element of arrays, as well as properties of objects:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

The drawback is that the callback is called in the context of each value and you therefore lose the context of your own object if applicable. More on this below at Functions.

The length property can also be used to add elements to the end of an array. That is equivalent to using the push-method:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

You'll see both variations a lot when looking through JavaScript library code.

Other built-in methods are reverse, join, shift, unshift, pop, slice, splice and sort:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8 | ```<br>``` |

Note: .unshift() method does not return a length property in Internet Explorer.

### Boolean Default

An array, no matter if it has elements or not, never defaults to false:

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

### Array<Type> Notation

In the jQuery API you'll often find the notation of Array<Type>:

```
dragPrevention    Array<String>

```

This indicates that the method doesn't only expect an array as the argument, but also specifies the expected type. The notation is borrowed from Java 5's generics notation (or C++ templates).

## Array-Like Object

Either a true JavaScript Array or a JavaScript Object that contains a nonnegative integer `length` property and index properties from `0` up to `length - 1`. This latter case includes array-like objects commonly encountered in web-based code such as the `arguments` object and the `NodeList` object returned by many DOM methods.

When a jQuery API accepts either plain Objects or Array-Like objects, a plain Object with a numeric `length` property will trigger the Array-Like behavior.

## PlainObject

The PlainObject type is a JavaScript object containing zero or more key-value pairs. The plain object is, in other words, an `Object` object. It is designated "plain" in jQuery documentation to distinguish it from other kinds of JavaScript objects: for example, `null`, user-defined arrays, and host objects such as `document`, all of which have a `typeof` value of "object." The `[jQuery.isPlainObject()](https://api.jquery.com/jQuery.isPlainObject/)` method identifies whether the passed argument is a plain object or not, as demonstrated below:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11 | ```<br>``` |

## Null

The `null` keyword is a JavaScript literal that is commonly used to express the absence of an intentional value.

## Date

The Date type is a JavaScript object that represents a single moment in time. Date objects are instantiated using their constructor function, which by default creates an object that represents the current date and time.

|     |     |
| --- | --- |
| 1 | ```<br>``` |

To create a Date object for an alternative date and time, pass numeric arguments in the following order: year, month, day, hour, minute, second, millisecond — although note that the month is zero-based, whereas the other arguments are one-based. The following creates a Date object representing January 1st, 2014, at 8:15.

|     |     |
| --- | --- |
| 1 | ```<br>``` |

## Function

A function in JavaScript can be either named or anonymous. Any function can be assigned to a variable or passed to a method, but passing member functions this way can cause them to be called in the context of another object (i.e. with a different "this" object).

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

You see a lot of anonymous functions in jQuery code:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |

The type of a function is "function".

### Arguments

Inside a function a special variable "arguments" is always available. It's similar to an array in that it has a length property, but it lacks the built-in methods of an array. The elements of the pseudo-array are the argument of the function call.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |

The arguments object also has a callee property, which refers to the function you're inside of. For instance:

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

### Context, Call and Apply

In JavaScript, the variable "this" always refers to the current context. By default, "this" refers to the window object. Within a function this context can change, depending on how the function is called.

All event handlers in jQuery are called with the handling element as the context.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |

You can specify the context for a function call using the function-built-in methods call and apply. The difference between them is how they pass arguments. Call passes all arguments through as arguments to the function, while apply accepts an array as the arguments.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |

### Scope

In JavaScript, all variables defined inside a function are only visible inside that function scope. Consider the following example:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8 | ```<br>``` |

It defines a variable _x_ in the global scope, then defines an anonymous function and executes it immediately (the additional parentheses are required for immediate execution). Inside the function another variable _x_ is defined with a different value. It is only visible within that function and doesn't overwrite the global variable.

### Closures

Closures are created whenever a variable that is defined outside the current scope is accessed from within some inner scope. In the following example, the variable _counter_ is visible within the create, increment, and print functions, but not outside of them.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14 | ```<br>``` |

The pattern allows you to create objects with methods that operate on data that isn't visible to the outside—the very basis of object-oriented programming.

### Proxy Pattern

Combining the above knowledge gives you as a JavaScript developer quite a lot of power. One way to combine that is to implement a proxy pattern in JavaScript, enabling the basics of aspect-oriented programming (AOP):

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8 | ```<br>``` |

The above wraps its code in a function to hide the "proxied"-variable. It saves jQuery's setArray-method in a closure and overwrites it. The proxy then logs all calls to the method and delegates the call to the original. Using apply(this, arguments) guarantees that the caller won't be able to notice the difference between the original and the proxied method.

## Callback

A callback is a plain JavaScript function passed to some method as an argument or option. Some callbacks are just events, called to give the user a chance to react when a certain state is triggered. jQuery's event system uses such callbacks everywhere:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

Most callbacks provide arguments and a context. In the event-handler example, the callback is called with one argument, an Event. The context is set to the handling element, in the above example, document.body.

Some callbacks are required to return something, others make that return value optional. To prevent a form submission, a submit event handler can return false:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

Instead of always returning false, the callback could check fields of the form for validity, and return false only when the form is invalid.

## Error

An instance of an Error object is thrown as an exception when a runtime error occurs. Error can also be used as base to define user custom exception classes. In JavaScript an error can be thrown as shown below:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

An error can also be thrown by the engine under some circumstances. For example, when trying to access a property of `null`:

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

## Selector

A selector is used in jQuery to select DOM elements from a DOM document. That document is, in most cases, the DOM document present in all browsers, but can also be an XML document received via Ajax.

The selectors are a composition of CSS and custom additions. All selectors available in jQuery are documented on the [Selectors API page](https://api.jquery.com/category/selectors/ "Selectors").

There are lot of plugins that leverage jQuery's selectors in other ways. The validation plugin accepts a selector to specify a dependency, whether an input is required or not:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

This would make a checkbox with name "emailrules" required only if the user entered an email address in the email field, selected via its id, filtered via a custom selector ":filled" that the validation plugin provides.

If Selector is specified as the type of an argument, it accepts everything that the jQuery constructor accepts, eg. Strings, Elements, Lists of Elements.

## Event

jQuery's event system normalizes the event object according to W3C standards. The event object is guaranteed to be passed to the event handler (no checks for window.event required). It normalizes the target, relatedTarget, which, metaKey and pageX/Y properties and provides both stopPropagation() and preventDefault() methods.

Those properties are all documented, and accompanied by examples, on the [Event object](https://api.jquery.com/category/events/event-object/ "Events") page.

The standard events in the Document Object Model are: `blur`, `focus`, `load`, `resize`, `scroll`, `unload`, `beforeunload`, `click`, `dblclick`, `mousedown`, `mouseup`, `mousemove`, `mouseover`, `mouseout`, `mouseenter`, `mouseleave`, `change`, `select`, `submit`, `keydown`, `keypress,` and `keyup`. Since the DOM event names have predefined meanings for some elements, using them for other purposes is not recommended. jQuery's event model can trigger an event by any name on an element, and it is propagated up the DOM tree to which that element belongs, if any.

## Element

An element in the Document Object Model (DOM) can have attributes, text, and children. It provides methods to traverse the parent and children and to get access to its attributes. Due to inconsistencies in DOM API specifications and implementations, however, those methods can be a challenge to use. jQuery provides a "wrapper" around those elements to help interacting with the DOM. But sometimes you will be working directly with DOM elements, or see methods that (also) accept DOM elements as arguments.

Whenever you call jQuery's `.each()` method or one of its event methods on a jQuery collection, the context of the callback function — `this` — is set to a DOM element.

Some properties of DOM elements are quite consistent among browsers. Consider this example of a simple onblur validation:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

You could replace `this.value` with `$(this).val()` to access the value of the text input via jQuery, but in that case you wouldn't gain anything.

## Text

Text is a node of the Document Object Model (DOM) that represents the textual content of an [element](https://api.jquery.com/Types/#Element) or an attribute. Consider the following code:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

If you retrieve the children of the paragraph of the example as follows:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

you obtain two children. The first one is the [element](https://api.jquery.com/Types/#Element) representing the `b` tag. The second child is a text node containing the string " world".

## jQuery

A jQuery object contains a collection of Document Object Model (DOM) elements that have been created from an HTML string or selected from a document. Since jQuery methods often use CSS selectors to match elements from a document, the set of elements in a jQuery object is often called a set of "matched elements" or "selected elements".

The jQuery object itself behaves much like an array; it has a `length` property and the elements in the object can be accessed by their numeric indices `[0]` to `[length-1]`. Note that a jQuery object is not actually a Javascript Array object, so it does not have all the methods of a true Array object such as `join()`.

Most frequently, you will use the jQuery() function to create a jQuery object. `jQuery()` can also be accessed by its familiar single-character alias of `$()`, unless you have called `jQuery.noConflict()` to disable this option. Many jQuery methods return the jQuery object itself, so that method calls can be chained:

In API calls that return `jQuery`, the value returned will be the original jQuery object unless otherwise documented by that API. API methods such as `.filter()` or `.not()` modify their incoming set and thus return a new jQuery object.

|     |     |
| --- | --- |
| 1 | ```<br>``` |

Whenever you use a "destructive" jQuery method that potentially changes the set of elements in the jQuery object, such as `.filter()` or `.find()`, that method actually returns a new jQuery object with the resulting elements. To return to the previous jQuery object, you use the `.end()` method.

A jQuery object may be empty, containing no DOM elements. You can create an empty jQuery object with `$()` (that is, passing no arguments at all). A jQuery object may also be empty if a selector doesn't select any elements, or if a chained method filters out all the elements. It is not an error; any further methods called on that jQuery object simply have no effect since they have no elements to act upon. So, in this example if there are no bad entries on the page then no elements will be colored red:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

## XMLHttpRequest

Some of jQuery's Ajax functions return the native XMLHttpRequest (XHR) object, or pass it as an argument to success/error/complete handlers, so that you can do additional processing or monitoring on the request. Note that Ajax functions only return or pass an XHR object when an XHR object is actually used in the request. For example, JSONP requests and cross-domain GET requests use a script element rather than an XHR object.

Although the XHR object is a standard, there are variations in its behavior on different browsers. Refer to the WHATWG site and Mozilla Developer Network for more information:

- [WHATWG living standard](https://xhr.spec.whatwg.org/ "https://xhr.spec.whatwg.org/")
- [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest "https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest")

## jqXHR

As of jQuery 1.5, the [$.ajax()](https://api.jquery.com/jQuery.ajax/) method returns the jqXHR object, which is a superset of the XMLHTTPRequest object. For more information, see the [jqXHR section of the $.ajax entry](https://api.jquery.com/jQuery.ajax/#jqXHR)

## Thenable

Any object that has a `then` method.

## Deferred Object

As of jQuery 1.5, the [Deferred](https://api.jquery.com/category/deferred-object/) object provides a way to register multiple callbacks into self-managed callback queues, invoke callback queues as appropriate, and relay the success or failure state of any synchronous or asynchronous function.

## Promise Object

This object provides a subset of the methods of the [Deferred](https://api.jquery.com/category/deferred-object/) object ( [`then`](https://api.jquery.com/deferred.then/), [`done`](https://api.jquery.com/deferred.done/), [`fail`](https://api.jquery.com/deferred.fail/), [`always`](https://api.jquery.com/deferred.always/), [`pipe`](https://api.jquery.com/deferred.pipe/), [`progress`](https://api.jquery.com/deferred.progress/), [`state`](https://api.jquery.com/deferred.state/) and [`promise`](https://api.jquery.com/deferred.promise/)) to prevent users from changing the state of the Deferred.

## Callbacks Object

A multi-purpose object that provides a powerful way to manage callback lists. It supports adding, removing, firing, and disabling callbacks. The Callbacks object is created and returned by the `$.Callbacks` function and subsequently returned by most of that function's methods.

## Document

A document object created by the browser's DOM parser, usually from a string representing HTML or XML.

## XML Document

A document object created by the browser's XML DOM parser, usually from a string representing XML. XML documents have different semantics than HTML documents, but most of the traversing and manipulation methods provided by jQuery will work with them.

## Assert

A reference to or instance of the object holding all of QUnit's assertions. See the [API documentation for `QUnit.assert`](https://api.qunitjs.com/config/QUnit.assert) for details.