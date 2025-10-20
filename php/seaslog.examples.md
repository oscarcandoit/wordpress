---
url: https://www.php.net/manual/en/seaslog.examples.php
scraped_at: 2025-10-20T02:32:08.366Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Examples [¶](https://www.php.net/manual/en/seaslog.examples.php\#seaslog.examples)

**Example #1 Get and set base path**

`<?php
$basePath1 = SeasLog::getBasePath();
SeasLog::setBasePath('/log/base_test');
$basePath2 = SeasLog::getBasePath();
var_dump($basePath1,$basePath2);
?>`

The above example will output
something similar to:

```
string(12) "/var/log/www"
string(14) "/log/base_test"

```

**Example #2 Get and set logger**

`<?php
$lastLogger1 = SeasLog::getLastLogger();
SeasLog::setLogger('testModule/app1');
$lastLogger2 = SeasLog::getLastLogger();
var_dump($lastLogger1,$lastLogger2);
?>`

The above example will output
something similar to:

```
string(7) "default"
string(15) "testModule/app1"

```

**Example #3 Fast write log**

``<?php
SeasLog::log(SEASLOG_ERROR,'this is a error test by ::log');
SeasLog::debug('this is a {userName} debug',array('{userName}' => 'neeke'));
SeasLog::info('this is a info log');
SeasLog::notice('this is a notice log');
SeasLog::warning('your {website} was down,please {action} it ASAP!',array('{website}' => 'github.com','{action}' => 'rboot'));
SeasLog::error('a error log');
SeasLog::critical('some thing was critical');
SeasLog::alert('yes this is a {messageName}',array('{messageName}' => 'alertMSG'));
SeasLog::emergency('Just now, the house next door was completely burnt out! {note}',array('{note}' => 'it`s a joke'));
?>``

As the default, _seaslog.default\_template = "%T \| %L \| %P \| %Q \| %t \| %M"_.
That's mean,as the default,log record style is： \`{dateTime} \| {level} \| {pid} \| {uniqid} \| {timeStamp} \| {logInfo}\`.


The above example will output
something similar to:

_seaslog.appender = 1_

```
2014-07-27 08:53:52 | ERROR | 23625 | 599159975a9ff | 1406422432.786 | this is a error test by log
2014-07-27 08:53:52 | DEBUG | 23625 | 599159975a9ff | 1406422432.786 | this is a neeke debug
2014-07-27 08:53:52 | INFO | 23625 | 599159975a9ff | 1406422432.787 | this is a info log
2014-07-27 08:53:52 | NOTICE | 23625 | 599159975a9ff | 1406422432.787 | this is a notice log
2014-07-27 08:53:52 | WARNING | 23625 | 599159975a9ff | 1406422432.787 | your github.com was down,please rboot it ASAP!
2014-07-27 08:53:52 | ERROR | 23625 | 599159975a9ff | 1406422432.787 | a error log
2014-07-27 08:53:52 | CRITICAL | 23625 | 599159975a9ff | 1406422432.787 | some thing was critical
2014-07-27 08:53:52 | EMERGENCY | 23625 | 599159975a9ff | 1406422432.787 | Just now, the house next door was completely burnt out! it is a joke

```

The above example will output
something similar to:

_seaslog.appender = 2_ or _seaslog.appender = 3_

```
The log style finally formatted such as:
<15>1 2017-08-27T01:24:59+08:00 vagrant-ubuntu-trusty test/logger[27171]: 2016-06-25 00:59:43 | DEBUG | 21423 | 599157af4e937 | 1466787583.322 | this is a neeke debug
<14>1 2017-08-27T01:24:59+08:00 vagrant-ubuntu-trusty test/logger[27171]: 2016-06-25 00:59:43 | INFO | 21423 | 599157af4e937 | 1466787583.323 | this is a info log
<13>1 2017-08-27T01:24:59+08:00 vagrant-ubuntu-trusty test/logger[27171]: 2016-06-25 00:59:43 | NOTICE | 21423 | 599157af4e937 | 1466787583.324 | this is a notice log

```

**Example #4 Fast count some type of log count value**

_SeasLog_ get count value of \`grep -wc\` use system pipe and return to PHP (array or int).


`<?php
$countResult1 = SeasLog::analyzerCount();
$countResult2 = SeasLog::analyzerCount(SEASLOG_WARNING);
$countResult3 = SeasLog::analyzerCount(SEASLOG_ERROR,date('Ymd',time()));
var_dump($countResult1,$countResult2,$countResult3);
?>`

The above example will output
something similar to:

```
array(8) {
  ["DEBUG"]=>
  int(3)
  ["INFO"]=>
  int(3)
  ["NOTICE"]=>
  int(3)
  ["WARNING"]=>
  int(3)
  ["ERROR"]=>
  int(6)
  ["CRITICAL"]=>
  int(3)
  ["ALERT"]=>
  int(3)
  ["EMERGENCY"]=>
  int(3)
}
int(7)
int(1)

```

**Example #5 Acquisit some type of log list**

_SeasLog_ get count value of \`grep -w\` use system pipe and return array to PHP.


`<?php
$detailErrorArray = SeasLog::analyzerDetail(SEASLOG_ERROR);
var_dump($detailErrorArray);
var_dump(SeasLog::analyzerDetail(SEASLOG_ERROR,date('Ymd',time())));
?>`

The above example will output
something similar to:

```
array(6) {
  [0] =>
  string(83) "2014-02-24 00:14:02 | ERROR | 8568 | 599157af4e937 | 1393172042.717 | test error 3 "
  [1] =>
  string(83) "2014-02-24 00:14:04 | ERROR | 8594 | 5991576584446 | 1393172044.104 | test error 3 "
  [2] =>
  string(83) "2014-02-24 00:14:04 | ERROR | 8620 | 1502697015147 | 1393172044.862 | test error 3 "
  [3] =>
  string(83) "2014-02-24 00:14:05 | ERROR | 8646 | 599159975a9ff | 1393172045.989 | test error 3 "
  [4] =>
  string(83) "2014-02-24 00:14:07 | ERROR | 8672 | 599159986ec28 | 1393172047.882 | test error 3 "
  [5] =>
  string(83) "2014-02-24 00:14:08 | ERROR | 8698 | 5991599981cec | 1393172048.736 | test error 3 "
}

array(2) {
  [0] =>
  string(83) "2014-02-24 00:14:02 | ERROR | 8568 | 599157af4e937 | 1393172042.717 | test error 3 "
  [1] =>
  string(83) "2014-02-24 00:14:04 | ERROR | 8594 | 5991576584446 | 1393172044.104 | test error 3 "
}

```

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/seaslog/examples.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fseaslog.examples%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=seaslog.examples&repo=en&redirect=https://www.php.net/manual/en/seaslog.examples.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google