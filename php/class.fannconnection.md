---
url: https://www.php.net/manual/en/class.fannconnection.php
scraped_at: 2025-10-20T02:31:06.260Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The FANNConnection class [¶](https://www.php.net/manual/en/class.fannconnection.php\#class.fannconnection)

(No version information available, might only be in Git)

## Introduction [¶](https://www.php.net/manual/en/class.fannconnection.php\#fannconnection.intro)

**FANNConnection** is used for the neural network connection.
The objects of this class are used in [fann\_get\_connection\_array()](https://www.php.net/manual/en/function.fann-get-connection-array.php) and [fann\_set\_weight\_array()](https://www.php.net/manual/en/function.fann-set-weight-array.php).


## Class synopsis [¶](https://www.php.net/manual/en/class.fannconnection.php\#fannconnection.synopsis)

class **FANNConnection**
{

/\\* Properties \*/

public[$from\_neuron](https://www.php.net/manual/en/class.fannconnection.php#fannconnection.props.from-neuron);

public[$to\_neuron](https://www.php.net/manual/en/class.fannconnection.php#fannconnection.props.to-neuron);

public[$weight](https://www.php.net/manual/en/class.fannconnection.php#fannconnection.props.weight);

/\\* Methods \*/

public[\_\_construct](https://www.php.net/manual/en/fannconnection.construct.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$from_neuron`, [int](https://www.php.net/manual/en/language.types.integer.php) `$to_neuron`, [float](https://www.php.net/manual/en/language.types.float.php) `$weight`)

public[getFromNeuron](https://www.php.net/manual/en/fannconnection.getfromneuron.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getToNeuron](https://www.php.net/manual/en/fannconnection.gettoneuron.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getWeight](https://www.php.net/manual/en/fannconnection.getweight.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[setWeight](https://www.php.net/manual/en/fannconnection.setweight.php)([float](https://www.php.net/manual/en/language.types.float.php) `$weight`): [void](https://www.php.net/manual/en/language.types.void.php)

}

## Properties [¶](https://www.php.net/manual/en/class.fannconnection.php\#fannconnection.props)

from\_neuron

The neuron where the connection starts.

to\_neuron

The neuron where the connection ends.

weight

The weight of the connection.

## Table of Contents [¶](https://www.php.net/manual/en/class.fannconnection.php\#class.fannconnection)

- [FANNConnection::\_\_construct](https://www.php.net/manual/en/fannconnection.construct.php) — The connection constructor
- [FANNConnection::getFromNeuron](https://www.php.net/manual/en/fannconnection.getfromneuron.php) — Returns the postions of starting neuron
- [FANNConnection::getToNeuron](https://www.php.net/manual/en/fannconnection.gettoneuron.php) — Returns the postions of terminating neuron
- [FANNConnection::getWeight](https://www.php.net/manual/en/fannconnection.getweight.php) — Returns the connection weight
- [FANNConnection::setWeight](https://www.php.net/manual/en/fannconnection.setweight.php) — Sets the connections weight

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/fann/fannconnection.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.fannconnection%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.fannconnection&repo=en&redirect=https://www.php.net/manual/en/class.fannconnection.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google