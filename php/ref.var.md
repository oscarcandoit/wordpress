---
url: https://www.php.net/manual/en/ref.var.php
scraped_at: 2025-10-20T02:47:09.714Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Variable handling Functions [¶](https://www.php.net/manual/en/ref.var.php\#ref.var)

## Table of Contents [¶](https://www.php.net/manual/en/ref.var.php\#ref.var)

- [boolval](https://www.php.net/manual/en/function.boolval.php) — Get the boolean value of a variable
- [debug\_zval\_dump](https://www.php.net/manual/en/function.debug-zval-dump.php) — Dumps a string representation of an internal zval structure to output
- [doubleval](https://www.php.net/manual/en/function.doubleval.php) — Alias of floatval
- [empty](https://www.php.net/manual/en/function.empty.php) — Determine whether a variable is empty
- [floatval](https://www.php.net/manual/en/function.floatval.php) — Get float value of a variable
- [get\_debug\_type](https://www.php.net/manual/en/function.get-debug-type.php) — Gets the type name of a variable in a way that is suitable for debugging
- [get\_defined\_vars](https://www.php.net/manual/en/function.get-defined-vars.php) — Returns an array of all defined variables
- [get\_resource\_id](https://www.php.net/manual/en/function.get-resource-id.php) — Returns an integer identifier for the given resource
- [get\_resource\_type](https://www.php.net/manual/en/function.get-resource-type.php) — Returns the resource type
- [gettype](https://www.php.net/manual/en/function.gettype.php) — Get the type of a variable
- [intval](https://www.php.net/manual/en/function.intval.php) — Get the integer value of a variable
- [is\_array](https://www.php.net/manual/en/function.is-array.php) — Finds whether a variable is an array
- [is\_bool](https://www.php.net/manual/en/function.is-bool.php) — Finds out whether a variable is a boolean
- [is\_callable](https://www.php.net/manual/en/function.is-callable.php) — Verify that a value can be called as a function from the current scope
- [is\_countable](https://www.php.net/manual/en/function.is-countable.php) — Verify that the contents of a variable is a countable value
- [is\_double](https://www.php.net/manual/en/function.is-double.php) — Alias of is\_float
- [is\_float](https://www.php.net/manual/en/function.is-float.php) — Finds whether the type of a variable is float
- [is\_int](https://www.php.net/manual/en/function.is-int.php) — Find whether the type of a variable is integer
- [is\_integer](https://www.php.net/manual/en/function.is-integer.php) — Alias of is\_int
- [is\_iterable](https://www.php.net/manual/en/function.is-iterable.php) — Verify that the contents of a variable is an iterable value
- [is\_long](https://www.php.net/manual/en/function.is-long.php) — Alias of is\_int
- [is\_null](https://www.php.net/manual/en/function.is-null.php) — Finds whether a variable is null
- [is\_numeric](https://www.php.net/manual/en/function.is-numeric.php) — Finds whether a variable is a number or a numeric string
- [is\_object](https://www.php.net/manual/en/function.is-object.php) — Finds whether a variable is an object
- [is\_real](https://www.php.net/manual/en/function.is-real.php) — Alias of is\_float
- [is\_resource](https://www.php.net/manual/en/function.is-resource.php) — Finds whether a variable is a resource
- [is\_scalar](https://www.php.net/manual/en/function.is-scalar.php) — Finds whether a variable is a scalar
- [is\_string](https://www.php.net/manual/en/function.is-string.php) — Find whether the type of a variable is string
- [isset](https://www.php.net/manual/en/function.isset.php) — Determine if a variable is declared and is different than null
- [print\_r](https://www.php.net/manual/en/function.print-r.php) — Prints human-readable information about a variable
- [serialize](https://www.php.net/manual/en/function.serialize.php) — Generates a storable representation of a value
- [settype](https://www.php.net/manual/en/function.settype.php) — Set the type of a variable
- [strval](https://www.php.net/manual/en/function.strval.php) — Get string value of a variable
- [unserialize](https://www.php.net/manual/en/function.unserialize.php) — Creates a PHP value from a stored representation
- [unset](https://www.php.net/manual/en/function.unset.php) — unset a given variable
- [var\_dump](https://www.php.net/manual/en/function.var-dump.php) — Dumps information about a variable
- [var\_export](https://www.php.net/manual/en/function.var-export.php) — Outputs or returns a parsable string representation of a variable

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/var/reference.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fref.var%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=ref.var&repo=en&redirect=https://www.php.net/manual/en/ref.var.php)

### User Contributed Notes 1 note

[up](https://www.php.net/manual/vote-note.php?id=124265&page=ref.var&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124265&page=ref.var&vote=down "Vote down!")

 -3


[**_aldemarcalazans@gmail_**](https://www.php.net/manual/en/ref.var.php#124265) [¶](https://www.php.net/manual/en/ref.var.php#124265)

**6 years ago**

`I thought the PHP developers should include in this section, the operator "identity" ( see [http://php.net/manual/en/language.operators.arithmetic.php](http://php.net/manual/en/language.operators.arithmetic.php)).
From an arithmetic point of view, this operator is useless but, as a converter from string to number, it is great. It does not force the numerical string to have an integer or float type, instead, it automatically determines the adequate type, depending on the numerical quantity represented by the string.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=ref.var&repo=en&redirect=https://www.php.net/manual/en/ref.var.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google