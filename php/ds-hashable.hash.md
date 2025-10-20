---
url: https://www.php.net/manual/en/ds-hashable.hash.php
scraped_at: 2025-10-20T02:53:21.427Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Ds\\Hashable::hash

(PECL ds >= 1.0.0)

Ds\\Hashable::hash — Returns a scalar value to be used as a hash value

### Description [¶](https://www.php.net/manual/en/ds-hashable.hash.php\#refsect1-ds-hashable.hash-description)

abstractpublic**Ds\\Hashable::hash**(): [mixed](https://www.php.net/manual/en/language.types.mixed.php)

Returns a scalar value to be used as the hash value of the objects.


While the hash value does not define equality, all objects that are equal according to [Ds\\Hashable::equals()](https://www.php.net/manual/en/ds-hashable.equals.php)
must have the same hash value. Hash values of equal objects don't have to be unique, for example
you could just return **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** for all objects and nothing would break - the only
implication would be that hash tables then turn into linked lists because all
your objects will be hashed to the same bucket. It's therefore very important
that you pick a good hash value, such as an ID or email address.


This method allows objects to be used as keys in structures such as
[Ds\\Map](https://www.php.net/manual/en/class.ds-map.php) and [Ds\\Set](https://www.php.net/manual/en/class.ds-set.php), or any
other lookup structure that honors this interface.


**Caution**

Do not pick a value that might change within the object, such as a public
property. Hash table lookups would fail because the hash has changed.


**Caution**

All objects that are equal must have the same hash value.


### Parameters [¶](https://www.php.net/manual/en/ds-hashable.hash.php\#refsect1-ds-hashable.hash-parameters)

This function has no parameters.

### Return Values [¶](https://www.php.net/manual/en/ds-hashable.hash.php\#refsect1-ds-hashable.hash-returnvalues)

A scalar value to be used as this object's hash value.


### Examples [¶](https://www.php.net/manual/en/ds-hashable.hash.php\#refsect1-ds-hashable.hash-examples)

**Example #1 **Ds\\Hashable::hash()** example**

`<?php
class HashableObject implements \Ds\Hashable
{
    private $name;
    private $email;
    public function __construct($name, $email)
    {
        $this->name  = $name;
        $this->email = $email;
    }
    /**
     * Should return the same value for all equal objects, but doesn't have to
     * be unique. This value will not be used to determine equality.
     */
    public function hash()
    {
        return $this->email;
    }
    /**
     * This determines equality, usually during a hash table lookup to determine
     * if the bucket's key matches the lookup key. The hash has to be equal if
     * the objects are equal, otherwise this determination wouldn't be reached.
     */
    public function equals($obj): bool
    {
        return $this->name  === $obj->name
            && $this->email === $obj->email;
    }
}
?>`

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/ds/ds/hashable/hash.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fds-hashable.hash%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=ds-hashable.hash&repo=en&redirect=https://www.php.net/manual/en/ds-hashable.hash.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google