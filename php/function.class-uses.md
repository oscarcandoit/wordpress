---
url: https://www.php.net/manual/en/function.class-uses.php
scraped_at: 2025-10-20T03:01:57.003Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# class\_uses

(PHP 5 >= 5.4.0, PHP 7, PHP 8)

class\_uses —
Return the traits used by the given class


### Description [¶](https://www.php.net/manual/en/function.class-uses.php\#refsect1-function.class-uses-description)

**class\_uses**([object](https://www.php.net/manual/en/language.types.object.php)\|[string](https://www.php.net/manual/en/language.types.string.php) `$object_or_class`, [bool](https://www.php.net/manual/en/language.types.boolean.php) `$autoload` = **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**): [array](https://www.php.net/manual/en/language.types.array.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

This function returns an array with the names of the traits that the
given `object_or_class` uses. This does however not include
any traits used by a parent class.


### Parameters [¶](https://www.php.net/manual/en/function.class-uses.php\#refsect1-function.class-uses-parameters)

`object_or_class`

An object (class instance) or a string (class name).


`autoload`

Whether to [autoload](https://www.php.net/manual/en/language.oop5.autoload.php)
if not already loaded.


### Return Values [¶](https://www.php.net/manual/en/function.class-uses.php\#refsect1-function.class-uses-returnvalues)

An array on success, or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** when the given class doesn't exist.


### Examples [¶](https://www.php.net/manual/en/function.class-uses.php\#refsect1-function.class-uses-examples)

**Example #1 **class\_uses()** example**

`<?php
trait foo { }
class bar {
use foo;
}
print_r(class_uses(new bar));
print_r(class_uses('bar'));
spl_autoload_register();
// use autoloading to load the 'not_loaded' class
print_r(class_uses('not_loaded', true));
?>`

The above example will output
something similar to:

```
Array
(
    [foo] => foo
)
Array
(
    [foo] => foo
)
Array
(
    [trait_of_not_loaded] => trait_of_not_loaded
)
```

### See Also [¶](https://www.php.net/manual/en/function.class-uses.php\#refsect1-function.class-uses-seealso)

- [class\_parents()](https://www.php.net/manual/en/function.class-parents.php) \- Return the parent classes of the given class
- [get\_declared\_traits()](https://www.php.net/manual/en/function.get-declared-traits.php) \- Returns an array of all declared traits

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/spl/functions/class-uses.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.class-uses%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.class-uses&repo=en&redirect=https://www.php.net/manual/en/function.class-uses.php)

### User Contributed Notes 6 notes

[up](https://www.php.net/manual/vote-note.php?id=110752&page=function.class-uses&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=110752&page=function.class-uses&vote=down "Vote down!")

35


[**_stealz at op dot pl_**](https://www.php.net/manual/en/function.class-uses.php#110752) [¶](https://www.php.net/manual/en/function.class-uses.php#110752)

**12 years ago**

`To get ALL traits including those used by parent classes and other traits, use this function:
<?php
function class_uses_deep($class, $autoload = true) {
    $traits = [];
    do {
        $traits = array_merge(class_uses($class, $autoload), $traits);
    } while($class = get_parent_class($class));
    foreach ($traits as $trait => $same) {
        $traits = array_merge(class_uses($trait, $autoload), $traits);
    }
    return array_unique($traits);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=125274&page=function.class-uses&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125274&page=function.class-uses&vote=down "Vote down!")

8


[**_Jos Macedo_**](https://www.php.net/manual/en/function.class-uses.php#125274) [¶](https://www.php.net/manual/en/function.class-uses.php#125274)

**5 years ago**

`Another alternative to get all parent traits is:
<?php
function getUsedTraits($classInstance) {
    $parentClasses = class_parents($classInstance);
    $traits = class_uses($classInstance);

    foreach ($parentClasses as $parentClass) {
        $traits = array_merge($traits, class_uses($parentClass));
    }

    return $traits;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=112671&page=function.class-uses&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=112671&page=function.class-uses&vote=down "Vote down!")

17


[**_ulf_**](https://www.php.net/manual/en/function.class-uses.php#112671) [¶](https://www.php.net/manual/en/function.class-uses.php#112671)

**12 years ago**

`A slighly modified version from Stealz that also checks all the "parent" traits used by the traits:
<?php
public static function class_uses_deep($class, $autoload = true)
    {
        $traits = [];
        // Get traits of all parent classes
        do {
            $traits = array_merge(class_uses($class, $autoload), $traits);
        } while ($class = get_parent_class($class));
        // Get traits of all parent traits
        $traitsToSearch = $traits;
        while (!empty($traitsToSearch)) {
            $newTraits = class_uses(array_pop($traitsToSearch), $autoload);
            $traits = array_merge($newTraits, $traits);
            $traitsToSearch = array_merge($newTraits, $traitsToSearch);
        };
        foreach ($traits as $trait => $same) {
            $traits = array_merge(class_uses($trait, $autoload), $traits);
        }
        return array_unique($traits);
    }
?>`

[up](https://www.php.net/manual/vote-note.php?id=122426&page=function.class-uses&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122426&page=function.class-uses&vote=down "Vote down!")

4


[**_Daniel Klein_**](https://www.php.net/manual/en/function.class-uses.php#122426) [¶](https://www.php.net/manual/en/function.class-uses.php#122426)

**7 years ago**

`If the class does not exist, you will get a warning, even if $autoload == false; I.e., if the class is not found, setting $autoload to false is not sufficient to silence the warning.
This is different from class_exists ($class_name, $autoload = true), which doesn't generate a warning in either case.`

[up](https://www.php.net/manual/vote-note.php?id=122427&page=function.class-uses&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122427&page=function.class-uses&vote=down "Vote down!")

4


[**_Daniel Klein_**](https://www.php.net/manual/en/function.class-uses.php#122427) [¶](https://www.php.net/manual/en/function.class-uses.php#122427)

**7 years ago**

`I have improved on ulf's improvement of stealz' code. I'm pretty sure the last "foreach" adds nothing, so I've removed it, as well as adding a check for string class names (as opposed to objects) to prevent the warning if the class is not found:
<?php
function class_uses_deep($class, $autoload = true) {
$traits = [];
// Get all the traits of $class and its parent classes
do {
    $class_name = is_object($class)? get_class($class): $class;
    if (class_exists($class_name, $autoload)) {
      $traits = array_merge(class_uses($class, $autoload), $traits);
    }
} while ($class = get_parent_class($class));
// Get traits of all parent traits
$traits_to_search = $traits;
while (!empty($traits_to_search)) {
    $new_traits = class_uses(array_pop($traits_to_search), $autoload);
    $traits = array_merge($new_traits, $traits);
    $traits_to_search = array_merge($new_traits, $traits_to_search);
};
return array_unique($traits);
}`

[up](https://www.php.net/manual/vote-note.php?id=125933&page=function.class-uses&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125933&page=function.class-uses&vote=down "Vote down!")

0


[**_donatj at gmail dot com_**](https://www.php.net/manual/en/function.class-uses.php#125933) [¶](https://www.php.net/manual/en/function.class-uses.php#125933)

**4 years ago**

`The popular stealz solution doesn't handle traits that use other traits. A little bit of recursion can clean the entire thing up a bit and make it more robust.
<?php
public function class_uses_deep( string $class, bool $autoload = true ) : array {
    $traits = class_uses($class, $autoload);
    if($parent = get_parent_class($class)) {
        $traits = array_merge($traits, class_uses_deep($parent, $autoload));
    }
    foreach( $traits as $trait ) {
        $traits = array_merge($traits, class_uses_deep($trait, $autoload));
    }
    return $traits;
}
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.class-uses&repo=en&redirect=https://www.php.net/manual/en/function.class-uses.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google