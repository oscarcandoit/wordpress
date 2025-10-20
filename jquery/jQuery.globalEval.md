---
url: https://api.jquery.com/jQuery.globalEval/
scraped_at: 2025-10-20T03:14:33.859Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.globalEval( code )Returns: [Anything](http://api.jquery.com/Types/\#Anything)

**Description:** Execute some JavaScript code globally.

- #### version added: [1.0.4](https://api.jquery.com/category/version/1.0.4/) [jQuery.globalEval( code )](https://api.jquery.com/jQuery.globalEval/\#jQuery-globalEval-code)

  - **code**

    Type: [String](http://api.jquery.com/Types/#String)

    The JavaScript code to execute.
- #### version added: [3.4](https://api.jquery.com/category/version/3.4/) [jQuery.globalEval( code \[, options \] )](https://api.jquery.com/jQuery.globalEval/\#jQuery-globalEval-code-options)

  - **code**

    Type: [String](http://api.jquery.com/Types/#String)

    The JavaScript code to execute.

  - **options**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject)


    - **nonce**

      Type: [string](http://api.jquery.com/Types/#string)

      The nonce attribute passed to the executed script.
- #### version added: [3.5](https://api.jquery.com/category/version/3.5/) [jQuery.globalEval( code \[, options \] \[, doc \] )](https://api.jquery.com/jQuery.globalEval/\#jQuery-globalEval-code-options-doc)

  - **code**

    Type: [String](http://api.jquery.com/Types/#String)

    The JavaScript code to execute.

  - **options**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject)


    - **nonce**

      Type: [string](http://api.jquery.com/Types/#string)

      The nonce attribute passed to the executed script.
  - **doc**

    Type: [Document](http://api.jquery.com/Types/#Document)

    A document in which context the code will be evaluated.

This method behaves differently from using a normal JavaScript `eval()` in that it's executed within the global context (which is important for loading external scripts dynamically).

### Example 1

Execute a script in the global context.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

### Example 2

Execute a script with a nonce value on a site with Content Security Policy enabled.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |