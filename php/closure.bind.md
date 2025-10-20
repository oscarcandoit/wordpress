---
url: https://www.php.net/manual/en/closure.bind.php
scraped_at: 2025-10-20T03:00:53.225Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Closure::bind

(PHP 5 >= 5.4.0, PHP 7, PHP 8)

Closure::bind —
Duplicates a closure with a specific bound object and class scope


### Description [¶](https://www.php.net/manual/en/closure.bind.php\#refsect1-closure.bind-description)

publicstatic**Closure::bind**([Closure](https://www.php.net/manual/en/class.closure.php) `$closure`, [?](https://www.php.net/manual/en/language.types.null.php)[object](https://www.php.net/manual/en/language.types.object.php) `$newThis`, [object](https://www.php.net/manual/en/language.types.object.php)\|[string](https://www.php.net/manual/en/language.types.string.php)\|[null](https://www.php.net/manual/en/language.types.null.php) `$newScope` = "static"): [?](https://www.php.net/manual/en/language.types.null.php)[Closure](https://www.php.net/manual/en/class.closure.php)

This method is a static version of [Closure::bindTo()](https://www.php.net/manual/en/closure.bindto.php).
See the documentation of that method for more information.


### Parameters [¶](https://www.php.net/manual/en/closure.bind.php\#refsect1-closure.bind-parameters)

`closure`

The anonymous functions to bind.


`newThis`

The object to which the given anonymous function should be bound, or
**`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** for the closure to be unbound.


`newScope`

The class scope to which the closure is to be associated, or
'static' to keep the current one. If an object is given, the type of the
object will be used instead. This determines the visibility of protected
and private methods of the bound object.
It is not allowed to pass (an object of) an internal class as this parameter.


### Return Values [¶](https://www.php.net/manual/en/closure.bind.php\#refsect1-closure.bind-returnvalues)

Returns a new [Closure](https://www.php.net/manual/en/class.closure.php) object, or **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** on failure.


### Examples [¶](https://www.php.net/manual/en/closure.bind.php\#refsect1-closure.bind-examples)

**Example #1 **Closure::bind()** example**

`<?php
class A {
    private static $sfoo = 1;
    private $ifoo = 2;
}
$cl1 = static function() {
    return A::$sfoo;
};
$cl2 = function() {
    return $this->ifoo;
};
$bcl1 = Closure::bind($cl1, null, 'A');
$bcl2 = Closure::bind($cl2, new A(), 'A');
echo $bcl1(), "\n";
echo $bcl2(), "\n";
?>`

The above example will output
something similar to:

```
1
2
```

### See Also [¶](https://www.php.net/manual/en/closure.bind.php\#refsect1-closure.bind-seealso)

- [Anonymous functions](https://www.php.net/manual/en/functions.anonymous.php)
- [Closure::bindTo()](https://www.php.net/manual/en/closure.bindto.php) \- Duplicates the closure with a new bound object and class scope

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/predefined/closure/bind.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclosure.bind%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=closure.bind&repo=en&redirect=https://www.php.net/manual/en/closure.bind.php)

### User Contributed Notes 2 notes

[up](https://www.php.net/manual/vote-note.php?id=110845&page=closure.bind&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=110845&page=closure.bind&vote=down "Vote down!")

97


[**_Vincius Krolow_**](https://www.php.net/manual/en/closure.bind.php#110845) [¶](https://www.php.net/manual/en/closure.bind.php#110845)

**12 years ago**

`With this class and method, it's possible to do nice things, like add methods on the fly to an object.
MetaTrait.php
<?php
trait MetaTrait
{

    private $methods = array();

    public function addMethod($methodName, $methodCallable)
    {
        if (!is_callable($methodCallable)) {
            throw new InvalidArgumentException('Second param must be callable');
        }
        $this->methods[$methodName] = Closure::bind($methodCallable, $this, get_class());
    }

    public function __call($methodName, array $args)
    {
        if (isset($this->methods[$methodName])) {
            return call_user_func_array($this->methods[$methodName], $args);
        }

        throw RunTimeException('There is no method with the given name to call');
    }

}
?>
test.php
<?php
require 'MetaTrait.php';

class HackThursday {
    use MetaTrait;

    private $dayOfWeek = 'Thursday';

}

$test = new HackThursday();
$test->addMethod('when', function () {
    return $this->dayOfWeek;
});

echo $test->when();
?>`

[up](https://www.php.net/manual/vote-note.php?id=116267&page=closure.bind&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=116267&page=closure.bind&vote=down "Vote down!")

11


[**_potherca at hotmail dot com_**](https://www.php.net/manual/en/closure.bind.php#116267) [¶](https://www.php.net/manual/en/closure.bind.php#116267)

**10 years ago**

`If you need to validate whether or not a closure can be bound to a PHP object, you will have to resort to using reflection.
<?php
/**
* @param \Closure $callable
*
* @return bool
*/
function isBindable(\Closure $callable)
{
    $bindable = false;
    $reflectionFunction = new \ReflectionFunction($callable);
    if (
        $reflectionFunction->getClosureScopeClass() === null
        || $reflectionFunction->getClosureThis() !== null
    ) {
        $bindable = true;
    }
    return $bindable;
}
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=closure.bind&repo=en&redirect=https://www.php.net/manual/en/closure.bind.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google