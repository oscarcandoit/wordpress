---
url: https://www.php.net/manual/en/closure.fromcallable.php
scraped_at: 2025-10-20T02:39:22.546Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Closure::fromCallable

(PHP 7 >= 7.1.0)

Closure::fromCallable — Converts a callable into a closure

### Description [¶](https://www.php.net/manual/en/closure.fromcallable.php\#refsect1-closure.fromcallable-description)

publicstatic**Closure::fromCallable**([callable](https://www.php.net/manual/en/language.types.callable.php) `$callback`): [Closure](https://www.php.net/manual/en/class.closure.php)

Create and return a new [anonymous\\
function](https://www.php.net/manual/en/functions.anonymous.php) from given `callback` using the
current scope. This method checks if the `callback` is
callable in the current scope and throws a [TypeError](https://www.php.net/manual/en/class.typeerror.php)
if it is not.


> **Note**:
>
>
> As of PHP 8.1.0, [First class callable syntax](https://www.php.net/manual/en/functions.first_class_callable_syntax.php) has the same semantics as this method.

### Parameters [¶](https://www.php.net/manual/en/closure.fromcallable.php\#refsect1-closure.fromcallable-parameters)

`callback`

The callable to convert.


### Return Values [¶](https://www.php.net/manual/en/closure.fromcallable.php\#refsect1-closure.fromcallable-returnvalues)

Returns the newly created [Closure](https://www.php.net/manual/en/class.closure.php) or throws a
[TypeError](https://www.php.net/manual/en/class.typeerror.php) if the `callback` is
not callable in the current scope.


### See Also [¶](https://www.php.net/manual/en/closure.fromcallable.php\#refsect1-closure.fromcallable-seealso)

- [Anonymous functions](https://www.php.net/manual/en/functions.anonymous.php)
- [First class callable syntax](https://www.php.net/manual/en/functions.first_class_callable_syntax.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/predefined/closure/fromcallable.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclosure.fromcallable%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=closure.fromcallable&repo=en&redirect=https://www.php.net/manual/en/closure.fromcallable.php)

### User Contributed Notes 3 notes

[up](https://www.php.net/manual/vote-note.php?id=121057&page=closure.fromcallable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121057&page=closure.fromcallable&vote=down "Vote down!")

13


[**_igorchernin at yahoo dot com_**](https://www.php.net/manual/en/closure.fromcallable.php#121057) [¶](https://www.php.net/manual/en/closure.fromcallable.php#121057)

**8 years ago**

`It seems that the result of the "fromCallable" behaves a little bit different then an original Lambda function.
class A {
    private $name;
    public function __construct($name)
    {
        $this->name = $name;
    }
}
// test callable
function getName()
{
      return $this->name;
}
$bob = new A("Bob");
$cl1 = Closure::fromCallable("getName");
$cl1 = $cl1->bindTo($bob, 'A');
//This will retrieve: Uncaught Error: Cannot access private property A::$name
$result = $cl1();
echo $result;
//But for a Lambda function
$cl2 = function() {
    return $this->name;
};
$cl2 = $cl2->bindTo($bob, 'A');
$result = $cl2();
// This will print Bob
echo $result;`

[up](https://www.php.net/manual/vote-note.php?id=122756&page=closure.fromcallable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122756&page=closure.fromcallable&vote=down "Vote down!")

5


[**_nakerlund at gmail dot com_**](https://www.php.net/manual/en/closure.fromcallable.php#122756) [¶](https://www.php.net/manual/en/closure.fromcallable.php#122756)

**7 years ago**

`I have two points:
It is possible to use Closure::fromCallable to convert private/protected methods to closures and use them outside the class.
Closure::fromCallable accepts late dynamic bindings using the keyword static if provided as a string.
My code below demonstrate how a private static method can be used as a callback in a function outside the class.
<?php
function myCustomMapper ( Callable $callable, string $str ): string {
return join(' ', array_map( $callable, explode(' ', $str) ) );
}
class MyClass {
    public static function mapUCFirst ( string $str ): string {
        $privateMethod = 'static::mapper';
        $mapper = Closure::fromCallable( $privateMethod );
        return myCustomMapper( $mapper, $str );
    }
    private static function mapper ( string $str ): string {
        return ucfirst( $str );
    }
}
echo MyClass::mapUCFirst('four little uncapitalized words');
// Prints: Four Little Uncapitalized Words
?>`

[up](https://www.php.net/manual/vote-note.php?id=122715&page=closure.fromcallable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122715&page=closure.fromcallable&vote=down "Vote down!")

6


[**_4-lom at live dot de_**](https://www.php.net/manual/en/closure.fromcallable.php#122715) [¶](https://www.php.net/manual/en/closure.fromcallable.php#122715)

**7 years ago**

`Sadly, your comparison is incorrect.
// The equivalent to
$cl1 = Closure::fromCallable("getName");
$cl1 = $cl1->bindTo($bob, 'A');
// is most likely this
$cl2 = function() {
    return call_user_func_array("getName", func_get_args());
};
$cl2 = $cl2->bindTo($bob, 'A');
Executing one or the other Closure should result in the same access violation error you already postet.
----
A simple PHP 7.0 polyfill could look like this:
----
namespace YourPackage;
/**
* Class Closure
*
* @see \Closure
*/
class Closure
{
    /**
     * @see \Closure::fromCallable()
     * @param callable $callable
     * @return \Closure
     */
    public static function fromCallable(callable $callable)
    {
        // In case we've got it native, let's use that native one!
        if(method_exists(\Closure::class, 'fromCallable')) {
            return \Closure::fromCallable($callable);
        }
        return function () use ($callable) {
            return call_user_func_array($callable, func_get_args());
        };
    }
}`

[＋add a note](https://www.php.net/manual/add-note.php?sect=closure.fromcallable&repo=en&redirect=https://www.php.net/manual/en/closure.fromcallable.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google